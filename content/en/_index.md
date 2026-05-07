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
        about: Professional Summary
        education: Education
        interests: Core Focus
      button:
        url: /uploads/resume.pdf
        text: Download CV
    design:
      css_class: dark
      background:
        color: var(--hb-bg-color)
  - block: cta-button-list
    content:
      buttons:
        - url: /projects/
          text: View Projects
          icon: rectangle-stack
        - url: /uploads/resume.pdf
          text: Download CV
          icon: document-arrow-down
        - url: mailto:juan.hdz.9718@gmail.com
          text: Contact Me
          icon: envelope
        - url: https://github.com/Danoop18
          text: GitHub
          icon: brands/github
        - url: https://www.linkedin.com/in/yeidan18
          text: LinkedIn
          icon: brands/linkedin
---
