
<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white">
  <img src="https://img.shields.io/badge/XGBoost-EB5B2A?style=for-the-badge&logo=xgboost&logoColor=white">
  <img src="https://img.shields.io/badge/Random%20Forest-228B22?style=for-the-badge">
</p>

# 🤖 High-Dimensional Binary Classification

This project develops and compares Machine Learning models for a binary classification problem involving a high-dimensional dataset.

The study combines preprocessing, dataset splitting, training-set balancing, feature standardization, comparison across different algorithm families, hyperparameter optimization, and stratified cross-validation.

---

## 📌 Business Problem

Binary classification problems appear in several real-world contexts, including fraud detection, risk identification, medical diagnosis, predictive maintenance, and event prediction.

In this project, the dataset contains **178 anonymized input features** and a binary target variable named `LABEL_TARGET`.

The challenge is to develop a model capable of correctly identifying the positive class while dealing with:

- High dimensionality
- Target-class imbalance
- Lack of semantic information about the features
- Potential nonlinear relationships among the attributes

Because the original event context was not provided, the analysis focuses on statistical and predictive performance without assigning unsupported business interpretations to the variables.

### 📈 Key Results

✅ Random Forest achieved the highest AUC among the evaluated models

✅ Approximately **0.994 AUC on the test set**

✅ Approximately **0.996 AUC on the final validation set**

✅ Approximately **98.6% recall on the test set**

✅ Approximately **99.1% recall on the validation set**

✅ The standard model achieved approximately **0.9945 mean cross-validation AUC**

✅ The standard model showed slightly better performance and lower variability than the optimized version

✅ The final model was selected based on performance, stability, and parsimony

---

## 💼 Analytical Impact

- Demonstrates the construction of a complete classification pipeline.
- Shows how to address class imbalance without modifying the test and validation distributions.
- Compares linear, probabilistic, and tree-based algorithms.
- Highlights the importance of AUC and recall in imbalanced classification problems.
- Uses cross-validation to evaluate model stability and generalization ability.
- Demonstrates that hyperparameter optimization does not always produce a superior model.
- Reinforces the importance of selecting models based on multiple metrics.

---

## 🎯 The Problem

The main objective of the project was to answer the following question:

> Which Machine Learning model provides the best ability to identify the positive class in a high-dimensional dataset with an imbalanced target variable?

To answer this question, five models were compared:

1. Baseline Logistic Regression
2. L2-Regularized Logistic Regression
3. Gaussian Naive Bayes
4. XGBoost
5. Random Forest

---

## 🚀 Overview

The dataset contains:

| Characteristic | Value |
| :--- | ---: |
| Records | 11,500 |
| Input features | 178 |
| Target variable | `LABEL_TARGET` |
| Classes | 2 |
| Missing values | 0 |
| Duplicate columns | 0 |

The target variable had the following distribution:

| Class | Records | Proportion |
| :--- | ---: | ---: |
| Class 0 | 9,200 | 80% |
| Class 1 | 2,300 | 20% |

This distribution characterizes an imbalanced classification problem.

---

## 🧪 Approach

The project was divided into two notebooks.

### Notebook 1 — Preprocessing

- Data loading and inspection
- Target-variable conversion
- Class-distribution analysis
- Train, validation, and test splitting
- Undersampling applied to the training set
- Storage of the processed datasets

### Notebook 2 — Modeling

- Feature standardization
- Development of auxiliary evaluation functions
- Training of different algorithms
- Metric comparison
- Model selection
- Hyperparameter optimization
- Stratified cross-validation
- Final evaluation on training, test, and validation sets
- Final model storage

---

## 🎯 Objectives

- Prepare the dataset for modeling.
- Preserve the original class distribution in the test and validation sets.
- Balance only the training set.
- Compare different algorithm families.
- Evaluate AUC, accuracy, recall, precision, and specificity.
- Select the model with the best generalization ability.
- Determine whether hyperparameter optimization produces consistent gains.
- Evaluate model stability through cross-validation.
- Save the final model for future use.

---

## 🧠 Methodology

### 🔹 1. Initial Data Analysis

The dataset was analyzed to verify:

