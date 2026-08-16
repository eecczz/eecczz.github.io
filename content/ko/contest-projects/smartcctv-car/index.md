---
title: Smart CCTV 차종 분류
date: 2026-07-30
summary: '폐차장 RTSP CCTV에서 차량을 탐지하고 NPU 환경에서 차종 단위로 분류하는 Edge-AI 관제 프로젝트입니다.'
featured: true
---

<div class="case-study-lead">
  <p class="case-study-kicker">BACKEND · AI · SYSTEM CASE STUDY</p>
  <p>폐차장 RTSP CCTV에서 차량을 탐지하고 NPU 환경에서 차종 단위로 분류하는 Edge-AI 관제 프로젝트입니다.</p>
  <div class="case-study-meta"><span><b>역할</b> Edge-AI 현장실습 · 모델 전처리/학습/변환/현장 적용</span><span><b>검증</b> 실제 폐차장 RTSP 환경 검증</span></div>
</div>

## 30초 요약

- **무엇을 만들었나** — 폐차장 RTSP CCTV에서 차량을 탐지하고 NPU 환경에서 차종 단위로 분류하는 Edge-AI 관제 프로젝트입니다.
- **내 기여 범위** — Edge-AI 현장실습 · 모델 전처리/학습/변환/현장 적용
- **현재 수준** — 실제 폐차장 RTSP 환경 검증
- **코드 근거** — [GitHub 저장소](https://github.com/eecczz/smartcctv_car-model_classifier)

> 팀 프로젝트는 전체 결과가 아니라 위에 적은 직접 기여 범위와, 면접에서 구현 이유를 설명할 수 있는 내용만 서술했습니다.

## 실제 구현 과정과 트러블슈팅

### 1. 전체 화면을 바로 분류하면 배경과 다중 차량이 예측을 흔듦

**판단과 수정** — 탐지→crop→분류의 two-stage 구조로 관심 차량만 분류했습니다.

### 2. 홍보용 차량 사진과 폐차장 CCTV 사이의 도메인 차이

**판단과 수정** — 학습 split 수치와 현장 유사 crop 검증을 분리해 기록하고, 실제 CCTV 조건을 별도 확인했습니다.

### 3. GPU 모델을 현장 NPU에서 그대로 실행할 수 없음

**판단과 수정** — 장비가 지원하는 연산과 입력 규격에 맞게 모델을 변환하고 Linux 관제 프로그램에 적용했습니다.

## 기술 선택과 이유

| 기술 | 선택 이유 |
|---|---|
| **YOLO26s detector** | CCTV 프레임에서 car/truck 위치를 먼저 제한해 분류 입력의 잡음을 줄이기 위해 |
| **YOLO26s classifier** | 차량 crop을 세부 차종으로 분류하고 top-5 후보까지 비교하기 위해 |
| **OpenCV · Python** | RTSP 프레임 처리, crop 생성, 결과 overlay를 하나의 파이프라인으로 묶기 위해 |
| **NPU runtime** | GPU가 아닌 현장 Edge 장비의 제약 안에서 실시간 추론하기 위해 |

## 검증 결과

- validation top-1 0.90665, top-5 0.97743을 기록했습니다.
- 실제 폐차장 RTSP 화면에서 detector 결과를 구동하고 분류 결합을 검증했습니다.
- 수치는 학습 split 기준이며 파손·가림·야간 조명에서는 성능이 달라질 수 있음을 명시했습니다.

## 시스템 흐름 — 이해 보조

![Smart CCTV 차종 분류 시스템 흐름](architecture.svg)

<p class="diagram-caption">이 그림은 구현 역량의 증거를 대신하지 않습니다. 실제 코드·README·커밋과 문제 해결 기록을 읽기 쉽게 연결한 보조 자료입니다.</p>

1. RTSP 카메라 프레임을 수집합니다.
2. COCO 사전학습 detector에서 car/truck bbox만 선택합니다.
3. bbox를 차량 crop으로 잘라 classifier 입력으로 정규화합니다.
4. AIHub 데이터로 학습한 분류기가 차종명·confidence·top-5를 반환합니다.
5. NPU용 형식으로 변환한 모델을 현장 관제 소프트웨어에 연결합니다.
6. bbox와 예측값을 화면과 로그에 남겨 오탐을 추적합니다.

## API · 시스템 경계

| 영역 | API/계약 | 책임 |
|---|---|---|
| `입력` | `RTSP/CCTV frame` | 폐차장 카메라 |
| `탐지` | `car, truck bbox` | YOLO26s detector |
| `분류` | `class, confidence, top-5` | YOLO26s classifier |
| `출력` | `overlay · 결과 이미지 · CSV` | 현장 관제 UI |

## 한계와 다음 실험

- 다중 차량에서 관심 차량을 안정적으로 선택하는 tracking 추가
- 차종별 confusion matrix와 현장 라벨셋으로 정량 재평가
- NPU latency/FPS와 CPU·메모리 사용량 계측

## 구현 근거

- [GitHub 저장소](https://github.com/eecczz/smartcctv_car-model_classifier)
- README의 기능 목록만 옮기지 않고 controller/service/source tree와 주요 commit 흐름을 함께 확인했습니다.
- 저장소·실행 기록·수상 결과로 확인되지 않는 성과 수치는 만들지 않았습니다.
