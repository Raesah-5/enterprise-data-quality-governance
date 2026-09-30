# Stage 01 — Data Profiling

## 🎯 Objective

The objective of this stage was to understand the structure and characteristics of the Customer 360 dataset before performing formal data quality assessment.

The profiling focused on:

* Dataset dimensions
* Data types
* Missing values
* Duplicate records
* Unique identifiers
* Numerical distributions
* Categorical distributions
* Date ranges

---

## 📊 Dataset Structure

The dataset contains:

* **100,000 records**
* **6 columns**

| Column         | Data Type         | Description                |
| -------------- | ----------------- | -------------------------- |
| `customer_id`  | Integer           | Customer identifier        |
| `age`          | Integer           | Customer age               |
| `gender`       | Object            | Customer gender            |
| `location`     | Object            | Customer location          |
| `income_level` | Object            | Customer income category   |
| `signup_date`  | Object → Datetime | Customer registration date |

---

## 🔎 Profiling

### Load Dataset

```python
import pandas as pd

df = pd.read_csv("customers.csv")

df.head()
```

### Dataset Dimensions

```python
df.shape
```

Result:

```text
(100000, 6)
```

### Data Types

```python
df.info()
```

---

## Missing Values

```python
df.isnull().sum()
```

No missing values were identified across the dataset.

---

## Duplicate Records

```python
df.duplicated().sum()
```

Result:

```text
0
```

No full duplicate records were identified.

---

## Customer ID Uniqueness

```python
df["customer_id"].nunique()
```

Result:

```text
100000
```

The number of unique customer IDs equals the total number of records, making `customer_id` a strong candidate for a primary key.

---

## Age Profiling

```python
df["age"].describe()
```

Observed age range:

```text
18 – 69
```

---

## Gender Distribution

```python
df["gender"].value_counts()
```

Result:

```text
Male      50120
Female    49880
```

---

## Income Level Distribution

```python
df["income_level"].value_counts()
```

Original values included:

```text
High      33560
LOW       33423
Medium    33017
```

An inconsistency in capitalization was identified between `LOW` and the standardized form `Low`.

---

## Location Distribution

```python
df["location"].value_counts()
```

Original values included:

```text
Mumbai       16859
Bangalore    16669
Chennal      16668
Hyderabad    16634
Kolkata      16603
Delhi        16567
```

An apparent naming inconsistency was identified:

```text
Chennal
```

instead of:

```text
Chennai
```

---

## Signup Date

```python
df["signup_date"] = pd.to_datetime(df["signup_date"])

df["signup_date"].min(), df["signup_date"].max()
```

Result:

```text
2017-01-01 → 2025-01-01
```

---

# 📌 Key Findings

The profiling stage established the baseline characteristics of the dataset.

### Findings

* 100,000 records and 6 columns
* No missing values identified
* No full duplicate records identified
* `customer_id` contains 100,000 unique values
* `age` ranges from 18 to 69
* `signup_date` ranges from 2017-01-01 to 2025-01-01
* Standardization observations were identified in `income_level` and `location`

---

# ✅ Conclusion

The dataset was successfully profiled and its main structural characteristics were documented.

The findings from this stage were used to define the Data Quality Rules in **Stage 02 — Data Quality Assessment**.
