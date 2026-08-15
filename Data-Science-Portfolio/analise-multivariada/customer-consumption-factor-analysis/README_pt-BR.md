<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white">
  <img src="https://img.shields.io/badge/Factor%20Analysis-003B57?style=for-the-badge">
</p>

# 🎯 Análise Fatorial do Consumo de Clientes

Este projeto aplica análise fatorial a variáveis de consumo, resposta a campanhas, canais de compra, perfil familiar, renda e tempo de relacionamento dos clientes.

O estudo identifica dimensões latentes que ajudam a explicar o comportamento dos clientes e apoiam segmentação e estratégia de marketing.

---

## 📌 Problema de Negócio

Equipes de marketing e áreas comerciais precisam compreender quais dimensões comportamentais explicam os padrões de consumo dos clientes.

Quando muitas variáveis descrevem gastos, canais de compra, campanhas, perfil familiar e tempo de relacionamento, a interpretação direta se torna complexa. A análise fatorial ajuda a resumir essas variáveis em dimensões latentes mais claras.

### 📈 Principais Resultados

✅ O KMO global inicial alcançou aproximadamente **0,8768**

✅ Após remover indicadores de estado civil com baixo KMO, o KMO global aumentou para **0,881**

✅ O teste de Bartlett foi significativo, com valor-p próximo de zero

✅ Quatro fatores latentes foram selecionados e interpretados

✅ A rotação oblíqua foi preferida porque correlações entre fatores ultrapassaram 0,30 em magnitude

---

## 💼 Impacto para o Negócio

* Apoia segmentação de clientes por dimensões comportamentais interpretáveis.
* Ajuda equipes de marketing a compreender receptividade a campanhas.
* Conecta intensidade de consumo, perfil familiar e comportamento digital.
* Reduz a complexidade da análise de comportamento dos clientes.
* Fornece base estatística para estratégias comerciais mais direcionadas.

---

## 🎯 O Problema

O comportamento de consumo dos clientes é explicado por múltiplas variáveis observadas que podem refletir dimensões latentes mais amplas.

O desafio é identificar esses fatores ocultos e interpretá-los de forma útil para decisões de negócio.

---

## 🚀 Visão Geral

Pergunta principal do projeto:

> Quais fatores latentes explicam o comportamento de consumo dos clientes considerando renda, gastos por categoria, canais de compra, campanhas e tempo de relacionamento?

Para responder essa pergunta, foram aplicadas limpeza dos dados, engenharia de atributos, testes de adequação, extração de fatores e análise de rotação.

---

## 🧪 Abordagem

O projeto combina:

* Limpeza dos dados
* Engenharia de atributos
* Codificação de variáveis categóricas
* Regularização da renda
* Padronização das variáveis
* Teste de esfericidade de Bartlett
* Análise de KMO
* Análise fatorial
* Rotação Varimax
* Rotação oblíqua

---

## 🎯 Objetivos

* Identificar dimensões latentes por trás do comportamento de consumo dos clientes.
* Validar a adequação da análise fatorial com Bartlett e KMO.
* Remover variáveis que reduzem a adequação fatorial.
* Comparar estratégias de rotação.
* Traduzir fatores em interpretações orientadas ao negócio.

---

## 🧠 Metodologia

### 🔹 1. Limpeza dos Dados

O identificador dos clientes foi removido porque não contribuía para a identificação dos fatores latentes.

Registros com renda ausente foram removidos devido à baixa proporção no dataset.

---

### 🔹 2. Engenharia de Atributos

Ano de nascimento e data de cadastro foram transformados em idade do cliente e tempo de relacionamento.

Variáveis de escolaridade e estado civil foram codificadas para análise numérica.

---

### 🔹 3. Padronização

As variáveis selecionadas foram padronizadas para colocar renda, gastos, idade, tempo de relacionamento e indicadores de canais de compra em uma escala comum.

---

### 🔹 4. Testes de Adequação

O teste de Bartlett indicou correlações suficientes para análise fatorial.

O KMO global inicial foi **0,8768**. Após remover indicadores de estado civil com baixo KMO, o KMO global aumentou para **0,881**.

---

### 🔹 5. Extração de Fatores e Rotação

Quatro fatores foram extraídos e interpretados. Como algumas correlações entre fatores ultrapassaram 0,30 em magnitude, a rotação oblíqua foi preferida.

---

## 📊 Análises e Resultados

### 📌 Interpretação Final dos Fatores

| Fator | Interpretação |
| :--- | :--- |
| 1 | Intensidade e diversidade de consumo |
| 2 | Receptividade às campanhas de marketing |
| 3 | Perfil familiar e etapa de vida |
| 4 | Comportamento digital e sensibilidade a promoções |

**Insight**

O comportamento dos clientes foi explicado principalmente por intensidade de gastos, resposta a campanhas, perfil familiar e interação digital ou promocional.

---

## 🤖 Validação

O fluxo de análise fatorial foi validado por meio de:

* Teste de esfericidade de Bartlett
* KMO global
* Valores individuais de KMO
* Matriz de correlação dos fatores
* Comparação de rotações

---

## 🧠 Principais Descobertas

* Quatro fatores latentes foram identificados e interpretados.
* Indicadores de estado civil reduziram a adequação e foram removidos do modelo fatorial principal.
* As correlações entre fatores indicaram que as dimensões não eram totalmente independentes.
* A rotação oblíqua gerou uma interpretação mais realista do comportamento dos clientes.
* Os fatores podem apoiar segmentação e estratégia de marketing.

---

## 🚀 Diferenciais do Projeto

* 🔥 Análise fatorial aplicada a dados de marketing e consumo.
* 📊 KMO aprimorado após remoção de variáveis de baixa adequação.
* 🧠 Quatro dimensões latentes interpretáveis de clientes.
* 🔍 Escolha da rotação baseada nas correlações entre fatores.

---

## 🛠️ Tecnologias Utilizadas

* Python
* Pandas
* Matplotlib
* Scikit-Learn
* Factor Analyzer
* Jupyter Notebook

---

## 🏁 Conclusão

A análise fatorial final identificou quatro dimensões relevantes do comportamento dos clientes.

Esses fatores resumem padrões complexos de consumo, campanhas, perfil familiar e interação digital em dimensões interpretáveis que podem apoiar segmentação e estratégias de marketing direcionadas.

---

## 📌 Limitações

* A interpretação dos fatores depende de julgamento analítico.
* A análise é descritiva e não estabelece causalidade.
* Registros com renda ausente foram removidos devido à baixa proporção.
* Os resultados devem ser validados com desfechos externos de negócio.

---

## 👨‍💻 Autor

Desenvolvido por **Brener Souza**

Estudante de Análise e Desenvolvimento de Sistemas | Aspirante a Cientista de Dados | Salesforce Administrator
