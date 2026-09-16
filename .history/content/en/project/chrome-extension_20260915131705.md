---
title: Automated Patient Registration Tool
summary: A web automation tool that manages batch patient registration and sample labeling during corporate health screenings, saving over 8 hours of manual data entry per session and eliminating name and labeling errors.
tags:
- JavaScript
- Web Automation
- Patient Registration
image:
  filename: /proyectos/extension_portada.png
  focal_point: Smart
  preview_only: false
  all_text: "HTML format for the batch clinical record extension cover sheet."
categories:
  - Engineering
date: '2024-03-01T00:00:00Z'
metric: "Ahorra más de 8 horas de registro manual por sesión en tomas empresariales y elimina errores de registro en datos personales y etiquetado"
---

### Problem

Corporate sample collection events require registering and labeling over 100 samples within a short timeframe. Performing this manually via the existing web-based LIMS was slow, lacked bulk upload capabilities, and was prone to errors; furthermore, it tied up staff, the label printer, and terminals for hours during each event. A typo in a person's record or a mislabeled container resulted in a loss of sample traceability, delays for corrections, and the erroneous mixing of personal data.

### What Was Built

A web automation tool that processes patient lists in batches and automatically interacts with the registration system: it fills out forms, submits records, and triggers label generation without requiring manual data entry for each patient.

### Technology

- **JavaScript**: DOM interaction to automate form filling, record submission, and label activation within the existing LIMS web interface.
- **Web Automation**: Automated form filling, record submission, and label activation on the existing web interface.

### How It Works

1. A patient list (name, date of birth, required tests, ID, gender) is prepared and loaded into the tool.
2. The automation iterates through the list, performs checks against the LIMS database, fills out the registration form for each patient, submits the record, and triggers label generation.
3. The process runs continuously without manual intervention until the batch is complete.

### Results

- **Metric**: Saves over 8 hours of manual registration time per corporate collection session and eliminates labeling errors caused by manual data entry. By using a single terminal running in the background, the technician is free to interact with a second session or attend to patients while the process runs.

- **Impact**: Staff are redirected from data entry to direct patient care during collection events. The risk of patient-label mismatches due to data entry errors is eliminated within the automated portion of the process.

### Evidence

- Tool currently in active use for corporate collection events at Hospital MAC.