# Stage 05 — Data Quality Monitoring & Reporting

## Overview

Stage 05 focuses on monitoring data quality across validation runs.

While the previous stages focused on profiling data, assessing quality, identifying findings, and defining validation rules, this stage introduces monitoring to track how data quality changes between different validation runs.

The main objective is to move from a one-time quality assessment toward an ongoing data quality monitoring approach.

---

## Objective

The objectives of this stage are to:

- Track data quality validation runs over time.
- Record key quality metrics for each run.
- Compare current results with previous runs.
- Detect changes in overall data quality.
- Identify failed data quality rules.
- Produce monitoring summaries and reports.

---

## Monitoring Concept

The monitoring process follows this flow:

```text
Dataset
   ↓
Data Quality Rules
   ↓
Validation Framework
   ↓
Validation Results
   ↓
Monitoring Log
   ↓
Quality Trend
   ↓
Monitoring Report
