# Capítulo 6

O objetivo da análise de agrupamentos é a divisão do conjunto de dados em subconjuntos chamados de grupos. Frequentemente, a análise de agrupamentos também é chamada de **classificação não supervisionada**.

## Métodos Hierárquicos

Foco em **métodos aglomerativos**: Partem de um nível mais baixo da hierarquia com $K = N$ conjuntos e vai fundindo os conjuntos conforme sobe, utilizando uma **função de ligação** para tal.

Essa **função de ligação** pode ser:

* Vizinho mais próximo: Utiliza os elementos mais próximos dos conjuntos
* Vizinho mais distante
* Distâncias médias: Utiliza a distância média entre os elementos dos grupos
* Centroides: Utiliza a distância entre centroides

Os algoritmos hierárquicos aglomerativos em geral trabalham com a matriz de distâncias na memória.

## Métodos de partição

### K-medias

Minimiza o critério do **custo quadrático**.

Resultado muito dependente da inicialização, uma vez que usa estratégia gulosa e pode cair em máximo local.

* Enquanto os centros ainda mudam bastante:
	* Para cada registro $r$
		* calcular a distância para cada centro $i$ e atribuir registro $r$ ao conjunto $C_i$ com centro mais próximo
	* Recalcular os centros dos conjuntos

O resultado do algoritmo k-médias é muito sensível à presença de outliers e ruído no conjunto de dados. Um outliers será sempre associado a algum grupo e será contabilizado no cálculo da média, o que pode afastar os centros calculados dos centros do conjunto mais denso de registros.

## Validação de grupos

* **Medidas externas**: que avaliam a qualidade do agrupamento em relação a uma informação externa sobre a estrutura de classes do problema:
	* *pureza* de um grupo é a porção dos registros do grupo que pertence à classe que contém;
	* *entropia* pode ser utilizada para avaliar a heterogeneidade do agrupamento, quanto menor a entropia, melhor o agrupamento.
a maioria dos registros daquele grupo.
* **Medidas internas**: que avaliam a qualidade do agrupamento a partir dos registros do conjunto de dados, em geral utilizando critérios geométricos, sabendo que um bom agrupamento é o que gera grupos coesos e separados:
	* PI (**índice de partição**) quando calculado com funções de pertinência binárias, é a razão entre o critério quadrático do k-médias e a soma ponderada das distâncias entre centro. Para avaliação de agrupamentos obtidos pelo algoritmo k-médias e suas variantes, o PI é um bom índice para a escolha do melhor agrupamento com o mesmo número de grupos $K$, considerando um conjunto de soluções obtidas com diversas inicializações aleatórias;
	* VAT (**visualização qualitativa da tendência de agrupamento**): Um bom agrupamento mostra um contraste mais intenso que um agrupamento de pior qualidade. A observação do data image do conjunto de dados com os registros simplesmente ordenados segundo o resultado do agrupamento permite uma avaliação qualitativa do resultado.
* **Medidas relativas**: que produzem um índice calculado pela combinação de critérios (internos) que avaliam a qualidade de um agrupamento em relação a outros.

## Particionamento de grafos

Solução do **problema do corte mínimo**. 

Grafo pode ser obtido através da **similaridade entre os registros**