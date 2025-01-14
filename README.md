## Análise do banco de dados 'Brewer's friend Beer Recipes’  

### 1. Resumo dos métodos utilizados:

Python: Como linguagem de programação principal para análise e processamento de dados.
Bibliotecas Python:
Pandas: Para manipulação de dados.
Matplotlib: Para criação de gráficos e visualização de dados.
NumPy: Para trabalhar com arrays, matrizes e funções matemáticas.
Scikit-learn (implicitamente mencionado pelas funções relacionadas à modelagem de machine learning, como KNeighbors e StratifiedKFold).
Funções e Técnicas:
Data Cleaning: Método isnull(): Para identificar dados faltantes.
Imputação de dados faltantes:
Mediana: Utilizada para substituir valores em variáveis com distribuição centralizada.
Média: Utilizada para substituir valores em variáveis com distribuição descentralizada.
get_dummies(): Para converter variáveis categóricas em variáveis dummy (codificação one-hot).
MenMaxScaler: Utilizado para normalização dos dados.
StratifiedKFold e Cross_val_score: Para validar e testar os modelos.
Boxplot e Histograma: Para análise visual de dispersão e distribuição dos dados.
Modelos de Machine Learning:
Logistic Regression (Regressão Logística).
Naive Bayes (NB).
Decision Tree (Árvore de Decisão).
K-Neighbors (K-NN).

### 2. Introdução:

Efetuou-se o presente estudo por meio da análise dos arquivos
disponibilizados na plataforma Kaggle, o dataset utilizado foi o: Brewer's Friend
Recipes, com 73.861 mil amostras de cervejas artesanai s e 176 estilos diferentes de
cervejas.

Os dados na plataforma Kaggle são atualizados em tempo real, e utilizou-se
um conjunto de dados em formato CSV, com download efetuado para análise em
fevereiro de 2021.

O processamento dos dados coletados foi realizado no ambiente COLAB e a
execução dos códigos foi efetuado na linguagem de programação python. As
bibliotecas utilizadas foram: Pandas: para a manipulação de dados, Matplotlib para
criação de gráficos e visualização de dados, Numpay para trabalhar com arrays,
matrizes e demais funções matemáticas e matplotlib para a visualização de gráficos
numpy.

O data cleaning, foi realizado por meio do método isnull() para identificar os
dados faltantes e eliminar as variáveis que possuíam mais de 55% de dados
faltantes, e para limpar a visualização, as variáveis: Beer ID, Name, URL, Style,
UserId, Priming Method e Priming Amount, que eram do tipo texto, e não possuíam
valor para a análise, foram desconsideradas.

As amostras utilizadas foram as que possuíam valores maiores que 1.000, na
coluna da variável styleID, foram os índices:7, 10, 134, 9, 4, 30, 86, 6, 175 e 39 que
possuem os valores : 11.940, 7.581, 2.617, 2.038, 1.753, 1.478, 1.268, 1.204, 1.152,
1.072 e 1.044.

Os dados que não estavam no tipo numérico, na coluna: sugar scale foram
classificados para zero e um. Constando para a descrição specific gravity, zero e
para palto, 1. E o mesmo ocorreu para a variável: Brew Method, que possui as
descrições: All grain, Biab, extract e partinal Mash, que foram convertidas pelo
mé todo get_dummies e concatenadas.

Após isso, para as demais variáveis que possuíam dados faltantes foi gerado
um gráfico boxplot para identificar a dispersão e um histograma para evidenciar a
distribuição dos dados, co m os dados das colunas: Boil Gravity( 3,66% de dados
faltantes), Mas Thickness( 40,91%) e Primary Temp (31,80%), e a substituição
desses dados foi dada pela mediana, devido a distribuição dos valores evidenciado
pelo histograma, os dados estão em sua maioria concentrados em volta de um valor
central. Já no caso do Pitch Rate (55,18%), a substituição foi feita pela média devido
a distribuição dos dados descentralizados.

A substituição pela média e média foi feita a partir d a premissa de método de
imputação ingênuo, já que as variáveis do banco de dados são contínuas, este
método é utilizado quando o dado faltante diz respeito a uma variável contínua. Se a
variável pode ser utilizada, a imputação através da média, ou seja, cada valor
faltante na variável Y será preenchido com a média dos valores observados da
variável Y . Outra opção é preencher esses dados com a mediana dos valores
observados de Y (MARTINS, 2017).

No que tange a separação das variáveis, a target foi definida: StyleID e as
preditoras, foram as demais variáveis do dataset. Os modelos utilizados foram de
classificação, 4 tipos: Logistic Regression, Naive Bayes, Decision Tree e
Kneighbors.Regressão logística, é determinada função que relaciona os preditores à
resposta de interesse está reservada a formas lineares (Santos et al. 2017).

