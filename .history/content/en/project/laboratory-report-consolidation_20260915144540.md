---
title: Laboratory Report Consolidation Tool
summary: A Python automation tool that consolidates weekly data from multiple Excel sources into a clean, consistent output, reducing calculation and manual formatting errors while saving over 8 hours of manual work per week.
tags:
- Python
- Excel
- KPIs
- Automation
- Report Consolidation
image: 
  filename: /projects/registroQC_cover.png 
  focal_point: Smart 
  preview_only: false 
  all_text: "Web streamlit for registration in QC"
categories:
  - Engineering
date: '2024-02-01T00:00:00Z'
Metric: "Saves over 8 hours of manual work per week through the semi-automation of weekly KPI reporting."
---

### Problem

Weekly KPI reports required manually extracting data from multiple Excel files, applying formulas across worksheets, and reformatting the output to match a standard structure—every single week. The process was slow, and any formula error or formatting deviation introduced inconsistencies that had to be identified and corrected before the report could be distributed.

### What Was Built

A Python-based automation tool that reads data from source Excel files, consolidates records, performs the required calculations, and writes the output into a consistent, pre-formatted structure ready for review. A process that previously took hours of manual work now runs in minutes.

### Technology

- **Python**: Core logic for data processing and output generation.
- **Pandas / OpenPyXL**: Loading multiple files, merging data, performing calculations, and generating structured Excel output.
- **Excel**: Format for source data and the final report.

### How It Works

1. The week's source files are placed in the designated input directory.
2. The script loads and merges records from all files, validates field consistency, and applies KPI calculations.
3. A clean, consistently formatted Excel report is written to the output directory, ready for review and distribution.

### Results

- **Metric**: Saves over 8 hours of manual work per week through the semi-automation of weekly KPI reporting.
- **Impact**: Calculation errors caused by manual formula entry were eliminated. Report formatting is consistent every week, regardless of who prepares it. Staff time is redirected from report assembly to analysis and decision-making.

### Evidence

- Tool currently in active use at the Hospital MAC clinical laboratory.
- Code maintained in a private repository.

##
![Pagina Inicial](/uploads/QC_registrator/inicio.png)

![Pagina Configuración](/uploads/QC_registrator/Configurar.png)

![Motor trabajando](/uploads/QC_registrator/Registro.png)
