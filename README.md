# 📊 Análise de Dados do iFood - Restaurantes

## 📋 Descrição do Projeto
Este projeto consiste na análise exploratória e limpeza de um grande conjunto de dados de estabelecimentos de delivery no Brasil. O objetivo principal é entender o perfil das categorias mais populares, o comportamento das variáveis relacionadas ao tempo e taxa de entrega, além de preparar os dados para análises e possíveis modelagens futuras

## 📊 Dataset
* Número de registros: aproximadamente 393 mil
* Colunas principais:
  * category 🍔 (categoria do estabelecimento)
  * delivery_fee 💸 (taxa de entrega)
  * delivery_time ⏱️ (tempo estimado de entrega em minutos)
  * distance 📍 (distância do entregador)
  * minimumOrderValue 💰 (valor mínimo para pedido)
  * rating ⭐ (nota média dos clientes)
  * Outros: availableForScheduling 📅, ibge 🌎, name 🏷️, paymentCodes 💳, price_range 💲, tags 🏷️

## 🧹 Limpeza de Dados
* Remoção de outliers usando o método do IQR (1.5x e 3x IQR) nas colunas contínuas:
  * delivery_fee 💸
  * delivery_time ⏱️
  * distance 📍
  * minimumOrderValue 💰
  * rating ⭐
* Após a limpeza, o dataset ficou com cerca de 391 mil registros, garantindo maior qualidade e confiabilidade nas análises.

## 🔍 Análise Exploratória Inicial (EDA)
* Distribuição das Categorias:
  * As categorias mais frequentes são lanches 🍔 (24.68%), brasileira 🇧🇷 (18.28%) e doces & bolos 🍰 (9.87%).

* Performance das Categorias Populares:

| Categoria     | Tempo Médio de Entrega (min) ⏱️ | Taxa Média de Entrega (R$) 💸 | Nota Média ⭐ | Estabelecimentos 🏪 |
|--------------|---------------------------------|------------------------------|--------------|--------------------|
| lanches      | 48.46                           | 6.34                         | 2.46         | 96,979             |
| brasileira   | 45.87                           | 6.67                         | 2.22         | 71,824             |
| doces & bolos| 44.80                           | 7.82                         | 2.20         | 38,770             |

* Os dados indicam que os consumidores preferem refeições rápidas, tradicionais e sobremesas, com uma pequena variação nas taxas e tempo de entrega.

* ## 📈 Análise Avançada e Modelagem

Após a análise exploratória inicial e limpeza dos dados, avançamos para análises mais profundas e modelagem, que incluem:

### Clusterização dos Restaurantes

- Utilizamos as variáveis **distance**, **rating** e as faixas de preço (cheapest, moderate, expensive e most expensive) para segmentar os restaurantes em **4 clusters**.
- Os clusters mostram grupos distintos de estabelecimentos com perfis diferentes:
  - Um cluster com restaurantes com preço moderado, avaliação baixa e maior volume de registros.
  - Um cluster com restaurantes mais baratos, avaliação baixa.
  - Um cluster com restaurantes caros e avaliação alta.
  - Um cluster com restaurantes baratos, porém com avaliação alta.
- Esta segmentação pode ajudar no direcionamento de estratégias de marketing e personalização de ofertas.

### Modelagem Preditiva

- Implementamos um modelo de regressão (Random Forest) para prever o número de pedidos.
- Os principais resultados do modelo foram:
  - **MAE (Erro Médio Absoluto):** 11.40
  - **RMSE (Raiz do Erro Quadrático Médio):** 14.88
- O modelo apresenta um desempenho satisfatório para previsões iniciais, podendo ser refinado em projetos futuros.

### Próximos passos sugeridos

- Explorar mais variáveis e novas features para melhorar a performance do modelo.
- Avaliar outras técnicas de modelagem e validação cruzada.
- Analisar sazonalidades e efeitos temporais com séries temporais.

## ⚙️ Como Rodar o Projeto
1. Clone este repositório.
2. Certifique-se de ter as bibliotecas necessárias instaladas:

pip install pandas matplotlib seaborn numpy

3. Carregue o dataset:

import pandas as pd
df = pd.read_csv('caminho/do/arquivo.csv')

4. Execute os notebooks ou scripts conforme ordem descrita para reproduzir as análises.

## 🗂️ Fonte dos Dados

📥 Os dados foram obtidos no [Kaggle](https://www.kaggle.com/datasets/ricardotachinardi/ifood-restaurants-data):

> [📦 iFood Restaurants Data - Kaggle](https://www.kaggle.com/datasets/ricardotachinardi/ifood-restaurants-data)

