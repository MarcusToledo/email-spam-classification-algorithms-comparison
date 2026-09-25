# Contribuindo

Sugestões e melhorias são bem-vindas.

## Como contribuir

1. Faça um fork do repositório.
2. Crie uma branch: `git checkout -b feat/minha-melhoria`.
3. Rode o notebook do início ao fim para garantir que tudo executa.
4. Se os resultados mudarem, atualize os gráficos em `assets/` e os números em
   [`docs/resultados.md`](docs/resultados.md) e no [`README.md`](README.md).
5. Abra um Pull Request descrevendo a mudança e o impacto nos resultados.

O [Guia de uso](docs/guia-de-uso.md) explica como executar o notebook e adicionar modelos.

## Estrutura do repositório

```text
.
├── ml_spam_email.ipynb                                   # Notebook com todo o experimento
├── email-spam-classifier-benchmark.pdf                   # Artigo com a análise completa
├── assets/                                               # Gráficos exportados do notebook
│   ├── accuracy.png
│   ├── precision-recall-f1.png
│   ├── tpr-tnr.png
│   └── composed-score.png
├── docs/
│   ├── resultados.md                                     # Métricas, gráficos e matrizes de confusão
│   ├── metodologia.md                                    # Pipeline, dataset, modelos e métricas
│   └── guia-de-uso.md                                    # Execução, configuração e problemas comuns
├── CONTRIBUTING.md
├── LICENSE                                               # Licença MIT (código)
├── LICENSE-ARTICLE.md                                    # Licença CC BY 4.0 (artigo)
└── README.md
```

## Ideias de evolução

- Validação cruzada (`cross_val_score`) em vez de uma única divisão treino/teste
- Busca de hiperparâmetros com `GridSearchCV`
- Curvas ROC e AUC por modelo
