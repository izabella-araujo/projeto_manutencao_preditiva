# Manutenção Preditiva de Aeronaves com Redes RNN e LSTM

## Descrição Inicial do Problema

A manutenção preditiva é uma abordagem que busca antecipar falhas em equipamentos antes que elas ocorram, utilizando dados históricos e informações coletadas por sensores. No contexto aeronáutico, essa prática é fundamental para garantir a segurança operacional e reduzir custos de manutenção.
Os motores de aeronaves estão sujeitos a desgaste ao longo do tempo devido às condições de operação. Falhas não detectadas podem ocasionar custos elevados de reparo, substituição de componentes e até riscos à segurança dos passageiros.
Por outro lado, realizar manutenções preventivas em excesso também gera custos desnecessários. Dessa forma, torna-se importante desenvolver mecanismos capazes de identificar, com antecedência, quais motores apresentam maior probabilidade de falha.
Este projeto utiliza dados históricos de operação e leituras de sensores para prever se um motor de aeronave apresenta risco de falha dentro de um determinado número de ciclos operacionais.


## Objetivo Geral

Desenvolver um modelo preditivo baseado em Redes Neurais Recorrentes (RNN) e Long Short-Term Memory (LSTM), capaz de identificar motores de aeronaves com risco de falha a partir de séries temporais contendo dados operacionais e medições de sensores.


## Estrutura Inicial do Projeto

```text
projeto/
├── data/
│   ├── PM_train.txt
│   ├── PM_test.txt
│   └── PM_truth.txt
│
├── src/
│   ├── data_loader.py
│   ├── preprocess.py
│   └── main.py
│
├── requirements.txt
└── README.md
```

---

## Etapa Atual do Desenvolvimento

Nesta primeira etapa foi implementada a estrutura inicial do projeto, contemplando:

### 1. Carregamento dos Dados

O módulo `data_loader.py` é responsável por carregar os conjuntos de dados utilizados no projeto:

* **PM_train.txt**: histórico completo dos motores até a ocorrência da falha;
* **PM_test.txt**: histórico parcial dos motores, utilizado para avaliação do modelo;
* **PM_truth.txt**: valores reais de vida útil remanescente dos motores do conjunto de teste.

Exemplo de carregamento:

```python
train_df = loader.load_train_data()
test_df = loader.load_test_data()
truth_df = loader.load_truth_data()
```

### 2. Limpeza Inicial dos Dados

O módulo `preprocess.py` contém a classe `DataCleaner`, responsável pela remoção de colunas vazias presentes nos arquivos originais.

```python
train_df = cleaner.remove_empty_columns(train_df)
test_df = cleaner.remove_empty_columns(test_df)
truth_df = cleaner.remove_empty_columns(truth_df)
```

Essa etapa garante que apenas colunas com informações relevantes sejam utilizadas nas próximas fases do projeto.

---

## Status do Projeto

🚧 Em desenvolvimento – Etapa 1 concluída: Estrutura inicial, carregamento e limpeza dos dados.

---

## Referência

https://www.kaggle.com/code/sharanharsoor/aircraft-predictive-maintenance/notebook
