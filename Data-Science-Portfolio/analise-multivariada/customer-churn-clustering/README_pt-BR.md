<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white">
  <img src="https://img.shields.io/badge/K--Means-003B57?style=for-the-badge">
</p>

# 🎯 Clusterização de Clientes com Churn

Este projeto aplica K-Means para segmentar clientes de assinatura com base em idade, gasto mensal, tempo de assinatura, taxa de uso, tickets de suporte e comportamento de cancelamento.

O estudo compara soluções de clusterização com e sem outliers e interpreta os grupos de clientes para estratégias de ativação, retenção e recuperação.

---

## 📌 Problema de Negócio

Empresas baseadas em assinatura precisam compreender diferentes perfis de clientes e identificar grupos com maior risco de cancelamento.

Ações genéricas de retenção podem desperdiçar recursos e não atender às necessidades de cada segmento. A clusterização ajuda a descrever grupos comportamentais e apoiar estratégias mais direcionadas.

### 📈 Principais Resultados

✅ A solução final selecionou **3 clusters**

✅ O modelo com e sem outliers apresentou o mesmo silhouette score: **0,4494**

✅ A remoção de outliers não alterou a estrutura dos clusters

✅ O Cluster 1 concentrou clientes de alto valor com comportamento crítico de cancelamento

✅ O Cluster 2 representou um grupo intermediário com risco elevado de churn

---

## 💼 Impacto para o Negócio

* Apoia a segmentação de clientes em negócios de receita recorrente.
* Ajuda a priorizar ações de retenção por perfil de cliente.
* Identifica grupos de alto valor com comportamento crítico de cancelamento.
* Apoia estratégias de ativação para clientes novos e de baixo consumo.
* Oferece base descritiva para ações comerciais e de suporte mais direcionadas.

---

## 🎯 O Problema

A empresa precisa ir além de ações amplas de churn e compreender quais grupos de clientes compartilham padrões semelhantes de uso, gasto, tempo de assinatura e interação com suporte.

O objetivo é criar segmentos interpretáveis sem tratar a clusterização como previsão causal individual.

---

## 🚀 Visão Geral

Pergunta principal do projeto:

> Quais segmentos de clientes podem ser identificados a partir do comportamento de assinatura e como eles diferem em risco de churn?

Para responder essa pergunta, foi aplicada clusterização com K-Means, avaliada por análise de silhueta e interpretação de negócio.

---

## 🧪 Abordagem

O projeto combina:

* Análise Exploratória dos Dados (EDA)
* Limpeza dos dados
* Padronização das variáveis
* Clusterização com K-Means
* Método do cotovelo
* Análise de silhueta
* Comparação de outliers
* Interpretação dos clusters

---

## 🎯 Objetivos

* Segmentar clientes de acordo com comportamento de assinatura.
* Comparar soluções de clusterização com diferentes números de grupos.
* Avaliar o efeito dos outliers na estrutura dos clusters.
* Interpretar os clusters sob a perspectiva de negócio.
* Apoiar estratégias de retenção, recuperação e ativação.

---

## 🧠 Metodologia

### 🔹 1. Análise Exploratória dos Dados

O dataset foi inspecionado para compreender variáveis comportamentais, distribuições e possíveis outliers.

---

### 🔹 2. Padronização das Variáveis

As variáveis foram padronizadas para evitar que atributos com maior escala dominassem o cálculo de distância do K-Means.

---

### 🔹 3. Seleção dos Clusters

O método do cotovelo e a análise de silhueta foram utilizados para comparar possíveis números de clusters.

A solução com 4 clusters foi avaliada inicialmente, mas a inspeção visual indicou sobreposição entre grupos. A solução com 3 clusters produziu perfis mais claros e interpretáveis.

---

### 🔹 4. Comparação com Outliers

Foram comparados modelos com e sem outliers. O silhouette score permaneceu **0,4494**, indicando que a remoção dos outliers não alterou a estrutura dos clusters.

---

## 📊 Análises e Resultados

### 📌 Interpretação Final dos Clusters

| Cluster | Interpretação |
| :--- | :--- |
| 0 | Clientes novos, de menor consumo e majoritariamente retidos |
| 1 | Clientes maduros, de alto valor e com churn crítico |
| 2 | Clientes intermediários com risco elevado de cancelamento |

**Insight**

A interpretação final manteve todos os registros porque os outliers afetaram a amplitude visual dos gráficos, mas não modificaram a composição dos grupos.

---

## 🤖 Validação

A solução de clusterização foi avaliada por meio de:

* Método do cotovelo
* Silhouette score
* Inspeção visual da separação dos clusters
* Comparação com e sem outliers

---

## 🧠 Principais Descobertas

* A solução com 3 clusters foi mais interpretável que a solução com 4 clusters.
* O Cluster 0 representa clientes novos, de baixo consumo e baixo churn.
* O Cluster 1 concentra clientes de alto valor com comportamento crítico de cancelamento.
* O Cluster 2 representa um grupo intermediário com risco elevado de churn.
* Interações de suporte e padrões de uso ajudaram a diferenciar perfis de clientes.

---

## 🚀 Diferenciais do Projeto

* 🔥 Segmentação de clientes com K-Means.
* 📊 Comparação entre soluções de clusterização.
* 🧠 Interpretação de perfis de clientes orientada ao negócio.
* 🔍 Avaliação do impacto dos outliers antes da seleção final.

---

## 🛠️ Tecnologias Utilizadas

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* Threadpoolctl
* Jupyter Notebook

---

## 🏁 Conclusão

A clusterização com K-Means identificou três perfis interpretáveis de clientes que podem apoiar estratégias de ativação, retenção e recuperação.

O resultado é descritivo e útil para segmentação de negócio, mas não deve ser interpretado como causal nem como previsão individual de churn.

---

## 📌 Limitações

* Clusterização não estabelece causalidade.
* A base é pequena, com 99 clientes.
* A variável de cancelamento apoia a interpretação, mas não substitui um modelo supervisionado de previsão de churn.
* Os resultados devem ser validados com dados operacionais e financeiros adicionais.

---

## 👨‍💻 Autor

Desenvolvido por **Brener Souza**

Estudante de Análise e Desenvolvimento de Sistemas | Aspirante a Cientista de Dados | Salesforce Administrator
