# **El algoritmo apriori**

El algoritmo apriori permite encontrar reglas de asociación significativas en conjuntos de datos que contienen transacciones (artículos comprados por clientes, por ejemplo). Para ello, previamente deben establecerse valores mínimos para las medidas de soporte y esperanza de una regla. Veamos el siguiente ejemplo, 

| Transacciones | Ítems                                                  | 
|:--------------|:-------------------------------------------------------|
| t1            | {Camiseta, Pantalón, Cinturón}                         | 
| t2            | {Camiseta, Chaqueta}                                   |   
| t3            | {Chaqueta, Guantes}                                    |  
| t4            | {Camiseta, Pantalón, Chaqueta}                         | 
| t5            | {Camiseta, Pantalón, Zapatillas, Chaqueta, Cinturón}   |   
| t6            | {Pantalón, Zapatillas, Cinturón}                       |
| t7            | {Pantalón, Cinturón, Zapatillas}                       | 

En la tabla superior podemos ver siete transacciones pertenecientes a una tienda de ropa. Utilizando el ejemplo expuesto, vamos a ir definiendo los conceptos necesarios para entender el algoritmo apriori.

|                                           | Definición                                             | Ejemplo                             | 
|:------------------------------------------|:-------------------------------------------------------|:------------------------------------|
| Conjunto de ítems (_item set_)            | <img src="https://render.githubusercontent.com/render/math?math=I=\{i_1,%20i_2,...,%20i_k\}">| <img src="https://render.githubusercontent.com/render/math?math=I=\{Camiseta,%20Pantalon,%20Cinturon,%20Chaqueta,%20Guantes,%20Zapatillas\}">|
| Transacciones                             | <img src="https://render.githubusercontent.com/render/math?math=T=\{t_1,%20t_2,...,%20t_n\}">| <img src="https://render.githubusercontent.com/render/math?math=t_1=\{Camiseta,%20Pantalon,%20Cinturon\}">  |
| Regla de asociación                       | <img src="https://render.githubusercontent.com/render/math?math=X%20\Rightarrow%20Y">, donde <br /> <img src="https://render.githubusercontent.com/render/math?math=X,%20Y%20\subset%20I"> y <img src="https://render.githubusercontent.com/render/math?math=X%20\cap%20Y=0">|   <img src="https://render.githubusercontent.com/render/math?math=\{Camiseta, Pantalon\} \Rightarrow \{Cinturon\}">|



Una **regla de asociación** nos indica, dado un ítem X, la probabilidad de que ocurra un ítem Y. Como hemos dicho anteriormente, el algoritmo apriori pretende buscar reglas significativas, como pueden ser:

  - Los clientes que compran leche, probablemente también comprarán cereales.
  - Los alumnos que cursan la asignatura _Machine Learning_, probablemente también cursarán la asignatura _Deep Learning_.

Para medir el grado de precisión de una regla disponemos de dos métricas, el soporte y la esperanza.

- **Soporte** (_support_). Medida de la probabilidad de que se dé <img src="https://render.githubusercontent.com/render/math?math=X \cup Y"> en nuestro espacio de transacciones. Dicho de otra forma, es el porcentaje de transacciones que aglutinan X e Y a la vez. Para valores demasiado bajos, nos indica que la regla no va a ser de gran utilidad por su
escasa incidencia.

  <img src="https://render.githubusercontent.com/render/math?math=Soporte(X \Rightarrow Y)=\dfrac{|X \cup Y|}{n}"> 
  <br/>
  <img src="https://render.githubusercontent.com/render/math?math=Soporte(Camiseta \Rightarrow Pantalon)=\dfrac{3}{7}=0.43">
  <br/>
  <img src="https://render.githubusercontent.com/render/math?math=Soporte(Pantalon \Rightarrow Cinturon)=\dfrac{4}{7}=0.57">


- **Confianza** (_confidence_). De entre las transacciones que contienen _X_, nos indica el porcentaje de las que además contienen _Y_. Valores demasiado bajos nos indicarán que la regla será poco fiable.

  <img src="https://render.githubusercontent.com/render/math?math=Confianza(X \Rightarrow Y)=\dfrac{Soporte(X \cup Y)}{Soporte(X)}"> 
  <br/>
  <img src="https://render.githubusercontent.com/render/math?math=Confianza(Pantalon \Rightarrow Cinturon)=\dfrac{4/7}{5/7}=0.8">
  <br/>
  <img src="https://render.githubusercontent.com/render/math?math=Confianza(Camiseta \Rightarrow Cinturon)=\dfrac{2/7}{4/7}=0.5">

El algoritmo apriori devuelve únicamente aquellas reglas con valores de soporte y confianza por encima del mínimo establecido.
