---
# Leave the homepage title empty to use the site title
title:
date: 2024-03-25
type: landing

sections:

  - block: features
    content:
      title: ""
      text: |
        <div class="portfolio-intro">
          <img src="avatar.jpg" alt="황선우 프로필 이미지" class="portfolio-avatar">
          <div class="portfolio-kicker">Game · Backend · AI Service Developer</div>
          <h1>황선우</h1>
          <p>
            전북대학교 IT정보공학과 4학년으로, Unity 게임 개발과 Spring Boot/FastAPI 기반 백엔드,
            AI 에이전트 서비스를 함께 만들어 온 개발자입니다. 유저가 반응할 장면을 상상하며 몰입하고,
            아이디어를 빠르게 시제품으로 옮긴 뒤 실행 가능한 서비스 구조로 다듬는 일을 좋아합니다.
          </p>
          <p>
            학점 4.0/4.5, 2021년 총장상(성적 우수, 전체 석차 1위), 2026년 캡스톤디자인 최우수상 및
            전북도청 도지사 표창을 기반으로 꾸준함과 실행력을 함께 증명해 왔습니다.
          </p>
          <div class="portfolio-links">
            <a href="mailto:swh06084@jbnu.ac.kr" aria-label="Email"><i class="fas fa-envelope"></i></a>
            <a href="https://github.com/eecczz" aria-label="GitHub"><i class="fab fa-github"></i></a>
          </div>
        </div>

  - block: markdown
    content:
      title: 주요 성과
      subtitle:
      text: |
        <div class="portfolio-highlight-grid">
          <div class="portfolio-highlight">
            <strong>4.0 / 4.5</strong>
            <span>전공 학업과 프로젝트를 병행하며 유지한 학점</span>
          </div>
          <div class="portfolio-highlight">
            <strong>총장상</strong>
            <span>2021년 성적 우수, 전체 석차 1위</span>
          </div>
          <div class="portfolio-highlight">
            <strong>최우수상 · 도지사 표창</strong>
            <span>전북도청 대도민 음성 챗봇 캡스톤디자인</span>
          </div>
          <div class="portfolio-highlight">
            <strong>산학·연구 경험</strong>
            <span>Unity 외주, 시각지능 연구실, 관제 소프트웨어 현장실습</span>
          </div>
        </div>
    design:
      columns: '1'

  - block: slider
    content:
      slides:

      - title: <span style="font-size:70%">가상현실 게임</span>
        content: |
          <div style="position: relative; text-align: center; color: white;">
            <div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; background-color: rgba(0, 0, 0, 0.5);"></div>
            <span style="position: relative; font-size: 70%;">실제 움직임과 닮은 입력·피격·상호작용으로 몰입감을 만드는 게임 개발</span>
          </div>
        align: center
        background:
          image:
            filename: nikita-kachanovsky-FJFPuE1MAOM-unsplash.jpg
            filters:
              brightness: 0.4
          position: center
          color: '#000'

      - title: <span style="font-size:70%">AI 서비스</span>
        content: |
          <div style="position: relative; text-align: center; color: white;">
            <div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; background-color: rgba(0, 0, 0, 0.5);"></div>
            <span style="position: relative; font-size: 70%;">음성, 영상, 추천 문제를 AI 에이전트와 웹서비스로 연결</span>
          </div>
        align: center
        background:
          image:
            filename: Ai.jpg
            filters:
              brightness: 0.4
          position: center
          color: '#000'

      - title: <span style="font-size:70%">백엔드·클라우드</span>
        content: |
          <div style="position: relative; text-align: center; color: white;">
            <div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; background-color: rgba(0, 0, 0, 0.5);"></div>
            <span style="position: relative; font-size: 70%;">Spring Boot, MariaDB, AWS 기반의 API와 미디어 처리 파이프라인 설계</span>
          </div>
        align: center
        background:
          image:
            filename: luke-chesser-2Bdyxgz3OM0-unsplash.jpg
            filters:
              brightness: 0.4
          position: center
          color: '#000'

    design:
      slide_height: '350px'
      slide_width: '100px'
      is_fullscreen: false
      loop: true
      interval: 3000

  - block: features
    id: features
    content:
      title: <br><br><span style="font-size:75%">핵심 역량</span>
      text: 프로젝트를 통해 반복적으로 쌓아 온 기술 방향입니다.<br><br>
      items:
        - name: AI 에이전트
          icon: code-branch
          icon_pack: fas
          description: <span style="font-size:90%">ReAct Agent, 실시간 코칭, 영상 분석 등 AI를 실제 서비스 흐름에 연결</span><br><br>
        - name: 백엔드 API
          icon: server
          icon_pack: fas
          description:  <span style="font-size:90%">Spring Boot, FastAPI, REST API, JWT 인증, MariaDB/PostgreSQL 기반 데이터 설계</span><br><br>
        - name: 클라우드·미디어
          icon: cloud
          icon_pack: fas
          description:  <span style="font-size:90%">AWS S3, Lambda, MediaConvert, HLS를 활용한 업로드·변환·스트리밍 구조 설계</span><br><br>
        - name: 게임 개발
          icon: gamepad
          icon_pack: fas
          description:  <span style="font-size:90%">Unity, C#, XR 입력, 절차적 애니메이션, 셰이더로 조작감과 타격감을 구현</span><br><br>
        - name: 웹 프론트엔드
          icon: desktop
          icon_pack: fas
          description:  <span style="font-size:90%">React, Next.js, TypeScript로 사용자 흐름과 API 연동 화면 구성</span><br><br>
        - name: 기획·몰입
          icon: lightbulb
          icon_pack: fas
          description:  <span style="font-size:90%">유저와 팀원의 반응을 상상하며 아이디어를 만들고, 목표에 맞게 수용적으로 조율</span><br><br>

  - block: collection
    content:
      id: section-swordplay
      title: <br>Wii Swordplay 클론
      subtitle:
      text: <br><br><br><br>
      count: 3
      offset: 0
      order: desc
      filters:
        folders:
          - sword-motion
          - hit-reaction
          - shader
    design:
      view: community/custom_pcard
      columns: '2'

  - block: collection
    content:
      id: section-game-projects
      title: <br>게임·XR 프로젝트
      subtitle:
      text: <br><br><br><br>
      count: 3
      offset: 0
      order: desc
      filters:
        folders:
          - game-projects
    design:
      view: community/custom_card
      columns: '2'

  - block: collection
    content:
      id: section-ai-projects
      title: <br>AI·에이전트 프로젝트
      subtitle:
      text: <br><br><br><br>
      count: 3
      offset: 0
      order: desc
      filters:
        folders:
          - ai-agent-projects
    design:
      view: community/custom_card
      columns: '2'

  - block: collection
    content:
      id: section-backend-projects
      title: <br>백엔드·웹서비스 프로젝트
      subtitle:
      text: <br><br><br><br>
      count: 8
      offset: 0
      order: desc
      filters:
        folders:
          - backend-projects
          - web-projects
          - react&spring
          - aws-lambda
          - video-preview
    design:
      view: community/custom_card
      columns: '2'

  - block: collection
    content:
      title: <br>팀프로젝트
      subtitle:
      text: <br><br><br><br>
      count: 3
      filters:
        author: ''
        category: ''
        exclude_featured: false
        publication_type: ''
        tag: ''
      offset: 0
      order: desc
      page_type: team-projects
    design:
      view: community/custom_card
      columns: '2'
    advanced:
      css_style: "text-align: center;"

  - block: markdown
    content:
      title:
      subtitle:
      text: |
        {{% cta cta_link="./contact/" cta_text="프로젝트 문의 →" %}}
    design:
      columns: '1'
---
