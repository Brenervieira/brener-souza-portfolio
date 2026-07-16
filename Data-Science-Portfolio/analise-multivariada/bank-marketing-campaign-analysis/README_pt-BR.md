<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white">
  <img src="https://img.shields.io/badge/XGBoost-EB5B2A?style=for-the-badge&logo=xgboost&logoColor=white">
  <img src="https://img.shields.io/badge/Logistic%20Regression-003B57?style=for-the-badge">
</p>

# 🏦 Análise de Campanha de Marketing Bancário

Este projeto aplica técnicas de Análise Multivariada e Machine Learning para identificar quais características dos clientes, condições financeiras e variáveis da campanha estão associadas à aceitação de uma oferta de depósito a prazo.

O estudo combina tratamento de dados ausentes, imputação com modelos supervisionados, balanceamento de classes e Regressão Logística para transformar dados de campanha em recomendações orientadas ao negócio.

---

## 📂 Fonte dos Dados

O conjunto de dados foi carregado diretamente de uma fonte pública durante a execução do notebook e, por isso, não está armazenado neste repositório.

Para reproduzir o projeto, basta executar o notebook com conexão à internet.

## 📌 Problema de Negócio

Uma instituição financeira realiza campanhas de marketing por telefone para oferecer produtos de investimento aos seus clientes.

Entretanto, grande parte dos contatos não resulta em conversão, aumentando os custos operacionais, consumindo o tempo da equipe comercial e podendo causar fadiga nos clientes abordados repetidamente.

O desafio consiste em compreender quais características estão associadas a uma maior probabilidade de aceite, permitindo que a instituição direcione melhor seus contatos e desenvolva campanhas mais eficientes.

### 📈 Principais Resultados

✅ A duração da ligação apresentou a associação positiva mais forte com a conversão, com **odds ratio de aproximadamente 2,79**

✅ Clientes com financiamento habitacional apresentaram menor chance de aceite, com **odds ratio de aproximadamente 0,59**

✅ Um número maior de contatos durante a mesma campanha esteve associado à redução da probabilidade de conversão, com **odds ratio de aproximadamente 0,69**

✅ Histórico de contatos anteriores, escolaridade e saldo bancário apresentaram associações positivas com o aceite

✅ O XGBoost ponderado melhorou o reconhecimento da categoria minoritária de escolaridade, alcançando **recall de aproximadamente 0,69 para a classe primary**

✅ A imputação de `education` foi realizada priorizando equilíbrio entre classes, e não apenas acurácia global

---

## 💼 Impacto para o Negócio

* Apoia a identificação de perfis de clientes mais receptivos às campanhas.
* Reduz a dependência de abordagens indiscriminadas e repetitivas.
* Sugere limitar tentativas excessivas de contato para evitar fadiga.
* Permite compreender como situação financeira e histórico de relacionamento influenciam a conversão.
* Demonstra como Machine Learning pode apoiar a qualidade dos dados antes da análise de negócio.
* Contribui para campanhas mais direcionadas, eficientes e orientadas por dados.

---

## 🎯 O Problema

Quais fatores mais influenciam a decisão de um cliente em aceitar ou recusar uma oferta de depósito a prazo em uma campanha bancária?

Para responder essa pergunta, foi necessário lidar com dois desafios:

1. Tratar dados ausentes sem introduzir viés excessivo nas informações.
2. Interpretar quais variáveis apresentam associação positiva ou negativa com a conversão.

---

## 🚀 Visão Geral

O projeto foi desenvolvido a partir do Bank Marketing Dataset, composto por **45.211 registros** e variáveis relacionadas a:

* Perfil sociodemográfico
* Situação financeira
* Histórico bancário
* Características do contato
* Histórico de campanhas anteriores
* Resultado da campanha

A variável alvo indica se o cliente aceitou ou não a oferta de depósito a prazo.

A distribuição da variável alvo apresentou forte desbalanceamento:

| Resultado   | Registros |
| :---------- | --------: |
| Não aceitou |    39.922 |
| Aceitou     |     5.289 |

---

## 🧪 Abordagem

O projeto combina:

* Análise Exploratória de Dados
* Tratamento de Valores Ausentes
* Codificação de Variáveis Categóricas
* Random Forest
* Balanceamento de Classes
* XGBoost com ponderação por amostra
* Imputação com Machine Learning
* Padronização de Variáveis
* Regressão Logística
* Interpretação de Coeficientes
* Análise de Odds Ratios

---

## 🎯 Objetivos

* Identificar variáveis associadas à aceitação da campanha.
* Tratar valores ausentes de maneira adequada ao contexto de cada variável.
* Utilizar Machine Learning para imputar a variável `education`.
* Comparar modelos de imputação considerando classes desbalanceadas.
* Reduzir o viés em favor da categoria majoritária.
* Interpretar os coeficientes da Regressão Logística.
* Traduzir os resultados analíticos em recomendações de negócio.

