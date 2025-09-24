---
# Leave the homepage title empty to use the site title
title: ''
date: 2022-10-24
type: landing

design:
  # Default section spacing
  spacing: '6rem'

sections:
  - block: resume-biography-3
    content:
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: admin
      text: ''
      # Show a call-to-action button under your biography? (optional)
      button:
        text: Download CV
        url: uploads/resume.pdf
      headings:
        about: ''
        education: ''
        interests: ''
    design:
      # Apply custom background image
      css_class: hero-section
      # Avatar customization
      avatar:
        size: medium # Options: small (150px), medium (200px, default), large (320px), xl (400px), xxl (500px)
        shape: circle # Options: circle (default), square, rounded
  - block: markdown
    content:
      title: '📚 My Research'
      subtitle: ''
      text: |-
        I am an atmospheric scientist with expertise in remote sensing, climate modeling, and hydrological hazards. My research focuses on understanding atmospheric moisture dynamics, particularly elevated moist layers, and their representation in satellite observations and climate models.

        Currently, I'm working as a postdoctoral researcher at Princeton University and NOAA-GFDL, where I investigate the relationship between extreme precipitation and river flood changes under warming conditions. I'm also contributing to high-resolution land surface model inter-comparison projects and implementing orographic disaggregation schemes for precipitation.

        My work bridges fundamental atmospheric science with applied climate research, helping us better understand and predict hydrological hazards in a changing climate.

        Please reach out to collaborate on atmospheric science, climate modeling, or remote sensing projects! 🌦️
    design:
      columns: '1'
  - block: collection
    id: papers
    content:
      title: Featured Publications
      filters:
        folders:
          - publications
        featured_only: true
    design:
      view: article-grid
      columns: 2
  - block: collection
    content:
      title: Recent Publications
      text: ''
      filters:
        folders:
          - publications
        exclude_featured: false
    design:
      view: citation
---
