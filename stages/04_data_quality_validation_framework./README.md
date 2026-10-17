# Stage 04 --- Data Quality Validation Framework

## Objective

This stage turns the Data Quality checks defined in earlier stages into
a reusable Python validation framework. A structured rule catalog stores
the rules, while a shared validation function evaluates each rule and
produces standardized results.

## What This Stage Covers

-   A catalog of 15 Data Quality rules (`DQ001`--`DQ015`).
-   Validation checks across Completeness, Uniqueness, Validity, and
    Consistency.
-   A reusable `validate_data()` function.
-   Rule-level results including total records, violations, valid
    records, quality rate, and `PASS` / `FAIL` status.
-   A view of failed rules and a final validation summary.

## Validation Workflow

**Dataset → Rule Catalog → Validation Logic → Rule Results → Quality
Summary**

The Python implementation and its execution outputs are in
[`04_data_quality_validation_framework.ipynb`](04_data_quality_validation_framework.ipynb).

## Reported Result

For the standardized dataset used in this project, the notebook reports:

-   **15 Data Quality rules**
-   **0 violations**
-   **100% quality rate**
-   **Overall status: PASS**

These results apply to the dataset and validation logic used for this
project run. The notebook should be rerun if the dataset or rules
change.

## Important Notes

-   The rule catalog documents the intended checks; the implementation
    in the notebook determines how each rule is actually evaluated.
-   Rule-level violation counts can overlap when one record fails more
    than one rule. Therefore, summing valid records across rules does
    not represent the number of unique valid records.
-   This stage provides the technical foundation for the monitoring work
    in Stage 05.
