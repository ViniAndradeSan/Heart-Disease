

# Heart Disease — Predição de Doença Cardíaca

Projeto desenvolvido para a disciplina de Aprendizado de Máquina. A proposta foi analisar um conjunto de dados de pacientes com doenças cardíacas e construir um modelo capaz de fazer uma estimativa da presença da doença a partir de informações clínicas.

## Objetivo

O principal objetivo desse trabalho foi desenvolver um modelo de classificação que pudesse auxiliar na identificação de pacientes com maior risco de doença cardíaca utilizando apenas informações obtidas em exames e consultas de rotina.

A ideia não é substituir um diagnóstico médico, mas servir como uma ferramenta de apoio para uma avaliação inicial.

---

## Integrantes

- Marcelo de Jesus Menezes
- VInicius Andrade Santos

---

## Fonte dos dados

Foi utilizado o dataset **Heart Disease**, base **Cleveland**, disponível no repositório **UCI Machine Learning**.

Os dados são carregados diretamente pelo pacote `ucimlrepo`, então não existe necessidade de baixar arquivos manualmente.

---

## Tipo do problema

**Classificação binária**

A variável alvo do dataset é `num`, que originalmente possui valores entre 0 e 4, indicando ausência ou diferentes níveis da doença.

Durante o pré-processamento foi feita a binarização da variável:

- **0:** ausência de doença cardíaca;
- **1:** presença de doença cardíaca (agrupando as classes 1, 2, 3 e 4).

Foram utilizados os 13 atributos clínicos da base, incluindo idade, sexo, colesterol, pressão arterial, frequência cardíaca máxima, tipo de dor no peito, oldpeak, talassemia, entre outros.

---

## Estrutura do projeto

```
├── README.md
├── notebook.ipynb
└── Dados obtidos automaticamente através do ucimlrepo
```

---

## Como executar

O notebook pode ser aberto tanto no Google Colab quanto no Jupyter Notebook.

Basta acessar:  **[colab.research.google.com/drive/1Ta7d-4apuKxgIWplJLrpIplThcDSQROY](https://colab.research.google.com/drive/1Ta7d-4apuKxgIWplJLrpIplThcDSQROY)**

Caso utilize o Colab, basta executar as células em ordem. A primeira instala as bibliotecas necessárias e as seguintes fazem o download automático do dataset.

Não é preciso adicionar nenhum arquivo manualmente.

---

## Etapas realizadas

Durante o desenvolvimento do projeto foram realizadas as seguintes etapas:

- Importação das bibliotecas;
- Carregamento do dataset;
- Análise exploratória dos dados;
- Tratamento dos valores ausentes;
- Visualização das distribuições das variáveis;
- Construção da matriz de correlação;
- Pré-processamento utilizando `Pipeline` e `ColumnTransformer`;
- Padronização das variáveis numéricas;
- Codificação das variáveis categóricas;
- Separação entre treino e teste;
- Treinamento dos modelos;
- Avaliação dos resultados;
- Comparação entre os algoritmos.

---

## Modelos utilizados

Os modelos avaliados durante o projeto foram:

| Modelo | Validação Cruzada |
|---------|------------------:|
| DummyClassifier | 0,541 ± 0,006 |
| SGDClassifier | 0,839 ± 0,048 |
| RandomForestClassifier | 0,814 ± 0,066 |

Após a comparação dos resultados, o **SGDClassifier** foi escolhido como modelo final por apresentar o melhor desempenho médio e uma boa estabilidade entre os folds da validação cruzada.

---

## Resultados

No conjunto de teste o modelo final obteve os seguintes resultados:

- **Acurácia:** 0,902
- **Precisão:** 0,893
- **Revocação:** 0,893
- **F1-score:** 0,893

Os resultados mostraram um bom equilíbrio entre as classes, indicando que o modelo conseguiu identificar pacientes com e sem doença cardíaca de maneira consistente.

---

## Considerações

Durante a análise também foi possível perceber que algumas variáveis apresentavam uma relação maior com a presença da doença, principalmente `oldpeak`, `thal`, `ca`, `cp` e `thalach`.

Mesmo apresentando um bom desempenho, o modelo ainda possui limitações. A base utilizada não é muito grande e algumas classes do problema original eram desbalanceadas, o que exigiu cuidados durante o pré-processamento.

Como trabalhos futuros seria interessante testar outros algoritmos, realizar ajuste de hiperparâmetros e utilizar bases maiores para verificar se os resultados continuam semelhantes.

---

## Divisão das atividades

**Marcelo de Jesus Menezes**

Responsável pelo desenvolvimento das seções **1 até 4.5** do notebook, incluindo:

- Introdução e definição do problema;
- Objetivos do projeto;
- Apresentação e compreensão do dataset;
- Análise exploratória dos dados (EDA);
- Visualizações e interpretação dos gráficos;
- Tratamento dos dados e preparação para a modelagem.

**Vinicius Andrade Santos**

Responsável pelo desenvolvimento das seções **após a 4.5**, incluindo:

- Pré-processamento final dos dados;
- Construção dos pipelines;
- Treinamento dos modelos;
- Validação cruzada;
- Avaliação das métricas;
- Comparação entre os algoritmos;
- Discussão dos resultados;
- Conclusão e organização final do notebook.
---

## Ferramentas utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- ucimlrepo

---

## Vídeo da apresentação 

Basta acessar: https://drive.google.com/file/d/1BIIq-IerPbqC18oALqsvgRpyseTym_4W/view?usp=sharing


## Uso de IA

Durante o desenvolvimento foram utilizadas ferramentas de IA como apoio na organização do código, esclarecimento de dúvidas sobre bibliotecas, interpretação de resultados e revisão de alguns textos.

Todo o notebook foi revisado manualmente pelo grupo, conferindo se os resultados obtidos eram coerentes com as análises realizadas e garantindo que o funcionamento do código estivesse de acordo com o esperado.
