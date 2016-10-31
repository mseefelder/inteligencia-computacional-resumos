# Capítulo 2

* Análise estatística
* Limpeza dos dados

## Análise monovariável

* **média**
* **variância**: medida de dispersão da amostra
* **desvio padrão**: mais usado para dispersão, tem escala da variável
* **mínimo** e **máximo**
* **mediana**: divide o conjunto de valores da variável em dois subconjuntos iguais
* **percentil**: divide de forma que P% dos valores sejam $<=$ a este valor
* **faixa interquartil**: entre o 25 percentil (1º quartil) e o 75 percentil (3º quartil)
* **moda**

## Análise Multivariada

### Matriz de correlações 

A correlação é uma medida padronizada da covariância de duas variáveis.

O coeficiente de correlação pode ser entendido como uma medida da redundância da informação representada por um par de variáveis. Variáveis totalmente correlacionadas **(positiva ou negativamente)** representam essencialmente a mesma informação e uma delas poderia ser descartada. Entretanto, exceto no caso de correlação total, não é possível decidir sobre qual variável remover apenas a partir da informação de correlação.

*Coeficiente de correlação* mede **apenas a dependência linear**, portanto um resultado = 0 não representa que não há relação entre as variáveis, apenas que a relação não é linear.

### Matriz de distâncias ou similaridades

Utiliza outra métrica que não é a correlação.

## Limpeza de dados

### Padronização de variáveis

* Por **mínimo e máximo**:
	* reduz a escala da variável ao intervalo [0,1] 
	* não deve ser utilizado na presença de outliers, pois o valor máximo ou mínimo de alguma variável pode gerar distorções
	* Na presença de outliers, os valores de máximo e mínimo podem ser substituídos pelos percentis 95 e 5
* Por **z-score**:
	* robusta a outliers 
	* variável padronizada tem média nula e desvio padrão um
	* em distribuições altamente assimétricas pode gerar uma distorção de escala, pois utiliza as estatísticas de média e desvio padrão, mais apropriadas para distribuições simétricas
* **Transformação do logaritmo**:
	* Para tornar simétricas as distribuições de variáveis

### Detecção de outliers

Analisar os *boxplots* para ter intuição da situação de *outliers*.

Utilizar ordenação da distância média entre registros (retirada da *matriz de distâncias*) para encontrar os registros mais distantes de todos.

### Valores ausentes

Basicamente existem duas estratégias principais para o tratamento de valores ausentes: a *eliminação do registro* contendo valores ausentes ou o *preenchimento* (imputação) dos dados ausentes.

O *preenchimento* pode ser feito por média, k-vizinhos ou algum outro método.

### Transformações Lineares

Em mineração de dados uma transformação linear é utilizada para realizar uma mudança de coordenadas do conjunto de dados para um novo conjunto de coordenadas, em geral de menor dimensionalidade, e com características mais apropriadas ao problema. As variáveis transformadas são combinações lineares das anteriores e, em princípio, não podem ser interpretadas no contexto da aplicação.

#### Análise de Componentes Principais (PCA)

A ACP permite a redução da dimensionalidade do conjunto de dados pela eliminação da redundância provocada pela correlação entre as variáveis. A ACP é realizada por um procedimento de cálculo da matriz de transformação linear ortogonal que, aplicada ao conjunto de dados, gera um novo conjunto de dados de variáveis transformadas.

**Considera que todas as variáveis de entrada são numéricas, com distribuição normal.**

O número $n$ de componentes principais é escolhido de forma que sua variância total represente uma parcela importante (em geral maior que 85%) da variância total dos dados originais.

#### Decomposição em Valores Singulares (SVD)

O cálculo da SVD é equivalente ao cálculo de decomposição em autovalores de matrizes simétricas. Pode ser utilizada para a remoção de vetores linearmente dependentes e realizar a diminuição de dimensionalidade de maneira similar à ACP.

### Análise Discriminante Linear (LDA)

A Análise Discriminante Linear (ADL), assim como a ACP e a SVD, é uma técnica para o cálculo de uma transformação linear. A ADL, entretanto, leva em consideração a informação da classe para o cálculo da transformação de tal forma que, no novo espaço de coordenadas, a separação entre as classes seja máxima.

A transformação da ADL é calculada de forma que o novo sistema de coordenadas produza dados com **máxima variância** *entre classes* e **mínima** *variância intraclasses*.

### Análise de Correlação Canônica

Em problemas de classificação, ADL calcula uma transformação linear que leva em consideração a informação das classes para definir um espaço de coordenadas onde a separação das classes é ótima. Em problemas de regressão é possível obter um resultado semelhante com a Análise de Correlação Canônica (ACC).