# Tech Challenge Fase 3 - Machine Learning Engineering

Projeto da Fase 03 (FIAP): análise e modelagem preditiva de **atrasos em voos** nos EUA, aplicando modelagem supervisionada e não supervisionada.

## Objetivos

- **EDA:** Exploração com estatísticas descritivas, visualizações e tratamento de valores ausentes.
- **Modelagem supervisionada:** Classificação (voo atrasa ou não) e Regressão (tempo de atraso), comparando pelo menos dois algoritmos.
- **Modelagem não supervisionada:** Clusterização de aeroportos e redução de dimensionalidade (PCA).
- **Apresentação crítica:** Conclusões, limitações e próximos passos.

## Estrutura do projeto

```
Projeto/
├── data/
│   ├── flights.csv          # Voos (atrasos, cancelamentos, etc.)
│   ├── airports.csv          # Aeroportos (IATA, cidade, coordenadas)
│   ├── airlines.csv          # Companhias aéreas
│   └── dicionario_dados_flights.pdf
├── tech_challenge_fase3_ml.ipynb   # Notebook principal
├── requirements.txt
├── video_explicação.mp4
└── README.md
```

**Aviso:**  
O arquivo `data/flights.csv` excede o limite de tamanho do GitHub (100 MB) e não foi incluído neste repositório.  

Para rodar o projeto, use o arquivo original fornecido pela FIAP e coloque-o em `data/flights.csv`.

## Como executar

1. **Ambiente:** Python 3.8+ com as dependências do `requirements.txt`.

   ```bash
   pip install -r requirements.txt
   ```

2. **Abrir o notebook:**

   ```bash
   jupyter notebook tech_challenge_fase3_ml.ipynb
   ```

   Ou no Jupyter Lab / VS Code com suporte a Jupyter.

3. **Dados:** O notebook permite configurar `SAMPLE_SIZE` no início do carregamento: use `SAMPLE_SIZE = 300_000` (ou outro valor) para uma amostra e execução mais rápida, ou `SAMPLE_SIZE = None` para usar o dataset completo de `flights.csv`.

## Conteúdo do notebook

1. **Configuração e carregamento** – Leitura de `flights`, `airports` e `airlines`.
2. **EDA** – Estatísticas descritivas, distribuições, atrasos por dia da semana, companhia e mês.
3. **Tratamento de missing** – Remoção de cancelados/desviados, preenchimento de atrasos por tipo, drop de colunas essenciais ausentes.
4. **Preparação de features** – Variáveis derivadas (período do dia), codificação de categóricas (AIRLINE, ORIGIN, DEST, PERIOD).
5. **Modelagem supervisionada** – Classificação (Regressão Logística vs Random Forest: acurácia, precisão, recall, F1, ROC-AUC) e Regressão (Ridge vs Random Forest: MAE, RMSE, R²).
6. **Modelagem não supervisionada** – Clusterização (K-Means em agregados por aeroporto: cotovelo, silhouette) e PCA (variância explicada, projeção PC1–PC2).
7. **Conclusões** – Principais achados, limitações e melhorias sugeridas.

## Entregáveis

- Repositório (GitHub ou Google Colab) com o código completo.
- Vídeo de apresentação (5 a 10 min) com trabalho, resultados e conclusões.
