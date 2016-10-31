# Capítulo 3

analista: primeiro modelo linear, depois compara com não-linear. Limite inferior

## Regressão

Como ajustar um modelo a partir dos dados observados que seja o mais próximo possível da relação real entre as variáveis que geraram a amostra

### Modelo linear

Modelo é linear nos **parâmetros** $\rightarrow$ vetor de saíde é uma combinação linear dos **regressores**.
No modelo linear puro, o **vetor de regressores** é igual às **variáveis de entrada**.

## Mínimos quadrados

Algoritmo mais simples para realizar a **regressão linear**: consistem em ajustas os **parâmetros**  utilizando o **Erro Médio Quadrático (EMQ)** como critério.

Estatísticamente,  *o EMQ pressupões que o vetor de resíduos tem **distribuição normal**, **média nula** e **variância constante***.

O *MMQ (Método dos Mínimos Quadrados)* produz os **parâmetros de mínima variância** e *se os **resíduos** do modelo tem **distribuição normal*** a solução é a de **máxima verossimilhança**.

Caso hajam vetores **linearmente dependentes** na **matriz de regressores** a solução pode ser **matematicamente instável**.

**Parâmetros** com **valores muito altos** são indicativo de que o **modelo tem complexidade inadequada**.

## *Overfitting*

Ocorre quando: 

* A **complexidade do modelo** é **maior do que a complexidade da relação**
* &
* O **tmanho da amostra** é **pequeno em relação à complexidade do modelo**

## Etapas da criação de um modelo

1. Escolha do **tipo** do modelo (pré-seleção de um conjunto defunções promissor);
2. Seleção da **estrutura** do modelo (limitar o espaço de soluções a um subconjunto através de hipóteses e conhecimento *a priori*);
3. Definição de um princípio indutivo para gerar o modelo, geralmente gerando um **problema de otimização**;
4. Solução do **problema de otimização** obitdo em 3 gerando os **parâmetros ajustados** do modelo

## Bias x variância

### *Bias*:

Diferença entre o valor real da função em $x(t)$ e o valor esperado da aproximação naquele ponto.

Acontece quando a complexidade do modelo é inferior à complexidade da função real.

### Variância:

Valor esperado da diferença entre uma estimativa do modelo e o valor esperado de todas as estimativas do modelo

É o efeito da complexidade do modelo ser maior que a complexidade real em relação ao tamanho da amostra.

## Regularização

Diminuir o espaço de solução para encontrar uma solução com complexidade menor e melhor relação de *bias* e variância

### Tikhonov

Minimização do EMQR (Erro Médio Quadrático Regularizado).

Adição de uma constante na diagonal principal da Matriz de Coeficientes para aumentar sua estabilidade.

### Por Componentes Principais

Utiliza SVD para a seleção apenas das colunas linearmente independentes da Matriz de Coeficientes  e monta o modelo com um número $r$ de colunas principais dessas, definido pelo usuário.

## Validação

O método de separar o conjunto de treinameto em uma parte para treinamento e outra para validação é muito simples, masfalha no caso de conjuntos pequenos de dados pois o jeito com o qual a partição é feita pode causar variações importantes nas estatísticas de validação. Por isso o recomendado é a técnica de **validação cruzada**.

### Validação cruzada

O conjunto de treinamento é dividido em K subconjuntos e a validação é realizada em $K$ ciclos: em cada ciclo, o modelo é ajustado utilizando $K− 1$ subconjuntos e avaliado no subconjunto correspondente ao ciclo.