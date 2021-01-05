# **Conceptos importantes**

- [**Aprendizaje supervisado**](https://en.wikipedia.org/wiki/Supervised_learning) (_supervised learning_). Tenemos etiquetado nuestro conjunto de datos de entrenamiento. Los algoritmos supervisados, después de haber aprendido a partir del conjunto de entrenamiento, deducen una función capaz de predecir la etiqueta/clase correspondiente a cualquier instancia de entrada. Dentro de este tipo de aprendizaje, hablamos de un algoritmo de regresión si el atributo objetivo es numérico, y de clasificación si es categórico. Ejemplos: árboles de decisión, _k-Nearest Neighbors_, _Support Vector Machines_, etc. 

- [**Aprendizaje no supervisado**](https://en.wikipedia.org/wiki/Unsupervised_learning) (_unsupervised learning_). Las observaciones dadas en el conjunto de datos no están etiquetadas, no hay un conocimiento a priori ni ningún atributo objetivo que predecir. Ejemplos: _k-means_, _Principal Component Analysis_, etc. 

- [**_Lazy learning_**](https://en.wikipedia.org/wiki/Lazy_learning). El algoritmo no aprende un modelo global o una generalización a partir del conjunto de entrenamiento. El atributo objetivo es estimado de forma local, para cada nueva instancia. Su fase de entrenamiento es rápida (no aprenden un modelo), mientras que la predicción es más lenta. Un ejemplo de algoritmo basado en instancias es k-NN, donde la clase/etiqueta de cada nueva instancia depende únicamente de sus _k_ vecinos más cercanos.

- [**_Eager learning_**](https://en.wikipedia.org/wiki/Eager_learning). A diferencia del aprendizaje basado en instancias, en este caso el algoritmo aprende un modelo global o una generalización a partir del conjunto de entrenamiento, antes de recibir nuevas instancias a clasificar. El modelo global construido se aplica para estimar la clase/etiqueta de todas las nuevas instancias. Dedica más tiempo a la fase de entrenamiento (aprenden un modelo) que a la de clasificación. Ejemplos: árboles de decisión, _Support Vector Machines_, etc.


https://medium.com/@lamiae.hana/parametric-and-nonparametric-machine-learning-algorithms-ec9a21f25705
