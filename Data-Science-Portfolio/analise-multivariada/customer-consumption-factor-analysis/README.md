<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white">
  <img src="https://img.shields.io/badge/Factor%20Analysis-003B57?style=for-the-badge">
</p>

# 🎯 Customer Consumption Factor Analysis

This project applies factor analysis to customer consumption, campaign response, purchase channels, family profile, income, and relationship-time variables.

The study identifies latent dimensions that help explain customer behavior and support segmentation and marketing strategy.

---

## 📌 Business Problem

Marketing and commercial teams need to understand which behavioral dimensions explain customer consumption patterns.

When many variables describe spending, purchase channels, campaigns, family profile, and relationship time, direct interpretation becomes complex. Factor analysis helps summarize these variables into clearer latent dimensions.

### 📈 Key Results

✅ Initial global KMO reached approximately **0.8768**

✅ After removing low-KMO marital-status indicators, global KMO increased to **0.881**

✅ Bartlett's test was significant, with p-value close to zero

✅ Four latent factors were selected and interpreted

✅ Oblique rotation was preferred because factor correlations exceeded 0.30 in magnitude

---

## 💼 Business Impact

* Supports customer segmentation through interpretable behavioral dimensions.
* Helps marketing teams understand campaign receptiveness.
* Connects consumption intensity, family profile, and digital behavior.
* Reduces complexity in customer behavior analysis.
* Provides a statistical basis for more targeted commercial strategies.

---

## 🎯 The Problem

Customer consumption behavior is explained by multiple observed variables that may reflect broader latent dimensions.

The challenge is to identify these hidden factors and interpret them in a way that supports business decisions.

---

## 🚀 Overview

Main question:

> Which latent factors explain customer consumption behavior considering income, product spending, purchase channels, campaigns, and relationship time?

To answer this question, data cleaning, feature engineering, adequacy tests, factor extraction, and rotation analysis were applied.

---

## 🧪 Approach

The project combines:

* Data cleaning
* Feature engineering
* Categorical encoding
* Income regularization
* Feature standardization
* Bartlett's sphericity test
* KMO analysis
* Factor analysis
* Varimax rotation
* Oblique rotation

---

## 🎯 Objectives

* Identify latent dimensions behind customer consumption behavior.
* Validate factor-analysis adequacy using Bartlett and KMO.
* Remove variables that reduce factor adequacy.
* Compare rotation strategies.
* Translate factors into business-oriented interpretations.

---

## 🧠 Methodology

### 🔹 1. Data Cleaning

The customer identifier was removed because it did not contribute to latent-factor identification.

Records with missing income were removed due to their low proportion in the dataset.

---

### 🔹 2. Feature Engineering

Birth year and customer registration date were transformed into customer age and relationship-time variables.

Education and marital-status variables were encoded for numerical analysis.

---

### 🔹 3. Standardization

Selected variables were standardized to place income, spending, age, relationship time, and purchase-channel indicators on a common scale.

---

### 🔹 4. Adequacy Tests

Bartlett's test indicated sufficient correlations for factor analysis.

The initial global KMO was **0.8768**. After removing low-KMO marital-status indicators, the global KMO increased to **0.881**.

---

### 🔹 5. Factor Extraction and Rotation

Four factors were extracted and interpreted. Because correlations between some factors exceeded 0.30 in magnitude, oblique rotation was preferred.

---

## 📊 Analyses and Results

### 📌 Final Factor Interpretation

| Factor | Interpretation |
| :--- | :--- |
| 1 | Consumption intensity and diversity |
| 2 | Marketing campaign receptiveness |
| 3 | Family profile and life stage |
| 4 | Digital behavior and promotion sensitivity |

**Insight**

Customer behavior was mainly explained by spending intensity, campaign response, family profile, and digital or promotional interaction.

---

## 🤖 Validation

The factor-analysis workflow was validated using:

* Bartlett's sphericity test
* Global KMO
* Individual KMO values
* Factor correlation matrix
* Rotation comparison

---

## 🧠 Main Findings

* Four latent factors were identified and interpreted.
* Marital-status indicators reduced adequacy and were removed from the main factor model.
* Factor correlations indicated that the dimensions were not fully independent.
* Oblique rotation produced a more realistic interpretation of customer behavior.
* The factors can support segmentation and marketing strategy.

---

## 🚀 Project Highlights

* 🔥 Factor analysis applied to marketing and consumption data.
* 📊 KMO improved after removing low-adequacy variables.
* 🧠 Four interpretable latent customer dimensions.
* 🔍 Rotation choice based on factor correlations.

---

## 🛠️ Technologies Used

* Python
* Pandas
* Matplotlib
* Scikit-Learn
* Factor Analyzer
* Jupyter Notebook

---

## 🏁 Conclusion

The final factor analysis identified four meaningful dimensions of customer behavior.

These factors summarize complex consumption, campaign, family, and digital-interaction patterns into interpretable dimensions that can support segmentation and targeted marketing strategies.

---

## 📌 Limitations

* Factor interpretation depends on analytical judgment.
* The analysis is descriptive and does not establish causality.
* Income records with missing values were removed due to their low proportion.
* Results should be validated with external business outcomes.

---

## 👨‍💻 Author

Developed by **Brener Souza**

Data Science Student | Salesforce Administration | CRM & Analytics
