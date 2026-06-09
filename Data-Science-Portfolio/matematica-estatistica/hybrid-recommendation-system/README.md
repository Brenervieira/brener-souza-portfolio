<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white">
  <img src="https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge">
  <img src="https://img.shields.io/badge/Seaborn-4C72B0?style=for-the-badge">
</p>

# 🎬 Movie Recommendation System (Hybrid Model)

A movie recommendation system based on **hybrid similarity**, combining:

* 🎭 Content (genres, cast, keywords, director)
* 📊 Performance (rating, popularity, number of votes)

In addition to generating recommendations, this project performs a **statistical analysis to validate whether similar movies also share similar evaluation patterns**.

---

## 🎯 The Problem

Platforms with large catalogs face the challenge of recommending relevant content efficiently.

This project addresses this problem by combining content similarity with real user evaluation metrics.

---

## 🚀 Overview

Most recommendation systems rely solely on content or user behavior.
This project proposes a hybrid approach to answer the following question:

> Do similar movies also share similar patterns in ratings and popularity?

---

## 🧪 Approach

This project follows a validation-oriented approach, where the recommendation system is not only built but also analyzed from a statistical perspective.

## 📌 The model demonstrated strong semantic coherence when recommending movies from the same narrative universe.

Base movie: **The Hobbit: The Battle of the Five Armies**

**Model recommendations:**

* The Hobbit: The Desolation of Smaug
* The Hobbit: An Unexpected Journey
* The Lord of the Rings: The Fellowship of the Ring
* The Lord of the Rings: The Two Towers
* The Lord of the Rings: The Return of the King

📊 Observation: The recommended movies belong to the same universe and present **similar ratings**, validating the model's consistency.

---

## 🎯 Objectives

* Build a vector-based recommendation system
* Combine content + performance metrics
* Statistically validate the results
* Investigate relationships between popularity, votes, and ratings

---

## 🧠 Methodology

### 🔹 1. Data Preprocessing

* Removal of null and duplicate values
* Text standardization (lowercase, whitespace removal)
* Conversion of columns into lists
* Stemming application

---

### 🔹 2. Feature Engineering

#### 📌 Content Vector

* Genres
* Keywords
* Cast
* Director

#### 📌 Performance Vector

* `vote_average` (average rating)
* `popularity` (popularity score)
* `vote_count` (number of votes)

#### 📌 Hybrid Vector

The final similarity is defined as:

```
sim_final = α * sim_content + β * sim_performance
```

Where:

* α = 0.7 (content weight)
* β = 0.3 (performance weight)

---

### 🔹 3. Similarity

**Cosine similarity** was used to measure the distance between movies.

---

### 🔹 4. Recommendation System

Given an input movie, the system returns the **top N most similar movies**, based on the hybrid vector.

---

## 📊 Analysis & Model Validation

These analyses aim to validate whether the recommendation system effectively captures meaningful patterns between movies.

---

### 🎬 Do similar movies have similar ratings?

![Rating Comparison](/Data-Science-Portfolio/matemática%20estatística/Recommendation%20System%20Hybrid%20Model/img/filmes_similares.png)

**Insight:**

> The recommended movies show ratings close to the base movie, indicating that the model successfully captures similar evaluation patterns.

---

### 📉 Do popularity and number of votes influence ratings?

**Results:**

* Popularity vs Rating → **0.27**
* Vote Count vs Rating → **0.31**

![Correlation Graph](/Data-Science-Portfolio/matemática%20estatística/Recommendation%20System%20Hybrid%20Model/img/grafico_popularidade.png)

**Insight:**

> Both variables show a weak positive correlation with ratings. This suggests that visibility factors are not direct determinants of quality, although there is a slight trend of collective validation in vote count.

📎 For a complete analysis and detailed methodology, check the project notebook.

---

### 🎭 Are there patterns across genres?

![Genre Boxplot](/Data-Science-Portfolio/matemática%20estatística/Recommendation%20System%20Hybrid%20Model/img/Distribuoção_Notas.png)

**Insight:**

> Some genres show greater consistency and higher average ratings, indicating distinct audience acceptance patterns.

---

## 🤖 System Validation

An analysis was conducted to verify whether recommended movies share similar patterns with the base movie.

**Result:**

> Recommended movies tend to have similar rating and popularity values, indicating that the model captures similarity beyond content alone.

---

## 🧠 Key Insights

* Weak correlation between popularity and rating (0.27)
* Vote count shows slight correlation with rating (0.31)
* Popularity ≠ Quality
* The hybrid model captures nuances beyond pure content similarity

---

## 🚀 Project Highlights

* 🔥 Hybrid model (content + performance)
* 📊 Statistical validation of results
* 🧠 Analytical interpretation (not just implementation)
* 🎯 Real-world Data Science problem structure

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* Seaborn

---

## 🏁 Conclusion

This project demonstrates that:

* Recommendation systems can be improved with performance data
* Content similarity alone does not capture full audience perception
* Statistical validation is essential to ensure recommendation quality

---

## 📌 Next Steps

* Apply clustering (K-Means)
* Dimensionality reduction (PCA)
* Build an interactive interface with Streamlit
* Deploy the model

---

## 👨‍💻 Author

Developed by **Brener Souza**
