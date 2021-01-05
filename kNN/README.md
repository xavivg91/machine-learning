# **El algoritmo k-NN**

El algoritmo _k-Nearest Neighbors_ (_k_ vecinos más cercanos) es un método de clasificación [**supervisada**](https://en.wikipedia.org/wiki/Supervised_learning), es decir, tenemos etiquetado nuestro conjunto de datos de entrenamiento. El algoritmo clasifica cada nueva instancia según el grupo mayoritario al que pertenecen sus _k_ vecinos más cercanos (_k_ instancias del conjunto de entrenamiento más cercanas). Las operaciones que lleva a cabo el algoritmo son las siguientes:

0. Como paso previo, es necesario normalizar los datos. Esta primera operación puede mejorar la exactitud del algoritmo.
1. Calcular la distancia entre la nueva instancia a clasificar y cada una de las instancias del conjunto de entrenamiento. Se suele utilizar la distancia euclidiana, aunque también puede emplearse la distancia de Manhattan o Chebyshev, entre otras. 
2. Seleccionar los _k_ vecinos más cercanos.
3. Asignar a la nueva instancia la clase/etiqueta mayoritaria entre los _k_ vecinos más cercanos.
4. Repetir los pasos 1, 2 y 3 para el resto de instancias a clasificar.

Se trata de un algoritmo [**basado en instancias**](https://en.wikipedia.org/wiki/Lazy_learning) (_lazy learning_). Esto significa que el algoritmo no aprende un modelo global o una generalización a partir del conjunto de entrenamiento, que sirva para clasificar todas las nuevas instancias. Por el contrario, k-NN estima de forma local: la clase/etiqueta de cada nueva instancia depende únicamente de sus _k_ vecinos más cercanos.

Además, k-NN está catalogado como un algoritmo **no paramétrico**, es decir, no presupone una forma concreta de los datos de entrenamiento y no utiliza una función para aproximarlos. En la regresión lineal, por ejemplo, se utiliza la función de una recta para aproximar los datos. 

**Ventajas**
- Sencillo de aprender e implementar.
- Puede ser utilizado para tareas de clasificación o regresión.
- Fase de entrenamiento rápida, puesto que no aprende un modelo.
- Capaz de clasificar instancias en tres o más categorías (_multiclass classification_).

**Inconvenientes**
- Su rendimiento empeora a medida que aumenta el volumen de datos. 
- Sensible a _k_ y a la métrica de distancia o similitud utilizada. 
- Computacionalmente costoso.
- Sensible a la [maldición de la dimensión](https://en.wikipedia.org/wiki/Curse_of_dimensionality).

**Aplicaciones**
- Sistemas de recomendación.
- Predecir si una persona es apta o no para recibir un préstamo bancario. Comprobar si los datos del cliente son similares o no a los de usuarios ya clasificados como morosos. 

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
