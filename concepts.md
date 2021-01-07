# **Conceptos**

**Básicos**

- [**_Data set_**](https://en.wikipedia.org/wiki/Data_set) (conjunto de datos). Colección de datos formada por columnas (atributos) y filas (instancias u observaciones). En algoritmos supervisados de _machine learning_, es necesario particionar nuestros datos en dos subconjuntos: conjunto de entrenamiento y conjunto de prueba.

- **Instancia**. Observación, fila, registro, objeto, ejemplo, etc. en un conjunto de datos. En una tabla con datos de jugadores de baloncesto, por ejemplo, cada fila es una instancia y representa a un jugador de baloncesto diferente. A su vez, cada instancia se compone de diferentes **atributos** (_features_) categóricos o cuantitativos, como pueden ser la edad, peso, altura, años de experiencia, nacionalidad, liga, etc. de los deportistas.

- [**_Training set_**](https://en.wikipedia.org/wiki/Training,_validation,_and_test_sets) (conjunto de entrenamiento). Subconjunto de datos utilizado para entrenar un modelo. Estos datos están etiquetados (_labeled_) mediante una columna denominada variable objetivo o salida (_target_ u _output_). 

- **_Target_**, **_output_** o **label** (variable o atributo objetivo, salida, etiqueta). Atributo que queremos predecir. Puede ser categórico ("Apto" o "No apto") o continuo (precio de una casa).

- [**_Test set_**](https://en.wikipedia.org/wiki/Training,_validation,_and_test_sets) (conjunto de prueba). Subconjunto de datos utilizado para evaluar el modelo. La finalidad del modelo, una vez ha sido entrenado, es predecir la variable objetivo de las instancias de prueba. 

**Aprendizajes**

- [**_Supervised learning_**](https://en.wikipedia.org/wiki/Supervised_learning) (aprendizaje supervisado). Tenemos etiquetado nuestro conjunto de datos de entrenamiento. Los algoritmos supervisados, mediante su aprendizaje a partir del conjunto de entrenamiento, deducen una función capaz de predecir la etiqueta correspondiente a instancias nueva. Es decir, el algoritmo entrena con instancias ya etiquetadas (conocemos el _target_), aprende una función que establece una correspondencia entre los datos de entrada y el _target_ (_mapping_), y aplica esta misma función para predecir el _target_ de instancias nuevas. 

  Dentro de este tipo de aprendizaje, hablamos de un algoritmo de regresión si el atributo objetivo es numérico, y de clasificación si es categórico. Ejemplos: árboles de         decisión, _k-Nearest Neighbors_, _Support Vector Machines_. 
  
- [**_Unsupervised learning_**](https://en.wikipedia.org/wiki/Unsupervised_learning) (aprendizaje no supervisado). Las observaciones dadas en el conjunto de datos no están etiquetadas, no hay un conocimiento a priori ni ningún atributo objetivo que predecir. Ejemplos: _k-means_, _Principal Component Analysis_.

- [**_Lazy or instance-based learning_**](https://en.wikipedia.org/wiki/Lazy_learning) (aprendizaje vago o basado en instancias). El algoritmo no aprende un modelo global o una generalización durante la fase de entrenamiento, simplemente guarda en memoria todas las instancias. El aprendizaje sucede en el mismo momento en el que se prueban los datos de test. El atributo objetivo es estimado de forma local, para cada nueva instancia. Su fase de entrenamiento es rápida (no construye un modelo global), mientras que la predicción es más lenta, puesto que compara cada nueva instancia con todas las instancias del conjunto de entrenamiento. Un ejemplo de algoritmo perezoso o basado en instancias es k-NN, donde la etiqueta de cada nueva instancia depende únicamente de sus _k_ vecinos más cercanos. 

- [**_Eager learning_**](https://en.wikipedia.org/wiki/Eager_learning) (aprendizaje entusiasta). A diferencia del aprendizaje basado en instancias, en este caso el algoritmo aprende un modelo global o una generalización a partir del conjunto de entrenamiento, antes de probar los datos de test. El modelo global construido se aplica para estimar la etiqueta de todas las nuevas instancias. Dedica más tiempo al entrenamiento (aprende un modelo) que a la predicción. Ejemplos: árboles de decisión, _Support Vector Machines_.

- [**_Matrix confusion_**](https://en.wikipedia.org/wiki/Confusion_matrix) (matriz de confusión). Herramienta para evaluar los aciertos y errores de un modelo de aprendizaje supervisado.



- **_Parametric algorithm_** (algoritmo paramétrico).

- **_Nonparametric algorithm_** (algoritmo no paramétrico). 
curva roc -> clasificador binario
https://medium.com/@lamiae.hana/parametric-and-nonparametric-machine-learning-algorithms-ec9a21f25705
da igual que incremente mucho el volumen de datos, se podran seguir expresando mediante un número finito de parametros
https://sefiks.com/2020/05/02/parametric-and-non-parametric-models-in-machine-learning/
https://www.aprendemachinelearning.com/que-es-overfitting-y-underfitting-y-como-solucionarlo/
