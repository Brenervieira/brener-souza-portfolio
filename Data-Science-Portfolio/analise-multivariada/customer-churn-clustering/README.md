<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white">
  <img src="https://img.shields.io/badge/K--Means-003B57?style=for-the-badge">
</p>

# 🎯 Customer Churn Clustering

This project applies K-Means clustering to segment subscription customers based on age, monthly spending, subscription time, usage rate, support tickets, and churn behavior.

The study compares cluster solutions with and without outliers and interprets customer groups for activation, retention, and recovery strategies.

---

## 📌 Business Problem

Subscription-based companies need to understand different customer profiles and identify groups with higher churn risk.

Generic retention actions can waste resources and fail to address the needs of each customer segment. Clustering helps describe behavioral groups and support more targeted business strategies.

### 📈 Key Results

✅ The final solution selected **3 clusters**

✅ The model with and without outliers produced the same silhouette score: **0.4494**

✅ Outlier removal did not change the cluster structure

✅ Cluster 1 concentrated high-value customers with critical churn behavior

✅ Cluster 2 represented an intermediate group with elevated churn risk

---

## 💼 Business Impact

* Supports customer segmentation for recurring-revenue businesses.
* Helps prioritize retention actions by customer profile.
* Identifies high-value groups with critical churn behavior.
* Supports activation strategies for new and low-consumption customers.
* Provides a descriptive basis for more targeted commercial and support actions.

---

## 🎯 The Problem

The company needs to move beyond broad churn actions and understand which customer groups share similar usage, spending, tenure, and support-interaction patterns.

The goal is to create interpretable customer segments without treating clustering as an individual causal prediction.

---

## 🚀 Overview

Main question:

> Which customer segments can be identified from subscription behavior, and how do they differ in churn risk?

To answer this question, K-Means clustering was applied and evaluated with silhouette analysis and business interpretation.

---

## 🧪 Approach

The project combines:

* Exploratory Data Analysis (EDA)
* Data cleaning
* Feature standardization
* K-Means clustering
* Elbow method
* Silhouette analysis
* Outlier comparison
* Cluster interpretation

---

## 🎯 Objectives

* Segment customers according to subscription behavior.
* Compare clustering solutions with different numbers of groups.
* Evaluate the effect of outliers on cluster structure.
* Interpret clusters from a business perspective.
* Support retention, recovery, and activation strategies.

---

## 🧠 Methodology

### 🔹 1. Data Exploration

The dataset was inspected to understand customer behavior variables, distributions, and potential outliers.

---

### 🔹 2. Feature Standardization

Variables were standardized to avoid attributes with larger scales dominating distance calculations in K-Means.

---

### 🔹 3. Cluster Selection

The elbow method and silhouette analysis were used to compare possible numbers of clusters.

The 4-cluster solution was initially evaluated, but visual inspection indicated overlap between groups. A 3-cluster solution produced clearer and more interpretable profiles.

---

### 🔹 4. Outlier Comparison

Models with and without outliers were compared. The silhouette score remained **0.4494**, indicating that outlier removal did not change the cluster structure.

---

## 📊 Analyses and Results

### 📌 Final Cluster Interpretation

| Cluster | Interpretation |
| :--- | :--- |
| 0 | Newer customers, lower spending, mostly retained |
| 1 | Mature, high-value customers with critical churn |
| 2 | Intermediate customers with elevated churn risk |

**Insight**

The final interpretation kept all records because outliers affected visualization amplitude but did not change the composition of the groups.

---

## 🤖 Validation

The clustering solution was evaluated using:

* Elbow method
* Silhouette score
* Visual inspection of cluster separation
* Comparison with and without outliers

---

## 🧠 Main Findings

* The 3-cluster solution was more interpretable than the 4-cluster solution.
* Cluster 0 represents newer customers with low consumption and low churn.
* Cluster 1 concentrates high-value customers with critical churn behavior.
* Cluster 2 represents an intermediate group with elevated churn risk.
* Support interactions and usage patterns helped distinguish customer profiles.

---

## 🚀 Project Highlights

* 🔥 Customer segmentation using K-Means.
* 📊 Comparison between cluster solutions.
* 🧠 Business interpretation of customer profiles.
* 🔍 Outlier impact evaluated before final model selection.

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* Threadpoolctl
* Jupyter Notebook

---

## 🏁 Conclusion

K-Means clustering identified three interpretable customer profiles that can support activation, retention, and recovery strategies.

The result is descriptive and useful for business segmentation, but it should not be interpreted as causal or as an individual churn prediction model.

---

## 📌 Limitations

* Clustering does not establish causality.
* The dataset is small, with 99 customers.
* The churn variable supports interpretation but does not replace supervised churn prediction.
* Results should be validated with additional operational and financial data.

---

## 👨‍💻 Author

Developed by **Brener Souza**

Data Science Student | Salesforce Administration | CRM & Analytics
