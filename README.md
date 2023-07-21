# Titanic
Repositório criado para fazer análise do **[desastre do Titanic, que é um desafio do Kaggle](https://www.kaggle.com/competitions/titanic/overview)**

O histórico dos resultados é mostrado abaixo, pelo Kaggle:
<img src = "https://github.com/ThiagoRBRibeiro/Titanic-Kaggle/blob/main/img/Imagem2.png" />

**[ETAPA 1: Primeiro Modelo](https://github.com/ThiagoRBRibeiro/Titanic-Kaggle/blob/main/An%C3%A1lise_do_Titanic_-_Parte_1_-_Arquivo_Final.ipynb)**

- Nesse etapa fizemos apenas o básico para conseguir verificar qual seria o resultado sem fazer nenhum tratamento nem engenharia dos dados.
  
  - Foi visualizado um resumo da base utilizando o [ydata-profiling](https://github.com/ydataai/ydata-profiling), **biblioteca capaz de gerar com poucas linhas toda a descrição do nosso dataset.**

  - Também eliminamos colunas com elevada cardinalidade, tratamos valores vazios utilizando a média e a moda das variáveis e eliminamos todas as colunas de texto.

  - Criamos os modelos utilizando 3 algoritmos: [Árvore de Classificação](https://scikit-learn.org/stable/modules/tree.html#classification), [KNN](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html) e [Regressão Logística](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html) e avaliamos esses modelos utilizando a acurácia e a matriz de confusão.

- **O score público retornado pelo Kaggle foi: 0,66746.**


**[ETAPA 2: Tratando as variáveis de texto](https://github.com/ThiagoRBRibeiro/Titanic-Kaggle/blob/main/An%C3%A1lise_do_Titanic_-_Parte_2_-_Arquivo_Final.ipynb)**

- Na segunda etapa o foco principal foi tratar as variáveis de texto para conseguirmos utilizar todas as variáveis no nosso modelo.
   - Para fazermos este tratamento, utilizamos **lambda function** e **OneHotEnconder**

- **O score público retornado pelo Kaggle foi: 0,66746.**


**[ETAPA 3: Aprofundando no negócio e melhorando os tratamentos dos dados](https://github.com/ThiagoRBRibeiro/Titanic-Kaggle/blob/main/An%C3%A1lise_do_Titanic_-_Parte_3_-_Arquivo_Inicial.ipynb)**

- Na terceira etapa o grande objetivo era entender melhor os dados para fazer um melhor tratamento e tentar melhorar o resultado obtido anteriormente
  - Então fizemos ajustes:
    - Na escala dos dados da colunas **Age** e **Fare
    - Entendemos melhor as colunas **SibSp** (Nº de irmãos/cônjuges a bordo do Titanic) e **Parch**(Nº de pais/filhos a bordo do Titanic) e criamos 2 novas colunas: **total de familiares a bordo do navio e se o passageiro estava sozinho ou não** . 

- **O score público retornado pelo Kaggle foi: 0,77033.**

**[ETAPA 4: Selecionando outros algoritmos para fazer a previsão](https://github.com/ThiagoRBRibeiro/Titanic-Kaggle/blob/main/An%C3%A1lise_do_Titanic_-_Parte_4_-_Arquivo_Inicial.ipynb)**

- Nessa etapa vamos manter todas as colunas (incluindo SibSp e parch) e utilizar novos algoritmos.
  
- Os algoritmos que vamos utilizar nessa etapa são a **Regressão Logística**, **[RandomForest](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html#sklearn.ensemble.RandomForestClassifier)**e **[MLPClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.neural_network.MLPClassifier.html)**.
  
- O MLPClassifier teve a maior acurácia, mas, provavalmente tivemos um **overfitting** dos dados, então piorou um pouco.
  
- **O score público retornado pelo Kaggle foi: 0,7679.**

**[ETAPA 5: Utilizando GridSearchCV e determinando os melhores parâmetros](https://github.com/ThiagoRBRibeiro/Titanic-Kaggle/blob/main/An%C3%A1lise_do_Titanic_-_Parte_5_-_Arquivo_Inicial.ipynb)**

- Agora utilizamos o **[GridSearchCV](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html)** para determinar os melhores parâmetros para os 3 modelos que utilizamos na etapa anterior.

- Nesse caso, o modelo RandomForest foi o que melhorou

- **O score público retornado pelo Kaggle foi: 0,78229.**
