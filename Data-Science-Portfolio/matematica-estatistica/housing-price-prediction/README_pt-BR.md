<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white">
  <img src="https://img.shields.io/badge/Statsmodels-003B57?style=for-the-badge">
</p>

# 🎯 Previsão de Preços de Imóveis com Regressão Não Paramétrica

Este projeto aplica técnicas de regressão não paramétrica e métodos de inferência estatística para prever preços de imóveis utilizando o California Housing Dataset.

O estudo compara Regressão Linear, Regressão Spline e Regressão Kernel, além de investigar diferenças estatísticas entre grupos de imóveis e regiões geográficas.

---

## 🎯 O Problema

Empresas do setor imobiliário precisam compreender quais fatores influenciam os preços dos imóveis e como características estruturais e geográficas impactam seu valor de mercado.

Modelos lineares tradicionais nem sempre conseguem capturar relações complexas e não lineares presentes em dados reais. Dessa forma, torna-se importante avaliar se métodos não paramétricos conseguem produzir previsões mais precisas e fornecer informações adicionais sobre os dados.

---

## 🚀 Visão Geral

Pergunta principal do projeto:

> Métodos de regressão não paramétrica conseguem prever preços de imóveis com maior precisão do que a regressão linear tradicional?

Para responder essa questão, diferentes modelos de regressão foram comparados utilizando métricas de desempenho e testes estatísticos não paramétricos.

---

## 🧪 Abordagem

O projeto combina:

* Análise Exploratória dos Dados (EDA)
* Correlação de Spearman
* Regressão Linear (Baseline)
* Regressão Spline
* Regressão Kernel
* Teste de Mann-Whitney
* Teste de Kruskal-Wallis

O objetivo não é apenas prever preços, mas também compreender como características dos imóveis e localização geográfica influenciam sua valorização.

---

## 🎯 Objetivos

* Prever preços de imóveis utilizando diferentes abordagens de regressão.
* Comparar modelos lineares e não paramétricos.
* Identificar relações relevantes entre as variáveis do dataset.
* Investigar diferenças estatisticamente significativas entre grupos.
* Avaliar a influência da localização geográfica sobre os preços dos imóveis.

---

## 🧠 Metodologia

### 🔹 1. Análise Exploratória dos Dados

O California Housing Dataset foi analisado para identificar:

* Valores ausentes
* Registros duplicados
* Distribuição das variáveis
* Possíveis outliers
* Relações entre atributos

---

### 🔹 2. Análise de Correlação

Foi utilizada a correlação de Spearman para identificar relações monotônicas entre as variáveis.

### 📌 Principais Relações

* MedInc × MedHouseVal → 0,68
* AveRooms × AveBedrms → 0,84
* Latitude × Longitude → -0,92

---

### 🔹 3. Modelo Baseline

Foi construída uma Regressão Linear Múltipla para servir como referência na comparação com os modelos não paramétricos.

---

### 🔹 4. Modelos Não Paramétricos

#### Regressão Spline

Utilizada para modelar relações não lineares através de transformações spline.

#### Regressão Kernel

Aplicada para capturar padrões complexos sem assumir uma forma funcional pré-definida.

---

### 🔹 5. Testes Estatísticos

#### Mann-Whitney

Comparação dos preços entre:

* Imóveis mais novos
* Imóveis mais antigos

#### Kruskal-Wallis

Comparação dos preços entre regiões geográficas criadas por clusterização utilizando latitude e longitude.

---

## 📊 Análises e Resultados

### 📌 Distribuição da Variável Alvo

![Target Distribution](./img/Target.png)

**Insight**

A variável alvo apresentou assimetria à direita, indicando que relações não lineares poderiam estar presentes nos dados.

---

### 📌 Heatmap de Correlação de Spearman

![Spearman](./img/spearman.png)

**Insight**

A renda mediana da região (MedInc) apresentou a associação positiva mais forte com os preços dos imóveis.

---

### 📌 Previsões da Regressão Kernel

![Kernel Regression](./img/kernel.png)

**Insight**

A Regressão Kernel apresentou previsões mais próximas dos valores reais quando comparada ao modelo linear.

---

### 📌 Comparação dos Modelos


![Model Performance](./img/modelos.png)
---

## 🤖 Validação

O desempenho dos modelos foi avaliado através das métricas:

* MAE (Erro Médio Absoluto)
* RMSE (Raiz do Erro Quadrático Médio)
* MSE (Erro Quadrático Médio)
* R² (Coeficiente de Determinação)

Além disso, a estabilidade da Regressão Kernel foi avaliada utilizando K-Fold Cross Validation, substituindo o Bootstrap devido ao elevado custo computacional da técnica.

---

## 🧠 Principais Descobertas

* A Regressão Kernel apresentou o melhor desempenho preditivo.
* A renda mediana da região foi a variável mais associada ao preço dos imóveis.
* Existem diferenças estatisticamente significativas entre imóveis novos e antigos.
* A localização geográfica exerce forte influência sobre os preços dos imóveis.
* Métodos não paramétricos foram mais eficientes na captura de relações complexas presentes nos dados.

---

## 🚀 Diferenciais do Projeto

* 🔥 Comparação entre métodos paramétricos e não paramétricos.
* 📊 Integração entre modelagem preditiva e inferência estatística.
* 🧠 Aplicação de testes estatísticos não paramétricos.
* 🌎 Segmentação geográfica utilizando K-Means.

---

## 🛠️ Tecnologias Utilizadas

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* Statsmodels
* SciPy

---

## 🏁 Conclusão

Os resultados demonstraram que técnicas de regressão não paramétrica podem superar a regressão linear tradicional em problemas que apresentam relações complexas e não lineares.

A Regressão Kernel apresentou o melhor desempenho preditivo entre os modelos avaliados, enquanto os testes estatísticos confirmaram que tanto a idade dos imóveis quanto sua localização geográfica estão associadas a diferenças significativas nos preços observados.

Este projeto demonstra a importância da combinação entre modelagem preditiva e inferência estatística para compreender problemas reais de negócio e apoiar a tomada de decisão baseada em dados.

---

## 📌 Limitações

* A Regressão Kernel exigiu redução da amostra devido ao alto custo computacional.
* O dataset não possui uma variável explícita de região, sendo necessário criar agrupamentos geográficos por clusterização.
* Os resultados são específicos do California Housing Dataset e não devem ser generalizados sem validação adicional.

---

## 👨‍💻 Autor

Desenvolvido por **Brener Souza**

Estudante de Análise e Desenvolvimento de Sistemas | Aspirante a Cientista de Dados | Salesforce Administrator
