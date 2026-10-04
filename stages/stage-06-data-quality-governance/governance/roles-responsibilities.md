# Data Quality Governance — Roles & Responsibilities

## Purpose

Data Quality Governance defines who is responsible for managing data quality and what each role is expected to do.

In this project, the roles are used as a proposed governance model to show how data quality responsibilities could be managed in a real organization.

## Roles

### Data Owner

The Data Owner is accountable for the data from a business perspective.

**Responsibilities:**

* Define business expectations for the data.
* Support decisions related to data quality.
* Approve important data quality policies or requirements.
* Ensure that data quality issues receive appropriate attention.

### Data Steward

The Data Steward manages data quality activities on an operational level.

**Responsibilities:**

* Monitor data quality issues.
* Review and coordinate issue resolution.
* Work with relevant teams to address data quality problems.
* Follow up on corrective actions.
* Support the maintenance of data quality rules.

### Data Quality Analyst

The Data Quality Analyst analyzes and evaluates data quality.

**Responsibilities:**

* Profile and analyze data.
* Define and execute data quality rules.
* Identify and document data quality issues.
* Monitor validation results.
* Report data quality findings.
* Support data quality improvement activities.

### Technical Team

The Technical Team supports technical changes required to resolve data quality problems.

**Responsibilities:**

* Investigate technical causes of data quality issues.
* Apply required system or data fixes.
* Support preventive actions when technical changes are needed.
* Confirm that technical changes have been implemented.

## Responsibility Matrix

| Activity                     | Data Owner        | Data Steward | Data Quality Analyst | Technical Team |
| ---------------------------- | ----------------- | ------------ | -------------------- | -------------- |
| Define business expectations | Responsible       | Support      | Support              | -              |
| Define data quality rules    | Approve / Support | Support      | Responsible          | Support        |
| Run data quality checks      | -                 | Support      | Responsible          | Support        |
| Identify quality issues      | -                 | Support      | Responsible          | Support        |
| Manage and follow up issues  | Support           | Responsible  | Support              | Support        |
| Approve important actions    | Responsible       | Support      | -                    | -              |
| Apply technical fixes        | -                 | Coordinate   | Support              | Responsible    |
| Re-validate after changes    | -                 | Support      | Responsible          | Support        |

## Project Limitation

The `customers.csv` dataset does not provide information about actual data owners, data stewards, source systems, or organizational responsibilities.

Therefore, the roles described in this document represent a **proposed governance model** for the project rather than confirmed organizational assignments.

This distinction is important because Data Governance should be based on documented responsibilities and organizational context rather than assumptions.
