
<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white">
  <img src="https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white">
  <img src="https://img.shields.io/badge/XGBoost-EB5B2A?style=for-the-badge&logo=xgboost&logoColor=white">
  <img src="https://img.shields.io/badge/Random%20Forest-228B22?style=for-the-badge">
</p>

# 🤖 Classificação Binária em Dados de Alta Dimensionalidade

Este projeto desenvolve e compara modelos de Machine Learning para resolver um problema de classificação binária em um conjunto de dados de alta dimensionalidade.

O estudo combina pré-processamento, divisão dos dados, balanceamento da classe de treinamento, padronização, comparação entre diferentes famílias de algoritmos, otimização de hiperparâmetros e validação cruzada estratificada.

---

## 📌 Problema de Negócio

Problemas de classificação binária aparecem em diferentes contextos, como detecção de fraude, identificação de risco, diagnóstico, manutenção preditiva e previsão de eventos.

Neste projeto, o conjunto de dados contém **178 variáveis de entrada anonimizadas** e uma variável alvo binária denominada `LABEL_TARGET`.

O desafio consiste em desenvolver um modelo capaz de identificar corretamente a classe positiva, mesmo diante de:

- Alta dimensionalidade
- Desbalanceamento da variável alvo
- Ausência de informações semânticas sobre as variáveis
- Possibilidade de relações não lineares entre os atributos

Como o contexto original do evento não foi disponibilizado, a análise concentra-se na qualidade estatística e preditiva dos modelos, sem atribuir interpretações de negócio não sustentadas às variáveis.

### 📈 Principais Resultados

✅ O Random Forest apresentou a maior AUC entre os modelos avaliados

✅ AUC de aproximadamente **0,994 no conjunto de teste**

✅ AUC de aproximadamente **0,996 no conjunto de validação final**

✅ Recall de aproximadamente **98,6% no teste**

✅ Recall de aproximadamente **99,1% na validação**

✅ Validação cruzada do modelo padrão com AUC média de aproximadamente **0,9945**

✅ O modelo padrão apresentou desempenho ligeiramente superior e menor variabilidade que a versão otimizada

✅ O modelo final foi escolhido considerando desempenho, estabilidade e parcimônia

---

## 💼 Impacto Analítico

- Demonstra a construção de um pipeline completo de classificação.
- Mostra como tratar classes desbalanceadas sem alterar os conjuntos de teste e validação.
- Compara algoritmos lineares, probabilísticos e baseados em árvores.
- Demonstra a importância da AUC e do recall em problemas com classes desbalanceadas.
- Utiliza validação cruzada para avaliar estabilidade e capacidade de generalização.
- Mostra que a otimização de hiperparâmetros nem sempre produz um modelo superior.
- Reforça a importância de selecionar modelos com base em múltiplas métricas.

---

## 🎯 O Problema

O objetivo principal do projeto foi responder à seguinte pergunta:

> Qual modelo de Machine Learning apresenta a melhor capacidade de identificar a classe positiva em um conjunto de dados de alta dimensionalidade e com variável alvo desbalanceada?

Para responder essa pergunta, foram comparados cinco modelos:

1. Regressão Logística baseline
2. Regressão Logística com regularização L2
3. Gaussian Naive Bayes
4. XGBoost
5. Random Forest

---

## 🚀 Visão Geral

O conjunto de dados possui:

| Característica | Valor |
| :--- | ---: |
| Registros | 11.500 |
| Variáveis de entrada | 178 |
| Variável alvo | `LABEL_TARGET` |
| Classes | 2 |
| Valores ausentes | 0 |
| Colunas duplicadas | 0 |

A variável alvo apresentava a seguinte distribuição:

| Classe | Registros | Proporção |
| :--- | ---: | ---: |
| Classe 0 | 9.200 | 80% |
| Classe 1 | 2.300 | 20% |

Essa distribuição caracteriza um problema de classificação desbalanceada.

---

## 🧪 Abordagem

O projeto foi dividido em dois notebooks.

### Notebook 1 — Pré-processamento

- Carregamento e inspeção dos dados
- Conversão da variável alvo
- Análise da distribuição das classes
- Separação em treino, validação e teste
- Aplicação de undersampling no conjunto de treino
- Salvamento dos conjuntos processados

### Notebook 2 — Modelagem

- Padronização das variáveis
- Construção de funções auxiliares
- Treinamento de diferentes algoritmos
- Comparação de métricas
- Seleção do modelo
- Otimização de hiperparâmetros
- Validação cruzada estratificada
- Avaliação final em treino, teste e validação
- Salvamento do modelo final

---

## 🎯 Objetivos

- Preparar os dados para modelagem.
- Preservar a distribuição original nos conjuntos de teste e validação.
- Balancear apenas o conjunto de treinamento.
- Comparar diferentes famílias de algoritmos.
- Avaliar AUC, acurácia, recall, precisão e especificidade.
- Selecionar o modelo com melhor capacidade de generalização.
- Verificar se a otimização de hiperparâmetros gera ganhos consistentes.
- Avaliar a estabilidade do modelo com validação cruzada.
- Salvar o modelo final para uso posterior.

