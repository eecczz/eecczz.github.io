---

title: 유튜브 클론
date: 2026-05-12
summary: 'React/Spring 구조, AWS Lambda 기반 영상 처리, 썸네일 hover preview를 실험한 유튜브형 영상 서비스 클론입니다.'
highlights:
  - title: Video Preview
    text: 썸네일 hover 후 일정 시간 머물렀을 때만 영상을 로드해 불필요한 재생을 줄였습니다.
    image: featured.png
  - title: 미디어 UX
    text: 썸네일, 영상, 재생바가 자연스럽게 전환되는 유튜브형 탐색 경험을 구현했습니다.
    image: https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&w=720&q=80
  - title: 영상 처리 구조
    text: 업로드와 재생을 고려해 React 화면과 서버/클라우드 처리 흐름을 분리했습니다.
    image: https://images.unsplash.com/photo-1485846234645-a62644f84728?auto=format&fit=crop&w=720&q=80
links:
  - name: GitHub
    url: https://github.com/eecczz
featured: true
---

유튜브 클론은 영상 업로드, 재생, 미리보기 경험을 직접 구현해 보기 위한 웹서비스 프로젝트입니다. 기존에는 React & Spring, AWS Lambda, Video Preview를 각각 따로 소개했지만, 실제로는 하나의 유튜브형 서비스 구현 과정이므로 대표 프로젝트로 통합했습니다.

가장 집중한 기능은 썸네일에 마우스를 올렸을 때 영상이 자연스럽게 preview되는 UX입니다. 사용자가 썸네일을 스쳐 지나갈 때마다 무거운 영상을 즉시 로드하지 않도록 hover 유지 시간 조건을 두고, 썸네일과 영상 엘리먼트를 전환하는 방식으로 성능과 사용성을 함께 고려했습니다.

- 기술 스택: React, Spring Boot, AWS Lambda, 영상 업로드/재생 처리
- 구현 포인트: hover video preview, 영상 로드 제어, 클라이언트/서버 분리 구조
- 관련 구현: 기존 Video Preview, AWS Lambda, React & Spring 섹션을 하나의 프로젝트 소개로 통합

## 주요 구현 포인트

### Video Preview

![Video Preview](featured.png)

썸네일 hover 후 일정 시간 머물렀을 때만 영상을 로드해 불필요한 재생을 줄였습니다.

### 미디어 UX

![미디어 UX](https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&w=720&q=80)

썸네일, 영상, 재생바가 자연스럽게 전환되는 유튜브형 탐색 경험을 구현했습니다.

### 영상 처리 구조

![영상 처리 구조](https://images.unsplash.com/photo-1485846234645-a62644f84728?auto=format&fit=crop&w=720&q=80)

업로드와 재생을 고려해 React 화면과 서버/클라우드 처리 흐름을 분리했습니다.
