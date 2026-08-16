---
title: Smart CCTV 낙상 감지
date: 2026-08-13
summary: '요양원 RTSP 영상에서 낙상 후보를 다단 검증하고 보수적 후처리로 오탐을 줄인 Edge-AI 관제 프로젝트입니다.'
featured: true
---

<div class="case-study-lead">
  <p class="case-study-kicker">BACKEND · AI · SYSTEM CASE STUDY</p>
  <p>요양원 RTSP 영상에서 낙상 후보를 다단 검증하고 보수적 후처리로 오탐을 줄인 Edge-AI 관제 프로젝트입니다.</p>
  <div class="case-study-meta"><span><b>역할</b> Edge-AI 현장실습 · 데이터/모델/후처리/현장 검증</span><span><b>검증</b> 실제 요양원 RTSP 환경 적용</span></div>
</div>

## 30초 요약

- **무엇을 만들었나** — 요양원 RTSP 영상에서 낙상 후보를 다단 검증하고 보수적 후처리로 오탐을 줄인 Edge-AI 관제 프로젝트입니다.
- **내 기여 범위** — Edge-AI 현장실습 · 데이터/모델/후처리/현장 검증
- **현재 수준** — 실제 요양원 RTSP 환경 적용
- **코드 근거** — [GitHub 저장소](https://github.com/eecczz/smartcctv_fall_detection)

> 팀 프로젝트는 전체 결과가 아니라 위에 적은 직접 기여 범위와, 면접에서 구현 이유를 설명할 수 있는 내용만 서술했습니다.

## 실제 구현 과정과 트러블슈팅

### 1. fall 단일 클래스가 배경과 화면 전체를 낙상으로 잡음

**판단과 수정** — person 비교군을 추가한 2-class detection으로 전환했습니다.

### 2. 앉거나 기대는 자세의 하체만 fall, 상체는 person으로 분리

**판단과 수정** — 겹치거나 가까운 bbox를 한 사람으로 묶고 애매한 경우 person으로 내리는 보수적 규칙을 만들었습니다.

### 3. Pose 관절 누락과 천장 시점 데이터 부족

**판단과 수정** — 3D pose를 바로 추가하기보다 hard negative, temporal smoothing, 현장 시점 파인튜닝을 우선 실험 대상으로 정리했습니다.

## 기술 선택과 이유

| 기술 | 선택 이유 |
|---|---|
| **YOLO26s detection** | 낙상 여부뿐 아니라 화면 속 위치와 confidence를 함께 얻기 위해 |
| **fall/person 2-class** | 쓰러지지 않은 사람을 비교군으로 제공해 단일 클래스의 배경 편향을 줄이기 위해 |
| **BBox post-processing** | 한 사람의 상·하체가 fall/person으로 나뉘는 부분 bbox 오류를 보수적으로 통합하기 위해 |
| **Zero-shot validation** | NPU에서 VLM을 지원하지 않는 제약 속에서 현장 맥락을 한 단계 더 검증하기 위해 |

## 검증 결과

- 추천 최종 fall 표시 기준을 confidence 0.70으로 높여 완전히 쓰러진 상태 중심으로 판정했습니다.
- 요양원 RTSP 카메라에서 모델과 후처리 흐름을 실행했습니다.
- 오탐을 숨기지 않고 부분 bbox·앉은 자세·원거리 미탐을 한계로 기록했습니다.

## 시스템 흐름 — 이해 보조

![Smart CCTV 낙상 감지 시스템 흐름](architecture.svg)

<p class="diagram-caption">이 그림은 구현 역량의 증거를 대신하지 않습니다. 실제 코드·README·커밋과 문제 해결 기록을 읽기 쉽게 연결한 보조 자료입니다.</p>

1. RTSP 프레임에서 사람·자세 후보를 얻습니다.
2. YOLO fall/person 모델이 후보를 2차 검증합니다.
3. 같은 사람으로 보이는 중복·인접 bbox를 그룹화합니다.
4. fall confidence와 bbox coverage가 충분한 경우만 fall로 유지합니다.
5. 권장 threshold 0.70과 현장 맥락 기반 zero-shot 검증을 적용합니다.
6. 확정 이벤트만 스냅샷·알림 파이프라인에 전달합니다.

## API · 시스템 경계

| 영역 | API/계약 | 책임 |
|---|---|---|
| `모델 입력` | `CCTV frame/crop` | RTSP + OpenCV |
| `판정` | `fall/person bbox` | YOLO26s |
| `후처리` | `grouped person bbox` | NMS · grouping · threshold |
| `이벤트` | `confirmed fall` | snapshot · DB · alert |

## 한계와 다음 실험

- 연속 프레임 tracking과 cooldown으로 단발성 오탐 억제
- 앉음·반쯤 누움 hard negative 데이터 보강
- 현장 validation set 기반 threshold/IoU 정량 튜닝

## 구현 근거

- [GitHub 저장소](https://github.com/eecczz/smartcctv_fall_detection)
- README의 기능 목록만 옮기지 않고 controller/service/source tree와 주요 commit 흐름을 함께 확인했습니다.
- 저장소·실행 기록·수상 결과로 확인되지 않는 성과 수치는 만들지 않았습니다.
