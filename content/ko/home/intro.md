---
# Use the Intro widget of the Blog template
widget: about.avatar

# This file represents a page section.
headless: true

# Order that this section will appear in.
weight: 10

author: admin
#design:
#  background:
#    color: '#090a0b'
#    text_color_light: true
#    video:
#      path:  # enter filename of a video in /assets/media
#  css_class: fullscreen
  
---

👋 Hi, there! I'm **Alice**, a machine learning researcher at Netflix.
{style="font-size: 1.2rem; background: #FFB76B; background: linear-gradient(to right, #FFB76B 0%, #FFA73D 30%, #FF7C00 60%, #FF7F04 100%); -webkit-background-clip: text; -webkit-text-fill-color: transparent;"}

Check out my [resumé](/about/) and portfolio below 😍

---
sections:
  - block: slider
    content:
      slides:

      - title: <span style="font-size:90%">AI</span>
        content: <span style="font-size:90%">의료/항공우주/컨텐츠 등 특성화 분야에 적용 가능한 AI 기술 개발<span style="font-size:90%">
        align: center
        background:
          image:
            filename: Ai.jpg
            filters:
              brightness: 0.4
          position: center
          color: '#000'

      - title: <span style="font-size:90%">Medical AI</span>
        content: <span style="font-size:90%">의료AI를 통한 질병 진단 및 환경 개선</span>
        align: center
        background:
          image:
            filename: medical.jpg
            filters:
              brightness: 0.4
          position: center
          color: '#000'

      - title: <span style="font-size:90%">Healthcare</span>
        content: <span style="font-size:90%">의료 및 헬스케어 분야에 적용 가능한 AI 기술 개발</span>
        align: center
        background:
          image:
            filename: healthcare.jpg
            filters:
              brightness: 0.4
          position: center
          color: '#000'

      - title: <span style="font-size:90%">Aerospace</span>
        content: <span style="font-size:90%">항공우주에 적용 가능한 특성화 AI 기술 개발</span>
        align: center
        background:
          image:
            filename: aerospace.jpg
            filters:
              brightness: 0.4
          position: center
          color: '#000'

      - title: <span style="font-size:90%">Contents AI</span>
        content: <span style="font-size:90%">웹툰 및 컨텐츠 적용 가능한 특성화 AI 기술 개발</span>
        align: center
        background:
          image:
            filename: contents.jpg
            filters:
              brightness: 0.4
          position: center
          color: '#000'

      - title: <span style="font-size:90%">Mathematics</span>
        content: <span style="font-size:90%">AI와 관련된 수학 및 최적화 이론 연구</span>
        align: center
        background:
          image:
            filename: mathematics.jpg
            filters:
              brightness: 0.4
          position: center
          color: '#000'

      - title: <span style="font-size:90%">Development</span>
        content: <span style="font-size:90%">기반 기술을 활용한 Full-Stack 어플리케이션 개발</span>
        align: center
        background:
          image:
            filename: development.jpg
            filters:
              brightness: 0.4
          position: center
          color: '#000'


      - title: <span style="font-size:90%">Recruit</span>
        content: <span style="font-size:90%">Interested in MacsLAB?</span>
        align: center
        background:
          image:
            filename: recruitment.jpg
            filters:
              brightness: 0.4
          position: center
          color: '#000'
        link:
          icon: user
          icon_pack: fas
          text: <span style="font-size:60%">Join Us</span>
          text-color: '#000'
          url: contact

    design:
      # Slide height is automatic unless you force a specific height (e.g. '400px')
      slide_height: '350px'
      is_fullscreen: true
      # Automatically transition through slides?
      loop: true
      # Duration of transition between slides (in ms)
      interval: 3000

  # - block: hero
  #   content:
  #     title: |
  #       <span style="font-size:75%">Medical AI & Computational Science (MACS) Lab</span>
  #     image:
  #       filename: welcome.jpg
  #     text: |
  #       <br>
        
  #       <span style="font-size:75%">전북대학교 의료 AI 및 계산 수학 연구실 (MACS Lab) 홈페이지에 오신 것을 환영합니다. MACS에서는 의료, 항공, 국방 분야에 AI 및 딥러닝을 활용한 연구를 수행하고 있으며, 의료 수학 및 AI 기반 연구도 함께 수행하고 있습니다. 뿐만 아니라, 풀스택 개발 및 AI를 활용한 어플리케이션 개발 등 Development & Deploy하는 실용적인 분야에도 집중하고 있습니다.</span>
---