---

## 🧠 Metodologia

### 🔹 1. Compreensão dos Dados

O conjunto de dados foi inspecionado para identificar:

* Tipos das variáveis
* Valores ausentes
* Distribuição da variável alvo
* Frequência das categorias
* Características financeiras e sociodemográficas

Foram encontrados valores ausentes principalmente em:

| Variável    | Valores ausentes |
| :---------- | ---------------: |
| `job`       |              288 |
| `education` |            1.857 |
| `contact`   |           13.020 |
| `poutcome`  |           36.959 |

---

### 🔹 2. Tratamento dos Valores Ausentes

Cada variável foi tratada de acordo com seu significado:

* `job`: preenchida com a moda, pois possuía apenas aproximadamente 0,64% de valores ausentes.
* `contact`: preenchida com `unknown`.
* `poutcome`: preenchida com `not_contacted_before`, representando clientes sem resultado registrado em campanhas anteriores.
* `education`: tratada por imputação utilizando Machine Learning.

---

### 🔹 3. Preparação das Variáveis

As variáveis binárias foram convertidas para valores numéricos:

* `default`
* `housing`
* `loan`

As variáveis `job` e `marital` foram transformadas utilizando One-Hot Encoding.

A escolaridade foi codificada como:

| Escolaridade | Código |
| :----------- | -----: |
| Primary      |      0 |
| Secondary    |      1 |
| Tertiary     |      2 |

---

### 🔹 4. Random Forest Base

O primeiro modelo avaliado para imputação de `education` foi um Random Forest sem balanceamento.

### Resultado

* Acurácia aproximada: **0,70**
* Recall da classe `primary`: **0,35**
* F1-score macro: **0,63**

Embora o modelo apresentasse boa acurácia global, demonstrou dificuldade em reconhecer a classe minoritária `primary`.

---

### 🔹 5. Random Forest Balanceado

Foi testado um segundo Random Forest utilizando:

```python
class_weight="balanced"
```

### Resultado

* Acurácia aproximada: **0,70**
* Recall da classe `primary`: **0,32**
* F1-score macro: **0,62**

A ponderação automática não produziu melhoria na identificação da categoria minoritária.

---

### 🔹 6. XGBoost com Ponderação por Amostra

Foi treinado um XGBoost utilizando pesos calculados para compensar o desbalanceamento entre as classes.

### Resultado

| Classe    | Precision | Recall | F1-score |
| :-------- | --------: | -----: | -------: |
| Primary   |      0,43 |   0,69 |     0,53 |
| Secondary |      0,77 |   0,62 |     0,69 |
| Tertiary  |      0,72 |   0,74 |     0,73 |

* Acurácia aproximada: **0,67**
* F1-score macro: **0,65**
* Recall macro: **0,68**

Apesar da redução na acurácia global, o modelo apresentou melhor equilíbrio entre as classes e aumentou significativamente o reconhecimento da categoria `primary`.

Por essa razão, o XGBoost ponderado foi selecionado para realizar a imputação final da variável `education`.

---

## ⚖️ Critério de Seleção do Modelo de Imputação

A escolha do modelo não foi baseada apenas na acurácia.

Como o objetivo era imputar valores ausentes sem favorecer excessivamente a classe majoritária, foram priorizados:

* Recall das classes minoritárias
* F1-score macro
* Equilíbrio entre as categorias
* Redução de viés na imputação

Essa decisão evitou que a maior parte dos registros ausentes fosse automaticamente classificada como `secondary`, apenas por ser a categoria mais frequente.

---

## 📊 Análise dos Fatores Associados à Conversão

Após o tratamento dos dados, foi aplicada Regressão Logística para avaliar como cada variável se relacionava com a probabilidade de aceite da campanha.

As variáveis foram padronizadas antes do treinamento, permitindo uma comparação mais adequada entre os coeficientes.

---

### 📌 Associações Positivas

| Variável            | Odds Ratio | Interpretação                                                   |
| :------------------ | ---------: | :-------------------------------------------------------------- |
| `duration`          |       2,79 | Ligações mais longas estiveram fortemente associadas ao aceite  |
| `pdays`             |       1,34 | Histórico temporal de contatos apresentou associação positiva   |
| `education_encoded` |       1,20 | Maior escolaridade esteve associada a maior chance de conversão |
| `previous`          |       1,16 | Contatos anteriores apresentaram associação positiva            |
| `job_student`       |       1,10 | Clientes estudantes apresentaram associação positiva            |
| `marital_single`    |       1,10 | Clientes solteiros apresentaram associação positiva             |
| `job_retired`       |       1,09 | Clientes aposentados apresentaram associação positiva           |
| `balance`           |       1,07 | Maior saldo apresentou associação positiva leve                 |

---

### 📌 Associações Negativas

