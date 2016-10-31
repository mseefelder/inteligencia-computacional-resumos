# Capítulo 5

Classificador: um modelo capaz de predizer a classe correta de um registro a partir dos valores das variáveis de entrada.

**Superfície de decisão**: Fronteira entre as regiões.

## Classificação Bayesiana

### Tipos de probabilidade

* **Probabilidade *a priori***: Probabilidade de ocorrência da classe $C_i$ na ausência de qualquer observação;
* **Probabilidade condicional:** Distribuição de probabilidades das variáveis $x$ quando a classe observada é $C_i$;
* **Probabilidade *a posteriori***: Probabilidade de observar a classe $C_i$ conhecendo a observação (evidência) dos valores das variáveis $x$.

### Métodos de decisão

* Pelo mínimo erro de classificação: Minimiza o erro de classificação
* Pelo mínimo risco codicional: Erro global é maior, mas erro é menor na classe de maior custo de classificação incorreta.

### Classificadores

#### Classificador Bayesiano Simples

Realiza a decisão por uma das formas apresentada acima, geralmente pelo mínimo erro de classificação.

A distribuição de probabilidade condicional dos registros do conjunto de treinamento é calculada, para cada classe, por uma estimativa que considera as variáveis de entrada independentes. Desta forma, o classificador Bayesiano Simples não leva em consideração a covariância entre as variáveis.

Em geral, a probabilidade condicional é estimada como uma distribuição normal monovariável cuja média e variância são estimados no conjunto de treinamento para a variável $x_{i}(t)$ nos registros da classe $C_j$.

A utilização da ACP para eliminar a correlação dos dados nem sempre produz bons resultados, mas é um recurso que pode ser empregado na busca pelo melhor modelo de classificação.

#### Classificador Bayesiano Quadrático

É possível generalizar regras de decisão como **funções discriminantes** em problemas de múltiplas classes.

O classificador Bayesiano com distribuições normais multivariadas (aproximando a distribuição condicional) é chamado de classificador Bayesiano Quadrático.

A estimativa dos parâmetros da equação normal para o cálculo da função discriminante pode se tornar inviável em problemas de alta dimensionalidade, uma vez que são necessários $ p + p(p + 1)/2$ parâmetros para cada classe. Para isso pode ser usada uma diminuição de dimensionalidade através de ACP ou ADL, por exemplo.

## Modelos Lineares de Classificação

Alguns métodos podem ser utilizados diretamente no ajuste de parâmetros do modelo linear, sem a necessidade de hipóteses ou estimativa da distribuição de probabilidades condicional.

### Mínimos Quadrados

Equivalente à decisão pelo menor erro ajustando um classificador.

### Mínimos Quadrados Ponderado

Efeitos equivalentes a decisão pelo risco condicional.

### Regressão Logística

Usa função sigmoide para ajuste de parâmetros.

## Avaliação de Classificadores

As estatísticas de avaliação de classificadores são calculadas a partir da matriz de confusão.

Muito utilizada em estatística para representar as possíveis soluções de um teste de hipóteses e utiliza a mesma terminologia. Em problemas de classificação, as linhas representam as classes observadas e as colunas representam as classes preditas pelo modelo.

**Acurácia** do modelo: Taxa de classificação correta do modelo

**Erro global** do modelo: Complemento da acurácia.

O erro global destaca melhor a diferença de desempenho de dois classificadores. Por exemplo, um modelo com acurácia de 96% tem o dobro do erro de outro modelo com 98% de acurácia.