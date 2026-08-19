---
title: All Projects
date: 2026-08-19
type: landing
sections:
  - block: markdown
    content:
      title: All Projects
      text: |
        <p class="project-archive-intro">Projects are organized by their context. Select a category first, or review a representative set before opening the full list.</p>
        <div class="project-archive-switcher"><a href="../contest-projects/" class="project-archive-choice"><span class="project-archive-eyebrow">TEAM · AWARD · FIELD</span><strong>Team, Award & Field Projects</strong><small>Capstone, competition, company-linked, and Edge-AI field cases</small><b>View all →</b></a><a href="../toy-projects/" class="project-archive-choice"><span class="project-archive-eyebrow">PERSONAL · TECHNICAL</span><strong>Personal Projects</strong><small>Backend, AI, and Unity cases designed, built, and validated independently</small><b>View all →</b></a></div>
    design:
      columns: '1'
  - block: collection
    content:
      title: Team, Award & Field Projects
      text: Four representative cases. Use the selection above for the full list.
      count: 4
      offset: 0
      order: desc
      filters:
        folders: [contest-projects]
    design:
      view: community/custom_card
      columns: '2'
  - block: collection
    content:
      title: Personal Projects
      text: Four representative cases. Use the selection above for the full list.
      count: 4
      offset: 0
      order: desc
      filters:
        folders: [toy-projects]
    design:
      view: community/custom_card
      columns: '2'
---
