---
title: ''
summary: ''
date: 2026-08-25
type: landing

sections:
  - block: resume-biography-3
    content:
      username: me
      text: ''
      button:
        text: Download CV
        url: uploads/resume.pdf
      headings:
        about: About
        education: Education
        interests: Research Interests
    design:
      background:
        gradient_mesh:
          enable: true
      name:
        size: md
      avatar:
        size: medium
        shape: circle

  - block: markdown
    content:
      title: Research
      subtitle: ''
      text: |-
        I am interested in intelligent autonomous systems that can perceive, localise, reason about, and interact with the physical world. My current work focuses on semantic SLAM, visual place recognition, computer vision, and robust perception for autonomous systems.
    design:
      columns: '1'

  - block: collection
    id: projects
    content:
      title: Selected Projects
      text: Research and engineering projects across robotics, autonomy, computer vision, and machine learning.
      filters:
        folders:
          - projects
    design:
      view: article-grid
      columns: 2
---
