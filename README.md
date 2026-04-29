# Titanic
Repositório criado para a **[competição do Kaggle sobre o desastre do Titanic](https://www.kaggle.com/competitions/titanic/overview)**

O histórico dos resultados é mostrado abaixo e pode ser obtido no Kaggle:
<img src="https://github.com/Davi-CGomes/Titanic/blob/main/img/grafico.png"/>

## [Etapa 1: Primeiro modelo](https://github.com/Davi-CGomes/Titanic/blob/main/Analise_Titanic.ipynb)
- Nesta etapa foi realizada uma análise básica dos dados, sem aplicação de tratamento ou engenharia de atributos, com o objetivo de estabelecer um baseline.
  - Foi gerado um resumo da base utilizando a biblioteca [ydata-profiling](https://docs.profiling.ydata.ai/latest/), permitindo uma visão geral das variáveis.
  - Também foram removidas colunas com alta cardinalidade, tratados valores nulos com média e moda, e excluídas variáveis textuais.
  - Foram treinados três modelos: Árvore de Classificação, KNN e Regressão Logística, avaliados por acurácia e matriz de confusão.
- **Score obtido no Kaggle: 0.66746**

## [Etapa 2: Tratamento das variáveis de texto](https://github.com/Davi-CGomes/Titanic/blob/main/Analise_Titanic2.ipynb)
- Nesta etapa foi realizado um tratamento mais avançado dos dados, incluindo a junção das bases de treino e teste para melhorar a imputação de valores faltantes.
  - Foram aplicadas técnicas como [OneHotEncoder](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.OneHotEncoder.html) e funções lambda para transformar os dados textuais em formato numérico. Mantivemos os mesmos modelos da etapa anterior para comparação de desempenho.
  - Foram utilizados os mesmos modelos da etapa anterior.
- **Score obtido no Kaggle: 0.76555**

## [Etapa 3: Melhorando o tratamento de dados](https://github.com/Davi-CGomes/Titanic/blob/main/Analise_Titanic3.ipynb)
- Foi feito uma análise maior dos dados para fazer um melhor tratamento e obter um melhor resultado.
- O que foi feito:
  - Ajuste na escala dos dados nas colunas **Age** e **Fare**
  - Foi analisado melhor as colunas **SibSp**(número de irmãos/cônjuges a bordo no Titanic) e **Parch**(número de pais/filhos a bordo no Titanic) e foi criado 2 novas colunas: total de familiares a bordo e se o passageiro estava sozinho ou não
- Utilizamos os mesmos modelos vistos anteriormente
- **Score obtido no Kaggle: 0.77751**

## [Etapa 4: Selecionando outros algoritmos para a previsão](https://github.com/Davi-CGomes/Titanic/blob/main/Analise_Titanic4.ipynb)
- Foi mantido todas as colunas e utilizados novos algoritmos para verificar o resultado do modelo
- Os algoritmos utilizados foram:
  - **Regressão Logística** (foi mantido por ter tido o melhor resultado nos testes anteriores)
  - **RandomForest**
  - **MLPClassifier (redes neurais)**
- O MLPClassifier obteve a maior acurácia nos dados de validação entre todos os modelos vistos até agora, porém ao usar esse modelo nos dados de teste o resultado foi pior que na etapa 3, mostrando que provavelmente ocorreu um **overfitting** do modelo.
- **Score obtido no Kaggle: 0.75598**

## [Etapa 5: Utilizando o GridSearchCV e determinando os melhores parâmetros](https://github.com/Davi-CGomes/Titanic/blob/main/Analise_Titanic5.ipynb)
- Foi utilizado o [GridSearchCV](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html) para determinar os melhores parâmetros para os modelos utilizados na etapa anterior.
- Nesse caso, o modelo escolhido foi o RandomForest e o resultado melhorou consideravelmente em relação a etapa 4 e foi melhor que na 3.
- **Score obtido no Kaggle: 0.77990**

  
