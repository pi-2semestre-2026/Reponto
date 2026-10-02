# Reponto

Projeto acadêmico de previsão de demanda a partir de dados de vendas.

## Estrutura de pastas

```
reponto/
├── data/
│   ├── raw/        # CSVs originais do Kaggle (não versionados)
│   └── processed/  # dados tratados pelo pipeline
├── notebooks/      # análises exploratórias em Jupyter
├── src/            # código-fonte (pipeline, modelos, app)
├── docs/           # documentação do projeto
├── requirements.txt
├── CLAUDE.md
└── README.md
```

## Setup

```bash
python -m venv .venv
.venv\Scripts\activate      # Windows
pip install -r requirements.txt
```
