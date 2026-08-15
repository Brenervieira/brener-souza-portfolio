<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white">
  <img src="https://img.shields.io/badge/Statsmodels-003B57?style=for-the-badge">
</p>

# 🎯 Previsão de Expectativa de Vida

Este projeto aplica modelagem de regressão e análise multivariada para prever a expectativa de vida a partir de indicadores socioeconômicos e de saúde pública.

O estudo compara modelos de regressão baseline e regularizados, além de avaliar multicolinearidade, desempenho preditivo e comportamento dos resíduos.

---

## 📌 Problema de Negócio

Instituições públicas e organizações de saúde precisam compreender quais indicadores estão associados à expectativa de vida para apoiar decisões baseadas em evidências.

Entretanto, a expectativa de vida é influenciada por múltiplas variáveis socioeconômicas e de saúde, muitas delas correlacionadas entre si. Por isso, é importante equilibrar desempenho preditivo e diagnóstico estatístico.

Utilizando modelos de regressão e técnicas de regularização, este projeto investiga qual abordagem apresenta melhor desempenho para prever a expectativa de vida preservando informações explicativas relevantes.

### 📈 Principais Resultados

✅ A Regressão Ridge foi selecionada como modelo final

✅ O R² de teste final alcançou aproximadamente **0,7937**

✅ O RMSE de teste final alcançou aproximadamente **4,0889**

✅ O MAE de teste final alcançou aproximadamente **2,9420**

✅ A remoção de `income_composition_of_resources` reduziu o desempenho, então a variável foi preservada apesar do VIF elevado

---

## 💼 Impacto para o Negócio

* Apoia a identificação de indicadores socioeconômicos e de saúde associados à expectativa de vida.
* Ajuda a comparar modelos preditivos em contexto de multicolinearidade.
* Demonstra como a regularização pode melhorar a estabilidade de modelos de regressão.
* Documenta limitações estatísticas sem descartar informações preditivas úteis.
* Oferece um fluxo analítico aplicável a discussões de políticas públicas e planejamento em saúde.

---

## 🎯 O Problema

A expectativa de vida é afetada por múltiplas dimensões, incluindo mortalidade, escolaridade, composição de renda, imunização, indicadores de doenças e gastos em saúde pública.

O desafio central é construir um modelo preditivo capaz de capturar essas relações, gerenciar multicolinearidade e validar os pressupostos do modelo.

---

## 🚀 Visão Geral

Pergunta principal do projeto:

> Qual abordagem de regressão oferece o melhor desempenho preditivo para expectativa de vida preservando informações socioeconômicas e de saúde relevantes?

Para responder essa pergunta, foram comparados Regressão Linear, Lasso, Ridge, Elastic Net e Ridge otimizada.

---

## 🧪 Abordagem

O projeto combina:

* Análise Exploratória dos Dados (EDA)
* Tratamento de valores ausentes
* Análise de outliers
* Engenharia de atributos
* Análise de VIF
* Regressão Linear
* Regressão Lasso
* Regressão Ridge
* Regressão Elastic Net
* Otimização com Grid Search
* Diagnóstico dos resíduos

---

## 🎯 Objetivos

* Prever a expectativa de vida utilizando indicadores socioeconômicos e de saúde.
* Comparar modelos de regressão baseline e regularizados.
* Avaliar o efeito da multicolinearidade nas decisões de modelagem.
* Preservar variáveis que melhoram o desempenho preditivo.
* Validar o comportamento dos resíduos e documentar limitações do modelo.

---

## 🧠 Metodologia

### 🔹 1. Análise Exploratória dos Dados

O dataset foi analisado para identificar valores ausentes, padrões de distribuição, possíveis outliers e relações com a expectativa de vida.

---

### 🔹 2. Preparação dos Dados

As colunas foram padronizadas, valores ausentes foram tratados, outliers foram analisados e atributos foram criados para melhorar a base de modelagem.

A base tratada foi salva como `data/df_final.parquet`.

---

### 🔹 3. Modelo Baseline

Foi construída uma Regressão Linear baseline para estabelecer uma referência inicial de desempenho.

---

### 🔹 4. Análise de Multicolinearidade

O VIF foi utilizado para avaliar multicolinearidade entre os preditores.

As variáveis `income_composition_of_resources` e `schooling` apresentaram VIF elevado. Entretanto, a remoção de `income_composition_of_resources` reduziu o desempenho preditivo, justificando sua permanência.

---

### 🔹 5. Modelos Regularizados

Lasso, Ridge, Elastic Net e Ridge otimizada foram avaliados e comparados com métricas de treino e teste.

---

## 📊 Análises e Resultados

### 📌 Comparação dos Modelos

| Modelo | R² teste | RMSE teste |
| :--- | ---: | ---: |
| Ridge | 0,7937 | 4,0889 |
| Ridge otimizada | 0,7936 | 4,0891 |
| Lasso | 0,7626 | 4,3859 |
| Elastic Net | 0,7301 | 4,6769 |

**Insight**

A Regressão Ridge apresentou o melhor equilíbrio entre capacidade preditiva e redução do erro.

---

## 🤖 Validação

O desempenho dos modelos foi avaliado por meio das métricas:

* MAE
* MSE
* RMSE
* R²

Os diagnósticos dos resíduos indicaram aproximação à normalidade na região central da distribuição, com desvios nas extremidades. A homocedasticidade não foi plenamente satisfeita e foi registrada como limitação.

---

## 🧠 Principais Descobertas

* A Regressão Ridge apresentou o melhor desempenho no conjunto de teste.
* A multicolinearidade estava presente, mas não justificou remoção automática de variáveis.
* A exclusão de `income_composition_of_resources` reduziu o desempenho do modelo.
* Modelos regularizados ajudaram a avaliar estabilidade em contexto de preditores correlacionados.
* Os pressupostos dos resíduos não foram integralmente atendidos, mas o modelo final permaneceu adequado ao objetivo preditivo.

---

## 🚀 Diferenciais do Projeto

* 🔥 Comparação entre regressão baseline e modelos regularizados.
* 📊 Integração entre modelagem preditiva e diagnóstico estatístico.
* 🧠 Análise de VIF para avaliação de multicolinearidade.
* 🔍 Seleção de modelo baseada em desempenho de teste e contexto analítico.

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
* PyArrow
* Jupyter Notebook

---

## 🏁 Conclusão

Os resultados demonstraram que a Regressão Ridge apresentou o melhor desempenho preditivo entre os modelos avaliados.

Embora tenham sido identificadas limitações relacionadas à multicolinearidade e aos diagnósticos dos resíduos, o modelo final permaneceu adequado ao objetivo preditivo do projeto.

Este projeto reforça que a seleção de modelos deve considerar tanto métricas de desempenho quanto o contexto estatístico da análise.

---

## 📌 Limitações

* A análise identifica associações, não relações causais.
* Parte da multicolinearidade permanece no conjunto de variáveis.
* A normalidade dos resíduos e a homocedasticidade não foram plenamente satisfeitas.
* Os resultados dependem da qualidade e cobertura do dataset analisado.

---

## 👨‍💻 Autor

Desenvolvido por **Brener Souza**

Estudante de Análise e Desenvolvimento de Sistemas | Aspirante a Cientista de Dados | Salesforce Administrator
