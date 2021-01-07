# **Conceptos**

**Básicos**

- [**Conjunto de datos**](https://en.wikipedia.org/wiki/Data_set) (_data set_). Colección de datos formada por columnas (atributos) y filas (instancias u observaciones). En algoritmos supervisados de _machine learning_, es necesario particionar nuestros datos en dos subconjuntos: conjunto de entrenamiento y conjunto de prueba.

- **Instancia**. Observación, fila, registro, objeto, ejemplo, etc. en un conjunto de datos. En una tabla con datos de jugadores de baloncesto, por ejemplo, cada fila es una instancia y representa a un jugador de baloncesto diferente. A su vez, cada instancia se compone de diferentes **atributos** (_features_) categóricos o cuantitativos, como pueden ser la edad, peso, altura, años de experiencia, nacionalidad, liga, etc. de los deportistas.

- [**Conjunto de entrenamiento**](https://en.wikipedia.org/wiki/Training,_validation,_and_test_sets) (_training set_). Subconjunto de datos utilizado para entrenar un modelo. Estos datos están etiquetados (_labeled_) mediante una columna denominada variable objetivo o _target_. 

- **Objetivo** (_target_). Atributo que queremos predecir. Puede ser categórico ("Apto" o "No apto") o continuo (precio de una casa).

- [**Conjunto de prueba**](https://en.wikipedia.org/wiki/Training,_validation,_and_test_sets) (_test set_). Subconjunto de datos utilizado para evaluar el modelo. La finalidad del modelo, una vez ha sido entrenado, es predecir la variable objetivo de las instancias de prueba. 

**Aprendizajes**

- [**Aprendizaje supervisado**](https://en.wikipedia.org/wiki/Supervised_learning) (_supervised learning_). Tenemos etiquetado nuestro conjunto de datos de entrenamiento. Los algoritmos supervisados, después de haber aprendido a partir del conjunto de entrenamiento, deducen una función capaz de predecir la etiqueta/clase correspondiente a cualquier instancia de entrada. Dentro de este tipo de aprendizaje, hablamos de un algoritmo de regresión si el atributo objetivo es numérico, y de clasificación si es categórico. Ejemplos: árboles de decisión, _k-Nearest Neighbors_, _Support Vector Machines_. 

- [**Aprendizaje no supervisado**](https://en.wikipedia.org/wiki/Unsupervised_learning) (_unsupervised learning_). Las observaciones dadas en el conjunto de datos no están etiquetadas, no hay un conocimiento a priori ni ningún atributo objetivo que predecir. Ejemplos: _k-means_, _Principal Component Analysis_.

- [**Aprendizaje vago o basado en instancias**](https://en.wikipedia.org/wiki/Lazy_learning) (_lazy or instance-based learning_). El algoritmo no aprende un modelo global o una generalización durante la fase de entrenamiento, simplemente guarda en memoria todas las instancias. El aprendizaje sucede en el mismo momento en el que se prueban los datos de test. El atributo objetivo es estimado de forma local, para cada nueva instancia. Su fase de entrenamiento es rápida (no construye un modelo global), mientras que la predicción es más lenta, puesto que compara cada nueva instancia con todas las instancias del conjunto de entrenamiento. Un ejemplo de algoritmo perezoso o basado en instancias es k-NN, donde la clase/etiqueta de cada nueva instancia depende únicamente de sus _k_ vecinos más cercanos. 

- [**_Eager learning_**](https://en.wikipedia.org/wiki/Eager_learning). A diferencia del aprendizaje basado en instancias, en este caso el algoritmo aprende un modelo global o una generalización a partir del conjunto de entrenamiento, antes de probar los datos de test. El modelo global construido se aplica para estimar la clase/etiqueta de todas las nuevas instancias. Dedica más tiempo al entrenamiento (aprende un modelo) que a la predicción. Ejemplos: árboles de decisión, _Support Vector Machines_.

- [**Matriz de confusión**](https://en.wikipedia.org/wiki/Confusion_matrix) (_matrix confusion_). Herramienta para evaluar los aciertos y errores de un modelo de aprendizaje supervisado.



- **Algoritmo paramétrico** (_parametric algorithm_).

- **Algoritmo no paramétrico** (_nonparametric algorithm_). 
curva roc -> clasificador binario
https://medium.com/@lamiae.hana/parametric-and-nonparametric-machine-learning-algorithms-ec9a21f25705
