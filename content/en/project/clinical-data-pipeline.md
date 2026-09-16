---
Title: "Clinical Data Pipeline: From Excel/VBA to Python"
Summary: "Evolution of a laboratory data workflow: starting with Excel/VBA macros for report consolidation and rebuilt as a Python/Pandas pipeline for more reliable and maintainable data processing."
Tags:
- Python
- Pandas
- VBA
- Excel
- Data Pipeline
- Reporting
image:
  filename: proyectos/Macros_formato.png
  focal_point: Smart
  preview_only: false
  all_text: "Representative image of the macro-enabled format used for the manual recording of weekly patient loads."
categories:
  - Engineering
date: '2023-01-01T00:00:00Z'
---

### Problem

Laboratory records were manually consolidated from multiple spreadsheets during each reporting cycle. The process relied on copy-paste operations, manual formula application, and formatting adjustments that had to be repeated from scratch every time. Errors accumulated unnoticed, and tracing their origins was difficult.

### What Was Built

The workflow evolved through two stages. First, a set of Excel/VBA macros automated the most repetitive formatting and consolidation steps within the existing spreadsheet environment. As requirements grew and data volume increased, the process was rebuilt as a Python/Pandas pipeline that performs the same consolidation and cleaning tasks more reliably, scriptably, and maintainably.

### Technology

**Stage 1 — Excel/VBA:**
- Excel macros for standardizing formats and performing basic field consolidation across sheets.
- VBA scripts to automate repetitive manual steps without altering the spreadsheet-based workflow.

{{< img src="uploads/Macros_formato.png" alt="cover macros application" >}}

**Stage 2 — Python/Pandas:**
- Python scripts replace manual data assembly.
- Pandas used for structured cleaning, validation, and transformation of records from multiple sources.

### How It Works

1. Raw records from multiple files are loaded into a single processing context (spreadsheet or script, depending on the stage).
2. Formatting inconsistencies are detected and corrected: date formats, field naming conventions, empty rows, and column misalignments.
3. A mapping is established between study codes and the common names used in reports to standardize the records.
4. Cleaned and validated data is written to a single, structured output file for operational reporting.

### Result

- **Impact**: Reduced risk of manual errors during report preparation. The transition from VBA to Python made the process easier to audit, modify, and transfer—since the logic resides in code rather than cell references. - The metric for this project is qualitative: the value lies in reproducibility and error reduction, not in a single measurable figure.

### Evidence

- Both stages implemented at Hospital MAC.
- VBA macros and Python scripts maintained in a private repository.


