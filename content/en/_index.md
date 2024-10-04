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
        <span style="font-size:110%; font-weight: bold;">Hwang Seon-woo</span><br><br>
        <span style="font-size:100%">I'm a sophomore at Chonbuk National University's Department of Computer and Artificial Intelligence, developing games and web applications, and preparing for a career as a developer.</span><br><br>
        <!-- Email icon added and styled -->
        <div style="text-align: center;">
          <a href="mailto:swh06084@jbnu.ac.kr" style="text-decoration: none; color: #ff5722;">
            <i class="fas fa-envelope" style="font-size: 2rem;"></i>
          </a>
        </div><br><br>

  - block: slider
    content:
      slides:

      - title: <span style="font-size:70%">Virtual Reality Game</span>
        content: <span style="font-size:70%">A game that immerses players with controls that mimic real-life movements.</span>
        align: center
        background:
          image:
            filename: nikita-kachanovsky-FJFPuE1MAOM-unsplash.jpg
            filters:
              brightness: 0.4
          position: center
          color: '#000'

      - title: <span style="font-size:70%">Web Service</span>
        content: <span style="font-size:70%">Creating creative and user-friendly web services.</span>
        align: center
        background:
          image:
            filename: luke-chesser-2Bdyxgz3OM0-unsplash.jpg
            filters:
              brightness: 0.4
          position: center
          color: '#000'

      - title: <span style="font-size:70%">RPG Game Development</span>
        content: <span style="font-size:70%">Developing games tailored for career opportunities in the RPG genre.</span>
        align: center
        background:
          image:
            filename: alice-alinari-HUqxgjORAnw-unsplash.jpg
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
      title: <br><br><span style="font-size:75%">Fields of Study</span>
      text: These are my learning goals and areas of interest as I work towards becoming a developer.<br><br>
      items:
        - name: Artificial Intelligence (AI)
          icon: code-branch
          icon_pack: fas
          description: <span style="font-size:90%">Creating creative and innovative AI services.</span><br><br>
        - name: Algorithms
          icon: code
          icon_pack: fas
          description:  <span style="font-size:90%">Learning algorithms for coding tests and those applied in AI, along with problem-solving.</span><br><br>
        - name: Planning
          icon: align-right
          icon_pack: fas
          description:  <span style="font-size:90%">Generating ideas for web/app development based on given requirements, focusing on what will attract users, and systematically organizing them.</span><br><br>
        - name: Networking
          icon: wifi
          icon_pack: fas
          description:  <span style="font-size:90%">Knowledge of networking to solve various problems in development practices.</span><br><br>
        - name: Game Development
          icon: gamepad
          icon_pack: fas
          description:  <span style="font-size:90%">Developing fun and trendy games efficiently for the game companies or users I aim to work for.</span><br><br>
        - name: Web Development
          icon: file
          icon_pack: fas
          description:  <span style="font-size:90%">Building sustainable code using appropriate design patterns and tackling real-world issues like traffic in a practical environment.</span><br><br>


  - block: collection
    content:
      id: section-1
      title: <br>Wii Swordplay Clone Game
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
      view: community/custom_card
      columns: '2'

  - block: collection
    content:
      id: section-1
      title: <br>YouTube Clone Web
      subtitle:
      text: <br><br><br><br>
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
      title: <br>Team Projects
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
        {{% cta cta_link="./contact/" cta_text="Join Project →" %}}
    design:
      columns: '1'
---
