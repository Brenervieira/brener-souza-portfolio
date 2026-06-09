<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Statsmodels-003B57?style=for-the-badge">
  <img src="https://img.shields.io/badge/Scipy-8CAAE6?style=for-the-badge">
</p>

# 🚔 Crime Rate Analysis using Multiple Linear Regression

This project applies statistical modeling techniques to investigate which socioeconomic, demographic, and urban factors influence crime rates.

The study combines Exploratory Data Analysis (EDA), correlation analysis, multiple linear regression, and statistical assumption validation to build an interpretable predictive model.

---

## 🎯 The Problem

Crime rates are influenced by multiple interconnected factors, making it difficult to identify which variables truly contribute to criminal activity.

Understanding these relationships is important for policymakers, urban planners, and public safety organizations seeking to allocate resources effectively and develop preventive strategies.

This project investigates whether socioeconomic and urban indicators can explain variations in crime rates through statistical modeling.

---

## 🚀 Overview

Main question:

> Can socioeconomic and urban variables explain crime rate variations through a statistically valid regression model?

To answer this question, multiple regression models were developed, refined, and validated using classical statistical diagnostics.

---

## 🧪 Approach

The project combines:

* Exploratory Data Analysis (EDA)
* Correlation Analysis
* Multiple Linear Regression
* Log Transformation
* Variance Inflation Factor (VIF)
* Rainbow Test
* Durbin-Watson Test
* Breusch-Pagan Test
* Goldfeld-Quandt Test
* Shapiro-Wilk Test

The goal is not only to build a predictive model but also to ensure that the statistical assumptions required for reliable inference are satisfied.

---

## 🎯 Objectives

* Identify factors associated with crime rates.
* Evaluate relationships between socioeconomic variables.
* Build an interpretable regression model.
* Diagnose multicollinearity issues.
* Validate linear regression assumptions.
* Assess model reliability through statistical tests.

---

## 🧠 Methodology

### 🔹 1. Data Exploration

The dataset was inspected to identify:

* Missing values
* Variable distributions
* Potential outliers
* Correlation patterns
* Statistical characteristics of the target variable

---

### 🔹 2. Correlation Analysis

Pearson correlation analysis was performed to identify relationships among variables.

### 📌 Key Findings

Strong correlations were observed between several predictor variables, indicating potential multicollinearity issues that required further investigation.

Examples included:

* Age × Pollution
* Rooms × Occupancy
* Industry × Taxes
* Distance × Age

---

### 🔹 3. Multiple Linear Regression

An initial Multiple Linear Regression model was developed to explain crime rate variation.

The model was subsequently refined through variable selection and diagnostic evaluation.

---

### 🔹 4. Multicollinearity Diagnosis

Variance Inflation Factor (VIF) analysis was applied to identify highly correlated predictors.

Variables presenting excessive multicollinearity were removed to improve model stability and interpretability.

---

### 🔹 5. Statistical Assumption Validation

Several diagnostic tests were performed:

#### Rainbow Test

Evaluated model linearity.

#### Durbin-Watson Test

Evaluated residual independence.

**Result:** approximately 1.94, indicating no significant autocorrelation.

#### Breusch-Pagan Test

Evaluated homoscedasticity.

#### Goldfeld-Quandt Test

Used as an additional heteroscedasticity diagnostic.

#### Shapiro-Wilk Test

Evaluated residual normality.

**Result:** p-value ≈ 0.1525

No evidence was found against normality.

---

## 📊 Analyses and Results

### 📌 Target Variable Distribution

![Target Variable ](./img/histo.png)

**Insight**

The crime rate distribution exhibited asymmetry, motivating the use of logarithmic transformation to improve model assumptions.

---

### 📌 Correlation Analysis

![Correlation](./img/corr.png)

**Insight**

Correlation analysis revealed important relationships among predictors and highlighted multicollinearity concerns.

---

### 📌 Multiple Regression Model

![Model](./img/modelo.png)

**Insight**

The refined model demonstrated strong explanatory power while satisfying the major assumptions required for statistical inference.

---

## 🤖 Validation

Model quality was evaluated through:

* R² Score
* Residual Analysis
* Multicollinearity Diagnostics
* Homoscedasticity Tests
* Normality Tests
* Residual Independence Tests

### 📌 Final Performance

* R² ≈ 0.86

This indicates that approximately 86% of the variability in crime rates can be explained by the selected predictors.

---

## 🧠 Main Findings

* Multiple socioeconomic factors influence crime rates.
* Several predictors initially presented multicollinearity issues.
* Variable selection improved model stability.
* Statistical assumptions were successfully validated.
* The final regression model explained approximately 86% of crime rate variation.

---

## 🚀 Project Highlights

* 🔥 Complete Multiple Linear Regression workflow.
* 📊 Correlation and multicollinearity analysis.
* 🧠 Application of VIF for feature selection.
* 📈 Full regression diagnostics and validation.
* ✅ Durbin-Watson, Breusch-Pagan, Goldfeld-Quandt and Shapiro-Wilk tests.
* 🎯 Strong explanatory performance (R² ≈ 0.86).

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Statsmodels
* SciPy
* Scikit-Learn

---

## 🏁 Conclusion

The results demonstrate that crime rate variation can be effectively explained through a Multiple Linear Regression framework when appropriate diagnostic procedures are applied.

The final model achieved strong explanatory performance while satisfying the principal assumptions required for reliable statistical inference.

This project highlights the importance of combining predictive modeling with rigorous statistical validation to obtain trustworthy analytical results.

---

## 📌 Limitations

* The analysis is limited to the variables available in the dataset.
* Correlation does not imply causation.
* External social and economic factors not present in the dataset may also influence crime rates.
* Results should be interpreted within the context of the studied population.

---

## 👨‍💻 Author

Developed by **Brener Souza**

Data Science Student | Salesforce Administration | CRM & Analytics
