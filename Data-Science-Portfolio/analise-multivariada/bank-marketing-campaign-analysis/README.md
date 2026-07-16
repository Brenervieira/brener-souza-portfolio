<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white">
  <img src="https://img.shields.io/badge/XGBoost-EB5B2A?style=for-the-badge&logo=xgboost&logoColor=white">
  <img src="https://img.shields.io/badge/Logistic%20Regression-003B57?style=for-the-badge">
</p>

# 🏦 Bank Marketing Campaign Analysis

This project applies Multivariate Analysis and Machine Learning techniques to identify which customer characteristics, financial conditions, and campaign variables are associated with accepting a term deposit offer.

The study combines missing-data treatment, supervised model-based imputation, class balancing, and Logistic Regression to transform campaign data into business-oriented recommendations.

---
## 📂 Data Source

The dataset is loaded directly from a public source during notebook execution and is therefore not stored in this repository.

To reproduce the project, run the notebook with an internet connection.

## 📌 Business Problem

A financial institution conducts telephone marketing campaigns to offer investment products to its customers.

However, a large proportion of contacts do not generate conversions, increasing operating costs, consuming sales team capacity, and potentially creating customer fatigue through repeated approaches.

The challenge is to understand which characteristics are associated with a higher probability of acceptance, enabling the institution to target contacts more effectively and develop more efficient campaigns.

### 📈 Key Results

✅ Call duration showed the strongest positive association with conversion, with an **odds ratio of approximately 2.79**

✅ Customers with housing loans showed lower acceptance likelihood, with an **odds ratio of approximately 0.59**

✅ A greater number of contacts during the same campaign was associated with lower conversion probability, with an **odds ratio of approximately 0.69**

✅ Previous contact history, education level, and account balance showed positive associations with acceptance

✅ Weighted XGBoost improved recognition of the minority education category, reaching approximately **0.69 recall for the primary class**

✅ Education imputation prioritized class balance rather than overall accuracy alone

---

## 💼 Business Impact

* Supports the identification of customer profiles that are more receptive to campaigns.
* Reduces reliance on broad and repetitive contact strategies.
* Suggests limiting excessive contact attempts to reduce customer fatigue.
* Helps explain how financial conditions and relationship history influence conversion.
* Demonstrates how Machine Learning can improve data quality before business analysis.
* Supports more targeted, efficient, and data-driven marketing campaigns.

---

## 🎯 The Problem

Which factors most influence a customer's decision to accept or reject a term deposit offer during a bank marketing campaign?

Answering this question required addressing two main challenges:

1. Treating missing data without introducing excessive bias.
2. Interpreting which variables are positively or negatively associated with conversion.

---

## 🚀 Overview

The project was developed using the Bank Marketing Dataset, containing **45,211 records** and variables related to:

* Sociodemographic profile
* Financial situation
* Banking history
* Contact characteristics
* Previous campaign history
* Campaign outcome

The target variable indicates whether the customer accepted the term deposit offer.

The target distribution was strongly imbalanced:

| Outcome        | Records |
| :------------- | ------: |
| Did not accept |  39,922 |
| Accepted       |   5,289 |

---

## 🧪 Approach

The project combines:

* Exploratory Data Analysis
* Missing-Value Treatment
* Categorical Variable Encoding
* Random Forest
* Class Balancing
* Sample-Weighted XGBoost
* Machine Learning Imputation
* Feature Standardization
* Logistic Regression
* Coefficient Interpretation
* Odds Ratio Analysis

---

## 🎯 Objectives

* Identify variables associated with campaign acceptance.
* Treat missing values according to each variable's business meaning.
* Use Machine Learning to impute the `education` variable.
* Compare imputation models under class imbalance.
* Reduce bias toward the majority category.
* Interpret Logistic Regression coefficients.
* Translate analytical results into business recommendations.

---

## 🧠 Methodology

### 🔹 1. Data Understanding

The dataset was inspected to identify:

* Variable types
* Missing values
* Target distribution
* Category frequencies
* Financial and sociodemographic characteristics

Missing values were found mainly in:

| Variable    | Missing values |
| :---------- | -------------: |
| `job`       |            288 |
| `education` |          1,857 |
| `contact`   |         13,020 |
| `poutcome`  |         36,959 |

---

### 🔹 2. Missing-Value Treatment

Each variable was treated according to its meaning:

* `job`: filled with the mode because only approximately 0.64% of its values were missing.
* `contact`: filled with `unknown`.
* `poutcome`: filled with `not_contacted_before`, representing customers without a recorded previous campaign outcome.
* `education`: imputed using Machine Learning.

---

### 🔹 3. Feature Preparation

Binary variables were converted into numerical values:

* `default`
* `housing`
* `loan`

The `job` and `marital` variables were transformed using One-Hot Encoding.

Education categories were encoded as:

| Education level | Code |
| :-------------- | ---: |
| Primary         |    0 |
| Secondary       |    1 |
| Tertiary        |    2 |

---

### 🔹 4. Baseline Random Forest

The first model evaluated for `education` imputation was an unbalanced Random Forest.

### Results

* Approximate accuracy: **0.70**
* Recall for the `primary` class: **0.35**
* Macro F1-score: **0.63**

Although the model achieved reasonable overall accuracy, it struggled to recognize the minority `primary` category.

---

### 🔹 5. Balanced Random Forest

A second Random Forest was tested using:

```python
class_weight="balanced"
```

### Results

* Approximate accuracy: **0.70**
* Recall for the `primary` class: **0.32**
* Macro F1-score: **0.62**

Automatic class weighting did not improve recognition of the minority category.

---

### 🔹 6. Sample-Weighted XGBoost

An XGBoost model was trained using sample weights to compensate for class imbalance.

### Results

