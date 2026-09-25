[← README](../README.md) · [Resultados](resultados.md) · [Metodologia](metodologia.md) · **Guia de uso**

# Guia de uso

## Executando o notebook

**Pré-requisitos:** Python 3 e acesso à internet (o dataset é baixado da UCI na execução).

### Google Colab

Abra o notebook no
[Google Colab](https://colab.research.google.com/github/MarcusToledo/email-spam-classifier-benchmark/blob/master/ml_spam_email.ipynb)
e execute **Runtime → Run all**.

### Localmente

```bash
git clone https://github.com/MarcusToledo/email-spam-classifier-benchmark.git
cd email-spam-classifier-benchmark

python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate

pip install pandas numpy matplotlib scikit-learn jupyter
jupyter notebook ml_spam_email.ipynb
```

Execute as células em ordem. A célula 4 imprime, para cada modelo, a acurácia, o relatório
de classificação e a matriz de confusão, ordenados pela pontuação composta:

```text
Modelo: Random Forest
Acurácia: 95.55%
Acurácia (quantidade amostras): 880 / 921
Pontuação Composta: 95.39
...
```

## Configuração

Os parâmetros do experimento ficam no próprio notebook:

| Parâmetro | Célula | Valor atual | Efeito |
|---|:-:|---|---|
| `url` | 2 | URL do Spambase na UCI | Fonte dos dados |
| `test_size` | 2 | `0.2` | Fração reservada para teste |
| `random_state` | 2 e 3 | `42` | Reprodutibilidade da divisão e dos modelos |
| `models` | 3 | 7 modelos | Adicione ou remova classificadores aqui |
| `hidden_layer_sizes` | 3 | `(12, 8)` | Arquitetura da rede neural |

## Adicionando um modelo

Adicione uma entrada ao dicionário `models` na célula 3. O restante do pipeline (métricas,
ordenação e gráficos) se adapta sozinho:

```python
from sklearn.ensemble import GradientBoostingClassifier

models["Gradient Boosting"] = GradientBoostingClassifier(random_state=42)
```

## Solução de problemas

**`HTTPError` ou `URLError` ao carregar o dataset**
A célula 2 baixa os dados de `archive.ics.uci.edu`. Verifique sua conexão ou baixe
`spambase.data` manualmente e troque `url` pelo caminho local do arquivo.

**Resultados diferentes dos publicados**
Com as sementes fixas, a única fonte de diferença é a versão das bibliotecas. Os resultados
publicados usam scikit-learn 1.9.1, pandas 3.0.6, NumPy 2.5.3 e Matplotlib 3.11.2.

**`ConvergenceWarning` da Rede Neural ou da Regressão Logística**
Aumente `max_iter` no construtor do modelo.
