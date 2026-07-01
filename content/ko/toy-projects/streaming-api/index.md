---

title: Streaming API
date: 2026-06-13
summary: '대용량 영상 업로드와 HLS 변환·재생 URL 제공을 목표로 한 Spring Boot + AWS 미디어 백엔드 프로젝트입니다.'
highlights:
  - title: 영상 업로드 API
    text: 대용량 영상과 메타데이터를 분리해 저장하고 조회하는 API 구조를 설계했습니다.
    image: featured.jpg
  - title: AWS 변환 파이프라인
    text: S3, Lambda, MediaConvert를 활용해 비동기 영상 변환 흐름을 구상했습니다.
    image: https://images.unsplash.com/photo-1558494949-ef010cbdcc31?auto=format&fit=crop&w=720&q=80
  - title: HLS 재생
    text: 화질 조절과 브라우저 재생을 고려해 HLS 재생 URL 제공 구조를 정리했습니다.
    image: https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&w=720&q=80
links:
  - name: GitHub
    url: https://github.com/eecczz/streamingAPI
featured: true
---

Streaming API는 대용량 영상 업로드와 스트리밍 처리를 목표로 한 Spring Boot 기반 백엔드 프로젝트입니다. AWS S3, Lambda, MediaConvert를 활용해 업로드된 영상을 HLS 형식으로 변환하고 재생 URL을 제공하는 구조를 설계했습니다.

유튜브 모작 프로젝트에서 고민했던 미디어 처리 문제를 백엔드와 클라우드 파이프라인 관점으로 확장한 작업입니다. 영상 메타데이터 저장, 업로드 API, 비동기 변환, 재생 URL 제공을 나누어 설계하며 미디어 서비스의 기본 구조를 학습했습니다.

- 기술 스택: Java, Spring Boot, MariaDB, AWS S3, Lambda, MediaConvert, HLS
- 구현 포인트: 영상 업로드 API, 메타데이터 저장, 비동기 변환 파이프라인
- 저장소: [eecczz/streamingAPI](https://github.com/eecczz/streamingAPI)

## 주요 구현 포인트

### 영상 업로드 API

![영상 업로드 API](featured.jpg)

대용량 영상과 메타데이터를 분리해 저장하고 조회하는 API 구조를 설계했습니다.

### AWS 변환 파이프라인

![AWS 변환 파이프라인](https://images.unsplash.com/photo-1558494949-ef010cbdcc31?auto=format&fit=crop&w=720&q=80)

S3, Lambda, MediaConvert를 활용해 비동기 영상 변환 흐름을 구상했습니다.

### HLS 재생

![HLS 재생](https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&w=720&q=80)

화질 조절과 브라우저 재생을 고려해 HLS 재생 URL 제공 구조를 정리했습니다.
