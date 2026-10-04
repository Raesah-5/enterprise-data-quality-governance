# Stage 06 — Data Quality Governance & Improvement

## Overview

The final stage of the project focuses on moving from Data Quality Monitoring to Data Quality Governance and Improvement.

Previous stages focused on identifying, validating, and monitoring data quality issues. This stage focuses on how identified issues can be managed, assigned, prioritized, resolved, and followed up.

---

## Objectives

This stage aims to:

- Understand the role of Data Quality Governance.
- Define Data Quality roles and responsibilities.
- Understand Data Ownership and Data Stewardship.
- Establish a basic Data Quality Issue Management process.
- Prioritize Data Quality Issues.
- Define corrective and preventive actions.
- Connect issue resolution with re-validation and monitoring.
- Establish a continuous Data Quality Improvement cycle.

---

## Governance Roles

The project uses a proposed governance model with the following roles:

| Role | Main Responsibility |
|---|---|
| Data Owner | Business accountability for the data and related decisions. |
| Data Steward | Operational management and follow-up of data quality. |
| Data Quality Analyst | Data analysis, validation, monitoring, and issue identification. |
| Technical Team | Technical investigation and implementation of required fixes. |

These roles represent a proposed governance model for the project and are not confirmed organizational assignments.

---

## Data Quality Issue Management

A failed Data Quality Rule can be converted into a managed Data Quality Issue.

The issue management lifecycle used in this project is:

**Open → Assigned → In Progress → Resolved → Validated → Closed**

A Data Quality Issue can contain:

- Issue ID
- Related Rule ID
- Issue Description
- Affected Data Element
- Priority
- Owner
- Status
- Corrective Action
- Validation Result
- Resolution Date

---

## Issue Prioritization

Data Quality Issues can be prioritized based on:

- Business Impact
- Data Impact
- Risk

The proposed priority levels are:

| Priority | Description |
|---|---|
| High | Significant business impact, critical data, or high risk. |
| Medium | Noticeable impact but no immediate high risk. |
| Low | Limited impact that can be handled through routine improvement. |

Because the project dataset does not contain business criticality or organizational risk information, these priorities are treated as an illustrative governance approach.

---

## Corrective and Preventive Actions

### Corrective Action

An action taken to fix an existing data quality problem.

### Preventive Action

An action taken to reduce the likelihood of the same problem occurring again.

For example:

> Corrective Action → Fix an invalid value.

> Preventive Action → Improve the source-system validation to prevent the invalid value from being entered again.

---

## Data Quality Improvement Cycle

The complete project workflow can be represented as:

**Profile → Assess → Validate → Monitor → Identify Issue → Assign → Improve → Re-validate → Monitor**

This connects Data Quality Management with Data Governance and creates a continuous improvement process.

---

## Connection to Previous Stages

| Stage | Focus |
|---|---|
| Stage 01 | Data Profiling |
| Stage 02 | Data Quality Assessment |
| Stage 03 | Data Quality Issues & Findings |
| Stage 04 | Data Quality Rules & Validation Framework |
| Stage 05 | Data Quality Monitoring & Reporting |
| Stage 06 | Data Quality Governance & Improvement |

The project therefore moves from understanding the data to assessing, validating, monitoring, and governing its quality.

---

## Project Limitations

The `customers.csv` dataset is a training dataset and does not provide:

- Actual Data Owners
- Actual Data Stewards
- Source-system ownership
- Business criticality
- Business impact assessments
- Organizational policies
- Reference sources for Accuracy
- Last Updated Date for Timeliness

Therefore, the governance roles, priorities, and responsibilities documented in this stage are presented as a proposed governance model rather than confirmed organizational information.

---

## Key Learning

The main lesson from this stage is that Data Quality is not only about detecting errors.

A failed Data Quality Rule is only the beginning.

A mature Data Quality process should be able to:

**Detect → Document → Assign → Prioritize → Improve → Validate → Monitor**

This creates a connection between Data Quality Management and Data Governance and supports continuous improvement over time.
