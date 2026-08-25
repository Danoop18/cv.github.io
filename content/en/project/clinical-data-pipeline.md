---
title: "Clinical Data Pipeline: From Excel/VBA to Python"
summary: "Evolution of a laboratory data workflow: starting with Excel/VBA macros to handle report consolidation, then rebuilt as a Python/Pandas pipeline for more reliable and maintainable data processing."
tags:
  - Python
  - Pandas
  - VBA
  - Excel
  - Data Pipeline
  - Reporting
categories:
  - Engineering
date: '2023-01-01T00:00:00Z'
---

### Problem

Laboratory records were consolidated manually from multiple spreadsheets each reporting cycle. The process relied on copy-paste operations, manual formula application, and format adjustments that were repeated from scratch every time. Errors accumulated silently, and tracing them back to their source was difficult.

### What was built

The workflow went through two stages. First, a set of Excel/VBA macros automated the most repetitive formatting and consolidation steps within the existing spreadsheet environment. As requirements grew and data volume increased, the process was rebuilt as a Python/Pandas pipeline that performs the same consolidation and cleaning in a more reliable, scriptable, and maintainable way.

### Technology

**Stage 1 — Excel/VBA:**
- Excel macros for format standardization and basic field consolidation across sheets.
- VBA scripting to automate repetitive manual steps without changing the spreadsheet-based workflow.

**Stage 2 — Python/Pandas:**
- Python scripts replace manual data assembly.
- Pandas for structured cleaning, validation, and transformation of multi-source records.

### How it works

1. Raw records from multiple files are loaded into a single processing context (spreadsheet or script, depending on the stage).
2. Formatting inconsistencies are detected and corrected: date formats, field naming, empty rows, and column mismatches.
3. Cleaned, validated data is written to a single output structured for operational reporting.

### Result

- **Impact**: Reduced manual error risk in report preparation. The transition from VBA to Python made the process easier to audit, modify, and hand off — the logic lives in code, not in cell references.
- The metric field for this project is qualitative: the value is in reproducibility and error reduction, not in a single measurable number.

### Evidence

- Both stages implemented at Hospital MAC.
- VBA macros and Python scripts maintained in private repository.
