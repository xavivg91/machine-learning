# **El algoritmo k-NN**

El algoritmo _k-Nearest Neighbors_ (_k_ vecinos más cercanos) es un método de clasificación **supervisada**, es decir, tenemos etiquetado nuestro conjunto de datos de entrenamiento. El algoritmo clasifica cada nueva instancia según el grupo al que pertenecen sus _k_ vecinos más cercanos (_k_ instancias del conjunto de entrenamiento más cercanas). Los pasos son los siguientes:

1. Normalizar los datos. Esta primera operación puede mejorar la exactitud del algoritmo.
2. Calcular la distancia entre la instancia a clasificar y cada una de las instancias del conjunto de entrenamiento. Se suele utilizar la distancia euclidiana, aunque también puede emplearse la distancia de Manhattan o Chebyshev, entre otras. 
3. Seleccionamos los _k_ elementos más cercanos
4. De los elementos seleccionados, ¿cuál es la clase/etiqueta mayoritaria? Una instancia es asignada a una clase si esta es la clase más frecuente entre los _k_ vecinos de entrenamiento.

Se trata de un algoritmo **basado en instancias** (_lazy learning_). Esto significa que el algoritmo no aprende un modelo o una generalización a partir del conjunto de entrenamiento, sino que compara cada nueva instancia con las instancias de entrenamiento. Sensible a _k_ y a la métrica de distancia o similitud utilizada. 

**Ventajas**: Sencillo de aprender e implementar.

**Inconvenientes**: Funciona bien con pocos datos, pero su rendimiento empeora para data sets con muchas filas y columnas. Recordemos que para cada nueva instancia a clasificar, el algoritmo tiene que calcular la distancia con todas las instancias de entrenamiento.

# **Ejemplo**

Dada la siguiente imagen...

<p align="center">
<img src='knn_ejemplo.png' height="225" /></a>
</p>

- El punto verde es la instancia a clasificar
- Los triangulos y cuadrados son instancias del conjunto de entrenamiento, pertenecientes a dos grupos diferentes.

¿A qué grupo pertenecerá el punto verde? Depende del valor de _k_:

Para k=1 → Se clasificará como triángulo, ya que la instancia más cercana es un triángulo

Para k=2 → Las dos instancias más cercanas son triángulos, así que se clasificará como triángulo

Para k=3 → Las tres instancias más cercanas son dos triángulos y un cuadrado. Como predominan los triángulos, se clasificará como triángulo.

Para k=5 → Las cinco instancias más cercanas son dos triángulos y tres cuadrados, así que se clasificará como cuadrado.

... y así sucesivamente.
