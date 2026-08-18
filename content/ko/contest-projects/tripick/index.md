---
title: TRIPICK — 관광 코스 검증
date: 2026-07-08
summary: 'TourAPI 관광지와 GPS 수행·리뷰·완주율을 결합해 검증된 코스를 다시 추천하는 참여형 플랫폼입니다.'
featured: true
---

<div class="case-study-lead">
  <p class="case-study-kicker">BACKEND · AI · SYSTEM CASE STUDY</p>
  <p>TourAPI 관광지와 GPS 수행·리뷰·완주율을 결합해 검증된 코스를 다시 추천하는 참여형 플랫폼입니다.</p>
  <div class="case-study-meta"><span><b>역할</b> Backend 역할 · TourAPI proxy/데이터 흐름/Trust Score/GPS 검증</span><span><b>검증</b> Web→React Native 확장 프로토타입</span></div>
</div>

## 주요 화면

홈에서는 현재 위치를 기준으로 주변 코스를 제안하고, 등록 코스·수행자 수와 새로 열린 코스를 한 화면에 배치했습니다. 사용자는 스타일·시간·이동 방식으로 스마트 코스를 만들거나 실제 이용자가 등록한 코스를 바로 탐색할 수 있습니다. 코스 카드에서는 거리·경유지 수·테마를 먼저 비교한 뒤 상세 화면으로 진입합니다.

<div class="screen-gallery screen-gallery--portrait">
  <figure>
    <img src="detail-home.webp" alt="현재 위치와 새로 열린 코스를 보여주는 TRIPICK 홈 화면">
    <figcaption>현재 위치 추천과 스마트 코스 진입</figcaption>
  </figure>
  <figure>
    <img src="detail-courses.webp" alt="전주의 시장·한옥마을·예술마을 코스를 탐색하는 화면">
    <figcaption>거리·경유지·테마를 비교하는 코스 목록</figcaption>
  </figure>
</div>

## 트러블 슈팅

### 1. TourAPI CORS·키 형식·실패가 웹과 앱에서 다르게 발생

proxy와 직접 호출 계약을 맞추고 mock fallback과 데이터 source 배지를 두었습니다.

### 2. 별점만으로는 실제 수행 가능한 코스인지 판단하기 어려움

수행자 수·완주율·리뷰를 분리해 Trust Score와 설명 항목을 만들었습니다.

### 3. Web 프로토타입과 React Native 코드가 갈라짐

공통 category와 trust 계산 규칙을 TypeScript로 이식하고 monorepo로 정리했습니다.

## 기술 선택과 이유

| 기술 | 선택 이유 |
|---|---|
| **TourAPI proxy** | 브라우저 CORS와 인증키 노출을 줄이고 응답을 캐시하기 위해 |
| **React Native · Expo** | GPS check-in을 실제 모바일 사용 흐름에서 검증하기 위해 |
| **Browser Geolocation** | 단순 작성자 추천이 아니라 실제 방문·완주 근거를 남기기 위해 |
| **Trust Score** | 별점만이 아니라 수행자 수·완주율·리뷰를 조합하기 위해 |

## 검증 결과

- TourAPI→코스 생성→GPS 수행→리뷰/Trust→랭킹의 데이터 선순환을 구현했습니다.
- Web에서 React Native로 확장하며 지도 preview·check-in·trace persistence를 커밋 단위로 추가했습니다.

## 시스템 흐름

![TRIPICK — 관광 코스 검증 시스템 흐름](architecture.svg)

1. TourAPI에서 전주 관광지 데이터를 정규화합니다.
2. 사용자가 후보를 조합해 코스를 만듭니다.
3. 모바일 GPS check-in이 방문·완주 흔적을 저장합니다.
4. 리뷰와 수행자 수·완주율을 Trust Score에 반영합니다.
5. 점수와 추천 사유를 카드·상세 화면에 표시합니다.
6. 검증된 코스가 랭킹에서 다시 노출됩니다.

## API · 시스템 경계

| 영역 | API/계약 | 책임 |
|---|---|---|
| `Tour` | `GET /spots` | TourAPI proxy·cache |
| `Course` | `create/detail/trace` | 코스·수행 기록 |
| `GPS` | `check-in` | 방문 검증 |
| `Trust` | `score + reason` | 랭킹 근거 |

## 다음 구현 계획

- 서버 영속 DB와 사용자 인증 연결
- GPS spoofing·중복 check-in 방지
- Trust Score 가중치 A/B 테스트와 운영 지표
