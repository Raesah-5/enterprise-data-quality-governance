# Enterprise Data Quality & Governance Project

A practical data quality and governance project using Python and Pandas to assess, document, and improve the quality of customer data.

## 📌 Project Overview

This project demonstrates a structured approach to **Enterprise Data Quality & Governance** using a Customer 360 dataset.

The project moves through the following stages:

1. Data Profiling
2. Data Quality Assessment
3. Data Quality Issues & Findings
4. Data Quality Rules & Validation Framework

The goal is to understand the data, define measurable quality rules, assess the dataset against those rules, document findings, and establish a reusable validation approach.

---

## 🛠️ Tools & Technologies

* Python
* Pandas
* Jupyter Notebook
* GitHub
* Data Quality Dimensions
* Data Quality Rules
* Data Validation
* Data Governance Concepts

---

## 📊 Dataset

The project uses a Customer 360 dataset containing customer-level information.

### Dataset Information

| Attribute |   Value |
| --------- | ------: |
| Records   | 100,000 |
| Columns   |       6 |

### Columns

| Column         | Description                |
| -------------- | -------------------------- |
| `customer_id`  | Unique customer identifier |
| `age`          | Customer age               |
| `gender`       | Customer gender            |
| `location`     | Customer location          |
| `income_level` | Customer income category   |
| `signup_date`  | Customer registration date |

---

## 🗂️ Project Stages

| Stage    | Focus                                     | Status         |
| -------- | ----------------------------------------- | -------------- |
| Stage 01 | Data Profiling                            | ✅ Completed    |
| Stage 02 | Data Quality Assessment                   | ✅ Completed    |
| Stage 03 | Data Quality Issues & Findings            | ✅ Completed    |
| Stage 04 | Data Quality Rules & Validation Framework | 🔄 In Progress |

---

## 🔎 Stage 01 — Data Profiling

The first stage focused on understanding the structure and characteristics of the dataset.

Key activities included:

* Dataset dimensions
* Data types
* Missing values
* Duplicate records
* Unique identifiers
* Numerical distributions
* Categorical distributions
* Date validation

### Key Findings

* 100,000 records and 6 columns
* No missing values identified
* No full duplicate records identified
* `customer_id` contains 100,000 unique values
* `age` ranges from 18 to 69
* `signup_date` ranges from 2017-01-01 to 2025-01-01
* Standardization observations were identified in `income_level` and `location`

---

## 🧪 Stage 02 — Data Quality Assessment

The second stage moved from profiling to measurable data quality assessment.

Four quality dimensions were assessed:

* Completeness
* Uniqueness
* Validity
* Consistency

A total of **15 Data Quality Rules (DQ001–DQ015)** were defined.

### Assessment Result

| Metric             | Result |
| ------------------ | -----: |
| Data Quality Rules |     15 |
| Total Violations   |      0 |
| Quality Rate       |   100% |
| Overall Status     |   PASS |

The rules were implemented to measure specific quality requirements rather than relying on subjective statements such as "the data looks clean."

---

## 🔍 Stage 03 — Data Quality Issues & Findings

This stage focused on interpreting the results of the quality assessment.

Two standardization observations were identified:

### Income Level

The dataset contained:

```text
LOW
```

which was standardized to:

```text
Low
```

### Location

The dataset contained:

```text
Chennal
```

which was standardized to:

```text
Chennai
```

These observations were treated separately from the final measured quality violations.

### Important Learning

A key lesson from this stage was that a data quality project should not assume that the dataset must contain many problems.

If clearly defined and measurable quality rules result in:

```text
0 violations
100% quality rate
```

that is a valid finding.

The objective of data quality assessment is to measure the data against defined requirements, not to create problems simply to produce findings.

---

## ⚙️ Stage 04 — Data Quality Rules & Validation Framework

The fourth stage moves the project toward a reusable Data Quality Validation Framework.

The framework connects:

```text
Data
 ↓
Data Quality Rule
 ↓
Validation Logic
 ↓
Violation Count
 ↓
Quality Rate
 ↓
PASS / FAIL
```

The project uses a structured quality results model containing:

* Rule ID
* Quality Dimension
* Field
* Total Records
* Violations
* Valid Records
* Quality Rate
* Status

This structure allows quality checks to become repeatable and easier to monitor.

**Status:** In Progress

---

## 📋 Data Quality Dimensions

| Dimension    | Purpose                                                     |
| ------------ | ----------------------------------------------------------- |
| Completeness | Checks whether required data is present                     |
| Uniqueness   | Checks whether values that should be unique are duplicated  |
| Validity     | Checks whether values meet defined rules or ranges          |
| Consistency  | Checks whether data follows standardized formats and values |

Accuracy and Timeliness were not included in the formal assessment because the project did not have sufficient external reference data or business metadata to measure them reliably.

---

## 📈 Overall Project Journey

```text
Data Profiling
      ↓
Data Quality Assessment
      ↓
Issues & Findings
      ↓
Quality Rules
      ↓
Validation Framework
      ↓
Future Governance & Monitoring
```

---

## 🧠 Key Lessons

* Data profiling and data quality assessment are different activities.
* Data quality should be measured using explicit and documented rules.
* Not every data observation represents a quality violation.
* Accuracy requires an appropriate source of truth.
* Timeliness requires business expectations or metadata.
* A dataset can legitimately achieve 100% against its defined quality rules.
* Data governance extends beyond data cleaning into standards, ownership, rules, monitoring, and accountability.

---

## 📁 Repository Structure

```text
enterprise-data-quality-governance/
│
├── README.md
│
├── data/
│
├── notebooks/
│
├── stages/
│
├── quality-rules/
│
└── requirements.txt
```

---

## 🚀 Future Development

Future stages may extend the project toward:

* Data Governance
* Data Ownership
* Data Standards
* Data Quality KPIs
* Quality Monitoring
* Data Quality Dashboards
* Continuous Validation
* Data Governance Roles & Responsibilities

---

## 📚 References

The project uses external learning references to support the understanding of Data Quality and Data Governance concepts.

One of the references used during the project is a Data Quality reference from King Saud University.
