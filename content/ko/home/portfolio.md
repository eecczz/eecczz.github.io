---
widget: portfolio
headless: true
weight: 30
title: ''
subtitle: ''

content:
  page_type: project
  filter_default: 0
  filter_button:
    - name: All
      tag: '*'
    - name: Machine Learning
      tag: ML
    - name: Computer Vision
      tag: CV
    - name: NLP
      tag: NLP

  design:
    view: "partials/masonry-card.html"
---

<style>
  /* Masonry Grid 스타일 */
  .masonry-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(600px, 1fr)) !important; /* 카드 최소 너비를 600px로 증가 */
    grid-gap: 40px !important; /* 카드 간격을 40px로 설정 */
    padding: 40px !important; /* 그리드의 여백을 40px로 설정 */
  }

  /* Masonry Card 스타일 */
  .masonry-card {
    display: flex;
    flex-direction: column;
    background: #fff !important;
    border-radius: 12px !important;
    overflow: hidden !important;
    box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3) !important; /* 그림자 크기 증가 */
    margin-bottom: 40px !important; /* 카드 하단 간격 증가 */
    padding: 32px !important; /* 카드 안의 내용 패딩을 32px로 증가 */
    font-size: 2rem !important; /* 카드 내부 텍스트 크기를 두 배로 증가 */
    transition: transform 0.3s ease-in-out !important;
  }

  /* 카드 Hover 시 확대 효과 */
  .masonry-card:hover {
    transform: scale(1.1) !important; /* 호버 시 약간 더 확대 */
  }

  /* 이미지 스타일 */
  .masonry-card-image {
    width: 100% !important;
    height: 500px !important; /* 이미지 높이를 500px로 증가 */
    object-fit: cover !important;
    margin-bottom: 24px !important; /* 이미지와 텍스트 사이 간격 */
  }

  /* 카드 내용 스타일 */
  .masonry-card-content {
    padding: 24px !important;
  }

  /* 제목 스타일 */
  .masonry-card-title {
    font-size: 2.5rem !important; /* 제목 크기를 2.5rem로 증가 */
    margin: 0 0 24px !important;
  }

  /* 설명 스타일 */
  .masonry-card-summary {
    font-size: 1.5rem !important; /* 설명 글씨 크기를 1.5rem로 증가 */
    color: #666 !important;
  }
</style>
