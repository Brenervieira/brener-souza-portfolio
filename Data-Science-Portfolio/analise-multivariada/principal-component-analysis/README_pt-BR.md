<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white">
</p>

# 🎯 Análise de Componentes Principais

Este projeto demonstra a aplicação de Principal Component Analysis (PCA) usando uma base sintética com oito atributos numéricos.

O estudo mostra como padronização, análise de variância, redução de dimensionalidade e validação cruzada podem ser combinadas antes de um modelo de classificação.

---

## 📌 Problema de Negócio

Bases com muitas dimensões podem conter variáveis redundantes ou difíceis de interpretar.

Em fluxos de análise e machine learning, a redução de dimensionalidade pode simplificar o espaço de atributos e apoiar uma modelagem mais eficiente.

Este projeto demonstra um fluxo de PCA que pode ser adaptado a bases com muitas variáveis numéricas correlacionadas.

### 📈 Principais Resultados

✅ O PCA foi aplicado após a padronização das variáveis

✅ A variância explicada foi avaliada para cada componente

✅ A validação cruzada comparou o desempenho com diferentes quantidades de componentes

✅ Um modelo final de Regressão Logística foi treinado com **6 componentes principais**

✅ Leave-One-Out Cross-Validation foi aplicado como etapa adicional de validação

---

## 💼 Impacto para o Negócio

* Demonstra como o PCA pode simplificar bases de alta dimensionalidade.
* Apoia modelagens mais eficientes por meio da redução do espaço de atributos.
* Oferece um fluxo reutilizável para redução de dimensionalidade.
* Ajuda a conectar variância explicada com desempenho do modelo posterior.
* Serve como base para aplicar PCA em datasets reais de negócio.

---

## 🎯 O Problema

Bases com muitos atributos numéricos podem conter informações sobrepostas e se tornar mais difíceis de interpretar ou modelar.

O desafio é reduzir a dimensionalidade preservando informação suficiente para classificação.

---

## 🚀 Visão Geral

Pergunta principal do projeto:

> Como o PCA pode reduzir o número de dimensões de entrada preservando informação útil para um fluxo de classificação?

Para responder essa pergunta, dados sintéticos foram gerados, padronizados, transformados com PCA e avaliados com Regressão Logística.

---

## 🧪 Abordagem

O projeto combina:

* Geração de dados sintéticos
* Padronização das variáveis
* Análise de Componentes Principais (PCA)
* Análise de variância explicada
* Regressão Logística
* Validação cruzada
* Leave-One-Out Cross-Validation
* Simulação de previsão com novos dados

---

## 🎯 Objetivos

* Demonstrar o PCA como técnica de redução de dimensionalidade.
* Avaliar a variância explicada por componente.
* Comparar desempenho de classificação com diferentes quantidades de componentes.
* Treinar um modelo final de Regressão Logística usando dimensões reduzidas.
* Simular previsão com novos dados semelhantes a sensores.

---

## 🧠 Metodologia

### 🔹 1. Geração de Dados Sintéticos

Foi gerada uma base sintética com **1.000 registros** e **8 atributos numéricos** para garantir reprodutibilidade.

---

### 🔹 2. Padronização

As variáveis foram padronizadas com `StandardScaler`, garantindo que todos os atributos contribuíssem em escala comparável antes do PCA.

---

### 🔹 3. Aplicação do PCA

O PCA foi ajustado aos dados padronizados, e a razão de variância explicada foi analisada para cada componente.

---

### 🔹 4. Avaliação do Modelo

A Regressão Logística foi avaliada com validação cruzada para diferentes números de componentes do PCA.

---

### 🔹 5. Modelo Final

O fluxo final utilizou **6 componentes** e simulou uma previsão para novos dados semelhantes a sensores.

---

## 📊 Análises e Resultados

### 📌 Variância Explicada e Seleção de Componentes

O notebook avaliou a variância explicada por cada componente e comparou o desempenho do modelo para diferentes quantidades de componentes principais.

**Insight**

A seleção de componentes deve considerar tanto a variância explicada quanto o desempenho do modelo posterior.

---

## 🤖 Validação

O fluxo foi validado por meio de:

* Validação cruzada com 5 folds
* Leave-One-Out Cross-Validation
* Comparação do desempenho da Regressão Logística em diferentes dimensões do PCA

---

## 🧠 Principais Descobertas

* A padronização é necessária antes do PCA quando as variáveis possuem escalas diferentes.
* O PCA transforma as variáveis originais em componentes ortogonais.
* Seis componentes foram usados no fluxo final de classificação.
* O PCA pode reduzir dimensionalidade preservando estrutura útil para modelagem.
* O alvo sintético limita a interpretação prática do desempenho preditivo.

---

## 🚀 Diferenciais do Projeto

* 🔥 Demonstração prática de redução de dimensionalidade.
* 📊 Análise de variância explicada por componente principal.
* 🧠 Fluxo de classificação construído após transformação por PCA.
* 🔍 Validação cruzada usada para comparar quantidades de componentes.

---

## 🛠️ Tecnologias Utilizadas

* Python
* NumPy
* Pandas
* Matplotlib
* Scikit-Learn
* Jupyter Notebook

---

## 🏁 Conclusão

O PCA reduziu a base sintética para um espaço menor de componentes, preservando estrutura suficiente para treinar um modelo de classificação.

O projeto funciona como uma demonstração metodológica compacta que pode ser expandida para bases reais de alta dimensionalidade.

---

## 📌 Limitações

* A base é sintética e não representa um processo real de negócio.
* A variável alvo é gerada aleatoriamente.
* O desempenho preditivo tem significado prático limitado.
* O projeto tem finalidade principalmente educacional e metodológica.

---

## 👨‍💻 Autor

Desenvolvido por **Brener Souza**

Estudante de Análise e Desenvolvimento de Sistemas | Aspirante a Cientista de Dados | Salesforce Administrator
