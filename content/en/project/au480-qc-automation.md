---
title: AU480 QC Data Automation
summary: Python automation system using Selenium and Pandas to extract, clean, and structure quality control data from Beckman Coulter AU480 clinical analyzers — eliminating repetitive manual handling.
tags:
  - Python
  - Selenium
  - Pandas
  - Clinical QC
  - Automation
categories:
  - Engineering
date: '2023-06-01T00:00:00Z'
aliases:
  - /project/bioinformatics-analyzer/
metric: "Processes weekly batches with over 100 analytes per day in approximately 1 hour"
---

### Problem

QC data from the AU480 clinical analyzer required manual extraction and handling across multiple sessions each week. The process was repetitive, error-prone, and made it difficult to track analyzer performance consistently over time. Any variation in manual handling introduced noise that obscured real QC trends.

### What was built

A Python automation system that connects to the analyzer data source via Selenium, extracts raw QC records, and processes them through a Pandas pipeline to produce clean, structured outputs ready for review and performance monitoring.

### Technology

- **Python**: Core scripting and data processing logic.
- **Selenium**: Automated interaction with the data extraction interface.
- **Pandas**: Data cleaning, normalization, and structured output generation.

### How it works

1. Selenium initiates an automated session and retrieves raw QC records from the AU480 data interface.
2. Records are loaded into a Pandas DataFrame and cleaned: inconsistent formats are normalized, duplicate entries removed, and expected fields validated.
3. The pipeline outputs structured tables ready for QC review and trend analysis without manual reformatting.

### Result

- **Metric**: Processes weekly batches with over 100 analytes per day in approximately 1 hour.
- **Impact**: Eliminated repetitive manual data handling. QC monitoring became consistent and reproducible — the same process runs the same way every week, regardless of who is doing it.

### Evidence

- Implementation in use at Hospital MAC clinical laboratory.
- Code maintained in private repository.
