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
        <div style="text-align: center;">
          <img src="avatar.jpg" alt="Profile Image" style="width: 150px; height: 150px; border-radius: 50%; display: block; margin-left: auto; margin-right: auto;"><br>
          <span style="font-size:110%; font-weight: bold;">황선우</span><br>
          <span style="font-size:100%">게임/웹을 개발하고 있습니다.</span><br><br>
        </div>
        <br><br>
        {{% cta cta_link="./about/" cta_text="More→" %}}


  - block: slider
    content:
      slides:

      - title: <span style="font-size:70%">가상현실 게임</span>
        content: <span style="font-size:70%">조작방식이 실제 움직임과 유사하여 몰입감을 느낄 수 있는 게임<span style="font-size:70%">
        align: center
        background:
          image:
            filename: Ai.jpg
            filters:
              brightness: 0.4
          position: center
          color: '#000'

      - title: <span style="font-size:70%">웹서비스</span>
        content: <span style="font-size:70%">창의적이고 편리한 웹서비스를 제작</span>
        align: center
        background:
          image:
            filename: healthcare.jpg
            filters:
              brightness: 0.4
          position: center
          color: '#000'

      - title: <span style="font-size:70%">RPG 게임 개발</span>
        content: <span style="font-size:70%">취업에 맞춤화된 장르의 게임들을 개발</span>
        align: center
        background:
          image:
            filename: mathematics.jpg
            filters:
              brightness: 0.4
          position: center
          color: '#000'

    design:
      # Slide height is automatic unless you force a specific height (e.g. '400px')
      slide_height: '350px'
      slide_width: '100px'
      is_fullscreen: false
      # Automatically transition through slides?
      loop: true
      # Duration of transition between slides (in ms)
      interval: 3000


  - block: features
    id: features
    content:
      title: <span style="font-size:75%">학습중인 분야</span>
      text: 저희 연구실에서는 다음과 같은 연구/개발 분야에 관심을 쏟고 있습니다.<br><br><br><br>
      items:
        - name: 인공지능(AI)
          icon: code-branch
          icon_pack: fas
          description: <span style="font-size:90%">창의적이고 혁신적인 AI 서비스를 제작</span><br><br>
        - name: 알고리즘
          icon: globe
          icon_pack: fas
          description:  <span style="font-size:90%">코딩 테스트에 나올 수 있는 알고리즘과 AI에 적용되는 알고리즘들을 학습하고 문제풀이 진행</span><br><br>
        - name: 기획
          icon: calculator
          icon_pack: fas
          description:  <span style="font-size:90%">특정 주제가 주어지고 그에 관련된 웹/앱을 만드는 요구사항이 주어질 때, 유저가 관심을 가질 만한 아이디어를 내고, 체계적으로 정리하는 것을 연구</span><br><br>
        - name: 네트워크
          icon: comment-dots
          icon_pack: fas
          description:  <span style="font-size:90%">개발 실무에서 다양한 문제 해결을 위한 네트워크 지식 공부</span><br><br>
        - name: 게임 개발
          icon: laptop
          icon_pack: fas
          description:  <span style="font-size:90%">내가 취업하려고 하는 게임회사나 유저들에게 필요한 재밌고 트렌디한 게임을 최적의 방법으로 구현하는 것을 공부 </span><br><br>
        - name: 웹 개발
          icon: app-store-ios
          icon_pack: fab
          description:  <span style="font-size:90%">현재 회사들이 필요한, 적절한 디자인 패턴을 사용해 지속가능한 코드와, 실무에서 겪을 수 있는 트래픽 등 다양한 상황들을 해결하는 데 필요한 개념을 학습하고 구현 </span><br><br>


  - block: collection
    content:
      id: section-1
      title: wii 검술대련 클론게임
      subtitle:
      text:
      count: 3
      offset: 0
      order: desc
      filters:
        folders:
          - sword-motion
          - hit-reaction
          - shader
    design:
      view: community/custom_card
      columns: '2'

  - block: collection
    content:
      id: section-1
      title: 유튜브 클론웹
      subtitle:
      text:
      count: 3
      offset: 0
      order: desc
      filters:
        folders:
          - react&spring
          - aws-lambda
          - video-preview
    design:
      view: community/custom_card
      columns: '2'

  - block: collection
    content:
      title: Team Projects
      subtitle:
      text:
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
        {{% cta cta_link="./contact/" cta_text="Join Project →" %}}
    design:
      columns: '1'
---