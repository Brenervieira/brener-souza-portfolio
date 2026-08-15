<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white">
  <img src="https://img.shields.io/badge/Factor%20Analysis-003B57?style=for-the-badge">
</p>

# 🎯 Purchase Behavior Factor Analysis

This project applies factor analysis to purchase behavior variables such as purchase frequency, average purchase value, preferred category, store tenure, and app usage.

The study evaluates whether the observed variables are suitable for factor analysis and uses adequacy tests to support latent-factor extraction.

---

## 📌 Business Problem

Retail and digital commerce teams often need to summarize customer behavior into fewer interpretable dimensions.

Instead of analyzing each behavior variable separately, factor analysis can reveal latent structures that support segmentation, customer profiling, and commercial strategy.

### 📈 Key Results

✅ Bartlett's test supported the use of factor analysis

✅ Global KMO reached approximately **0.9120**

✅ All individual KMO values were above **0.90**

✅ The dataset was considered suitable for factor analysis

✅ Rotation analysis was used to improve interpretability

---

## 💼 Business Impact

* Helps summarize purchase behavior into latent dimensions.
* Supports customer profiling and segmentation.
* Reduces analytical complexity when interpreting related behavior variables.
* Provides statistical evidence before applying factor extraction.
* Creates a foundation for business-oriented interpretation of customer behavior.

---

## 🎯 The Problem

Customer purchase behavior is measured through multiple related variables.

The challenge is to verify whether these variables share enough correlation structure to justify factor analysis and support latent-dimension interpretation.

---

## 🚀 Overview

Main question:

> Are purchase behavior variables sufficiently correlated to be summarized through factor analysis?

To answer this question, Bartlett's test, KMO analysis, and factor extraction were applied.

---

## 🧪 Approach

The project combines:

* Data loading
* Correlation adequacy assessment
* Bartlett's sphericity test
* Kaiser-Meyer-Olkin (KMO) test
* Factor analysis
* Rotation analysis
* Latent-factor interpretation

---

## 🎯 Objectives

* Evaluate whether the dataset is suitable for factor analysis.
* Apply Bartlett's test and KMO validation.
* Identify latent structures in purchase behavior variables.
* Improve interpretability through rotation.
* Support customer-behavior interpretation using fewer dimensions.

---

## 🧠 Methodology

### 🔹 1. Data Loading

The dataset was loaded from `data/dataset.csv` and inspected before factor-analysis validation.

---

### 🔹 2. Bartlett's Test

Bartlett's sphericity test was used to verify whether the correlation matrix was significantly different from an identity matrix.

---

### 🔹 3. KMO Test

The KMO test was used to evaluate sampling adequacy for factor analysis.

The global KMO was approximately **0.9120**, indicating strong adequacy.

---

### 🔹 4. Factor Analysis

Factor analysis was applied after validating the statistical assumptions.

---

### 🔹 5. Rotation

Rotation was evaluated to improve factor interpretability and support business-oriented conclusions.

---

## 📊 Analyses and Results

### 📌 KMO Results

| Metric | Result |
| :--- | ---: |
| Global KMO | 0.9120 |
| Minimum individual KMO | 0.9021 |
| Maximum individual KMO | 0.9197 |

**Insight**

The high KMO values indicate that the dataset has strong adequacy for factor analysis.

---

## 🤖 Validation

The use of factor analysis was validated through:

* Bartlett's sphericity test
* Global KMO
* Individual KMO values
* Interpretation of factor structure

---

## 🧠 Main Findings

* The variables showed sufficient shared structure for factor analysis.
* Purchase frequency, average value, category preference, store tenure, and app usage can be studied as related indicators.
* The high KMO values support latent-factor extraction.
* Factor analysis can reduce complexity in purchase-behavior interpretation.

---

## 🚀 Project Highlights

* 🔥 Statistical validation before factor extraction.
* 📊 KMO analysis used to evaluate sampling adequacy.
* 🧠 Factor analysis applied to customer purchase behavior.
* 🔍 Rotation considered to improve interpretability.

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Factor Analyzer
* Jupyter Notebook

---

## 🏁 Conclusion

The statistical adequacy tests supported the use of factor analysis in the purchase behavior dataset.

The project provides a compact workflow for evaluating and extracting latent dimensions from customer behavior variables.

---

## 📌 Limitations

* The project uses a small set of observed variables.
* Factor names depend on analytical interpretation.
* Results should be validated with additional behavioral and business context.

---

## 👨‍💻 Author

Developed by **Brener Souza**

Data Science Student | Salesforce Administration | CRM & Analytics
