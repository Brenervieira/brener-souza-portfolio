<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white">
  <img src="https://img.shields.io/badge/Statsmodels-003B57?style=for-the-badge">
</p>

# 🎯 Life Expectancy Prediction

This project applies regression modeling and multivariate analysis to predict life expectancy using socioeconomic and public-health indicators.

The study compares baseline and regularized regression models while evaluating multicollinearity, predictive performance, and residual behavior.

---

## 📌 Business Problem

Public institutions and health organizations need to understand which indicators are associated with life expectancy in order to support evidence-based planning.

However, life expectancy is influenced by multiple correlated socioeconomic and health-related variables, making it important to balance predictive performance with statistical diagnostics.

Using regression models and regularization techniques, this project investigates which approach best predicts life expectancy while preserving relevant explanatory information.

### 📈 Key Results

✅ Ridge Regression was selected as the final model

✅ Final test R² reached approximately **0.7937**

✅ Final test RMSE reached approximately **4.0889**

✅ Final test MAE reached approximately **2.9420**

✅ Removing `income_composition_of_resources` reduced model performance, so the variable was preserved despite high VIF

---

## 💼 Business Impact

* Supports the identification of socioeconomic and health indicators associated with life expectancy.
* Helps compare predictive models under multicollinearity.
* Demonstrates how regularization can improve regression model stability.
* Documents statistical limitations without discarding useful predictive information.
* Provides an analytical workflow that can support public policy and health-planning discussions.

---

## 🎯 The Problem

Life expectancy is affected by multiple dimensions, including mortality, schooling, income composition, immunization, disease indicators, and public-health expenditure.

The central challenge is to build a predictive model that captures these relationships while managing multicollinearity and validating model assumptions.

---

## 🚀 Overview

Main question:

> Which regression approach provides the best predictive performance for life expectancy while preserving relevant socioeconomic and health information?

To answer this question, Linear Regression, Lasso, Ridge, Elastic Net, and an optimized Ridge model were compared.

---

## 🧪 Approach

The project combines:

* Exploratory Data Analysis (EDA)
* Missing-value treatment
* Outlier analysis
* Feature engineering
* VIF analysis
* Linear Regression
* Lasso Regression
* Ridge Regression
* Elastic Net Regression
* Grid Search optimization
* Residual diagnostics

---

## 🎯 Objectives

* Predict life expectancy using socioeconomic and health indicators.
* Compare baseline and regularized regression models.
* Evaluate the effect of multicollinearity on model decisions.
* Preserve variables that improve predictive performance.
* Validate residual behavior and document model limitations.

---

## 🧠 Methodology

### 🔹 1. Data Exploration

The dataset was analyzed to identify missing values, distribution patterns, potential outliers, and relationships with life expectancy.

---

### 🔹 2. Data Preparation

Columns were standardized, missing values were treated, outliers were analyzed, and engineered features were created to improve the modeling dataset.

The cleaned dataset was saved as `data/df_final.parquet`.

---

### 🔹 3. Baseline Model

A baseline Linear Regression model was developed as an initial performance reference.

---

### 🔹 4. Multicollinearity Analysis

Variance Inflation Factor (VIF) was used to evaluate multicollinearity among predictors.

The variables `income_composition_of_resources` and `schooling` showed high VIF values. However, removing `income_composition_of_resources` reduced predictive performance, so the variable was kept.

---

### 🔹 5. Regularized Models

Lasso, Ridge, Elastic Net, and optimized Ridge models were evaluated and compared using train and test metrics.

---

## 📊 Analyses and Results

### 📌 Model Performance Comparison

| Model | Test R² | Test RMSE |
| :--- | ---: | ---: |
| Ridge | 0.7937 | 4.0889 |
| Optimized Ridge | 0.7936 | 4.0891 |
| Lasso | 0.7626 | 4.3859 |
| Elastic Net | 0.7301 | 4.6769 |

**Insight**

Ridge Regression achieved the best balance between predictive power and error reduction.

---

## 🤖 Validation

Model performance was evaluated using:

* MAE (Mean Absolute Error)
* MSE (Mean Squared Error)
* RMSE (Root Mean Squared Error)
* R² Score

Residual diagnostics indicated approximate normality in the center of the distribution, with deviations in the extremes. Homoscedasticity was not fully satisfied and was documented as a limitation.

---

## 🧠 Main Findings

* Ridge Regression delivered the best test performance.
* Multicollinearity was present but did not justify automatic feature removal.
* Removing `income_composition_of_resources` reduced model performance.
* Regularized models helped evaluate stability under correlated predictors.
* Residual assumptions were not fully satisfied, but the model remained appropriate for the predictive objective.

---

## 🚀 Project Highlights

* 🔥 Comparison between baseline and regularized regression models.
* 📊 Integration of predictive modeling and statistical diagnostics.
* 🧠 VIF analysis used to evaluate multicollinearity.
* 🔍 Model selection based on test performance and analytical context.

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* Statsmodels
* SciPy
* PyArrow
* Jupyter Notebook

---

## 🏁 Conclusion

The results showed that Ridge Regression provided the strongest predictive performance among the evaluated models.

Although multicollinearity and residual-diagnostic limitations were identified, the final model remained suitable for the predictive goal of the project.

This project reinforces that model selection should consider both performance metrics and statistical context.

---

## 📌 Limitations

* The analysis identifies associations rather than causal relationships.
* Some multicollinearity remains in the feature set.
* Residual normality and homoscedasticity were not fully satisfied.
* Results depend on the quality and coverage of the analyzed dataset.

---

## 👨‍💻 Author

Developed by **Brener Souza**

Data Science Student | Salesforce Administration | CRM & Analytics
