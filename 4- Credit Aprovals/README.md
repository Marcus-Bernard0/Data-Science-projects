# Sumário

**[1. Intdodução](https://github.com/Marcus-Bernard0/Data-Science-projects/tree/master/4-%20Credit%20Aprovals#1introdu%C3%A7%C3%A3o)	 <br>
[2. Sobre os dados](https://github.com/Marcus-Bernard0/Data-Science-projects/tree/master/4-%20Credit%20Aprovals#2-sobre-os-dados)	 <br>
[3. Exploração dos dados](https://github.com/Marcus-Bernard0/Data-Science-projects/tree/master/4-%20Credit%20Aprovals#3-explora%C3%A7%C3%A3o-dos-dados)	 <br>
[4. Visualização](https://github.com/Marcus-Bernard0/Data-Science-projects/tree/master/4-%20Credit%20Aprovals#4-visualiza%C3%A7%C3%A3o)	 <br>
[5. Pré Processamento](https://github.com/Marcus-Bernard0/Data-Science-projects/tree/master/4-%20Credit%20Aprovals#5-pr%C3%A9-processamento) <br>
[6. Modelo](https://github.com/Marcus-Bernard0/Data-Science-projects/tree/master/4-%20Credit%20Aprovals#6-modelo)	 <br>
[7. Conclusão](https://github.com/Marcus-Bernard0/Data-Science-projects/tree/master/4-%20Credit%20Aprovals#7-conclus%C3%A3o)**	


# 1.Introdução
O projeto consiste em uma análise de dados e a criação de um modelo de Machine Learning com a principal finalidade de aprovar concessão de crédito. A base de dados está disponível na UCI,  Credit Approval Data Set. Os dados foram ocultos para proteger a privacidade dos mesmos. Nesse documento terá uma abordagem nas principais modelagem e aplicação realizada neste dataset a fim de obter um bom resultado. 


# 2. Sobre os dados
A base de dados contém 15 atributos. Como dito na introdução, os dados foram alterados para aumentar a privacidade. Assim, os dados foram baixados dessa maneira.
<br>
![dados-projeto](https://github.com/Marcus-Bernard0/Data-Science-projects/blob/master/4-%20Credit%20Aprovals/imagens/DescricaoDados.png)
<br>
*Figura 1:  Base de dados do projeto*


# 3. Exploração dos dados
Nessa etapa, o principal objetivo era conhecer mais sobre os dados. Foi analisada informações dos dados, no qual confirmava os tipos de dados que continham nesse dataset. Ademais, foi explorado valores nulos, estatísticas como correlação e variância. 
<br>
<br>
![correlaçãp](https://github.com/Marcus-Bernard0/Data-Science-projects/blob/master/4-%20Credit%20Aprovals/imagens/CorrelacaoDosDados.png) <br>
*Figura 2: Tabela de correlação dos dados*

Nessa etapa, ficou evidente que uma (1)  feature tinha uma alta variância. O procedimento para tratar essa variância irá estar no próximo tópico. Abaixo a variância dos campos numéricos.
<br>
<br>
![variância](https://github.com/Marcus-Bernard0/Data-Science-projects/blob/master/4-%20Credit%20Aprovals/imagens/variancia.png)
<br>
*Figura 3: Tabela de variância*
<br>
# 4. Visualização
Nessa fase, o foco era nos plots de gráfico. Busquei analisar padrões de distribuição, análise de outliers através de boxplots e percentis. 
<br>
<br>
![histograma](https://github.com/Marcus-Bernard0/Data-Science-projects/blob/master/4-%20Credit%20Aprovals/imagens/histogramas.png)
<br>
*Figura 5: Análise da distribuição dos dados numéricos através do Histograma.*
<br>
<br>
Nota-se que os dados não seguem uma distribuição normal. Além disso, nos outliers a coluna dita acima que contém uma alta variância também contém outliers em maior quantidade e escala. Abaixo, outlier do campo 0.1. Foi plotado separadamente a fim de facilitar a visualização.
<br>
<br>
![coluna0.1](https://github.com/Marcus-Bernard0/Data-Science-projects/blob/master/4-%20Credit%20Aprovals/imagens/boxplotColuna0.1.png)
<br>
*Figura 7: Gráfico de caixas da coluna 0.1 - Outliers*
<br>
# 5. Pré Processamento
Nessa etapa o objetivo era realizar todos os ajustes nos dados a fim de projetar um bom modelo de Machine Learning. Na coluna com alta variância, 0.1, foi realizada uma transformação logarítmica para conter a variância. Analisando o novo boxplot após a transformação percebe-se uma estabilização da coluna, conforme a figura abaixo.
<br>
<br>
![colunanova](https://github.com/Marcus-Bernard0/Data-Science-projects/blob/master/4-%20Credit%20Aprovals/imagens/boxplotColunaTransformada.png)
<br>
*Figura 8: Boxplot da coluna transformada*
<br>
<br>
Outrossim, foi analisada a distribuição dos dados da variável target. Como analisado, foi decidido não balancear os dados dessa coluna, pois seguia uma distribuição relativamente boa. E também foi criado uma pipeline aplicando One Hot Encoder nas colunas categóricas, e Standard Scaler para padronizar os dados numéricos. 
<br>
<br>
![balanceamento](https://github.com/Marcus-Bernard0/Data-Science-projects/blob/master/4-%20Credit%20Aprovals/imagens/BalanceamentoTarget.png)
<br>
*Figura 9: Gráfico da distribuição dos dados alvos*
<br>
# 6. Modelo
Os modelos escolhidos foram Random Forest Classifier e Logistic Regression. A avaliação do modelo consistiu em acuracy, confusion matrix, classifcation report e Cross Validate. O modelo Random Forest teve uma acurácia maior 87% contra 83% do Logistic Regression.
<br>
<br>
 ![random-forest](https://github.com/Marcus-Bernard0/Data-Science-projects/blob/master/4-%20Credit%20Aprovals/imagens/ModelRandom.png)
 <br>
*Figura 10: Matriz de confusão Random Forest*
<br>
<br>
![logistic](https://github.com/Marcus-Bernard0/Data-Science-projects/blob/master/4-%20Credit%20Aprovals/imagens/ModeloLogisticRegression.png)
<br>
*Figura 11: Matriz de confusão Logistic Regression*
<br>

# 7. Conclusão
Para o projeto, o modelo escolhido foi o Random Forest. Pois apresenta uma maior acurácia e com uma matriz de confusão com os valores errados (Falso Positivo e Falso negativo) em menor quantidade. 
Outro ponto importante a ressaltar é a análise do Cross Validation. O Random Forest alcançou 87.3% enquanto o outro modelo 87,13%. Lembrando que a acurácia da Logistic foi de 83 %. Sendo assim, há uma grande diferença entre as acurácias. Já o modelo Random Forest tem uma menor diferença, (87,3 - 87).
