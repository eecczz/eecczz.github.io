---
title: 쇼핑몰 백엔드
date: 2026-05-20
summary: 'Spring Boot·JPA·Querydsl로 상품 탐색부터 장바구니·주문·PortOne 테스트 결제 검증까지 구현한 서비스입니다.'
featured: true
---

<div class="case-study-lead">
  <p class="case-study-kicker">BACKEND · AI · SYSTEM CASE STUDY</p>
  <p>Spring Boot·JPA·Querydsl로 상품 탐색부터 장바구니·주문·PortOne 테스트 결제 검증까지 구현한 서비스입니다.</p>
  <div class="case-study-meta"><span><b>역할</b> 개인 프로젝트 · 상품/장바구니/주문/결제/배포</span><span><b>검증</b> jcloud Ubuntu executable jar 배포</span></div>
</div>

## 주요 화면

상품 목록에서 상세 옵션을 확인하고 장바구니에 담은 뒤 합계·수량을 검토해 주문으로 넘어가는 구매 흐름을 구현했습니다. 목록 조회와 장바구니 상태가 주문·결제 도메인으로 이어지도록 구성했습니다.

![상품을 조회하고 옵션을 선택하는 목록 화면](capture-list.png)

![선택 상품과 합계를 확인하는 장바구니 화면](capture-cart.png)

## 트러블 슈팅

### 1. 빌드할 때마다 Querydsl QEntity 재생성이 불안정함

Spring Boot 3의 Jakarta 전환 이후에도 오래된 Querydsl Gradle 플러그인과 생성 경로 설정이 함께 남아 있어, Q타입이 중복 생성되거나 stale source가 참조됐습니다.

서드파티 플러그인을 제거하고 `querydsl-jpa:5.0.0:jakarta`와 APT annotation processor로 생성 경로를 하나로 통일했습니다. `JavaCompile.generatedSourceOutputDirectory`를 `build/generated/querydsl`로 고정하고 `clean`에서 해당 디렉터리를 지우도록 해 재현 가능한 빌드로 바꿨습니다.

![Querydsl Q타입 생성 설정 변경 전후](code-querydsl.svg)

### 2. 결제 성공 화면만 믿으면 주문 상태와 실제 승인 결과가 어긋날 수 있음

imp_uid를 서버에서 검증한 뒤 주문 상태를 갱신했습니다.

### 3. 배포 시 MySQL socket/JDBCConnectionException으로 애플리케이션이 기동 실패

DB host·port·방화벽·환경변수를 분리 점검하고 실제 DB 연결을 배포 체크리스트로 남겼습니다.

## 기술 선택과 이유

| 기술 | 선택 이유 |
|---|---|
| **Spring MVC · Thymeleaf** | 서버 렌더링으로 구매 흐름과 세션 인증을 빠르게 끝까지 검증하기 위해 |
| **JPA · Querydsl** | 도메인 관계를 모델링하고 검색·페이징 조건을 동적으로 조합하기 위해 |
| **PortOne sandbox** | 실결제 없이 승인 식별자와 주문 상태 처리 흐름을 검증하기 위해 |
| **MariaDB** | 회원·상품·장바구니·주문 데이터를 트랜잭션으로 관리하기 위해 |

## 검증 결과

- 회원가입→상품 탐색→장바구니→테스트 결제→주문 상태의 end-to-end 흐름을 구현했습니다.
- jcloud Ubuntu에 executable jar로 배포했습니다.

## 시스템 흐름

![쇼핑몰 백엔드 시스템 흐름](architecture.svg)

1. 사용자가 상품을 검색하고 상세를 조회합니다.
2. 세션 로그인 사용자가 장바구니 수량을 변경합니다.
3. 서비스 계층이 합계와 주문 항목을 계산합니다.
4. PortOne 테스트 결제 후 imp_uid를 서버에 전달합니다.
5. 서버가 결제 검증 결과에 따라 주문 상태를 변경합니다.
6. Executable jar를 jcloud Ubuntu에서 실행합니다.

## API · 시스템 경계

| 영역 | API/계약 | 책임 |
|---|---|---|
| `Catalog` | `GET /demo/list, /item-detail/{id}` | 검색·상세 |
| `Cart` | `GET /cart, POST /updatecart, /deletecart` | 장바구니 |
| `Order` | `GET/POST /purchase, /order/payment` | 주문 생성 |
| `Payment` | `POST /payment/validation/{imp_uid}` | 결제 검증 |

## 다음 구현 계획

- 결제 검증과 주문 상태 변경의 idempotency 보장
- 동시 수량 변경·재고 차감에 optimistic locking 적용
- CI/CD·health check·로그 수집 추가
