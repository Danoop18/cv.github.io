---
title: Automated Patient Registration Tool
summary: Web automation tool that handles bulk patient registration and sample labeling for corporate testing campaigns, saving over 6 hours of manual data entry per session and eliminating labeling errors.
tags:
  - JavaScript
  - Web Automation
  - Patient Registration
categories:
  - Engineering
date: '2024-03-01T00:00:00Z'
metric: "Saves over 6 hours of manual registration per corporate testing session and eliminates user labeling errors"
---

### Problem

Corporate testing campaigns required registering large lists of patients and printing labeled sample containers in a short time window. Doing this manually through the existing web-based system was slow, error-prone, and tied up staff for hours during collection events. A single typo in a patient record or a mislabeled container had downstream consequences for sample identification.

### What was built

A web automation tool that processes patient lists in batch and interacts with the registration system automatically — filling forms, submitting records, and triggering label generation without manual entry for each individual patient.

### Technology

- **JavaScript**: Client-side scripting and DOM interaction for form automation.
- **Web automation**: Automated form filling, record submission, and label triggering against the existing web interface.

### How it works

1. A patient list is prepared (name, ID, service type) and loaded into the tool.
2. The automation iterates through the list, fills the registration form for each patient, submits the record, and triggers label generation.
3. The process runs continuously without manual intervention until the full batch is complete.

### Result

- **Metric**: Saves over 6 hours of manual registration per corporate testing session and eliminates user labeling errors.
- **Impact**: Staff redirected from data entry to patient-facing tasks during collection events. The risk of patient-label mismatches due to manual input errors was eliminated for the automated portion of the process.

### Evidence

- Tool in active use for corporate testing campaigns at Hospital MAC.
