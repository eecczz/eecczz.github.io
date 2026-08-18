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

## 주요 화면

도청·시군 정보를 질문하면 검색 근거를 바탕으로 답변하고, 음성 대화 중에는 아바타 상태와 사용자 발화 흐름을 함께 표시합니다.

![도청 정보를 답변하는 음성 챗봇 대화 화면](detail-avatar.png)

![음성 응답 상태를 보여주는 챗봇 아바타 화면](featured.png)

## 트러블 슈팅

### 1. AI가 말하는 중에도 사용자의 새 발화를 받아야 함

요청 한 번에 STT→답변→TTS를 모두 끝내는 단방향 흐름 대신 socket 기반 실시간 음성 파이프라인으로 재구성했습니다. 사용자 발화가 감지되면 진행 중인 응답·재생을 중단하고 새 발화 처리를 시작하는 barge-in 흐름을 적용했습니다.

### 2. 일별 전체 수집이 늦어 페이지 누락과 embedding 서버 오류가 발생

직접 구현한 사이트별 수집기의 예외를 계속 보강하는 대신 Crawl4AI를 도입해 동적 페이지·본문 정제·비동기 수집을 표준화했습니다. 전체 수집만 반복하지 않고 incremental/full/site 단위 실행을 나눠 실패 범위와 BGE-M3 embedding 부하를 줄였습니다.

### 3. RAG 답변이 느려 오픈소스 모델의 한계라고 단정하기 쉬움

파이프라인만 의심하지 않고 서로 다른 크기의 Qwen 3.5 모델로 같은 질의를 비교해 모델 선택이 end-to-end latency에 미치는 영향을 확인하고 응답 모델을 교체했습니다.

### 4. STT가 발화 첫 음절을 자주 놓침

초기 테스트에서 VAD 기본값을 그대로 사용해 음성이 충분히 들어온 뒤에야 STT 구간이 시작됐습니다. VAD의 발화 시작 지연과 confidence 관련 값을 조정해 감지 직후부터 음성 버퍼가 STT로 전달되게 하고, 첫 소리 인식률을 대화 테스트로 반복 확인했습니다.

### 5. 지자체별 URL·SPA 구조 차이로 일부 수집 실패

실제 URL과 base path를 사이트별 설정으로 분리하고, 일반 HTML과 브라우저 렌더링이 필요한 페이지를 같은 실패 경로로 묶지 않았습니다.

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

## 시스템 흐름

![전북도청 대도민 음성 챗봇 시스템 흐름](architecture.svg)

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

## 다음 구현 계획

- 답변마다 문서 출처와 최신 수집 시각 표시
- SPA 크롤러의 browser pool·timeout·retry 운영 지표 추가
- STT/LLM/TTS 구간별 latency와 실패율 모니터링