A classificação com uma NB, pode ser chamada de rede probabilística ou
rede causal, é vista como um modelo que utiliza teoria dos grafos, condições de
Markove distribuição de probabilidades para representar uma situação, suas
variáveis e estados e então realizar inferências. A condição de Markovarma que as
variáveis não-descendentes não fornecem informações adicionais sobre a variável
em questão, segundo Pearl (1988) apud Machado et al. (2020).

Já o K-NN, ou K - vizinhos mais próximos, é um classificador conhecido
devido a sua simplicidade, fácil entendimento, performance relativamente alta,
habilidade de lidar com dados binários ou multi-classe, apresenta baixa identificação
de erros, é usado em diversas aplicações e baseado em um conjunto de
treinamento (DENG et al., 2016; ROGERS; GIROLAMI, 2011; GUTIERREZ et al. ,
2016; GLOWACZ; GLOWACZ, 2016; YU et al., 2016 apud Rosso 2017).

No que se refere ao algoritmo que constrói uma árvore de decisão, ele tem
um passo principal, que é a escolha de um atributo para rotular o nó atual da árvore.
Deve-se escolher o atributo que tenha o maior poder de discriminação entre as
classes para os exemplos no nó atual. Para isso, deve-se utilizar uma medida de
poder de discriminação de classes (CARVALHO, 2005).

A função para teste utilizada foi a def modelos classificação(a, b), e a
normalização devido a utilização do KNeighbors, foi a MenMaxScaler e a função
para testar qual seria o melhor modelo, foi a StratifiedKFold e a Cross_val_ score.
Depois foi feito o instanciamento das funções e os parâmetros foram passados. E foi
utilizado a função dicionário do python para mostrar os melhores resultados.

Após os resultados exibidos, foi definido a melhor função a ser utilizada, e a
execução foi realizada, exibindo, como resultado da função a melhor acurácia,
melhor K, método de distância e melhor valor para p.

## 3. Conclusão

Em primeiro momento, verificou a necessidade da limpeza dos dados, após a
limpeza e parâmetros de substituição de dados faltantes, procedeu-se com a
normalização dos dados e a substituição dos dados ausentes pela mediana. Análise
feita a partir da dispersão dos dados, por meio da visualização dos gráficos de
boxplot e histograma.

A definição do algoritmo de melhor performance foi definido após testes com:
regressão Logística: 0.44735207768744356 Naive Bayes: 0.47202461607949414,
Decision Tree 0.4711777326106595, KNN: 0.47628726287262874 e o melhor p: 1.
Mostrando que após os resultados exibidos, a melhor função utilizada foi
KNN, e a execução foi realizada, exibindo, como resultado da função, a melhor
acurácia, melhor K, método de distância e melhor valor para p. Os valores foram:
Melhor acurácia: 0.46519308943089427, Melhor k: 9. Método a distância:
chebyshev e Melhor valor p: 1.


## 3. Referências:
   
MARTINS, Paola da Silva. Imputação de Dados Faltantes . Rio de Janeiro, 2017.
19 p. Monografia( Bacharel em Estatística) - Universidade Federal Fluminense.

SANTOS, Hellen Geremias et al. Machine learning para análises preditivas em
saúde: exemplo de aplicação para predizer óbito em idosos de São Paulo,
Brasil . Cadernos de Saúde Pública, Rio de Janeiro, 35 ed., v. 7, p.1-19, Julho,
2019.

Didaticatec, exercício do curso utilizado como base para implementar o código do curso.

MACHADO, E.; DE ASSIS, C.; PEREIRA, Modelagem, Implementação e  Avaliação de Estratégias de Negociação Baseadas em Algoritmos de  Aprendizado de Máquina para o Mercado Financeiro. Revista Brasileira de  Computação Aplicada, v. 12, n. 1, p. 16-31, 8 jan. 2020.  

CARVALHO, D R. Árvore De Decisão / Algoritmo Genético Para Tratar o  Problema De Pequenos Disjuntos Em Classificação De Dados . Programa de Pós  Graduação – Universidade Federal do Rio de Janeiro.Rio de Janeiro. p.1-173 .2005.  

ROSSO,Pedro Augusto Di Francia. Desenvolvimento e Implementação de  Aplicativo de Segurança para Sistemas de Áudio em Smartphones . TCC  (graduação) - Universidade Federal de Santa Catarina, Araranguá, Curso de  Engenharia da Computação, 2017.  

