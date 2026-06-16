
<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white">
  <img src="https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge">
  <img src="https://img.shields.io/badge/Seaborn-4C72B0?style=for-the-badge">
</p>

# 🎬 Movie Recommendation System (Hybrid Model)

Sistema de recomendação de filmes baseado em **similaridade híbrida**, combinando:

* 🎭 Conteúdo (gênero, elenco, palavras-chave, direção)
* 📊 Performance (nota, popularidade, número de votos)

Além da recomendação, o projeto realiza uma **análise estatística para validar se filmes similares também apresentam padrões semelhantes de avaliação**.

---

## 📌 Problema de Negócio

Plataformas de streaming e marketplaces de conteúdo precisam recomendar itens relevantes para aumentar engajamento, retenção e satisfação dos usuários.

Entretanto, sistemas baseados apenas em conteúdo podem ignorar aspectos importantes relacionados à percepção do público, enquanto abordagens focadas apenas em popularidade tendem a reforçar conteúdos já conhecidos.

Este projeto propõe um sistema de recomendação híbrido que combina características do conteúdo dos filmes com métricas reais de avaliação dos usuários para gerar recomendações mais relevantes e consistentes.

### 📈 Principais Resultados

✅ O modelo recomendou corretamente filmes pertencentes ao mesmo universo narrativo

✅ As recomendações apresentaram notas semelhantes ao filme de referência

✅ Foi observada baixa correlação entre popularidade e qualidade percebida

✅ O número de avaliações apresentou correlação positiva moderada com a nota dos filmes

✅ A combinação de conteúdo e performance gerou recomendações mais contextualizadas

---

## 💼 Impacto para o Negócio

* Demonstra como sistemas híbridos podem melhorar a relevância das recomendações.
* Reduz a dependência exclusiva de métricas de popularidade.
* Aumenta a capacidade de descoberta de conteúdos relacionados.
* Contribui para estratégias de retenção e engajamento de usuários.
* Mostra como técnicas de Data Science podem ser aplicadas em sistemas reais de recomendação.


## 🎯 O Problema

Plataformas com grandes catálogos enfrentam o desafio de recomendar conteúdos relevantes de forma eficiente.

Este projeto busca resolver esse problema combinando similaridade de conteúdo com métricas reais de avaliação dos usuários.

---

## 🚀 Visão Geral

A maioria dos sistemas de recomendação utiliza apenas conteúdo ou comportamento do usuário.
Neste projeto, foi proposta uma abordagem híbrida que responde à seguinte pergunta:

> Filmes semelhantes também apresentam padrões semelhantes de avaliação e popularidade?

---

## 🧪 Abordagem

Este projeto segue uma abordagem orientada a validação, onde o sistema de recomendação não é apenas construído, mas também analisado sob uma perspectiva estatística.

## 📌 Exemplo de Recomendação Gerada

Filme base: **The Hobbit: The Battle of the Five Armies**

Recomendações:

- The Hobbit: The Desolation of Smaug
- The Hobbit: An Unexpected Journey
- The Lord of the Rings: The Fellowship of the Ring
- The Lord of the Rings: The Two Towers
- The Lord of the Rings: The Return of the King

### Insight

O modelo demonstrou alta coerência semântica ao recomendar filmes pertencentes ao mesmo universo narrativo e com padrões semelhantes de avaliação.

📊 Observação: Os filmes recomendados pertencem ao mesmo universo e apresentam **notas semelhantes**, validando a coerência do modelo.

---

## 🎯 Objetivos

* Construir um sistema de recomendação baseado em similaridade de vetores
* Combinar conteúdo + métricas de desempenho
* Validar estatisticamente os resultados
* Investigar relações entre popularidade, votos e avaliação

---

## 🧠 Metodologia

### 🔹 1. Tratamento de Dados

* Remoção de valores nulos e duplicados
* Padronização de texto (lowercase, remoção de espaços)
* Conversão de colunas para listas
* Aplicação de stemming

