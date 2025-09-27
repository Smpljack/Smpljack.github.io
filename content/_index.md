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
        I am an atmospheric scientist with expertise in the hydrological cycle and a particular interest in hydrological hazards, utilizing remote sensing and climate modeling. My doctoral research elucidated our ability to resolve vertical moisture structures in the atmosphere with [satellite observations  and reanalysis data](/publications/elevated-moist-layers-reanalysis/), and how the moisture structure couples to the [dynamics of precipitating convection](/publications/seasonal-emergence-moist-layers/). Besides analysing large and sparse datasets, I was fortunate to have had the opportunity of actively participating in the [EUREC4A field campaign](/publications/eurec4a-dataset/) on Barbados in 2020.

        My ongoing postdoctoral research revolves around hydrological extremes on the land surface. In my [recent pre-print](/publications/precipitation-streamflow-thermodynamics/) I used the GFDL climate model to shed light on the  relationship between extreme precipitation and river flood changes under a warming climate. I also implemented an orographic disaggregation scheme into the GFDL land model for downscaling precipitation and other meteorological fields to an advanced, machine-learning based sub-grid scheme, called [HydroBlocks](https://hess.copernicus.org/articles/22/3311/2018/). Currently, I am preparing simulations for a kilometer-scale land surface model inter-comparison project to examine the models' readiness for recent paradigm changing pushes to high resolution climate modeling.

        Please reach out to collaborate on atmospheric science, hydrological hazards, or remote sensing projects! 🌦️ 🛰 ️
        
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
