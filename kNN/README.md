# **El algoritmo k-NN**

El algoritmo _k-Nearest Neighbors_ (_k_ vecinos más cercanos) es un método de clasificación [**supervisada**](https://es.wikipedia.org/wiki/Aprendizaje_supervisado), es decir, tenemos etiquetado nuestro conjunto de datos de entrenamiento. El algoritmo clasifica cada nueva instancia según el grupo mayoritario al que pertenecen sus _k_ vecinos más cercanos (_k_ instancias del conjunto de entrenamiento más cercanas). Las operaciones que lleva a cabo el algoritmo son las siguientes:

0. Como paso previo, es necesario normalizar los datos. Esta primera operación puede mejorar la exactitud del algoritmo.
1. Calcular la distancia entre la nueva instancia a clasificar y cada una de las instancias del conjunto de entrenamiento. Se suele utilizar la distancia euclidiana, aunque también puede emplearse la distancia de Manhattan o Chebyshev, entre otras. 
2. Seleccionar los _k_ vecinos más cercanos.
3. Asignar a la nueva instancia la clase/etiqueta mayoritaria entre los _k_ vecinos más cercanos.
4. Repetir los pasos 1, 2 y 3 para el resto de instancias a clasificar.

Se trata de un algoritmo [**basado en instancias**](https://es.wikipedia.org/wiki/Aprendizaje_vago) (_lazy learning_). Esto significa que el algoritmo no aprende un modelo o una generalización a partir del conjunto de entrenamiento, sino que compara cada nueva instancia con las instancias de entrenamiento. 

**Ventajas**
- Sencillo de aprender e implementar.
- Puede ser utilizado para tareas de clasificación o regresión.
- Fase de entrenamiento rápida, no es necesario construir un modelo.

**Inconvenientes**
- Su rendimiento empeora a medida que aumenta el volumen de datos. 
- Sensible a _k_ y a la métrica de distancia o similitud utilizada. 
- Computacionalmente costoso.
- Sensible a la [maldición de la dimensión](https://es.wikipedia.org/wiki/Maldici%C3%B3n_de_la_dimensi%C3%B3n).

**Aplicaciones**
- Sistemas de recomendación.

# **Ejemplo**

Dada la siguiente imagen...

<p align="center">
<img src='knn_ejemplo.png' height="225" /></a>
</p>

- El punto verde es una nueva instancia a clasificar.
- Los triangulos y cuadrados son instancias del conjunto de entrenamiento, pertenecientes a dos grupos diferentes.

¿A qué grupo pertenecerá el punto verde? Depende del valor de _k_:

| _k_   | Triángulos | Cuadrados | El punto verde será...  |
|-------| -----------|-----------|-------------------------|
| _k=1_ |      1     |     0     |       1>0 → Triángulo   |
| _k=2_ |      2     |     0     |       2>0 → Triángulo   |
| _k=3_ |      2     |     1     |       2>1 → Triángulo   |
| _k=4_ |      2     |     2     |       2=2               |
| _k=5_ |      2     |     3     |       2<3 → Cuadrado    |


Siempre es mejor escoger un número impar de vecinos, de forma que no tengamos empates.
