---
# Leave the homepage title empty to use the site title
title: ""
date: 2022-10-24
type: landing

design:
  # Default section spacing
  spacing: "6rem"

sections:
  - block: resume-biography-3
    content:
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: admin
      text: ""
      headings:
        about: Resumen Profesional
        education: Formación
        interests: Especialización
      button:
        url: /uploads/resume.pdf
        text: Descargar CV
    design:
      css_class: dark
      background:
        color: var(--hb-bg-color)
  - block: cta-button-list
    design:
      spacing:
        padding:
          top: "1rem"
          bottom: "1rem"
    content:
      buttons:
        - url: /es/projects/
          text: Proyectos de Ingeniería
          icon: rectangle-stack
        - url: /es/project/axolotl-regeneration-research/
          text: Track de Investigación
          icon: beaker
        - url: /es/personal-lab/
          text: Laboratorio Personal
          icon: cpu-chip
        - url: /uploads/resume.pdf
          text: Descargar CV
          icon: document-arrow-down
        - url: mailto:juan.hdz.9718@gmail.com
          text: Contactar
          icon: envelope
        - url: https://github.com/Danoop18
          text: GitHub
          icon: brands/github
        - url: https://www.linkedin.com/in/yeidan18
          text: LinkedIn
          icon: brands/linkedin
---
