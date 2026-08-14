---
title: 전북도청 대도민 음성 챗봇
date: 2026-06-01
summary: '전북도청·시군 데이터를 GraphRAG로 검색하고 STT/TTS로 전달하는 공공 음성 정보 서비스입니다.'
featured: true
---

<div class="case-study-lead">
  <p class="case-study-kicker">BACKEND · AI · SYSTEM CASE STUDY</p>
  <p>전북도청·시군 데이터를 GraphRAG로 검색하고 STT/TTS로 전달하는 공공 음성 정보 서비스입니다.</p>
  <div class="case-study-meta"><span><b>역할</b> 캡스톤 · FastAPI/음성 파이프라인/GraphRAG/크롤러 운영</span><span><b>검증</b> 캡스톤 최우수상 · 전북도지사 표창</span></div>
</div>

## 30초 요약

- **무엇을 만들었나** — 전북도청·시군 데이터를 GraphRAG로 검색하고 STT/TTS로 전달하는 공공 음성 정보 서비스입니다.
- **내 기여 범위** — 캡스톤 · FastAPI/음성 파이프라인/GraphRAG/크롤러 운영
- **현재 수준** — 캡스톤 최우수상 · 전북도지사 표창
- **코드 근거** — 비공개/별도 저장소 없이 프로젝트 산출물과 구현 기록을 기준으로 정리

> 팀 프로젝트는 전체 결과가 아니라 위에 적은 직접 기여 범위와, 면접에서 구현 이유를 설명할 수 있는 내용만 서술했습니다.

## 실제 구현 과정과 트러블슈팅

### 1. 군산·완주 사이트의 URL/base-path 차이로 수집 실패

**판단과 수정** — 실제 URL을 직접 확인하고 사이트별 base path 설정을 분리했습니다.

### 2. 일반 HTML과 SPA 지자체 사이트를 같은 로더로 처리하기 어려움

**판단과 수정** — 11개 일반 사이트는 수동 트리거로 먼저 안정화하고 3개 SPA는 Playwright fallback 대상으로 분리했습니다.

### 3. 음성 응답이 길어지면 체감 지연과 대화 흐름이 끊김

**판단과 수정** — STT/TTS와 응답 파이프라인을 분리하고 스피치 엔지니어링 오픈소스의 비동기 종료 문제까지 추적했습니다.

## 기술 선택과 이유

| 기술 | 선택 이유 |
|---|---|
| **FastAPI** | STT·검색·LLM·TTS처럼 지연 특성이 다른 단계를 비동기 API로 조합하기 위해 |
| **STT/TTS** | 웹 탐색이 익숙하지 않은 도민도 자연어 음성으로 정책·민원을 찾게 하기 위해 |
| **GraphRAG** | 도청 대규모 문서의 관계와 출처를 보존하며 답변 근거를 검색하기 위해 |
| **Incremental crawler** | 11개 일반 사이트와 SPA 사이트의 갱신 주기와 실패 양상이 달라 부분 재수집하기 위해 |

## 검증 결과

- 도민 대상 실제 서비스 목표로 공공 데이터 수집·검색·음성 응답 전 과정을 구현했습니다.
- 캡스톤디자인 최우수상과 전북도청 도지사 표창을 받았습니다.
- 크롤러 rollback·증분 배포·사이트별 장애 격리 기록이 실제 운영 경험으로 남아 있습니다.

## 시스템 흐름 — 이해 보조

![전북도청 대도민 음성 챗봇 시스템 흐름](architecture.svg)

<p class="diagram-caption">이 그림은 구현 역량의 증거를 대신하지 않습니다. 실제 코드·README·커밋과 문제 해결 기록을 읽기 쉽게 연결한 보조 자료입니다.</p>

1. 사용자 음성을 STT로 텍스트화합니다.
2. 질의를 정규화하고 대화 맥락과 함께 FastAPI에 전달합니다.
3. GraphRAG가 도청·시군 데이터에서 관련 노드와 문서를 찾습니다.
4. LLM이 검색 근거를 바탕으로 답변을 생성합니다.
5. TTS가 답변을 음성으로 변환하고 캐릭터 UI와 동기화합니다.
6. 크롤러가 incremental/full/site 단위로 원천 데이터를 갱신합니다.

## API · 시스템 경계

| 영역 | API/계약 | 책임 |
|---|---|---|
| `Crawler` | `POST /api/v1/crawler/trigger/incremental` | 변경분 수집 |
| `Crawler` | `POST /trigger/full` | 전체 재수집 |
| `Crawler` | `POST /trigger/site/{code}` | 사이트별 장애 격리 |
| `Chat` | `STT → GraphRAG → LLM → TTS` | 도민 음성 응답 |

## 한계와 다음 실험

- 답변마다 문서 출처와 최신 수집 시각 표시
- SPA 크롤러의 browser pool·timeout·retry 운영 지표 추가
- STT/LLM/TTS 구간별 latency와 실패율 모니터링

## 구현 근거

- 비공개/별도 저장소 없이 프로젝트 산출물과 구현 기록을 기준으로 정리
- README의 기능 목록만 옮기지 않고 controller/service/source tree와 주요 commit 흐름을 함께 확인했습니다.
- 개발 중 남긴 Codex 대화에서는 문제 진단·가설·수정 순서를 확인했습니다.
- 저장소·실행 기록·수상 결과로 확인되지 않는 성과 수치는 만들지 않았습니다.
