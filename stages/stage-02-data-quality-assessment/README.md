# Stage 02 — Data Quality Assessment

## 🎯 Objective

The objective of this stage was to move from descriptive data profiling to a structured and measurable **Data Quality Assessment**.

Instead of simply reviewing the dataset, specific Data Quality Rules were defined and used to measure the dataset against four selected quality dimensions:

* Completeness
* Uniqueness
* Validity
* Consistency

Accuracy and Timeliness were not included in the formal assessment because the project did not have sufficient external reference data or business metadata to measure these dimensions reliably.

---

# 📐 Data Quality Dimensions

## 1. Completeness

Checks whether required data is present and not missing.

Example:

```text
customer_id must not be NULL
```

---

## 2. Uniqueness

Checks whether values that should be unique contain duplicates.

Example:

```text
customer_id must be unique
```

---

## 3. Validity

Checks whether data values meet predefined rules, ranges, or allowed values.

Examples:

```text
Age must be between 18 and 69
```

```text
Gender must be Male or Female
```

---

## 4. Consistency

Checks whether data follows standardized values and formats.

Examples:

```text
LOW → Low
Chennal → Chennai
```

---

# 📋 Data Quality Rules

A total of **15 Data Quality Rules** were defined.

| Rule ID | Dimension    | Field          | Rule                                  |
| ------- | ------------ | -------------- | ------------------------------------- |
| DQ001   | Completeness | `customer_id`  | Must not contain NULL values          |
| DQ002   | Completeness | `age`          | Must not contain NULL values          |
| DQ003   | Completeness | `gender`       | Must not contain NULL values          |
| DQ004   | Completeness | `location`     | Must not contain NULL values          |
| DQ005   | Completeness | `income_level` | Must not contain NULL values          |
| DQ006   | Completeness | `signup_date`  | Must not contain NULL values          |
| DQ007   | Uniqueness   | `customer_id`  | Must be unique                        |
| DQ008   | Validity     | `age`          | Must be between 18 and 69             |
| DQ009   | Validity     | `gender`       | Must be Male or Female                |
| DQ010   | Validity     | `income_level` | Must be High, Medium, or Low          |
| DQ011   | Validity     | `location`     | Must belong to the approved locations |
| DQ012   | Validity     | `signup_date`  | Must contain valid dates              |
| DQ013   | Consistency  | `income_level` | Must use consistent capitalization    |
| DQ014   | Consistency  | `location`     | Must use standardized location names  |
| DQ015   | Consistency  | `signup_date`  | Must use a consistent date format     |

---

# 🧪 Quality Assessment Method

Each rule was evaluated using a standard result structure.

The assessment calculates:

```text
Valid Records = Total Records - Violations
```

and:

```text
Quality Rate = (Valid Records / Total Records) × 100
```

The status is determined based on the validation result.

---

# 💻 Validation Examples

## DQ001 — Customer ID Completeness

```python
violations = df["customer_id"].isnull().sum()
```

---

## DQ007 — Customer ID Uniqueness

```python
violations = df["customer_id"].duplicated().sum()
```

---

## DQ008 — Age Validity

```python
violations = ((df["age"] < 18) | (df["age"] > 69)).sum()
```

---

## DQ009 — Gender Validity

```python
allowed_gender = ["Male", "Female"]

violations = (~df["gender"].isin(allowed_gender)).sum()
```

---

## DQ010 — Income Level Validity

```python
allowed_income = ["High", "Medium", "Low"]

violations = (~df["income_level"].isin(allowed_income)).sum()
```

---

## DQ012 — Signup Date Validity

```python
df["signup_date"] = pd.to_datetime(
    df["signup_date"],
    errors="coerce"
)

violations = df["signup_date"].isnull().sum()
```

Using `errors="coerce"` allows invalid date values to be converted to `NaT`, making them measurable as validation violations.

---

# 📊 Quality Results

The assessment generated a `quality_results` structure containing:

```text
rule_id
dimension
field
total_records
violations
valid_records
quality_rate
status
```

Example:

```python
result = {
    "rule_id": "DQ001",
    "dimension": "Completeness",
    "field": "customer_id",
    "total_records": len(df),
    "violations": violations,
    "valid_records": len(df) - violations,
    "quality_rate": ((len(df) - violations) / len(df)) * 100,
    "status": "PASS" if violations == 0 else "FAIL"
}
```

---

# 📈 Final Assessment Result

After applying the defined Data Quality Rules and standardizing the identified values:

| Metric             |  Result |
| ------------------ | ------: |
| Total Records      | 100,000 |
| Data Quality Rules |      15 |
| Total Violations   |       0 |
| Quality Rate       |    100% |
| Overall Status     |    PASS |

All 15 defined rules passed the assessment.

---

# 🔎 Important Findings

Although the final assessment resulted in zero violations, the profiling stage identified two standardization observations:

### Income Level

```text
LOW → Low
```

### Location

```text
Chennal → Chennai
```

These observations were addressed through standardization and were treated separately from the final measured violations.

This distinction is important because an observation found during profiling is not automatically equivalent to a failed quality rule.

---

# ⚠️ Assessment Limitations

## Accuracy

Accuracy was not formally assessed.

Determining whether a value is factually correct requires an appropriate source of truth or trusted reference data.

For example, the dataset alone cannot confirm whether a customer's recorded age is actually their correct age.

---

## Timeliness

Timeliness was not formally assessed.

Measuring timeliness requires business context such as:

* Expected update frequency
* Data refresh schedule
* Acceptable data latency
* Business deadlines

This information was not available within the project scope.

---

# 🧠 Key Learning

A major lesson from this stage was that Data Quality Assessment should be based on **defined and measurable rules**.

The objective is not to find as many problems as possible.

Instead, the objective is to determine whether the data meets the defined quality requirements.

Therefore:

```text
15 Rules
0 Violations
100% Quality Rate
```

is a valid data quality result when supported by clearly defined rules and validation logic.

---

# ✅ Conclusion

Stage 02 established a measurable Data Quality Assessment framework for the Customer 360 dataset.

The assessment covered:

* Completeness
* Uniqueness
* Validity
* Consistency

A total of 15 Data Quality Rules were defined and evaluated.

The final assessment resulted in:

```text
100% Quality Rate
0 Violations
PASS
```

The results from this stage were then used as the foundation for **Stage 03 — Data Quality Issues & Findings**.
