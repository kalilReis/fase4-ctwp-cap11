# FIAP - Faculdade de Informática e Administração Paulista

<p align="center">
<a href= "https://www.fiap.com.br/"><img src="assets/logo-fiap.png" alt="FIAP - Faculdade de Informática e Admnistração Paulista" border="0" width=40% height=40%></a>
</p>

<br>

# FASE 04/CTWP/Cap11

## Kalil

## 👨‍🎓 Integrantes

- <a href="https://github.com/kalilReis">Kalil Reis de Sisto</a>

## 👩‍🏫 Professores

### Tutor(a)

- <a href="https://www.linkedin.com/company/inova-fusca">Leonardo Ruiz Orabona</a>

### Coordenador(a)

- <a href="https://www.linkedin.com/company/inova-fusca"> André Godoy acho</a>

## 📜 Descrição

## 🎯 Objetivo

Desenvolver um modelo de machine learning utilizando a metodologia **CRISP-DM** para classificar amostras de sementes de trigo (Kama, Rosa, Canadian) com base em características físicas.

---

## 📁 Dataset Utilizado

- **Fonte**: [UCI Machine Learning Repository – Seeds Dataset](https://archive.ics.uci.edu/dataset/236/seeds)
- **Total de Amostras**: 210
- **Características**:
  - Área
  - Perímetro
  - Compacidade
  - Comprimento do Núcleo
  - Largura do Núcleo
  - Coeficiente de Assimetria
  - Comprimento do Sulco do Núcleo

---

## 📊 1. Análise e Pré-processamento dos Dados

- Leitura do dataset (`seeds_dataset.txt`)
- Renomeação de colunas e mapeamento de classes
- Estatísticas descritivas: média, mediana, desvio padrão
- Visualizações:
  - Histogramas
  - Boxplots
  - Gráficos de dispersão (pairplot)
- Verificação de valores ausentes (nenhum encontrado)
- Escalonamento com `StandardScaler`

---

## 🤖 2. Implementação de Modelos de Classificação

- Divisão treino/teste (70% / 30%)
- Modelos utilizados:
  - K-Nearest Neighbors (KNN)
  - Support Vector Machine (SVM)
  - Random Forest
- Avaliação com:
  - Acurácia
  - Precisão
  - Recall
  - F1-score
  - Matrizes de confusão

### 🔍 Resultados (antes da otimização)

| Modelo        | Acurácia | F1-score (ponderado) |
| ------------- | -------- | -------------------- |
| KNN           | 90%      | 0.91                 |
| SVM (padrão)  | 92%      | 0.92                 |
| Random Forest | 90%      | 0.91                 |

---

## 🛠️ 3. Otimização de Hiperparâmetros

- Otimização via `GridSearchCV` aplicada ao SVM
- Parâmetros testados:
  - `C`: [0.1, 1, 10]
  - `kernel`: ['linear', 'rbf']
- **Melhores parâmetros encontrados**: `C=1`, `kernel='linear'`
- **Melhor acurácia (validação cruzada)**: 95.93%
- Acurácia no conjunto de teste manteve-se em 90%

---

## 📈 4. Interpretação e Insights

- O modelo SVM (kernel linear) apresentou **melhor desempenho global**
- A classe 1 (Rosa) teve precisão e recall altíssimos em todos os modelos
- Algumas confusões ocorreram entre as classes 0 (Kama) e 2 (Canadian), o que pode indicar semelhança entre suas características
- O modelo SVM é adequado para **uso prático em cooperativas agrícolas**, proporcionando automação com precisão superior a 90%

---

## ✅ Checklist de Requisitos

| Tarefa                                                            | Concluído |
| ----------------------------------------------------------------- | --------- |
| Análise e pré-processamento dos dados                             | ✅        |
| Estatísticas descritivas                                          | ✅        |
| Visualização com histogramas, boxplots e gráficos de dispersão    | ✅        |
| Verificação e tratamento de valores ausentes                      | ✅        |
| Aplicação de normalização/padronização                            | ✅        |
| Separação de treino e teste                                       | ✅        |
| Implementação de pelo menos 3 algoritmos                          | ✅        |
| Avaliação com acurácia, precisão, recall, F1 e matriz de confusão | ✅        |
| Otimização de hiperparâmetros (GridSearch ou RandomizedSearch)    | ✅        |
| Reavaliação após otimização                                       | ✅        |
| Análise de desempenho e extração de insights                      | ✅        |

---

### 🤖 Assistência de IA

Este projeto foi desenvolvido com o auxílio do **ChatGPT (OpenAI)** para organização do código, análises e documentação.

## 📋 Licença

<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"><p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/agodoi/template">MODELO GIT FIAP</a> por <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://fiap.com.br">Fiap</a> está licenciado sobre <a href="http://creativecommons.org/licenses/by/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">Attribution 4.0 International</a>.</p>
