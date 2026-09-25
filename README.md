# Detecção de Spam em Emails: comparação de algoritmos de classificação

Estudo comparativo de sete algoritmos de machine learning para classificar emails como
**spam** ou **não spam**, usando o dataset público **Spambase** (UCI). O objetivo é
descobrir qual modelo oferece o melhor equilíbrio entre acerto geral, detecção de spam e
preservação de emails legítimos.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/MarcusToledo/email-spam-classifier-benchmark/blob/master/ml_spam_email.ipynb)
![Python](https://img.shields.io/badge/python-3-3776AB?logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikitlearn&logoColor=white)
![Jupyter](https://img.shields.io/badge/jupyter-notebook-F37626?logo=jupyter&logoColor=white)
![Dataset](https://img.shields.io/badge/dataset-UCI%20Spambase-blue)
[![License: MIT](https://img.shields.io/badge/c%C3%B3digo-MIT-yellow.svg)](LICENSE)
[![License: CC BY 4.0](https://img.shields.io/badge/artigo-CC%20BY%204.0-lightgrey.svg)](LICENSE-ARTICLE.md)

> **Resultado principal:** o **Random Forest** obteve a maior acurácia (**95,55%**) e a maior
> pontuação composta (**95,39**), com 98,3% dos emails legítimos preservados.

## Destaques

- **7 algoritmos comparados:** Naive Bayes, Regressão Logística, Árvore de Decisão,
  Random Forest, SVM, KNN e Rede Neural (MLP).
- **Mesmo protocolo para todos:** mesmas 57 features, divisão treino/teste 80/20,
  normalização com `StandardScaler` e `random_state=42`. Os resultados se repetem a cada
  execução.
- **7 métricas por modelo:** acurácia, precisão, recall, F1-score, TPR, TNR e uma
  pontuação composta que resume todas.
- **Artigo científico** em PDF com fundamentação teórica, metodologia e discussão.

## Resultados

Avaliação em 921 emails de teste, ordenada pela pontuação composta.

| # | Modelo | Acurácia | TPR (spam detectado) | TNR (legítimo preservado) | Pontuação composta |
|:-:|--------|:--------:|:--------------------:|:-------------------------:|:------------------:|
| 🥇 | **Random Forest** | **95,55%** | 91,8% | **98,3%** | **95,39** |
| 🥈 | Support Vector Machine | 93,49% | 89,2% | 96,6% | 93,30 |
| 🥉 | Rede Neural (MLP) | 93,16% | 92,3% | 93,8% | 93,12 |
| 4 | Árvore de Decisão | 91,97% | 88,7% | 94,4% | 91,82 |
| 5 | Regressão Logística | 91,97% | 87,4% | 95,3% | 91,77 |
| 6 | K-Nearest Neighbors | 89,36% | 84,4% | 93,0% | 89,13 |
| 7 | Naive Bayes | 82,19% | **93,8%** | 73,6% | 83,18 |

![Gráfico de barras horizontais com a pontuação composta de cada modelo](assets/composed-score.png)

Precisão, recall, F1, matrizes de confusão e todos os gráficos estão em
[Resultados](docs/resultados.md).

## Início rápido

Abra no [Google Colab](https://colab.research.google.com/github/MarcusToledo/email-spam-classifier-benchmark/blob/master/ml_spam_email.ipynb)
e execute **Runtime → Run all**, ou rode localmente:

```bash
git clone https://github.com/MarcusToledo/email-spam-classifier-benchmark.git
cd email-spam-classifier-benchmark
pip install pandas numpy matplotlib scikit-learn jupyter
jupyter notebook ml_spam_email.ipynb
```

## Documentação

| Página | Conteúdo |
|---|---|
| [Resultados](docs/resultados.md) | Tabela completa de métricas, análise, gráficos e matrizes de confusão |
| [Metodologia](docs/metodologia.md) | Pipeline, dataset, decisões de projeto, hiperparâmetros e fórmulas das métricas |
| [Guia de uso](docs/guia-de-uso.md) | Execução, parâmetros configuráveis, como adicionar modelos e solução de problemas |
| [Contribuindo](CONTRIBUTING.md) | Como contribuir, estrutura do repositório e ideias de evolução |
| [Artigo (PDF)](email-spam-classifier-benchmark.pdf) | *Análise Comparativa de Modelos de Classificação para Detecção de Spam em Emails* |

## Licença

- **Código** (notebook e demais arquivos): [MIT](LICENSE).
- **Artigo** (`email-spam-classifier-benchmark.pdf`):
  [CC BY 4.0](LICENSE-ARTICLE.md). Você pode reutilizar e adaptar o texto, desde que cite
  o autor.

## Autor

**Marcus Toledo** · Universidade Tecnológica Federal do Paraná (UTFPR), Dois Vizinhos – PR
