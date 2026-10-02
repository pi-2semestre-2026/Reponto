# Reponto — regras para Claude Code

## O projeto
Assistente de IA para previsão de demanda e recomendação de reposição de
estoque em pequeno varejo de mercado. Projeto acadêmico (PII), em grupo,
prazo de 3-4 meses. Detalhes completos em docs/BRIEFING.md.

Dataset: Store Sales – Time Series Forecasting (Favorita, Kaggle, versão
getting started). Granularidade: família de produto por loja. Previsão semanal.

## Regra principal: este é um projeto de aprendizado
O dono deste repositório implementa o pipeline de dados, a regra de
reposição, a camada de explicação e as avaliações para APRENDER.

- Antes de escrever código que implemente um conceito de dados ou ML
  (limpeza, agregação, features, modelo, validação, métricas, simulação de
  estoque, avaliação), explique o conceito e pergunte se ele quer escrever.
- Ao revisar código dele, aponte o erro e explique por quê — não reescreva.
- Infraestrutura pode ser feita direto: estrutura de pastas, configuração,
  ambiente, dependências, scripts de dado falso, correção de erro de ambiente.

## Decisões fechadas — não sugerir alternativas
- Modelo: baseline (média móvel) + LightGBM, validação walk-forward
- Dados em CSV/Parquet. Sem banco de dados.
- Sem login, sem autenticação, sem deploy robusto, sem Docker
- Sem LangChain, LangGraph, RAG, deep learning, tuning de hiperparâmetros
- Estoque é simulado (não existe no dataset), com parâmetros documentados

## Convenções
- data/raw/ nunca vai para o Git (train.csv tem ~120 MB)
- O recorte congelado vai em data/processed/ e É versionado
- Contrato entre modelo e app: data/processed/previsoes.csv com as colunas
  loja, familia, semana, demanda_prevista, demanda_real