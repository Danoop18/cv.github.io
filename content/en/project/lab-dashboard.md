---
title: Clinical Laboratory KPI Dashboard & Digital Logbook
summary: Streamlit-based digital logbook and KPI dashboard that replaced multi-user manual record entry, making laboratory data searchable and comparable in real time.
tags:
  - Python
  - Streamlit
  - Pandas
  - KPIs
  - Digital Logbook
categories:
  - Engineering
date: '2024-01-01T00:00:00Z'
metric: "Fully digital logbook system — eliminates manual multi-user entry and accelerates record lookup and cross-referencing"
---

### Problem

Laboratory records were maintained across physical logbooks and disconnected spreadsheets updated by multiple staff members. Searching for a specific record meant going through pages manually. Cross-referencing across dates, analysts, or services was not feasible in daily operation. There was no single place to see what was happening across the lab on a given day.

### What was built

An interactive Streamlit application that serves as both a structured digital logbook and an operational KPI dashboard. Staff enter records through a form interface; the application stores, organizes, and displays the data in a way that makes lookup, filtering, and comparison immediate.

### Technology

- **Python**: Backend data logic and application structure.
- **Streamlit**: Web-based interactive interface for data entry and visualization.
- **Pandas**: Data structuring, filtering, and KPI aggregation.

### How it works

1. Laboratory staff enter records through a structured form in the web interface (service type, analyst, result, date, notes).
2. Entries are stored and indexed so that any record can be retrieved by date, analyst, or service without scrolling through physical pages.
3. The dashboard layer aggregates entries into operational KPIs: daily volume by service, QC pass rates, workload distribution across analysts.

### Result

- **Metric**: Fully digital logbook system — eliminates manual multi-user entry and accelerates record lookup and cross-referencing.
- **Impact**: The lab no longer runs parallel physical and digital records. Data entered once is immediately queryable. Decision-making based on operational trends became possible without manual report preparation.

### Evidence

- Deployed in the clinical laboratory at Hospital MAC.
- Code maintained in private repository.
