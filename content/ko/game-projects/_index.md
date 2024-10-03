---
# Leave the homepage title empty to use the site title
title:
date: 2024-03-25
type: landing

sections:

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
          - swordplay/sword-motion
          - swordplay/hit-reaction
          - swordplay/shader
    design:
      view: community/custom_card
      columns: '2'

  - block: collection
    content:
      title: Gone
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
      page_type: gone
    design:
      view: community/custom_card
      columns: '2'
    advanced:
      css_style: "text-align: center;"
---