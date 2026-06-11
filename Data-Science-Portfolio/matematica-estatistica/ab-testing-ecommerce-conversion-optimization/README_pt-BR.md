<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Statsmodels-003B57?style=for-the-badge">
  <img src="https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge">
  <img src="https://img.shields.io/badge/AB%20Testing-FF6F00?style=for-the-badge">
</p>

# 🧪 A/B Testing for E-Commerce Conversion Optimization

Este projeto utiliza técnicas de Experimentação, Teste de Hipóteses e Estatística Aplicada para avaliar se uma nova versão da experiência do usuário (V1) é capaz de aumentar a taxa de conversão em comparação com a versão atual (Controle).

O estudo combina Análise Exploratória de Dados (EDA), Teste Qui-Quadrado, Regressão Logística, Testes Estatísticos Complementares e Análise Segmentada por Fonte de Tráfego para gerar recomendações orientadas a negócio.

---

## 🎯 O Problema

Empresas frequentemente realizam experimentos A/B para validar mudanças em produtos digitais antes de disponibilizá-las para todos os usuários.

No entanto, nem toda diferença observada entre grupos representa uma melhoria real.

É necessário utilizar métodos estatísticos para determinar se os resultados observados são significativos ou se podem ter ocorrido apenas por acaso.

Este projeto investiga se a versão V1 gera aumento real na taxa de conversão quando comparada à versão Controle.

---

## 🚀 Visão Geral

Pergunta principal:

> A nova versão da experiência do usuário (V1) aumenta significativamente a taxa de conversão em comparação com a versão atual (Controle)?

Para responder essa pergunta foram aplicadas técnicas estatísticas clássicas de experimentação e inferência.

---

## 🧪 Abordagem

O projeto combina:

* Análise Exploratória de Dados (EDA)
* Teste Qui-Quadrado
* Teste t para comparação de médias
* Teste de Levene
* Teste de Welch
* Regressão Logística
* Análise Segmentada por Fonte de Tráfego
* Avaliação de Lift de Conversão

O objetivo não é apenas verificar significância estatística, mas também avaliar o impacto de negócio da nova versão.

---

## 🎯 Objetivos

* Avaliar se existe diferença significativa entre Controle e V1.
* Medir o impacto da nova versão na conversão.
* Validar os resultados utilizando diferentes abordagens estatísticas.
* Investigar a consistência do efeito entre diferentes fontes de tráfego.
* Traduzir resultados estatísticos em recomendações de negócio.

---

## 🧠 Metodologia

### 🔹 1. Exploração dos Dados

O conjunto de dados foi analisado para identificar:

* Valores ausentes
* Duplicações
* Distribuição dos grupos experimentais
* Distribuição das conversões
* Possíveis inconsistências

---

### 🔹 2. Avaliação da Qualidade dos Dados

Durante a análise exploratória foi identificado que aproximadamente 94,8% dos registros possuíam combinações repetidas de atributos.

Como o dataset não contém identificadores únicos de usuários, não foi possível determinar se essas repetições representam observações redundantes ou usuários distintos com características semelhantes.

Essa limitação foi considerada durante a interpretação dos resultados.

---

### 🔹 3. Teste Qui-Quadrado

O teste Qui-Quadrado foi utilizado para avaliar a associação entre:

* Grupo Experimental (Controle ou V1)
* Conversão (0 ou 1)

O objetivo foi verificar se a taxa de conversão observada difere significativamente entre os grupos.

---

### 🔹 4. Testes Estatísticos Complementares

Embora a variável de conversão seja binária e o teste Qui-Quadrado não exija normalidade, foram realizadas análises complementares para compreender melhor o comportamento dos dados.

Foram aplicados:

* Shapiro-Wilk
* QQ Plot
* Levene
* Welch

Essas análises possuem caráter exploratório e auxiliaram na validação dos resultados obtidos.

---

### 🔹 5. Regressão Logística

A Regressão Logística foi utilizada como abordagem complementar ao teste Qui-Quadrado.

O modelo permitiu avaliar o impacto da versão V1 sobre a probabilidade de conversão dos usuários.

---

### 🔹 6. Análise por Fonte de Tráfego

