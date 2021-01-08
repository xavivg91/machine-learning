# **Conceptos**

**Básicos**

- [**_Data set_**](https://en.wikipedia.org/wiki/Data_set) (conjunto de datos). Colección de datos formada por columnas (atributos) y filas (instancias u observaciones). En algoritmos supervisados de _machine learning_, es necesario particionar nuestros datos en dos subconjuntos: conjunto de entrenamiento y conjunto de prueba.

- **Instancia**. Observación, fila, registro, objeto, ejemplo, etc. en un conjunto de datos. En una tabla con datos de jugadores de baloncesto, por ejemplo, cada fila es una instancia y representa a un jugador de baloncesto diferente. A su vez, cada instancia se compone de diferentes **atributos** (_features_) categóricos o cuantitativos, como pueden ser la edad, peso, altura, años de experiencia, nacionalidad, liga, etc. de los deportistas.

- [**_Training set_**](https://en.wikipedia.org/wiki/Training,_validation,_and_test_sets) (conjunto de entrenamiento). Subconjunto de datos utilizado para aprender un modelo. Estos datos están etiquetados (_labeled_) mediante una columna denominada variable objetivo o salida (_target_ u _output_). 

- **_Target_**, **_output_** o **_label_** (variable o atributo objetivo, salida, etiqueta). Atributo que queremos predecir. Puede ser categórico ("Apto" o "No apto") o continuo (precio de una casa).

- [**_Test set_**](https://en.wikipedia.org/wiki/Training,_validation,_and_test_sets) (conjunto de prueba). Subconjunto de datos utilizado para evaluar el modelo. La finalidad del modelo aprendido durante el entrenamiento es predecir la variable objetivo de las instancias de prueba. 

- **_Mapping function_**. Función que se deduce durante el entrenamiento y establece una correspondencia entre los datos de entrada y el _target_. Una vez construida, se utiliza esta misma función para predecir el _target_ de instancias nuevas. Se puede interpretar como una función <img src="https://render.githubusercontent.com/render/math?math=Y=f(x)"> que mapea los datos de entrada en una salida.

**Aprendizajes**

- [**_Supervised learning_**](https://en.wikipedia.org/wiki/Supervised_learning) (aprendizaje supervisado). Tenemos etiquetado nuestro conjunto de datos de entrenamiento. Los algoritmos supervisados, mediante su aprendizaje a partir del conjunto de entrenamiento, deducen una función capaz de predecir la etiqueta correspondiente a nuevas instancias. Es decir, el algoritmo entrena con instancias ya etiquetadas (conocemos el _target_), aprende una función que establece una correspondencia entre los datos de entrada y el _target_ (_mapping function_), y posteriormente aplica esta misma función para predecir el _target_ de instancias nuevas. 

  Dentro de este tipo de aprendizaje, hablamos de un algoritmo de regresión si el atributo objetivo es numérico, y de clasificación si es categórico. Ejemplos: árboles de         decisión, _k-Nearest Neighbors_, _Support Vector Machines_. 
  
- [**_Unsupervised learning_**](https://en.wikipedia.org/wiki/Unsupervised_learning) (aprendizaje no supervisado). Las observaciones dadas en el conjunto de datos no están etiquetadas, no hay un conocimiento a priori ni ningún atributo objetivo que predecir. Ejemplos: _k-means_, _Principal Component Analysis_.

- [**_Lazy or instance-based learning_**](https://en.wikipedia.org/wiki/Lazy_learning) (aprendizaje vago o basado en instancias). El algoritmo no aprende un modelo global o una generalización durante el entrenamiento, simplemente guarda en memoria todas las instancias. El aprendizaje sucede en el mismo momento en el que se prueban los datos de test. El atributo objetivo es estimado de forma local, para cada nueva instancia. Su fase de entrenamiento es rápida (no construye un modelo global), mientras que la predicción es más lenta, puesto que compara cada nueva instancia con todas las instancias del conjunto de entrenamiento. Un ejemplo de algoritmo perezoso o basado en instancias es k-NN, donde la etiqueta de cada nueva instancia depende únicamente de sus _k_ vecinos más cercanos. 

- [**_Eager learning_**](https://en.wikipedia.org/wiki/Eager_learning) (aprendizaje entusiasta). A diferencia del aprendizaje basado en instancias, en este caso el algoritmo aprende un modelo global o una generalización a partir del conjunto de entrenamiento, antes de probar los datos de test. El modelo global construido se aplica para estimar la etiqueta de todas las nuevas instancias. Dedica más tiempo al entrenamiento (aprende un modelo) que a la predicción. Ejemplos: árboles de decisión, _Support Vector Machines_.

**Suposiciones del _training set_**

- **_Parametric algorithm_** (algoritmo paramétrico). Algoritmo que realiza suposiciones acerca de la forma de la función (_functional form_) que predice la variable objetivo. Simplifican la _mapping function_ a formas o distribuciones específicas y conocidas que pueden ser expresadas con un número fijo de parámetros (combinación lineal de los datos de entrada, por ejemplo). El número de instancias de entrenamiento no afecta en la complejidad del modelo, puesto que el número de parámetros para la forma escogida va a ser el mismo. Lo único que cambia son los valores de los parámetros, cuya función es ajustar la función a nuestros datos de entrenamiento. Una vez estimados, las predicciones son independientes de nuestros datos de entrenamiento. Dicho de otra forma, los algoritmos paramétricos resumen los datos de entrenamiento en un número fijo de parámetros, a costa de limitar lo que podemos aprender. 

  La regresión lineal simple es un ejemplo de algoritmo paramétrico, ya que simplifica la _mapping function_ a una recta. Como hemos dicho anteriormente, da igual que              incrementemos el número de instancias de entrenamiento, una recta siempre va a requerir únicamente de dos parámetros (pendiente y ordenada al origen). El valor de los             parámetros o coeficientes de regresión debe estimarse para construir la recta que mejor se ajusta a los datos de entrenamiento. Otro ejemplo es la regresión logística.
  
  ¿Qué ventajas tiene este método? Es fácil de entender, su entrenamiento es rápido (número finito de parámetros) y requiere pocos datos de entrenamiento, pero a costa de          limitar la complejidad del modelo generado.  Proporciona poca flexibilidad,  debido a que el ajuste a los datos depende de la forma de la función escogida. Su rendimiento      será mejor o peor en función de si nuestra hipótesis o suposición acerca de la forma de la _mapping function_ es cierta o no. 
  
  Definición más simple: los algoritmos paramétricos realizan suposiciones rígidas acerca de la distribución o forma que siguen los datos de entrenamiento,  estiman los            parámetros  que  definen esa distribución, y comprueban si los supuestos iniciales se cumplen.
  
- **_Nonparametric algorithm_** (algoritmo no paramétrico). No hace suposiciones acerca de la forma de la función (_functional form_) que predice la variable objetivo. Es libre de aprender cualquier forma (_functional form_) de las instancias de entrenamiento. Es decir, no depende de una forma o distribución inicialmente definida, sino de los datos de entrenamiento observados ("_let the data speak for itself_"). La complejidad del modelo crece a medida que el número de instancias de entrenamiento aumenta (cuanto más complejo, más parámetros). Esto se traduce en una mayor flexibilidad y en estimaciones más adecuadas. Por otro lado, requieren más datos de entrenamiento (no hace suposiciones), resultan más lentos (modelo más complejo a construir) y son propensos a _overfitting_. Ejemplos:  árboles de decisión, _k-Nearest Neighbors_, _Support Vector Machines_.

  Estos algoritmos se utilizan cuando disponemos de muchos datos de entrenamiento, de los cuales no tenemos un conocimiento previo de su distribución. 


- [**_Matrix confusion_**](https://en.wikipedia.org/wiki/Confusion_matrix) (matriz de confusión). Herramienta para evaluar los aciertos y errores de un modelo de aprendizaje supervisado.

deterministico probabilistico
