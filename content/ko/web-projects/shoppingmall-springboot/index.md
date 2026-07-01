---
title: PaymentAPI - 쇼핑몰 데모
date: 2026-05-20
summary: '상품 조회, 장바구니, 구매 페이지, PortOne 테스트 결제 검증을 제공하는 Spring Boot + MariaDB 쇼핑몰 데모입니다.'
links:
  - name: GitHub
    url: https://github.com/eecczz/shoppingmall-springboot
featured: true
---

PaymentAPI는 Spring Boot와 MariaDB 기반의 쇼핑몰 데모 프로젝트입니다. 상품 조회에서 상세 보기, 장바구니, 구매 페이지, PortOne 테스트 결제 검증까지 쇼핑몰의 핵심 흐름을 구현했습니다.

초기에는 Thymeleaf 기반 서버 사이드 렌더링으로 화면을 구성했고, 이후 클라이언트 사이드 흐름과 결제/소셜 로그인 구현을 고려하며 React 기반 구조로 확장하는 경험을 했습니다. jcloud Ubuntu 환경에 executable jar로 배포한 경험도 포함되어 있습니다.

- 기술 스택: Spring Boot, Spring MVC, MariaDB, Spring Data JPA, Querydsl, Thymeleaf
- 구현 포인트: 세션 기반 로그인, 검색/페이징, 장바구니, 결제 검증, 서버 배포
- 저장소: [eecczz/shoppingmall-springboot](https://github.com/eecczz/shoppingmall-springboot)
