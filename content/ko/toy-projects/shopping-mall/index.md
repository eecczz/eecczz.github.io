---

title: 쇼핑몰 프로젝트
date: 2026-05-20
summary: '상품 조회, 장바구니, 구매 페이지, PortOne 테스트 결제 검증을 제공하는 Spring Boot + MariaDB 쇼핑몰 데모입니다.'
highlights:
  - title: 쇼핑몰 화면
    text: 상품 목록, 상세, 장바구니, 구매 페이지로 이어지는 기본 쇼핑 흐름을 만들었습니다.
    image: capture-list.png
  - title: 장바구니 흐름
    text: 상품 수량, 합계 계산, 체크아웃 진입까지 쇼핑몰의 구매 전 단계를 확인할 수 있게 구성했습니다.
    image: capture-cart.png
  - title: 로그인 화면
    text: 장바구니와 결제 흐름을 세션 기반 인증 화면으로 연결하는 구조를 실험했습니다.
    image: capture-signin.png
links:
  - name: GitHub
    url: https://github.com/eecczz/shoppingmall-springboot
featured: true
---

쇼핑몰 프로젝트는 Spring Boot와 MariaDB 기반의 쇼핑몰 데모 프로젝트입니다. 상품 조회에서 상세 보기, 장바구니, 구매 페이지, PortOne 테스트 결제 검증까지 쇼핑몰의 핵심 흐름을 구현했습니다.

초기에는 Thymeleaf 기반 서버 사이드 렌더링으로 화면을 구성했고, 이후 클라이언트 사이드 흐름과 결제/소셜 로그인 구현을 고려하며 React 기반 구조로 확장하는 경험을 했습니다. jcloud Ubuntu 환경에 executable jar로 배포한 경험도 포함되어 있습니다.

- 기술 스택: Spring Boot, Spring MVC, MariaDB, Spring Data JPA, Querydsl, Thymeleaf
- 구현 포인트: 세션 기반 로그인, 검색/페이징, 장바구니, 결제 검증, 서버 배포
- 저장소: [eecczz/shoppingmall-springboot](https://github.com/eecczz/shoppingmall-springboot)

## 주요 구현 포인트

### 쇼핑몰 화면

![쇼핑몰 화면](capture-list.png)

상품 목록, 상세, 장바구니, 구매 페이지로 이어지는 기본 쇼핑 흐름을 만들었습니다.

### 장바구니 흐름

![장바구니 흐름](capture-cart.png)

상품 수량, 합계 계산, 체크아웃 진입까지 쇼핑몰의 구매 전 단계를 확인할 수 있게 구성했습니다.

### 로그인 화면

![로그인 화면](capture-signin.png)

장바구니와 결제 흐름을 세션 기반 인증 화면으로 연결하는 구조를 실험했습니다.