---

## 🧠 Metodologia

### 🔹 1. Análise Inicial dos Dados

O conjunto de dados foi analisado para verificar:

- Dimensões
- Tipos das variáveis
- Valores ausentes
- Colunas duplicadas
- Distribuição da variável alvo

Não foram identificados valores ausentes ou colunas duplicadas.

---

### 🔹 2. Conversão da Variável Alvo

A variável `LABEL_TARGET`, inicialmente booleana, foi convertida para valores inteiros:

```python
df["LABEL_TARGET"] = df["LABEL_TARGET"].astype(int)
````

As classes passaram a ser representadas como:

* `0`: classe negativa
* `1`: classe positiva

---

### 🔹 3. Divisão dos Dados

O conjunto de dados foi dividido em:

| Conjunto    | Registros | Proporção positiva |
| :---------- | --------: | -----------------: |
| Treinamento |     8.050 |             20,15% |
| Validação   |     1.725 |             19,19% |
| Teste       |     1.725 |             20,12% |

Os conjuntos de validação e teste mantiveram uma distribuição próxima à distribuição original.

---

### 🔹 4. Balanceamento do Conjunto de Treinamento

Foi aplicado undersampling da classe majoritária exclusivamente no conjunto de treinamento.

Após o balanceamento:

| Classe   | Registros |
| :------- | --------: |
| Classe 0 |     1.622 |
| Classe 1 |     1.622 |

O conjunto final de treinamento passou a conter:

* 3.244 registros
* 50% de registros da classe 0
* 50% de registros da classe 1

Essa estratégia evitou alterar artificialmente a distribuição dos conjuntos utilizados para avaliação.

---

### 🔹 5. Padronização das Variáveis

As variáveis foram padronizadas utilizando `StandardScaler`.

O objeto foi ajustado apenas com os dados de treinamento e posteriormente aplicado aos conjuntos de teste e validação.

Essa abordagem reduz o risco de vazamento de informação entre os conjuntos.

---

## 🤖 Modelos Avaliados

### 🔹 Regressão Logística — Baseline

| Métrica        | Validação |
| :------------- | --------: |
| AUC            |     0,496 |
| Acurácia       |     0,681 |
| Recall         |     0,432 |
| Precisão       |     0,298 |
| Especificidade |     0,744 |

O modelo apresentou desempenho próximo de uma classificação aleatória em relação à AUC.

---

### 🔹 Regressão Logística com Regularização L2

Foi aplicada regularização L2 utilizando:

```python
C=0.1
solver="liblinear"
```

| Métrica        | Validação |
| :------------- | --------: |
| AUC            |     0,496 |
| Acurácia       |     0,658 |
| Recall         |     0,429 |
| Precisão       |     0,275 |
| Especificidade |     0,716 |

A regularização não trouxe melhora relevante em relação ao modelo baseline.

---

### 🔹 Gaussian Naive Bayes

| Métrica        | Validação |
| :------------- | --------: |
| AUC            |     0,983 |
| Acurácia       |     0,954 |
| Recall         |     0,888 |
| Precisão       |     0,883 |
| Especificidade |     0,970 |

A mudança para uma abordagem probabilística produziu um ganho expressivo de desempenho.

---

### 🔹 XGBoost

| Métrica        | Validação |
| :------------- | --------: |
| AUC            |     0,992 |
| Acurácia       |     0,962 |
| Recall         |     0,968 |
| Precisão       |     0,862 |
| Especificidade |     0,961 |

O XGBoost apresentou excelente desempenho, sugerindo a presença de padrões não lineares nos dados.

---

### 🔹 Random Forest

| Métrica        | Validação |
| :------------- | --------: |
| AUC            |     0,994 |
| Acurácia       |     0,950 |
| Recall         |     0,986 |
| Precisão       |     0,809 |
| Especificidade |     0,936 |

O Random Forest apresentou:

* Maior AUC
* Maior recall
* Excelente capacidade de identificação da classe positiva

Por esse motivo, foi selecionado para a etapa de otimização.

---

## 📊 Comparação dos Modelos

| Modelo                       |       AUC |  Acurácia |    Recall |  Precisão |
| :--------------------------- | --------: | --------: | --------: | --------: |
| Random Forest                | **0,994** |     0,950 | **0,986** |     0,809 |
| XGBoost                      |     0,992 | **0,962** |     0,968 |     0,862 |
| Gaussian Naive Bayes         |     0,983 |     0,954 |     0,888 | **0,883** |
| Regressão Logística L2       |     0,496 |     0,658 |     0,429 |     0,275 |
| Regressão Logística baseline |     0,496 |     0,681 |     0,432 |     0,298 |

O Random Forest foi selecionado principalmente por apresentar a maior AUC e o maior recall.

---

## ⚙️ Otimização de Hiperparâmetros

O Random Forest foi otimizado utilizando:

* `RandomizedSearchCV`
* 30 combinações de hiperparâmetros
* Validação cruzada estratificada com cinco folds
* AUC como métrica principal

Os melhores hiperparâmetros encontrados foram:

```python
{
    "n_estimators": 200,
    "min_samples_split": 2,
    "min_samples_leaf": 1,
    "max_features": "sqrt",
    "max_depth": 15,
    "class_weight": None,
    "bootstrap": True
}
```

A melhor AUC média obtida durante a busca foi aproximadamente:

```text
0,9936
```

---

## 🔍 Random Forest Padrão versus Otimizado

Para verificar se a otimização trouxe ganhos reais, os dois modelos foram comparados por validação cruzada.

| Modelo                  |  AUC média | Desvio-padrão |
| :---------------------- | ---------: | ------------: |
| Random Forest padrão    | **0,9945** |    **0,0016** |
| Random Forest otimizado |     0,9936 |        0,0022 |

O Random Forest padrão apresentou:

* AUC média ligeiramente superior
* Menor variabilidade entre os folds
* Menor complexidade de configuração
* Desempenho mais estável

Assim, o modelo padrão foi mantido como modelo final, seguindo o princípio da parcimônia.

---

## ✅ Avaliação Final

| Conjunto    |   AUC | Acurácia | Recall | Precisão | Especificidade |
| :---------- | ----: | -------: | -----: | -------: | -------------: |
| Treinamento | 0,999 |    0,966 |  1,000 |    0,856 |          0,956 |
| Teste       | 0,994 |    0,950 |  0,986 |    0,809 |          0,936 |
| Validação   | 0,996 |    0,963 |  0,991 |    0,843 |          0,950 |

Os resultados indicam alta capacidade de discriminação e excelente sensibilidade para a classe positiva.

A proximidade entre os resultados de teste e validação também fornece evidências de estabilidade do modelo.

---

## 🧠 Principais Descobertas

* Os modelos lineares não conseguiram representar adequadamente os padrões dos dados.
* O Gaussian Naive Bayes apresentou melhora expressiva em relação à Regressão Logística.
* XGBoost e Random Forest obtiveram os melhores desempenhos.
* O Random Forest apresentou a maior AUC e o maior recall.
* A otimização não produziu ganhos consistentes em relação ao modelo padrão.
* A validação cruzada confirmou a estabilidade do Random Forest padrão.
* A seleção do modelo deve considerar desempenho, variabilidade e complexidade.
* A elevada dimensionalidade não impediu que modelos baseados em árvores identificassem padrões relevantes.

---

## 🚀 Destaques do Projeto

* 🔥 Pipeline completo de classificação supervisionada.
* 📊 Conjunto de dados com 178 variáveis de entrada.
* ⚖️ Tratamento de desbalanceamento com undersampling.
* 🤖 Comparação entre cinco modelos de Machine Learning.
* 📈 Avaliação por AUC, acurácia, recall, precisão e especificidade.
* 🔍 Otimização com Randomized Search.
* ✅ Validação cruzada estratificada.
* 🧠 Seleção baseada em desempenho, estabilidade e parcimônia.
* 💾 Salvamento do modelo final e do objeto de padronização.

---

## 🛠️ Tecnologias Utilizadas

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* XGBoost
* Pickle
* Jupyter Notebook

---

## 🏁 Conclusão

Este projeto teve como objetivo desenvolver e avaliar modelos capazes de realizar uma classificação binária em um conjunto de dados de alta dimensionalidade.

Foram comparadas diferentes famílias de algoritmos, incluindo modelos lineares, probabilísticos e baseados em árvores.

A Regressão Logística apresentou AUC próxima de 0,50, indicando dificuldade em representar os padrões presentes nos dados. Em contraste, Gaussian Naive Bayes, XGBoost e Random Forest apresentaram desempenho significativamente superior.

O Random Forest obteve o melhor equilíbrio entre as métricas avaliadas, alcançando AUC de aproximadamente 0,994 no teste e 0,996 na validação, além de recall superior a 98% em ambos os conjuntos.

Embora a versão otimizada também tenha apresentado excelente desempenho, a validação cruzada demonstrou que o modelo padrão possuía AUC média ligeiramente superior, menor variabilidade e menor complexidade.

Dessa forma, o Random Forest padrão foi selecionado como modelo final, seguindo o princípio da parcimônia.

Os resultados demonstram que a avaliação de modelos não deve se limitar a uma única divisão dos dados ou a uma métrica isolada. Validação cruzada, estabilidade, capacidade de generalização e complexidade também devem fazer parte do processo de seleção.

---

## 📌 Limitações

* As variáveis foram anonimizadas, impossibilitando uma interpretação individual dos atributos.
* O contexto de negócio da variável alvo não foi disponibilizado.
* O undersampling remove parte dos registros da classe majoritária.
* O excelente desempenho pode estar relacionado a padrões específicos do conjunto de dados.
* O projeto não incluiu análise de explicabilidade com SHAP ou Permutation Importance.
* O modelo ainda precisaria ser validado em dados externos antes de uma aplicação real.
* Não foi realizada análise de custo de falsos positivos e falsos negativos.

---

## 👨‍💻 Autor

Desenvolvido por **Brener Souza**

Estudante de Data Science | Salesforce Administration | CRM & Analytics
