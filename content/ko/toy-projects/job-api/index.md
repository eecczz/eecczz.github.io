---
title: Job API Project
date: 2026-05-12
summary: '사람인 채용공고 크롤링, 검색/필터링, 지원 내역, 북마크, JWT 인증을 제공하는 Spring Boot 기반 REST API 프로젝트입니다.'
highlights:
  - title: 채용공고 목록 화면
    text: 사람인에서 수집한 공고를 지역, 경력, 급여, 기술스택, 마감일 기준으로 조회하는 목록 화면입니다.
    image: job-list.png
  - title: 검색 API 구현
    text: /jobs 검색 API가 필터 조건을 받아 Specification 검색과 페이지 응답을 구성하는 흐름을 보여줍니다.
    image: api-source.png
  - title: 사람인 크롤링 덤프
    text: Jsoup 기반 크롤러가 사람인 공고를 페이지 단위로 수집하고 중복 URL을 제외해 저장하는 과정을 정리했습니다.
    image: crawl-dump.png
links:
  - name: GitHub
    url: https://github.com/eecczz/jobAPI
featured: true
---

Job API Project는 사람인 채용공고를 크롤링해 MariaDB에 저장하고, 저장된 공고를 검색/필터링할 수 있도록 만든 Spring Boot 기반 REST API 프로젝트입니다. 단순 CRUD에 그치지 않고 실제 채용공고 데이터 수집, 조건 검색, 지원/북마크 흐름, JWT 인증 구조를 함께 다뤘습니다.

사람인 검색 결과의 `.item_recruit` 영역에서 회사명, 공고 제목, 지역, 경력, 학력, 고용형태, 마감일, 기술스택, 급여, URL을 추출하고, 이미 저장된 URL은 제외해 중복 저장을 막았습니다. 이후 `/jobs` API에서 키워드, 회사명, 직무, 기술스택, 지역, 경력, 급여 조건과 정렬 기준을 받아 페이지 단위로 응답하도록 구성했습니다.

- 기술 스택: Java, Spring Boot, Spring Web, Spring Data JPA, Querydsl, MariaDB, JWT, Gradle, Jsoup
- 구현 포인트: 사람인 크롤링, 공고 검색/필터링, 지원 내역, 북마크, 인증/권한 흐름
- 저장소: [eecczz/jobAPI](https://github.com/eecczz/jobAPI)

## 주요 구현 포인트

### 채용공고 목록 화면

![채용공고 목록 화면](job-list.png)

크롤링으로 저장된 공고를 목록 형태로 조회하고, 지역/경력/급여/기술스택/마감일 기준으로 탐색하는 화면입니다. 공고별 회사명, 위치, 경력 조건, 급여, 기술스택, 지원 액션이 한 번에 보이도록 구성했습니다.

### 검색 API 구현

![검색 API 구현](api-source.png)

`GET /jobs` 요청에 검색어, 지역, 기술스택, 정렬 기준을 전달하면 Specification 기반 조건 검색을 만들고, `jobPostings`, `sortOrder`, `pagenum`을 포함한 응답 맵을 반환합니다. 실제 컨트롤러 구현 흐름이 보이도록 소스 기반 캡처로 정리했습니다.

### 사람인 크롤링 덤프

![사람인 크롤링 덤프](crawl-dump.png)

`POST /jobs/crawl` 요청으로 사람인 검색 결과를 페이지 단위로 수집하고, Jsoup selector로 공고 필드를 추출합니다. URL 기준 중복 제거 후 MariaDB에 저장하는 흐름을 로그와 테이블 형태로 정리했습니다.
