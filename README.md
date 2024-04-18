# Desenvolvimento de Estratégias de Investimento Automatizado

Este repositório contém a solução desenvolvida para o Trabalho Prático da disciplina "Tópicos em Sistemas Inteligentes", que tem como objetivo criar e aprimorar estratégias de investimento automatizado utilizando técnicas de Aprendizado de Máquina (AM) no mercado brasileiro de ações, especificamente com dados das ações da Vale.

## Solução Proposta

### Modelos de Aprendizado de Máquina e Validação

Foram desenvolvidos cinco modelos de AM para resolver problemas de classificação e regressão, utilizando os dados das ações da Vale:

- Random Forest
- Multilayer Perceptron
- XGBoost
- Naive Bayes (para classificação)
- Linear Regressor (para regressão)
- k-Nearest Neighbors

A técnica de validação com janela deslizante foi aplicada, retrainando os modelos em intervalos diários (1 dia), semanais (5 dias) e mensais (22 dias).

### Ensemble Learning

Foram aplicadas técnicas de ensemble learning para combinar os resultados dos modelos, incluindo:

#### Regressão:

- Média das saídas dos modelos
- Média ponderada pela assertividade dos modelos, utilizando dados da janela deslizante para ponderação.

#### Classificação Binária:

- Votação simples dos modelos
- Média das saídas dos modelos, aplicando um limiar arbitrário para criação da saída binária
- Média ponderada pela assertividade dos modelos, utilizando dados da janela deslizante para ponderação.

### Stacking

Foi utilizado um modelo de aprendizado supervisionado (XGBoost) para combinar as saídas dos modelos obtidos com janela deslizante, sem retreinamento do modelo de stacking. Foram desenvolvidos modelos de stacking para resolver os problemas de classificação e regressão.

### Simulação de Retorno Financeiro

Realizou-se a simulação do retorno utilizando como entrada para tomada de decisões de compra e venda o resultado do período de testes obtido nas etapas anteriores. Foram calculados o retorno diário dos resultados dos modelos de classificação e regressão, considerando métricas como média dos retornos diários e desvio padrão, e plotados gráficos do retorno acumulado e retorno versus risco no período de testes.