- Dimensions
- Variable types
- Missing values
- Duplicate columns
- Target-variable distribution

No missing values or duplicate columns were identified.

---

### 🔹 2. Target-Variable Conversion

The `LABEL_TARGET` variable, initially stored as Boolean, was converted into integers:

```python
df["LABEL_TARGET"] = df["LABEL_TARGET"].astype(int)
````

The classes were represented as:

* `0`: negative class
* `1`: positive class

---

### 🔹 3. Data Splitting

The dataset was divided into:

| Dataset    | Records | Positive-class proportion |
| :--------- | ------: | ------------------------: |
| Training   |   8,050 |                    20.15% |
| Validation |   1,725 |                    19.19% |
| Test       |   1,725 |                    20.12% |

The validation and test sets maintained distributions close to the original dataset.

---

### 🔹 4. Training-Set Balancing

Undersampling of the majority class was applied exclusively to the training set.

After balancing:

| Class   | Records |
| :------ | ------: |
| Class 0 |   1,622 |
| Class 1 |   1,622 |

The final training set contained:

* 3,244 records
* 50% Class 0
* 50% Class 1

This strategy avoided artificially changing the distribution of the datasets used for evaluation.

---

### 🔹 5. Feature Standardization

The features were standardized using `StandardScaler`.

The scaler was fitted only on the training data and then applied to the test and validation sets.

This approach reduces the risk of information leakage across datasets.

---

## 🤖 Evaluated Models

### 🔹 Baseline Logistic Regression

| Metric      | Validation |
| :---------- | ---------: |
| AUC         |      0.496 |
| Accuracy    |      0.681 |
| Recall      |      0.432 |
| Precision   |      0.298 |
| Specificity |      0.744 |

The model achieved an AUC close to random classification performance.

---

### 🔹 L2-Regularized Logistic Regression

L2 regularization was applied using:

```python
C=0.1
solver="liblinear"
```

| Metric      | Validation |
| :---------- | ---------: |
| AUC         |      0.496 |
| Accuracy    |      0.658 |
| Recall      |      0.429 |
| Precision   |      0.275 |
| Specificity |      0.716 |

Regularization did not produce a relevant improvement over the baseline model.

---

### 🔹 Gaussian Naive Bayes

| Metric      | Validation |
| :---------- | ---------: |
| AUC         |      0.983 |
| Accuracy    |      0.954 |
| Recall      |      0.888 |
| Precision   |      0.883 |
| Specificity |      0.970 |

The probabilistic approach produced a substantial performance improvement.

---

### 🔹 XGBoost

| Metric      | Validation |
| :---------- | ---------: |
| AUC         |      0.992 |
| Accuracy    |      0.962 |
| Recall      |      0.968 |
| Precision   |      0.862 |
| Specificity |      0.961 |

XGBoost achieved excellent performance, suggesting the presence of nonlinear patterns in the data.

---

### 🔹 Random Forest

| Metric      | Validation |
| :---------- | ---------: |
| AUC         |      0.994 |
| Accuracy    |      0.950 |
| Recall      |      0.986 |
| Precision   |      0.809 |
| Specificity |      0.936 |

Random Forest achieved:

* The highest AUC
* The highest recall
* Excellent positive-class identification

For this reason, it was selected for hyperparameter optimization.

---

## 📊 Model Comparison

| Model                        |       AUC |  Accuracy |    Recall | Precision |
| :--------------------------- | --------: | --------: | --------: | --------: |
| Random Forest                | **0.994** |     0.950 | **0.986** |     0.809 |
| XGBoost                      |     0.992 | **0.962** |     0.968 |     0.862 |
| Gaussian Naive Bayes         |     0.983 |     0.954 |     0.888 | **0.883** |
| L2 Logistic Regression       |     0.496 |     0.658 |     0.429 |     0.275 |
| Baseline Logistic Regression |     0.496 |     0.681 |     0.432 |     0.298 |

Random Forest was selected mainly because it achieved the highest AUC and recall.

---

## ⚙️ Hyperparameter Optimization

Random Forest was optimized using:

* `RandomizedSearchCV`
* 30 hyperparameter combinations
* Five-fold stratified cross-validation
* AUC as the primary metric

The best hyperparameters were:

```python
{
    "n_estimators": 200,
    "min_samples_split": 2,
    "min_samples_leaf": 1,
    "max_features": "sqrt",
    "max_depth": 15,
    "class_weight": None,
    "bootstrap": True
}
```

The best mean AUC obtained during the search was approximately:

```text
0.9936
```

---

## 🔍 Standard versus Optimized Random Forest

To determine whether optimization produced real gains, both models were compared using cross-validation.

| Model                   |   Mean AUC | Standard deviation |
| :---------------------- | ---------: | -----------------: |
| Standard Random Forest  | **0.9945** |         **0.0016** |
| Optimized Random Forest |     0.9936 |             0.0022 |

The standard Random Forest achieved:

* Slightly higher mean AUC
* Lower variability across folds
* Lower configuration complexity
* More stable performance

Therefore, the standard model was retained as the final model according to the principle of parsimony.

---

## ✅ Final Evaluation

| Dataset    |   AUC | Accuracy | Recall | Precision | Specificity |
| :--------- | ----: | -------: | -----: | --------: | ----------: |
| Training   | 0.999 |    0.966 |  1.000 |     0.856 |       0.956 |
| Test       | 0.994 |    0.950 |  0.986 |     0.809 |       0.936 |
| Validation | 0.996 |    0.963 |  0.991 |     0.843 |       0.950 |

The results indicate excellent discriminative ability and high sensitivity toward the positive class.

The similarity between the test and validation results also provides evidence of model stability.

---

## 🧠 Main Findings

* Linear models were unable to adequately represent the patterns in the dataset.
* Gaussian Naive Bayes substantially outperformed Logistic Regression.
* XGBoost and Random Forest achieved the strongest performance.
* Random Forest obtained the highest AUC and recall.
* Hyperparameter optimization did not produce consistent gains over the standard model.
* Cross-validation confirmed the stability of the standard Random Forest.
* Model selection should consider performance, variability, and complexity.
* High dimensionality did not prevent tree-based models from identifying relevant patterns.

---

## 🚀 Project Highlights

* 🔥 Complete supervised-classification pipeline.
* 📊 Dataset containing 178 input features.
* ⚖️ Class-imbalance treatment through undersampling.
* 🤖 Comparison of five Machine Learning models.
* 📈 Evaluation through AUC, accuracy, recall, precision, and specificity.
* 🔍 Optimization using Randomized Search.
* ✅ Stratified cross-validation.
* 🧠 Model selection based on performance, stability, and parsimony.
* 💾 Final model and scaler storage.

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* XGBoost
* Pickle
* Jupyter Notebook

---

## 🏁 Conclusion

This project aimed to develop and evaluate models capable of performing binary classification on a high-dimensional dataset.

Different algorithm families were compared, including linear, probabilistic, and tree-based models.

Logistic Regression achieved an AUC close to 0.50, indicating difficulty representing the patterns present in the data. In contrast, Gaussian Naive Bayes, XGBoost, and Random Forest achieved significantly stronger performance.

Random Forest provided the best balance across the evaluated metrics, reaching approximately 0.994 AUC on the test set and 0.996 on the validation set, with recall above 98% in both datasets.

Although the optimized version also achieved excellent performance, cross-validation showed that the standard model had a slightly higher mean AUC, lower variability, and lower complexity.

Therefore, the standard Random Forest was selected as the final model according to the principle of parsimony.

The results demonstrate that model evaluation should not rely on a single data split or isolated metric. Cross-validation, stability, generalization ability, and complexity should also be considered during model selection.

---

## 📌 Limitations

* The features were anonymized, preventing individual feature interpretation.
* The business context of the target variable was not provided.
* Undersampling removes part of the majority-class observations.
* The strong performance may reflect patterns specific to this dataset.
* The project did not include explainability analysis using SHAP or Permutation Importance.
* External validation would be necessary before real-world deployment.
* The costs of false positives and false negatives were not assessed.

---

## 👨‍💻 Author

Developed by **Brener Souza**

Data Science Student | Salesforce Administration | CRM & Analytics
