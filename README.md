# Clase-15-08-2024

Para esta clase tenemos los distintos metodos de discretizacion, la discretizacion se refiere a buscar el equivalente de la representacion de laplace de un sistema en el espacio Z o espacio discreto. Podemos lograr esto por medio de 6 metodos distintos.

## Metodods de discretización 

### Invarianza al pulso
En este metodo, basicamente debemos encontrar la transformada Z de la anti transformada de laplace de un sistema:

$$(𝐶)𝑧 =𝑇𝑍{(ℒ)^{-1}(𝐶(𝑠)}𝑡=𝐾𝑇)$$

El termino T se debe multiplicar por toda la funcion, esto para tener en cuenta el tiempo de muestreo.

💡Ejemplo 1: 

$$C(s)=\frac{4}{(s+1)}+\frac{5}{(s+10)}$$

$$ℒ^{-1}[C(s)]={3e}^{-t}+{5e}^{-10t}$$

$$ℒ^{-1}[C(s)]_{t=KT}={3e}^{-t}+{5e}^{-10t}$$

$$C(z)=T Z[{3e}^{-KT}+{5e}^{-10KT}]$$

$$C(z)=T [\frac{3Z}{(Z-{e}^{-T})}+\frac{5Z}{(Z-{e}^{-10T})}]$$

### Invarianza al paso

Este metodo que es bastante similar al anterior, debemos hacer exactamente lo mismo, pero añadiendo la funcion de paso unitario.

$$ u(k)=u(t) $$

$${Z}^{-1}[C(s)\frac{Z}{(Z-1)}]=ℒ^{-1}[C(s)\frac{1}{S}]$$

$$Z[{ℒ^{-1}[C(s)\frac{1}{S}]}]=\frac{Z}{Z-1}$$

Podriamos decir que este metodo es igual al anterior solo que multiplicando el resultado final por la funcion paso discreta para ver su respuesta a la misma.

### Metodo euler hacia adelante

haciendo uso de las derivadas, las cuales son el calculo de una pendiente en un punto especifico, podemos hacer una recreacion de una señal continua, la fdiferencia que tenemos con el metodo que veremos mas adelante es que hacemos la pendiente con el dato siguiente y no el anterior.

$$\frac{d}{dkT}(kT)=\frac{x(k+1)-x(k)}{T}$$

$$ℒ[\\frac{d}{dkT}x(t)=sX(s)]$$

Para la transformada Z

$$Z[\frac{x(k+1)-x(k)}{T}]=\frac{Z-1}{T}X(Z) $$

Podemos decir que:

$$s≈\frac{z-1}{T}$$

### Metodo euler hacia atras

Como se comento en el metodo anterior, este metodo es igual al de adelanto pero hacia atra, es decir tomamos la pendiente con referencia al dato actual y al anterior.

$$\frac{d}{dkT}(kT)=\frac{x(k)-x(k-1)}{T}$$

$$ℒ[\\frac{d}{dkT}x(t)=sX(s)]$$

Para la transformada Z

$$Z[\frac{x(k)-x(k-1)}{T}]=\frac{1-z^{-1}}{T}X(Z) $$

Podemos decir que:

$$s≈\frac{z-1}{Tz}$$

### Método trapezoidal “Tustin”

En este metodo adiferencia de los dos anteriores no solo trazamos una linea recta, sino que se intenta dibujar una figura geometrica, un trapecio, cuya parte superior intenta emular los valores de una señal.

version de Laplace:

$$s=\frac{\frac{2}{T}(z-1)}{z+1} $$

version de Z:

$$s=\frac{1+\frac{Ts}{2}}{1-\frac{Ts}{2}} $$

## Teorema de muestreo:

Este teorema nos presenta el problema que relaciona la frecuencia de muestreo y la frecuencia de la señal que se quiere generar, este problema se presenta cuando la frecuancia de muestreo es mas baja que el doble de la frecuencia de  la señal deseada.

basicamente podemos decir que el sistema no tiene la capacidad de mostrar de manera fiel la señal que trata de recrear.

💡Ejemplo 2: 

![Señal seno discretizada](lab1 C.D.\scope_2.PNG)

