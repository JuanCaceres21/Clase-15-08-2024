# Clase-15-08-2024

Para esta clase tenemos los distintos metodos de discretizacion, la discretizacion se refiere a buscar el equivalente de la representacion de laplace de un sistema en el espacio Z o espacio discreto. Podemos lograr esto por medio de 6 metodos distintos.

## Invarianza al pulso
En este metodo, basicamente debemos encontrar la transformada Z de la anti transformada de laplace de un sistema:

$$(𝐶)𝑧 =𝑇𝑍{(ℒ)^{-1}(𝐶(𝑠)}𝑡=𝐾𝑇)$$

El termino T se debe multiplicar por toda la funcion, esto para tener en cuenta el tiempo de muestreo.

💡Ejemplo 1: 

$$C(s)=\frac{4}{(s+1)}+\frac{5}{(s+10)}$$

$$ℒ^{-1}[C(s)]={3e}^{-t}+{5e}^{-10t}$$

$$ℒ^{-1}[C(s)]_{t=KT}={3e}^{-t}+{5e}^{-10t}$$

$$C(z)=T Z[{3e}^{-KT}+{5e}^{-10KT}]$$

$$C(z)=T [\frac{3Z}{(Z-{e}^{-T})}+\frac{5Z}{(Z-{e}^{-10T})}]$$

## Invarianza al paso

Este metodo que es bastante similar al anterior, debemos hacer exactamente lo mismo, pero añadiendo la funcion de paso unitario.

$$u(k)=u(t)&&

$${(Z)}^{-1}[C(s)\frac{Z}{(Z-1)}]=ℒ^{-1}[C(s)\frac{1}{S}]$$
