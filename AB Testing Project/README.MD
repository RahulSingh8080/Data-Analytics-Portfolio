# 📊 A/B Testing Project

**Author**: Rahul Singh  
**Dataset**: [AB_dataset.csv from Kaggle]
**Language**: Python

---

## 📁 Project Overview

This project focuses on evaluating whether a **new landing page** leads to better conversion rates than an **old landing page** using an A/B testing framework. The goal is to make a data-driven decision by applying **hypothesis testing**, specifically a **Two-Proportion Z-Test**.

---

## 📚 Table of Contents

1. [Data Overview](#data-overview)
2. [Cleaning and Preprocessing](#cleaning-and-preprocessing)
3. [Exploratory Data Analysis](#exploratory-data-analysis)
4. [Hypothesis Testing](#hypothesis-testing)
5. [Key Findings](#key-findings)
6. [How to Run](#how-to-run)
7. [License](#license)

---

## 📊 Data Overview

- **Source**: Kaggle A/B Testing dataset
- **Total Records**: 294,478
- **Columns**:
  - `user_id`
  - `timestamp`
  - `group` — control or treatment
  - `landing_page` — old_page or new_page
  - `converted` — 1 if user converted, else 0

---

## 🧹 Cleaning and Preprocessing

- Removed mismatched records (e.g., treatment group seeing old_page)
- Dropped duplicate user IDs (to ensure independent records)
- Converted timestamp column to datetime format
- Final dataset shape: `290,584 rows × 5 columns`

---

## 📈 Exploratory Data Analysis

- Grouped and visualized conversions for control vs treatment
- Added `day` column for optional time-based trends
- Plotted:
  - Bar chart for conversions by group
  - Pie chart to compare conversion percentage distribution

**Observations**:
- Control group conversion rate ≈ **12.04%**
- Treatment group conversion rate ≈ **11.88%**

---

## 🧪 Hypothesis Testing – Two-Proportion Z-Test

### 🎯 Goal

To determine if the **new landing page** performs significantly better than the old one in terms of user conversion.

### 🧾 Hypotheses

- **Null (H₀)**: Conversion rate of old_page = Conversion rate of new_page
- **Alternative (H₁)**: Conversion rates are not equal

### ✅ Why Z-Test?

- Comparing proportions between two independent groups
- Binary outcome (converted = 0 or 1)

### 🔍 Results

- **Z-statistic**: `1.31`
- **p-value**: `0.189`

**Interpretation**: Since `p > 0.05`, we fail to reject the null hypothesis.

---

## 📌 Key Findings

- The **new page** does not lead to a **statistically significant improvement** in conversion rate.
- Even though the control group showed slightly better results, the difference is not enough to recommend a change.

> 📢 **Takeaway**: Don't rely on gut feelings — use statistical testing to support product decisions.

---

## 🛠️ How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/rahulsinghdatascience/ab-testing-math.git
   cd ab-testing-math