Após identificar um efeito positivo geral da versão V1, foi investigado se esse impacto permanecia consistente entre diferentes canais de aquisição.

Foram avaliadas as seguintes fontes:

* Organic
* Direct
* Referrals
* Email Marketing
* Paid Search
* Social Media

---

## 📊 Análises e Resultados

### 📌 Distribuição dos Grupos Experimentais

![Distribuicao](./img/disy.jpg)

**Insight**

Os grupos Controle e Tratamento apresentaram distribuição equilibrada, reduzindo possíveis vieses amostrais.

---

### 📌 Conversão por Grupo

![Conversão](./img/graf.png)



| Grupo    | Conversão |
| -------- | --------: |
| Controle |    10,01% |
| V1       |    10,99% |


**Insight**

A versão V1 apresentou aumento absoluto de aproximadamente 0,98 ponto percentual na taxa de conversão.

---

### 📌 Lift por Fonte de Tráfego

![Gráfico Lift](./img/lift_grafico.png)

| Fonte de Tráfego | Lift Relativo |
| ---------------- | ------------: |
| Social Media     |        11,38% |
| Email Marketing  |        11,09% |
| Paid Search      |        10,75% |
| Direct           |         9,87% |
| Organic          |         9,46% |
| Referrals        |         8,49% |

**Insight**

O impacto positivo da V1 foi observado em todas as fontes analisadas, indicando que o efeito do tratamento não ficou restrito a um único segmento de usuários.

---

### 📌 Resultado Estatístico


**Resultado**

| Estatistica | Resultados     |
| ----------- |---------------:|
| Estatistica |   510.10       |
| Valor-p     | ≈ 6,03 × 10⁻¹¹³|

**Insight**

Os testes estatísticos forneceram evidências suficientes para rejeitar a hipótese nula, indicando associação significativa entre a versão exibida e a conversão.

---

## 🤖 Validação

A robustez da análise foi avaliada por meio de:

* Teste Qui-Quadrado
* Teste t
* Teste de Levene
* Teste de Welch
* Regressão Logística
* Análise Segmentada por Canal

Os resultados foram consistentes entre diferentes abordagens estatísticas.

---

## 🧠 Principais Descobertas

* A versão V1 apresentou taxa de conversão superior ao grupo Controle.
* O aumento relativo de conversão foi de aproximadamente 9,78%.
* Todas as fontes de tráfego apresentaram ganhos positivos.
* Social Media e Email Marketing apresentaram os maiores lifts observados.
* Os resultados permaneceram consistentes entre diferentes testes estatísticos.
* A análise sugere que o efeito observado dificilmente ocorreu por acaso.

---

## 🚀 Destaques do Projeto

* 🔥 Aplicação prática de A/B Testing.
* 📊 Utilização de Teste Qui-Quadrado para inferência estatística.
* 🧠 Aplicação de Regressão Logística.
* 📈 Avaliação de Lift Absoluto e Relativo.
* 🎯 Segmentação por Fonte de Tráfego.
* ✅ Tradução dos resultados em recomendações de negócio.

---

## 🛠️ Tecnologias Utilizadas

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* SciPy
* Statsmodels
* Scikit-Learn

---

## 🏁 Conclusão

A análise demonstrou que a versão V1 apresentou desempenho superior ao grupo Controle, aumentando a taxa de conversão de aproximadamente 10,01% para 10,99%.

Os testes estatísticos realizados forneceram evidências suficientes para rejeitar a hipótese nula e indicar que a diferença observada dificilmente ocorreu por acaso.

A análise segmentada por fonte de tráfego reforçou essa conclusão, demonstrando ganhos consistentes em todos os canais avaliados.

Os resultados sugerem que a implementação da versão V1 pode gerar melhorias reais de desempenho para o negócio.

---

## 📌 Limitações

* O dataset não possui identificadores únicos de usuários.
* Não foi possível validar se registros repetidos representam usuários distintos ou observações redundantes.
* Os resultados devem ser interpretados dentro do contexto do experimento analisado.
* Outros fatores comportamentais não presentes no dataset podem influenciar a conversão.

---

## 👨‍💻 Autor

Desenvolvido por **Brener Souza**

Data Science Student | Salesforce Administration | CRM & Analytics
