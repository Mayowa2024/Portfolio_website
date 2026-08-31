---
title: ''
summary: ''
date: 2026-08-25
type: landing

sections:
  - block: photo-ribbon
    id: formula-student-highlight
    content:
      title: Formula Student AI UK 2026 — 1st Overall
      project: /projects/formula-student-ai
      images:
        - file: trackside-engineering.jpeg
          alt: Track-side engineering on the autonomous Formula Student car
          priority: true
        - file: team-and-apc.jpeg
          alt: Oxford Brookes Racing Autonomous team with the APC vehicle
        - file: winning-team.jpeg
          alt: Formula Student AI UK 2026 winning team celebration
        - file: awards.jpeg
          alt: Mayowa Adebambo with the Formula Student AI trophies
        - file: mayowa-with-car.jpeg
          alt: Mayowa Adebambo beside the Formula Student vehicle
        - file: featured.jpeg
          alt: Oxford Brookes Racing Autonomous team with its awards
    design:
      spacing:
        padding: [1.25rem, 0, 1.5rem, 0]

  - block: resume-biography-3
    content:
      username: me
      text: ''
      button:
        text: Download CV
        url: uploads/Oluwamayowa_Adebambo_Robotics_CV_Experience_First.pdf
      headings:
        about: About
        education: Education
    design:
      background:
        gradient_mesh:
          enable: false
      name:
        size: md
      avatar:
        size: medium
        shape: circle

  - block: markdown
    id: research
    content:
      title: Research
      subtitle: ''
      text: |-
        I am interested in intelligent autonomous systems that can perceive, localise, reason about, and interact with the physical world. My current work focuses on semantic SLAM, visual place recognition, computer vision, and robust perception for autonomous systems.

        You can also read my [technical literature review of AI perception, safety, and deployment challenges in autonomous vehicles](/projects/ai-autonomous-vehicles-review/).
    design:
      columns: '1'

  - block: collection
    id: research-projects
    content:
      title: Research Projects
      count: 2
      filters:
        folders:
          - projects
        tag: Research
    design:
      view: article-grid
      columns: 2
      show_date: false

  - block: collection
    id: projects
    content:
      title: Projects
      text: My research and engineering projects across robotics, autonomy, computer vision, and machine learning.
      count: 6
      filters:
        folders:
          - projects
    design:
      view: article-grid
      columns: 2
      show_date: false
  - block: resume-experience
    content:
      username: me
    design:
      # Hugo date format
      date_format: 'January 2006'
      # Education or Experience section first?
      is_education_first: false
  - block: resume-skills
    content:
      title: Skills & Hobbies
      username: me
  - block: resume-awards
    content:
      title: Awards
      username: me
  - block: resume-languages
    content:
      title: Languages
      username: me
---
