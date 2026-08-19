---
title: 프로젝트 전체 보기
date: 2026-08-19
type: landing

sections:
  - block: markdown
    content:
      title: 프로젝트 전체 보기
      text: |
        <p class="project-archive-intro">프로젝트 성격에 따라 사례를 나누었습니다. 아래에서 먼저 관심 있는 유형을 고르거나, 각 영역의 대표 사례를 살펴본 뒤 전체 목록으로 이동할 수 있습니다.</p>
        <div class="project-archive-switcher">
          <a href="../contest-projects/" class="project-archive-choice">
            <span class="project-archive-eyebrow">TEAM · AWARD · FIELD</span>
            <strong>팀·수상·현장 프로젝트</strong>
            <small>캡스톤·공모전·기업 연계 및 Edge-AI 현장 적용 사례</small>
            <b>전체 보기 →</b>
          </a>
          <a href="../toy-projects/" class="project-archive-choice">
            <span class="project-archive-eyebrow">PERSONAL · TECHNICAL</span>
            <strong>개인 프로젝트</strong>
            <small>기획부터 구현·배포까지 직접 검증한 백엔드·AI·Unity 사례</small>
            <b>전체 보기 →</b>
          </a>
        </div>
    design:
      columns: '1'

  - block: collection
    content:
      title: 팀·수상·현장 프로젝트
      text: 대표 4개 사례입니다. 나머지 프로젝트는 위 버튼에서 모두 볼 수 있습니다.
      count: 4
      offset: 0
      order: desc
      filters:
        folders:
          - contest-projects
    design:
      view: community/custom_card
      columns: '2'

  - block: collection
    content:
      title: 개인 프로젝트
      text: 대표 4개 사례입니다. 나머지 프로젝트는 위 버튼에서 모두 볼 수 있습니다.
      count: 4
      offset: 0
      order: desc
      filters:
        folders:
          - toy-projects
    design:
      view: community/custom_card
      columns: '2'
---
