<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white">
  <img src="https://img.shields.io/badge/Factor%20Analysis-003B57?style=for-the-badge">
</p>

# 🎯 Análise Fatorial do Comportamento de Compra

Este projeto aplica análise fatorial a variáveis de comportamento de compra, como frequência de compras, valor médio, categoria mais comprada, tempo de loja e uso do aplicativo.

O estudo avalia se as variáveis observadas são adequadas para análise fatorial e utiliza testes de adequação para apoiar a extração de fatores latentes.

---

## 📌 Problema de Negócio

Equipes de varejo e comércio digital frequentemente precisam resumir o comportamento dos clientes em dimensões mais interpretáveis.

Em vez de analisar cada variável comportamental separadamente, a análise fatorial pode revelar estruturas latentes que apoiam segmentação, caracterização de perfis e estratégia comercial.

### 📈 Principais Resultados

✅ O teste de Bartlett sustentou o uso da análise fatorial

✅ O KMO global alcançou aproximadamente **0,9120**

✅ Todos os valores individuais de KMO ficaram acima de **0,90**

✅ A base foi considerada adequada para análise fatorial

✅ A análise de rotação foi utilizada para melhorar a interpretabilidade

---

## 💼 Impacto para o Negócio

* Ajuda a resumir o comportamento de compra em dimensões latentes.
* Apoia segmentação e caracterização de perfis de clientes.
* Reduz a complexidade analítica na interpretação de variáveis relacionadas.
* Fornece evidência estatística antes da extração de fatores.
* Cria uma base para interpretação de comportamento de clientes orientada ao negócio.

---

## 🎯 O Problema

O comportamento de compra dos clientes é medido por múltiplas variáveis relacionadas.

O desafio é verificar se essas variáveis compartilham estrutura de correlação suficiente para justificar análise fatorial e apoiar a interpretação de dimensões latentes.

---

## 🚀 Visão Geral

Pergunta principal do projeto:

> As variáveis de comportamento de compra possuem correlação suficiente para serem resumidas por análise fatorial?

Para responder essa pergunta, foram aplicados teste de Bartlett, análise de KMO e extração de fatores.

---

## 🧪 Abordagem

O projeto combina:

* Carregamento dos dados
* Avaliação da adequação das correlações
* Teste de esfericidade de Bartlett
* Teste Kaiser-Meyer-Olkin (KMO)
* Análise fatorial
* Análise de rotação
* Interpretação de fatores latentes

---

## 🎯 Objetivos

* Avaliar se a base é adequada para análise fatorial.
* Aplicar validação com Bartlett e KMO.
* Identificar estruturas latentes em variáveis de comportamento de compra.
* Melhorar a interpretabilidade por meio de rotação.
* Apoiar a interpretação do comportamento de clientes usando menos dimensões.

---

## 🧠 Metodologia

### 🔹 1. Carregamento dos Dados

O dataset foi carregado a partir de `data/dataset.csv` e inspecionado antes da validação da análise fatorial.

---

### 🔹 2. Teste de Bartlett

O teste de esfericidade de Bartlett foi utilizado para verificar se a matriz de correlação era significativamente diferente de uma matriz identidade.

---

### 🔹 3. Teste KMO

O teste KMO foi utilizado para avaliar a adequação amostral para análise fatorial.

O KMO global foi de aproximadamente **0,9120**, indicando forte adequação.

---

### 🔹 4. Análise Fatorial

A análise fatorial foi aplicada após a validação dos pressupostos estatísticos.

---

### 🔹 5. Rotação

A rotação foi avaliada para melhorar a interpretação dos fatores e apoiar conclusões orientadas ao negócio.

---

## 📊 Análises e Resultados

### 📌 Resultados do KMO

| Métrica | Resultado |
| :--- | ---: |
| KMO global | 0,9120 |
| Menor KMO individual | 0,9021 |
| Maior KMO individual | 0,9197 |

**Insight**

Os altos valores de KMO indicam forte adequação da base para análise fatorial.

---

## 🤖 Validação

O uso da análise fatorial foi validado por meio de:

* Teste de esfericidade de Bartlett
* KMO global
* Valores individuais de KMO
* Interpretação da estrutura fatorial

---

## 🧠 Principais Descobertas

* As variáveis apresentaram estrutura compartilhada suficiente para análise fatorial.
* Frequência de compras, valor médio, categoria preferida, tempo de loja e uso do app podem ser estudados como indicadores relacionados.
* Os altos valores de KMO sustentam a extração de fatores latentes.
* A análise fatorial pode reduzir a complexidade na interpretação do comportamento de compra.

---

## 🚀 Diferenciais do Projeto

* 🔥 Validação estatística antes da extração de fatores.
* 📊 Análise de KMO para avaliar adequação amostral.
* 🧠 Análise fatorial aplicada ao comportamento de compra de clientes.
* 🔍 Rotação considerada para melhorar a interpretabilidade.

---

## 🛠️ Tecnologias Utilizadas

* Python
* Pandas
* NumPy
* Matplotlib
* Factor Analyzer
* Jupyter Notebook

---

## 🏁 Conclusão

Os testes de adequação estatística sustentaram o uso da análise fatorial na base de comportamento de compra.

O projeto oferece um fluxo compacto para avaliar e extrair dimensões latentes a partir de variáveis comportamentais de clientes.

---

## 📌 Limitações

* O projeto utiliza um conjunto pequeno de variáveis observadas.
* Os nomes dos fatores dependem de interpretação analítica.
* Os resultados devem ser validados com contexto comportamental e de negócio adicional.

---

## 👨‍💻 Autor

Desenvolvido por **Brener Souza**

Estudante de Análise e Desenvolvimento de Sistemas | Aspirante a Cientista de Dados | Salesforce Administrator
