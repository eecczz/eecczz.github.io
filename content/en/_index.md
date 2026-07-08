---
title:
date: 2024-03-25
type: landing

sections:

  - block: features
    content:
      title: ""
      text: |
        <div class="portfolio-intro">
          <img src="avatar.jpg" alt="Hwang Seon-woo profile image" class="portfolio-avatar">
          <div class="portfolio-kicker">Game / Backend / AI Service Developer</div>
          <h1>Hwang Seon-woo</h1>
          <p>
            I am a senior IT Information Engineering student at Jeonbuk National University, building Unity games,
            Spring Boot/FastAPI backends, and AI agent services. I like imagining the moment users will react to,
            turning ideas into prototypes quickly, and refining them into executable service structures.
          </p>
          <p>
            I have kept a 4.0/4.5 overall academic GPA, received the 2021 President's Award for academic excellence
            with the top overall rank, and earned capstone awards including a Jeonbuk Provincial Governor citation.
          </p>
          <div class="portfolio-links">
            <a href="mailto:swh06084@jbnu.ac.kr" aria-label="Email"><i class="fas fa-envelope"></i></a>
            <a href="https://github.com/eecczz" aria-label="GitHub"><i class="fab fa-github"></i></a>
          </div>
        </div>

  - block: markdown
    content:
      title: Key Achievements
      subtitle:
      text: |
        <div class="portfolio-highlight-grid">
          <div class="portfolio-highlight">
            <strong>Overall academic GPA 4.0/4.5</strong>
            <span>Maintained while balancing major coursework and projects</span>
          </div>
          <div class="portfolio-highlight">
            <strong>President's Award</strong>
            <span>2021 academic excellence, top overall rank</span>
          </div>
          <div class="portfolio-highlight">
            <strong>Grand Prize / Governor Citation</strong>
            <span>Jeonbuk public voice chatbot capstone project</span>
          </div>
          <div class="portfolio-highlight">
            <strong>Industry & Research Experience</strong>
            <span>Unity contract work, visual intelligence lab, monitoring software internship</span>
          </div>
          <div class="portfolio-highlight">
            <strong>Open Source Contribution</strong>
            <span>Contributed a fix for a video playback initialization error</span>
          </div>
        </div>
    design:
      columns: '1'

  - block: slider
    content:
      slides:

      - title: <span style="font-size:70%">Interactive Games</span>
        content: |
          <div style="position: relative; text-align: center; color: white;">
            <span style="position: relative; font-size: 70%; text-shadow: 0 2px 8px rgba(0, 0, 0, 0.45);">Building immersive game interactions through motion-like input, hit reactions, and feedback loops</span>
          </div>
        align: center
        background:
          image:
            filename: nikita-kachanovsky-FJFPuE1MAOM-unsplash.jpg
            filters:
              brightness: 0.4
          position: center
          color: '#000'

      - title: <span style="font-size:70%">AI Services</span>
        content: |
          <div style="position: relative; text-align: center; color: white;">
            <span style="position: relative; font-size: 70%; text-shadow: 0 2px 8px rgba(0, 0, 0, 0.45);">Connecting voice, video, and recommendation problems to AI agents and web services</span>
          </div>
        align: center
        background:
          image:
            filename: Ai.jpg
            filters:
              brightness: 0.4
          position: center
          color: '#000'

      - title: <span style="font-size:70%">Backend & Cloud</span>
        content: |
          <div style="position: relative; text-align: center; color: white;">
            <span style="position: relative; font-size: 70%; text-shadow: 0 2px 8px rgba(0, 0, 0, 0.45);">Designing APIs and media pipelines with Spring Boot, MariaDB, AWS, and HLS</span>
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
      title: <br><br><span style="font-size:75%">Core Strengths</span>
      text: Technical directions I have repeatedly built through projects.<br><br>
      items:
        - name: AI Agents
          icon: code-branch
          icon_pack: fas
          description: <span style="font-size:90%">Connecting ReAct agents, real-time coaching, and video analysis to usable service flows</span><br><br>
        - name: Backend APIs
          icon: server
          icon_pack: fas
          description: <span style="font-size:90%">Spring Boot, FastAPI, REST APIs, JWT auth, and MariaDB/PostgreSQL data design</span><br><br>
        - name: Cloud & Media
          icon: cloud
          icon_pack: fas
          description: <span style="font-size:90%">Upload, conversion, and streaming architecture with AWS S3, Lambda, MediaConvert, and HLS</span><br><br>
        - name: Game Development
          icon: gamepad
          icon_pack: fas
          description: <span style="font-size:90%">Unity, C#, XR input, procedural animation, and shaders for responsive controls and hit feedback</span><br><br>
        - name: Web Frontend
          icon: desktop
          icon_pack: fas
          description: <span style="font-size:90%">React, Next.js, and TypeScript interfaces connected to backend APIs</span><br><br>
        - name: Product Thinking
          icon: lightbulb
          icon_pack: fas
          description: <span style="font-size:90%">Shaping ideas around user and teammate reactions, then adjusting them toward clear goals</span><br><br>

  - block: markdown
    content:
      title: Game Projects
      subtitle:
      text: |
        <div class="home-project-grid">
          <article class="home-project-card">
            <a class="home-project-title" href="./toy-projects/swordplay/">Wii Swordplay Remake</a>
            <p>A Unity WebGL project that recreates sword swinging, hit reactions, and Wii-like shader styling with mouse input.</p>
            <div class="home-project-highlights">
              <div><img src="./toy-projects/swordplay/featured.jpg" alt="Sword controls"><strong>Sword Controls</strong><span>Converted mouse input into sword rotation and position for a direct swinging feel.</span></div>
              <div><img src="./toy-projects/swordplay/detail-hit-reaction.jpg" alt="Hit reaction"><strong>Hit Reaction</strong><span>Strengthened impact feedback with a self-balancing recovery flow.</span></div>
              <div><img src="./toy-projects/swordplay/detail-shader.jpg" alt="Wii-like shader"><strong>Wii-like Shader</strong><span>Used simple colors, low gloss, and outline-like styling to echo the original visual tone.</span></div>
            </div>
          </article>

          <article class="home-project-card">
            <a class="home-project-title" href="./contest-projects/soulslike-game/">Soulslike Game</a>
            <p>A four-person Unity action game project set in a colosseum for an introductory creative engineering design course.</p>
            <div class="home-project-highlights">
              <div><img src="./contest-projects/soulslike-game/detail-arena.png" alt="Boss sequence"><strong>Boss Sequence</strong><span>Built tension with wide-range attacks and strong visual effects.</span></div>
              <div><img src="./contest-projects/soulslike-game/featured.png" alt="Dodge and combo"><strong>Dodge & Combo</strong><span>Designed a combat rhythm where the player reads attacks, dodges, and counters.</span></div>
              <div><img src="./contest-projects/soulslike-game/detail-combat.png" alt="Colosseum stage"><strong>Colosseum Stage</strong><span>Created a confrontation space for a final battle between the player and boss.</span></div>
            </div>
          </article>

          <article class="home-project-card">
            <a class="home-project-title" href="./toy-projects/metaxr-project/">MetaXR Project</a>
            <p>An XR action prototype connecting hand movement and spatial presence to combat interactions.</p>
            <div class="home-project-highlights">
              <div><img src="./toy-projects/metaxr-project/featured.png" alt="XR combat input"><strong>XR Combat Input</strong><span>Mapped controller motion to attack and defense interactions.</span></div>
              <div><img src="./toy-projects/metaxr-project/detail-unity.png" alt="Close interaction"><strong>Close Interaction</strong><span>Composed close-range action scenes where the player faces monsters directly.</span></div>
              <div><img src="./toy-projects/metaxr-project/detail-xr.png" alt="Unity prototype"><strong>Unity Prototype</strong><span>Validated XR input, collision, and monster reactions in a fast action prototype.</span></div>
            </div>
          </article>
        </div>
    design:
      columns: '1'

  - block: markdown
    content:
      title: Web & App Services
      subtitle:
      text: |
        <div class="home-project-grid">
          <article class="home-project-card">
            <a class="home-project-title" href="./toy-projects/shopping-mall/">Shopping Mall Project</a>
            <p>A Spring Boot and MariaDB shopping mall demo covering product browsing, cart, purchase, and payment verification flows.</p>
            <div class="home-project-highlights">
              <div><img src="./toy-projects/shopping-mall/capture-list.png" alt="Product list"><strong>Product List</strong><span>Implemented the basic shopping flow from product list to cart and purchase pages.</span></div>
              <div><img src="./toy-projects/shopping-mall/capture-cart.png" alt="Cart flow"><strong>Cart Flow</strong><span>Handled quantity updates, total price calculation, and checkout entry.</span></div>
              <div><img src="./toy-projects/shopping-mall/capture-signin.png" alt="Login screen"><strong>Login Screen</strong><span>Connected cart and payment flows to a session-based authentication screen.</span></div>
            </div>
          </article>

          <article class="home-project-card">
            <a class="home-project-title" href="./toy-projects/youtube-clone/">YouTube Remake</a>
            <p>A YouTube-style video service remake exploring hover preview, upload, and playback architecture.</p>
            <div class="home-project-highlights">
              <div><img src="./toy-projects/youtube-clone/featured.png" alt="Video Preview"><strong>Video Preview</strong><span>Reduced unnecessary loading by previewing only after a hover dwell time.</span></div>
              <div><img src="./toy-projects/youtube-clone/detail-player.png" alt="Media UX"><strong>Media UX</strong><span>Built a YouTube-like exploration experience with thumbnails, video, and playback controls.</span></div>
              <div><img src="./toy-projects/youtube-clone/detail-upload.png" alt="Upload flow"><strong>Upload Flow</strong><span>Separated the React screen and backend/cloud processing for upload and playback.</span></div>
            </div>
          </article>

          <article class="home-project-card">
            <a class="home-project-title" href="./toy-projects/restaurant-agent/">Restaurant ReAct Agent</a>
            <p>A FastAPI-based AI agent that interprets location, price, and context, then calls search and filtering tools for explainable restaurant recommendations.</p>
            <div class="home-project-highlights">
              <div><img src="./toy-projects/restaurant-agent/featured.png" alt="Restaurant query"><strong>Restaurant Query</strong><span>Extracts area and preference conditions from natural-language requests.</span></div>
              <div><img src="./toy-projects/restaurant-agent/detail-result.png" alt="Search tool"><strong>Search Tool</strong><span>Uses Kakao Local API and a sample dataset to search candidate restaurants.</span></div>
              <div><img src="./toy-projects/restaurant-agent/detail-trace.png" alt="Filtering and recommendation"><strong>Filtering & Recommendation</strong><span>Reflects price, context, and review conditions to produce explainable recommendations.</span></div>
            </div>
          </article>
        </div>
    design:
      columns: '1'

  - block: markdown
    content:
      title: Career & Awards
      subtitle:
      text: |
        <div class="home-project-grid">
          <article class="home-project-card">
            <a class="home-project-title" href="./contest-projects/speech-coach/">SpeakUp (AI&SW Competition Bronze Prize)</a>
            <p>An AI coaching service for presentations, interviews, and negotiation practice, centered on real-time feedback and session reports.</p>
            <div class="home-project-highlights">
              <div><img src="./contest-projects/speech-coach/featured.png" alt="Real-time coaching"><strong>Real-time Coaching</strong><span>Analyzes speaking speed, fillers, silence, and other signals during practice.</span></div>
              <div><img src="./contest-projects/speech-coach/detail-dashboard.png" alt="Session dashboard"><strong>Session Dashboard</strong><span>Collects practice records and metrics to show improvement over time.</span></div>
              <div><img src="./contest-projects/speech-coach/detail-ai.png" alt="AI report"><strong>AI Report</strong><span>Summarizes next-step improvements from transcript and attention segments.</span></div>
            </div>
          </article>
          <article class="home-project-card">
            <a class="home-project-title" href="./contest-projects/jeonbuk-chatbot/">Jeonbuk Voice Chatbot (Governor Citation)</a>
            <p>A public-service project combining voice conversation and a character UI to help residents find policy and civil-service information.</p>
            <div class="home-project-highlights">
              <div><img src="./contest-projects/jeonbuk-chatbot/featured.png" alt="Character chatbot"><strong>Character Chatbot</strong><span>Used a character-based UI to make public information feel more approachable.</span></div>
              <div><img src="./contest-projects/jeonbuk-chatbot/detail-avatar.png" alt="Voice conversation"><strong>Voice Conversation</strong><span>Focused on letting residents ask for information conversationally.</span></div>
              <div><img src="./contest-projects/jeonbuk-chatbot/detail-public.png" alt="Public service UX"><strong>Public Service UX</strong><span>Organized response flows to explain policy and civil-service information clearly.</span></div>
            </div>
          </article>
        </div>
    design:
      columns: '1'

  - block: markdown
    content:
      title:
      subtitle:
      text: |
        {{% cta cta_link="./contact/" cta_text="Contact ->" %}}
    design:
      columns: '1'
---
