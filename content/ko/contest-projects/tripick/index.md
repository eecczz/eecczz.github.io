---

title: TRIPICK - 관광 코스 검증 플랫폼
date: 2026-06-25
summary: 'TourAPI, GPS 수행 데이터, 리뷰, 완주율을 결합해 신뢰할 수 있는 관광 코스를 제공하는 사용자 참여형 관광 플랫폼입니다.'
highlights:
  - title: 검증된 코스 랭킹
    text: GPS 수행 데이터, 리뷰, 완주율을 기반으로 관광 코스 신뢰도를 계산했습니다.
    image: featured.png
  - title: Trust Score
    text: 단순 별점이 아니라 수행자 수와 완주율까지 반영한 점수 구조를 설계했습니다.
    image: https://images.unsplash.com/photo-1488646953014-85cb44e25828?auto=format&fit=crop&w=720&q=80
  - title: 관광 데이터 활용
    text: TourAPI와 사용자 참여 데이터를 연결해 추천이 다시 검증되는 흐름을 만들었습니다.
    image: https://images.unsplash.com/photo-1500530855697-b586d89ba3ee?auto=format&fit=crop&w=720&q=80
links:
  - name: GitHub
    url: https://github.com/eecczz/tripick
featured: true
---

TRIPICK은 한국관광공사 TourAPI와 사용자의 실제 수행 데이터(GPS, 리뷰, 완주율)를 결합해 신뢰할 수 있는 관광 코스를 제공하는 참여형 관광 플랫폼입니다. 단순 추천이 아니라, 사용자가 코스를 만들고 다른 사용자가 실제로 수행하며 검증된 코스가 다시 추천되는 데이터 선순환 구조를 목표로 합니다.

프로젝트에서 황선우는 Backend 역할을 맡았습니다. 관광 코스 랭킹, Trust Score, GPS Check-in, 리뷰 시스템, 추천 사유 제공처럼 서비스의 핵심 데이터 흐름을 백엔드 관점에서 설계하고 확장 가능한 구조를 고민했습니다.

- 기술 스택: React, Vite, TourAPI, Kakao Map JavaScript SDK, Browser Geolocation API
- 구현 포인트: 관광 코스 생성, GPS 검증, 리뷰, Trust Score, 랭킹 흐름
- 저장소: [eecczz/tripick](https://github.com/eecczz/tripick)

## 주요 구현 포인트

### 검증된 코스 랭킹

![검증된 코스 랭킹](featured.png)

GPS 수행 데이터, 리뷰, 완주율을 기반으로 관광 코스 신뢰도를 계산했습니다.

### Trust Score

![Trust Score](https://images.unsplash.com/photo-1488646953014-85cb44e25828?auto=format&fit=crop&w=720&q=80)

단순 별점이 아니라 수행자 수와 완주율까지 반영한 점수 구조를 설계했습니다.

### 관광 데이터 활용

![관광 데이터 활용](https://images.unsplash.com/photo-1500530855697-b586d89ba3ee?auto=format&fit=crop&w=720&q=80)

TourAPI와 사용자 참여 데이터를 연결해 추천이 다시 검증되는 흐름을 만들었습니다.
