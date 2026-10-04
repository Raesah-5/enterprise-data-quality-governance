# Data Quality Issue Management

## Purpose

Data Quality Issue Management provides a structured way to record, assign, track, resolve, and validate data quality issues.

This allows a failed data quality rule to become a managed issue rather than remaining only as a validation result.

## Issue Lifecycle

Data quality issues can move through the following lifecycle:

**Open → Assigned → In Progress → Resolved → Validated → Closed**

### Open

The issue has been identified and documented.

### Assigned

The issue has been assigned to the appropriate owner or responsible team.

### In Progress

Investigation or corrective action is taking place.

### Resolved

The corrective action has been completed.

### Validated

The data quality rule has been executed again to confirm that the issue has been resolved.

### Closed

The issue has been successfully resolved and validated.

## Issue Management Information

A Data Quality Issue should contain information such as:

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

## Corrective and Preventive Actions

### Corrective Action

The action taken to fix the existing data quality problem.

### Preventive Action

The action taken to reduce the likelihood of the same problem happening again.

For example, correcting an invalid value is a corrective action, while improving an input validation rule in the source system may be a preventive action.

## Validation Before Closure

An issue should not be considered closed only because a correction was made.

The related Data Quality Rule should be executed again to confirm that the issue has been resolved.

This connects Issue Management with the Validation and Monitoring processes developed in previous project stages.

## Project Limitation

The dataset does not provide actual organizational owners, business impact assessments, or source-system information.

Therefore, ownership, priority, and corrective actions in this project should be treated as an illustrative governance model rather than real organizational assignments.
