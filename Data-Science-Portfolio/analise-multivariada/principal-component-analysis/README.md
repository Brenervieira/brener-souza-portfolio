<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white">
</p>

# 🎯 Principal Component Analysis

This project demonstrates Principal Component Analysis (PCA) using a synthetic dataset with eight numerical attributes.

The study shows how standardization, variance analysis, dimensionality reduction, and cross-validation can be combined before a classification model.

---

## 📌 Business Problem

High-dimensional datasets can contain redundant or difficult-to-interpret variables.

In analytical and machine learning workflows, dimensionality reduction can simplify the feature space and support more efficient modeling.

This project demonstrates a PCA workflow that can be adapted to datasets with many correlated numerical variables.

### 📈 Key Results

✅ PCA was applied after feature standardization

✅ Explained variance was evaluated for each component

✅ Cross-validation compared model performance across different component counts

✅ A final Logistic Regression model was trained with **6 principal components**

✅ Leave-One-Out Cross-Validation was applied as an additional validation step

---

## 💼 Business Impact

* Demonstrates how PCA can simplify high-dimensional datasets.
* Supports more efficient modeling by reducing the feature space.
* Provides a reusable workflow for dimensionality reduction.
* Helps connect explained variance with downstream model performance.
* Serves as a foundation for applying PCA to real business datasets.

---

## 🎯 The Problem

Datasets with many numerical attributes may contain overlapping information and can become harder to interpret or model.

The challenge is to reduce dimensionality while preserving enough information for classification.

---

## 🚀 Overview

Main question:

> How can PCA reduce the number of input dimensions while preserving useful information for a classification workflow?

To answer this question, synthetic data was generated, standardized, transformed with PCA, and evaluated with Logistic Regression.

---

## 🧪 Approach

The project combines:

* Synthetic data generation
* Feature standardization
* Principal Component Analysis (PCA)
* Explained variance analysis
* Logistic Regression
* Cross-validation
* Leave-One-Out Cross-Validation
* New-data prediction simulation

---

## 🎯 Objectives

* Demonstrate PCA as a dimensionality-reduction technique.
* Evaluate explained variance by component.
* Compare classification performance with different component counts.
* Train a final Logistic Regression model using reduced dimensions.
* Simulate prediction with new sensor-like data.

---

## 🧠 Methodology

### 🔹 1. Synthetic Data Generation

A synthetic dataset with **1,000 records** and **8 numerical attributes** was generated for reproducibility.

---

### 🔹 2. Standardization

The features were standardized using `StandardScaler`, ensuring that all attributes contributed on a comparable scale before PCA.

---

### 🔹 3. PCA Application

PCA was fitted to the standardized data, and the explained variance ratio was inspected for each component.

---

### 🔹 4. Model Evaluation

Logistic Regression was evaluated using cross-validation across different numbers of PCA components.

---

### 🔹 5. Final Model

The final workflow used **6 components** and simulated a prediction for new sensor-like data.

---

## 📊 Analyses and Results

### 📌 Explained Variance and Component Selection

The notebook evaluated the variance explained by each component and compared model performance across different PCA component counts.

**Insight**

Component selection should consider both explained variance and the performance of the downstream model.

---

## 🤖 Validation

The workflow was validated using:

* 5-fold cross-validation
* Leave-One-Out Cross-Validation
* Logistic Regression performance comparison across PCA dimensions

---

## 🧠 Main Findings

* Standardization is required before PCA when variables have different scales.
* PCA transforms the original features into orthogonal components.
* Six components were used in the final classification workflow.
* PCA can reduce dimensionality while preserving useful structure for modeling.
* The synthetic target limits practical interpretation of predictive performance.

---

## 🚀 Project Highlights

* 🔥 Practical demonstration of dimensionality reduction.
* 📊 Explained variance analysis by principal component.
* 🧠 Classification workflow built after PCA transformation.
* 🔍 Cross-validation used to compare component counts.

---

## 🛠️ Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Scikit-Learn
* Jupyter Notebook

---

## 🏁 Conclusion

PCA reduced the synthetic dataset into a smaller component space while preserving enough structure to train a classification model.

The project serves as a compact methodological demonstration that can be expanded to real high-dimensional datasets.

---

## 📌 Limitations

* The dataset is synthetic and does not represent a real business process.
* The target variable is randomly generated.
* Predictive performance has limited practical meaning.
* The project is primarily educational and methodological.

---

## 👨‍💻 Author

Developed by **Brener Souza**

Data Science Student | Salesforce Administration | CRM & Analytics
