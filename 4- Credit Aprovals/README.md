# Sumário

**1.Introdução	 <br>
2. Sobre os dados	 <br>
3. Exploração dos dados	 <br>
4. Visualização	 <br>
5. Pré Processamento	 <br>
6. Modelo	 <br>
7. Conclusão**	


# 1.Introdução
O projeto consiste em uma análise de dados e a criação de um modelo de Machine Learning com a principal finalidade de aprovar concessão de crédito. A base de dados está disponível na UCI,  Credit Approval Data Set. Os dados foram ocultos para proteger a privacidade dos mesmos. Nesse documento terá uma abordagem nas principais modelagem e aplicação realizada neste dataset a fim de obter um bom resultado. 


# 2. Sobre os dados
A base de dados contém 15 atributos, sendo: 
A1	b, a
A2	continuous
A3	continuous
A4	u, y, l, t.
A5	g, p, gg
A6	c, d, cc, i, j, k, m, r, q, w, x, e, aa, ff.
A7	v, h, bb, j, n, z, dd, ff, o.
A8	continuous
A9	t, f.
A10	t, f.
A11	continuous
A12	t, f.
A13	g, p, s.
A14	continuous
A15	continuous
A16	+,-

Como dito na introdução, os dados foram alterados para aumentar a privacidade. Assim, os dados foram baixados dessa maneira.

 
Figura 1:  Base de dados do projeto


# 3. Exploração dos dados
Nessa etapa, o principal objetivo era conhecer mais sobre os dados. Foi analisada informações dos dados, no qual confirmava os tipos de dados que continham nesse dataset. Ademais, foi explorado valores nulos, estatísticas como correlação e variância.
 
Figura 2: Tabela de correlação dos dados

Nessa etapa, ficou evidente que uma (1)  feature tinha uma alta variância. O procedimento para tratar essa variância irá estar no próximo tópico. Abaixo a variância dos campos numéricos.


 
Figura 3: Tabela de variância


# 4. Visualização
Nessa fase, o foco era nos plots de gráfico. Busquei analisar padrões de distribuição, análise de outliers através de boxplots e percentis. 
 
Figura 5: Análise da distribuição dos dados numéricos através do Histograma.


Nota-se que os dados não seguem uma distribuição normal. Além disso, nos outliers a coluna dita acima que contém uma alta variância também contém outliers em maior quantidade e escala. Abaixo, outlier do campo 0.1. Foi plotado separadamente a fim de facilitar a visualização. 

 
Figura 7: Gráfico de caixas da coluna 0.1 - Outliers



# 5. Pré Processamento
Nessa etapa o objetivo era realizar todos os ajustes nos dados a fim de projetar um bom modelo de Machine Learning. Na coluna com alta variância, 0.1, foi realizada uma transformação logarítmica para conter a variância. Analisando o novo boxplot após a transformação percebe-se uma estabilização da coluna, conforme a figura abaixo.
 
Figura 8: Boxplot da coluna transformada 

Outrossim, foi analisada a distribuição dos dados da variável target. Como analisado, foi decidido não balancear os dados dessa coluna, pois seguia uma distribuição relativamente boa. E também foi criado uma pipeline aplicando One Hot Encoder nas colunas categóricas, e Standard Scaler para padronizar os dados numéricos. 

 
Figura 9: Gráfico da distribuição dos dados alvos
# 6. Modelo
Os modelos escolhidos foram Random Forest Classifier e Logistic Regression. A avaliação do modelo consistiu em acuracy, confusion matrix, classifcation report e Cross Validate. O modelo Random Forest teve uma acurácia maior 87% contra 83% do Logistic Regression.

 
Figura 10: Matriz de confusão Random Forest

 
Figura 11: Matriz de confusão Logistic Regression


# 7. Conclusão
Para o projeto, o modelo escolhido foi o Random Forest. Pois apresenta uma maior acurácia e com uma matriz de confusão com os valores errados (Falso Positivo e Falso negativo) em menor quantidade. 
Outro ponto importante a ressaltar é a análise do Cross Validation. O Random Forest alcançou 87.3% enquanto o outro modelo 87,13%. Lembrando que a acurácia da Logistic foi de 83 %. Sendo assim, há uma grande diferença entre as acurácias. Já o modelo Random Forest tem uma menor diferença, (87,3 - 87).
