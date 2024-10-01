---
# Display name
title: 황선우

# Is this the primary user of the site?
superuser: true

# Role/position
role: '백엔드/게임 개발'

# Status emoji
status:
  icon: ☕️

# Organizations/Affiliations
#organizations:
#- name: 腾讯
#  url: ""

# Short bio (displayed in user profile at end of posts)
bio: 게임, 웹을 개발하고 있습니다.

#interests:
#- Artificial Intelligence
#- Computational Linguistics
#- Information Retrieval

#education:
#  courses:
#  - course: PhD in Artificial Intelligence
#    institution: Stanford University
#    year: 2012
#  - course: MEng in Artificial Intelligence
#    institution: Massachusetts Institute of Technology
#    year: 2009
#  - course: BSc in Artificial Intelligence
#    institution: Massachusetts Institute of Technology
#    year: 2008

# Social/Academic Networking
# For available icons, see: https://docs.hugoblox.com/getting-started/page-builder/#icons
#   For an email link, use "fas" icon pack, "envelope" icon, and a link in the
#   form "mailto:your-email@example.com" or "#contact" for contact widget.
social:
  - icon: envelope
    icon_pack: fas
    link: 'about/#contact' # For a direct email link, use "mailto:test@example.org".
# Uncomment below for Github link
#- icon: github
#  icon_pack: fab
#  link: https://github.com/gcushen

# Link to a PDF of your resume/CV from the About widget.
# To enable, copy your resume/CV to `static/files/cv.pdf` and uncomment the lines below.
# - icon: cv
#   icon_pack: ai
#   link: files/cv.pdf

# Enter email to display Gravatar (if Gravatar enabled in Config)
#email: ""
---
---
title: My page
type: landing

sections:
  - block: slider
    content:
      slides:
        - title: 👋 Welcome to the group
          content: Take a look at what we're working on...
          align: center
          background:
            image:
              # Specify an image from `assets/media/`
              # or delete the image section to remove it
              filename: coders.jpg
              filters:
                brightness: 0.7
            position: right
            color: '#666'
        - title: Lunch & Learn ☕️
          content: 'Share your knowledge with the group and explore exciting new topics together!'
          align: left
          background:
            image:
              # Specify an image from `assets/media/`
              # or delete the image section to remove it
              filename: contact.jpg
              filters:
                brightness: 0.7
            position: center
            color: '#555'
        - title: World-Class Semiconductor Lab
          content: 'Just opened last month!'
          align: right
          background:
            image:
              # Specify an image from `assets/media/`
              # or delete the image section to remove it
              filename: welcome.jpg
              filters:
                brightness: 0.5
            position: center
            color: '#333'
          link:
            icon: graduation-cap
            icon_pack: fas
            text: Join Us
            url: ../contact/
    design:
      # Slide height is automatic unless you force a specific height (e.g. '400px')
      slide_height: ''
      # Make the slides full screen within the browser window?
      is_fullscreen: true
      # Automatically transition through slides?
      loop: false
      # Duration of transition between slides (in ms)
      interval: 2000
---

Alice Wu is a professor of artificial intelligence at the Stanford AI Lab. Her research interests include distributed robotics, mobile computing and programmable matter. She leads the Robotic Neurobiology group, which develops self-reconfiguring robots, systems of self-organizing robots, and mobile sensor networks.

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed neque elit, tristique placerat feugiat ac, facilisis vitae arcu. Proin eget egestas augue. Praesent ut sem nec arcu pellentesque aliquet. Duis dapibus diam vel metus tempus vulputate.

{{< icon name="download" pack="fas" >}} {{< staticref "uploads/resume.pdf" "newtab" >}}Download{{< /staticref >}} my resumé as a PDF.
