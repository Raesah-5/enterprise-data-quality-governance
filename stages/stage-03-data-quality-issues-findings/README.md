# Stage 03 — Data Quality Issues & Findings

## 🎯 Objective

The objective of this stage was to analyze and interpret the results from the Data Quality Assessment performed in Stage 02.

The focus was not only on identifying violations, but also on understanding the difference between:

* Data quality violations
* Data standardization observations
* Data quality limitations
* Findings that require additional business context

---

# 🔎 From Assessment to Findings

Stage 02 produced a final result of:

```text
15 Data Quality Rules
0 Violations
100% Quality Rate
PASS
```

At first, this result raised an important question:

> If no quality rules failed, does that mean there are no data quality findings?

Further analysis showed that the answer is not necessarily.

The profiling stage had already identified some data standardization observations that needed to be interpreted separately from the formal rule violations.

---

# Finding 01 — Income Level Standardization

## Observation

The original dataset contained:

```text
LOW
```

while the standardized value was:

```text
Low
```

The difference is related to capitalization and representation rather than missing data.

### Standardization

```python
df["income_level"] = df["income_level"].replace({
    "LOW": "Low"
})
```

### Before

```text
High
LOW
Medium
```

### After

```text
High
Low
Medium
```

### Classification

**Consistency / Standardization Observation**

This observation was addressed before the final quality assessment.

---

# Finding 02 — Location Standardization

## Observation

The original dataset contained:

```text
Chennal
```

instead of:

```text
Chennai
```

### Standardization

```python
df["location"] = df["location"].replace({
    "Chennal": "Chennai"
})
```

### Before

```text
Chennal
```

### After

```text
Chennai
```

### Classification

**Consistency / Standardization Observation**

This was treated as a data standardization issue rather than a confirmed business-level accuracy error.

---

# 📊 Findings vs. Quality Violations

An important distinction was established during this stage.

| Type                        | Example                                  | Interpretation               |
| --------------------------- | ---------------------------------------- | ---------------------------- |
| Quality Violation           | Missing required value                   | Fails a defined rule         |
| Standardization Observation | `LOW` → `Low`                            | Representation inconsistency |
| Standardization Observation | `Chennal` → `Chennai`                    | Naming inconsistency         |
| Accuracy Limitation         | Unknown whether age is factually correct | Requires external source     |
| Timeliness Limitation       | Unknown whether data is up to date       | Requires business metadata   |

This distinction prevents every observation from being automatically classified as a data quality failure.

---

# 🧠 Important Learning

One of the most important lessons from this project was understanding that **a data quality project does not need to produce a large number of errors to be successful**.

Initially, it may seem that a data quality analysis should identify many problems.

However, the purpose of data quality assessment is to measure the data against clearly defined requirements.

If the defined rules produce:

```text
0 Violations
100% Quality Rate
```

then that is a valid result.

The analyst should document the result rather than create or exaggerate problems simply to produce findings.

---

# Accuracy Cannot Be Confirmed From the Dataset Alone

The project did not have an external source of truth.

Therefore, some values could not be assessed for factual accuracy.

For example:

```text
customer_id = 10001
age = 35
```

The dataset can tell us that the value is:

* Present
* Numeric
* Within the defined range

But it cannot independently confirm that the customer's actual age is 35.

Therefore, the **Validity** of the value can be assessed based on the defined rule, while its **Accuracy** requires an appropriate reference source.

---

# Timeliness Cannot Be Confirmed From the Dataset Alone

The dataset contains signup dates, but this does not automatically tell us whether the data is sufficiently current for a business process.

Timeliness would require information such as:

* Expected data refresh frequency
* Data update schedule
* Acceptable data latency
* Business requirements

Because this information was not available, Timeliness was not included in the formal assessment.

---

# 📌 Findings Summary

| Finding                | Type                          | Action                      |
| ---------------------- | ----------------------------- | --------------------------- |
| `LOW` vs `Low`         | Consistency / Standardization | Standardized                |
| `Chennal` vs `Chennai` | Consistency / Standardization | Standardized                |
| Accuracy               | Assessment Limitation         | Requires external reference |
| Timeliness             | Assessment Limitation         | Requires business metadata  |

---

# 🔗 Relationship With Stage 02

The findings from this stage were based on the results and observations from:

**Stage 02 — Data Quality Assessment**

The assessment established the measurable quality result, while this stage focused on interpreting what those results mean.

```text
Stage 02
Data Quality Assessment
        ↓
Measured Results
        ↓
Stage 03
Findings & Interpretation
```

---

# 🧠 Key Takeaways

### 1. Not every observation is a violation

A standardization issue may exist without causing a formal quality rule failure.

### 2. Data quality must be measurable

Quality conclusions should be supported by defined rules and validation logic.

### 3. Accuracy requires a source of truth

The dataset cannot always validate its own factual correctness.

### 4. Business context matters

Some quality dimensions cannot be evaluated without understanding the business requirements.

### 5. A clean result is still a result

A 100% quality rate can be a legitimate outcome when the assessment is based on appropriate and measurable rules.

---

# ✅ Conclusion

Stage 03 provided the interpretation layer between technical validation and broader Data Quality understanding.

The project identified two standardization observations:

```text
LOW → Low
Chennal → Chennai
```

while the formal Data Quality Assessment resulted in:

```text
15 Rules
0 Violations
100% Quality Rate
PASS
```

The stage also established important assessment limitations around Accuracy and Timeliness.

These findings provide the foundation for **Stage 04 — Data Quality Rules & Validation Framework**, where the quality rules and validation process are structured into a reusable framework.
