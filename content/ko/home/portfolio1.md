---
# Order that this section appears on the page.
weight: 40
title: ''
subtitle: ''

sections:
  - block: collection  # 블록 스타일로 변경
    content:
      page_type: project  # 표시할 페이지 유형 (예: 프로젝트)
      filter_default: 0  # 기본 필터 인덱스
      filters:
        - name: All
          tag: '*'
        - name: Machine Learning
          tag: ML
        - name: Computer Vision
          tag: CV
        - name: NLP
          tag: NLP

    design:
      view: masonry  # masonry 뷰 스타일 사용
      columns: 3  # 컬럼 수를 정의

---
