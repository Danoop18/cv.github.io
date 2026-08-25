---
title: Laboratory Report Consolidation Tool
summary: Python automation tool that consolidates weekly laboratory data from multiple Excel sources into a single clean output, reducing calculation errors, manual formatting, and saving over 8 hours of manual work per week.
tags:
  - Python
  - Excel
  - KPIs
  - Automation
  - Report Consolidation
categories:
  - Engineering
date: '2024-02-01T00:00:00Z'
metric: "Saves over 8 hours of manual work per week by semi-automating weekly KPI report generation"
---

### Problem

Weekly KPI reports required manually pulling data from multiple Excel files, applying formulas across sheets, and reformatting the output to match a standard layout — every week. The process was time-consuming, and any formula error or formatting deviation introduced inconsistencies that needed to be found and corrected before the report could be distributed.

### What was built

A Python automation tool that reads data from the source Excel files, consolidates records, applies the required calculations, and writes the output in a consistent, pre-formatted structure ready for review. The process that previously took hours of manual work runs in minutes.

### Technology

- **Python**: Core data processing logic and output generation.
- **Pandas / OpenPyXL**: Multi-file data loading, merging, calculation, and structured Excel output.
- **Excel**: Source data format and final report output format.

### How it works

1. Source files from the week are placed in the designated input directory.
2. The script loads and merges records from all files, validates field consistency, and applies the KPI calculations.
3. A clean, consistently formatted Excel report is written to the output directory, ready for review and distribution.

### Result

- **Metric**: Saves over 8 hours of manual work per week by semi-automating weekly KPI report generation.
- **Impact**: Calculation errors caused by manual formula entry were eliminated. Report format is now consistent every week regardless of who prepares it. Staff time is redirected from report assembly to analysis and decision-making.

### Evidence

- Tool in active use at Hospital MAC clinical laboratory.
- Code maintained in private repository.