---

### 🔹 2. Engenharia de Features

#### 📌 Vetor de Conteúdo

* Gêneros
* Palavras-chave
* Elenco
* Direção

#### 📌 Vetor de Performance

* `vote_average` (nota média)
* `popularity` (popularidade)
* `vote_count` (número de votos)

#### 📌 Vetor Híbrido

A similaridade final é definida como:

```
sim_final = α * sim_conteudo + β * sim_performance
```

Onde:

* α = 0.7 (peso do conteúdo)
* β = 0.3 (peso da performance)

---

### 🔹 3. Similaridade

Foi utilizada a **similaridade do cosseno** para medir a proximidade entre os filmes.

---

### 🔹 4. Sistema de Recomendação

Dado um filme de entrada, o sistema retorna os **top N filmes mais similares**, considerando o vetor híbrido.

---

## 📊 Análises e Validação do Modelo

Este conjunto de análises busca validar se o sistema de recomendação realmente captura padrões relevantes entre os filmes.

---

### 🎬 Filmes similares têm notas parecidas?

![Comparação de Notas](/Data-Science-Portfolio/matematica-estatistica/hybrid-recommendation-system/img/filmes_similares.png)

**Insight:**

> Os filmes recomendados apresentam notas próximas ao filme base, indicando que o modelo consegue capturar padrões semelhantes de avaliação.

---

### 📉 Popularidade e volume de avaliações influenciam a nota?


**Resultados:**

* Popularidade vs Nota → **0.27**
* Número de votos vs Nota → **0.31**

![Grafico Correlação](/Data-Science-Portfolio/matematica-estatistica/hybrid-recommendation-system/img/grafico_popularidade.png)


**Insight:**

> Ambas as variáveis apresentam correlação positiva fraca com a avaliação. Isso indica que fatores de visibilidade não são determinantes diretos de qualidade, embora exista leve tendência de validação coletiva no número de votos.

📎 Para análise completa e metodologia detalhada, consulte o notebook do projeto.

---

### 🎭 Existe padrão entre gêneros?

![Boxplot por Gênero](/Data-Science-Portfolio/matematica-estatistica/hybrid-recommendation-system/img/distribuicao_notas.png)

**Insight:**

> Alguns gêneros apresentam maior consistência e melhores avaliações médias, indicando padrões distintos de aceitação do público.

---

## 🤖 Validação do Sistema

Foi analisado se os filmes recomendados apresentam padrões semelhantes ao filme base.

**Resultado:**

> Observou-se que os filmes recomendados tendem a apresentar valores próximos de avaliação e popularidade, indicando que o modelo captura similaridade além do conteúdo.

---

## 🧠 Principais Insights

* A correlação entre popularidade e nota é fraca (0.27)
* O número de votos possui leve correlação com avaliação (0.31)
* Popularidade ≠ Qualidade
* O modelo híbrido captura nuances que não seriam percebidas apenas pelo conteúdo

---

## 🚀 Diferenciais do Projeto

* 🔥 Modelo híbrido (conteúdo + performance)
* 📊 Validação estatística dos resultados
* 🧠 Interpretação analítica (não apenas implementação)
* 🎯 Estrutura próxima de problemas reais de Data Science

---

## 🛠️ Tecnologias Utilizadas

* Python
* Pandas
* NumPy
* Scikit-learn
* Matplotlib
* Seaborn

---

## 🏁 Conclusão

O projeto demonstra que:

* Sistemas de recomendação podem ser aprimorados com dados de performance
* Similaridade de conteúdo isolada não captura toda a percepção do público
* A validação estatística é essencial para garantir qualidade nas recomendações

---

## 📌 Próximos Passos

* Aplicar clusterização (K-Means)
* Redução de dimensionalidade (PCA)
* Criar interface interativa com Streamlit
* Deploy do modelo

---

## 👨‍💻 Autor

Desenvolvido por **Brener Souza**
