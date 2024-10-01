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
    grid-template-columns: repeat(auto-fill, minmax(500px, 1fr)); /* 카드 최소 너비를 500px로 증가 */
    grid-gap: 32px; /* 카드 간격을 32px로 설정 */
    padding: 32px; /* 그리드의 여백을 32px로 설정 */
  }

  /* Masonry Card 스타일 */
  .masonry-card {
    display: flex;
    flex-direction: column;
    background: #fff;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 4px 16px rgba(0, 0, 0, 0.2); /* 그림자 크기 증가 */
    margin-bottom: 32px; /* 카드 하단 간격 */
    padding: 24px; /* 카드 안의 내용 패딩을 24px로 증가 */
    transition: transform 0.3s ease-in-out;
    font-size: 1.5rem; /* 카드 내부 텍스트 크기를 증가 */
  }

  /* 카드 Hover 시 확대 효과 */
  .masonry-card:hover {
    transform: scale(1.05); /* 호버 시 약간 확대 */
  }

  /* 이미지 스타일 */
  .masonry-card-image {
    width: 100%;
    height: 400px; /* 이미지 높이를 400px로 고정 */
    object-fit: cover;
    margin-bottom: 24px; /* 이미지와 텍스트 사이 간격 */
  }

  /* 카드 내용 스타일 */
  .masonry-card-content {
    padding: 16px;
  }

  /* 제목 스타일 */
  .masonry-card-title {
    font-size: 2rem; /* 제목 크기를 2rem로 증가 */
    margin: 0 0 16px;
  }

  /* 설명 스타일 */
  .masonry-card-summary {
    font-size: 1.25rem; /* 설명 글씨 크기를 1.25rem로 설정 */
    color: #666;
  }
</style>