| Variável          | Odds Ratio | Interpretação                                                              |
| :---------------- | ---------: | :------------------------------------------------------------------------- |
| `housing`         |       0,59 | Financiamento habitacional esteve associado a menor chance de aceite       |
| `campaign`        |       0,69 | Muitas tentativas na mesma campanha reduziram a probabilidade de conversão |
| `loan`            |       0,80 | Empréstimo pessoal ativo esteve associado a menor chance de aceite         |
| `job_blue-collar` |       0,82 | Essa categoria ocupacional apresentou associação negativa                  |
| `job_housemaid`   |       0,90 | Associação negativa com a conversão                                        |
| `job_technician`  |       0,90 | Associação negativa com a conversão                                        |

---

## ⚠️ Interpretação da Variável `duration`

A duração da ligação foi o fator com maior associação positiva.

Entretanto, essa variável só é conhecida depois que o contato já começou ou terminou.

Portanto:

* Ela é útil para compreender o comportamento da campanha.
* Pode indicar maior interesse ou engajamento durante a ligação.
* Não deve ser utilizada para selecionar previamente quais clientes serão contatados.
* Seu uso em modelos de seleção pré-campanha poderia causar vazamento de informação.

---

## 🧠 Principais Descobertas

* Clientes com financiamento habitacional ou empréstimo pessoal ativo apresentaram menor probabilidade de aceite.
* Maior saldo bancário apresentou associação positiva, embora moderada.
* Contatos anteriores estiveram associados a maior chance de conversão.
* Maior escolaridade apresentou associação positiva com o aceite.
* Estudantes e aposentados demonstraram perfis relativamente mais receptivos.
* Muitas tentativas de contato durante a mesma campanha estiveram associadas à redução da conversão.
* A duração da ligação foi o fator mais forte, mas deve ser interpretada apenas após o contato.
* O tratamento de classes desbalanceadas foi essencial para uma imputação mais justa da escolaridade.

---

## 🚀 Destaques do Projeto

* 🔥 Aplicação de Machine Learning para imputação de dados ausentes.
* ⚖️ Comparação de modelos sob desbalanceamento de classes.
* 🧠 Escolha baseada em F1-score macro e recall das classes minoritárias.
* 📊 Aplicação de Regressão Logística para interpretação de fatores.
* 🔍 Utilização de odds ratios para traduzir os coeficientes.
* 💼 Conversão dos resultados em recomendações para campanhas bancárias.
* ⚠️ Identificação do risco de vazamento de informação na variável `duration`.

---

## 💡 Recomendações de Negócio

Com base nos resultados, a instituição pode:

* Priorizar clientes com maior disponibilidade financeira e histórico de relacionamento.
* Considerar escolaridade e perfil ocupacional na segmentação, sem utilizar essas características de maneira discriminatória.
* Evitar contatos excessivos durante uma mesma campanha.
* Desenvolver estratégias específicas para clientes com financiamentos ou empréstimos ativos.
* Utilizar informações de contatos anteriores para melhorar a priorização.
* Analisar a duração das chamadas como indicador posterior de engajamento, e não como variável prévia de seleção.

---

## 🛠️ Tecnologias Utilizadas

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* XGBoost
* UCI Machine Learning Repository
* Jupyter Notebook

---

## 🏁 Conclusão

O projeto demonstrou como técnicas de Análise Multivariada e Machine Learning podem ser combinadas para tratar problemas de qualidade dos dados e compreender os fatores associados à conversão em campanhas bancárias.

Na etapa de imputação da variável `education`, o Random Forest apresentou maior acurácia global, mas demonstrou dificuldade em reconhecer a classe minoritária. O XGBoost ponderado apresentou melhor equilíbrio entre as categorias, aumentando o recall da classe `primary` de aproximadamente 0,35 para 0,69.

Como o objetivo da imputação era reduzir o viés em favor da classe majoritária, o XGBoost foi selecionado mesmo apresentando acurácia global ligeiramente inferior.

A Regressão Logística revelou que fatores financeiros, histórico de contato, escolaridade e intensidade da campanha estão associados à decisão do cliente. Os resultados também indicaram que abordagens excessivas podem reduzir a probabilidade de aceite.

O projeto reforça que a seleção de modelos não deve considerar apenas uma métrica isolada. É necessário avaliar o objetivo do problema, o comportamento das classes e o impacto que as decisões analíticas podem gerar no contexto de negócio.

---

## 📌 Limitações

* A análise identifica associações, não relações causais.
* A variável `duration` não está disponível antes da realização do contato.
* O modelo de imputação não elimina completamente o risco de classificações incorretas.
* Algumas variáveis categóricas foram simplificadas durante o processamento.
* O forte desbalanceamento da variável alvo deve ser considerado em futuros modelos preditivos.
* Os resultados são específicos do conjunto de dados analisado.
* O projeto não avaliou o impacto financeiro direto das recomendações propostas.

---

## 👨‍💻 Autor

Desenvolvido por **Brener Souza**

Estudante de Data Science | Salesforce Administration | CRM & Analytics