| Class     | Precision | Recall | F1-score |
| :-------- | --------: | -----: | -------: |
| Primary   |      0.43 |   0.69 |     0.53 |
| Secondary |      0.77 |   0.62 |     0.69 |
| Tertiary  |      0.72 |   0.74 |     0.73 |

* Approximate accuracy: **0.67**
* Macro F1-score: **0.65**
* Macro recall: **0.68**

Despite lower overall accuracy, the model achieved better balance across classes and substantially improved recognition of the `primary` category.

For this reason, weighted XGBoost was selected for the final imputation of the `education` variable.

---

## ⚖️ Imputation Model Selection Criteria

The model was not selected based on accuracy alone.

Because the objective was to impute missing values without excessively favoring the majority class, the following metrics were prioritized:

* Minority-class recall
* Macro F1-score
* Balance across categories
* Reduced imputation bias

This decision reduced the likelihood that most missing records would automatically be classified as `secondary` merely because it was the most frequent category.

---

## 📊 Analysis of Conversion Factors

After data treatment, Logistic Regression was applied to evaluate how each variable was associated with campaign acceptance probability.

Variables were standardized before model training, enabling a more appropriate comparison of coefficients.

---

### 📌 Positive Associations

| Variable            | Odds Ratio | Interpretation                                                    |
| :------------------ | ---------: | :---------------------------------------------------------------- |
| `duration`          |       2.79 | Longer calls were strongly associated with acceptance             |
| `pdays`             |       1.34 | Previous contact timing showed a positive association             |
| `education_encoded` |       1.20 | Higher education was associated with higher conversion likelihood |
| `previous`          |       1.16 | Previous contacts showed a positive association                   |
| `job_student`       |       1.10 | Student customers showed a positive association                   |
| `marital_single`    |       1.10 | Single customers showed a positive association                    |
| `job_retired`       |       1.09 | Retired customers showed a positive association                   |
| `balance`           |       1.07 | Higher account balance showed a mild positive association         |

---

### 📌 Negative Associations

| Variable          | Odds Ratio | Interpretation                                                         |
| :---------------- | ---------: | :--------------------------------------------------------------------- |
| `housing`         |       0.59 | Housing loans were associated with lower acceptance likelihood         |
| `campaign`        |       0.69 | More attempts within the same campaign reduced conversion probability  |
| `loan`            |       0.80 | Active personal loans were associated with lower acceptance likelihood |
| `job_blue-collar` |       0.82 | This occupation category showed a negative association                 |
| `job_housemaid`   |       0.90 | Negative association with conversion                                   |
| `job_technician`  |       0.90 | Negative association with conversion                                   |

---

## ⚠️ Interpreting the `duration` Variable

Call duration showed the strongest positive association.

However, this variable is only known after the contact has started or ended.

Therefore:

* It is useful for understanding campaign behavior.
* It may indicate greater interest or engagement during the call.
* It should not be used to select customers before contact.
* Using it in pre-campaign selection models could introduce information leakage.

---

## 🧠 Main Findings

* Customers with housing or personal loans showed a lower probability of acceptance.
* Higher account balances showed a positive, although moderate, association.
* Previous contacts were associated with higher conversion likelihood.
* Higher education showed a positive association with acceptance.
* Students and retired customers appeared relatively more receptive.
* Repeated contact attempts during the same campaign were associated with lower conversion.
* Call duration was the strongest factor but should only be interpreted after contact.
* Class-imbalance treatment was essential for fairer education imputation.

---

## 🚀 Project Highlights

* 🔥 Machine Learning applied to missing-data imputation.
* ⚖️ Model comparison under class imbalance.
* 🧠 Selection based on macro F1-score and minority-class recall.
* 📊 Logistic Regression applied to factor interpretation.
* 🔍 Odds ratios used to translate coefficients into understandable effects.
* 💼 Analytical results converted into bank marketing recommendations.
* ⚠️ Identification of information-leakage risk in the `duration` variable.

---

## 💡 Business Recommendations

Based on the results, the institution could:

* Prioritize customers with greater financial availability and previous relationship history.
* Consider education and occupation when segmenting audiences, while avoiding discriminatory use of personal characteristics.
* Avoid excessive contact attempts during the same campaign.
* Develop specific strategies for customers with active housing or personal loans.
* Use previous contact information to improve prioritization.
* Treat call duration as a post-contact engagement indicator rather than a pre-contact selection feature.

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* XGBoost
* UCI Machine Learning Repository
* Jupyter Notebook

---

## 🏁 Conclusion

The project demonstrated how Multivariate Analysis and Machine Learning techniques can be combined to address data-quality problems and understand factors associated with conversion in bank marketing campaigns.

During `education` imputation, Random Forest achieved higher overall accuracy but struggled to identify the minority category. Weighted XGBoost produced better balance across classes, increasing recall for the `primary` class from approximately 0.35 to 0.69.

Because the purpose of imputation was to reduce majority-class bias, XGBoost was selected despite its slightly lower overall accuracy.

Logistic Regression showed that financial factors, contact history, education, and campaign intensity were associated with customer decisions. The results also suggested that excessive contact attempts may reduce acceptance probability.

The project reinforces that model selection should not rely on a single metric. The analytical objective, class behavior, and business consequences of model decisions must also be considered.

---

## 📌 Limitations

* The analysis identifies associations rather than causal relationships.
* The `duration` variable is not available before customer contact.
* Model-based imputation does not eliminate classification errors.
* Some categorical variables were simplified during preprocessing.
* Strong target imbalance should be addressed in future predictive models.
* Results are specific to the analyzed dataset.
* The project did not estimate the direct financial impact of the proposed recommendations.

---

## 👨‍💻 Author

Developed by **Brener Souza**

Data Science Student | Salesforce Administration | CRM & Analytics
