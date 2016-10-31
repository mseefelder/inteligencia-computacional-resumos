# Capítulo 4

## Autocovariância e Autocorrelação:

As funções de autocorrelação e de correlação cruzada permitem identificar as características dinâmicas do processo em estudo, conforme modelos de séries temporais e sistemas dinâmicos.

Vamos considerar **processos estacionários**:

### Processo Estacionário

* Também chamados de **Sistemas Dinâmicos Inverantes no Tempo**;
* Características estatísticas não se alteram em amostras distintas;
* Distribuição de probabilidade de uma sequência é idêntica à distribuição da sequência defasada de $k$ registros.

### Autocovariância:

* É a covariância entre um registro $y(t)$ e outro registro $y(t + k)$;
* Em um **processo estacionário** autocovariância entre dois registros separados de $k$ instantes de tempo é a mesma para qualquer instante $t$ e depende apenas do valor de $k$, chamado de atraso.

### Autocorrelação:

* Valor adimensional;
* Um valor para cada atraso $k$;
* O conjunto dos valores de autocorrelação para todos os valores de atraso é chamado **função de autocorrelação** (ACF) ou **correlograma**;
* Os valores de autocorrelação são simétricos em relação à $k= 0$.

### Covariância e correlação cruzadas:

* Em sistemas dinâmicos em que as entradas e saídas do sistema são observadas, é possível calcular as funções de covariância e de correlação cruzadas;
* A função de correlação cruzada mostra a correlação entre as variáveis de entrada e saída do sistema em relação a diversos valores de atraso.
