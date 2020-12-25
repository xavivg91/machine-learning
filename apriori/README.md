# **El algoritmo apriori**

El algoritmo apriori permite encontrar reglas de asociación significativas en conjuntos de datos que contienen transacciones (artículos comprados por clientes, por ejemplo). Para ello, previamente deben establecerse valores mínimos para las medidas de soporte y esperanza de una regla. Veamos el siguiente ejemplo, 

| Transacciones | Ítems                                                  | 
|:--------------|:-------------------------------------------------------|
| t1            | {Camiseta, Pantalón, Cinturón}                         | 
| t2            | {Camiseta, Chaqueta}                                   |   
| t3            | {Jacket, Guantes}                                      |  
| t4            | {Camiseta, Pantalón, Chaqueta}                         | 
| t5            | {Camiseta, Pantalón, Zapatillas, Chaqueta, Cinturón}   |   
| t6            | {Pantalón, Zapatillas, Cinturón}                       |
| t7            | {Pantalón, Cinturón, Zapatillas}                       | 

En la tabla superior podemos ver siete transacciones pertenecientes a una tienda de ropa. A continuación, y utilizando el ejemplo expuesto, vamos a ir definiendo los conceptos necesarios para entender el algoritmo apriori.

|                                           | Definición                                             | Ejemplo                             | 
|:------------------------------------------|:-------------------------------------------------------|:------------------------------------|
| Conjunto de ítems (_item set_)            | <img src="https://render.githubusercontent.com/render/math?math=I=\{i_1,%20i_2,...,%20i_k\}">| <img src="https://render.githubusercontent.com/render/math?math=I=\{Camiseta,%20Pantalon,%20Cinturon,%20Chaqueta,%20Guantes,%20Zapatillas\}">|
| Transacciones                             | <img src="https://render.githubusercontent.com/render/math?math=T=\{t_1,%20t_2,...,%20t_n\}">| <img src="https://render.githubusercontent.com/render/math?math=t_1=\{Camiseta,%20Pantalon,%20Cinturon\}">  |
| Regla de asociación                       | <img src="https://render.githubusercontent.com/render/math?math=X%20\Rightarrow%20Y">, <br /> <img src="https://render.githubusercontent.com/render/math?math=X,%20Y%20\subset%20I"> y <img src="https://render.githubusercontent.com/render/math?math=X%20\cap%20Y">|   <img src="https://render.githubusercontent.com/render/math?math=\{Camiseta, Pantalon\} \Rightarrow \{Cinturon\}">|

Una regla de asociación nos indica, dado un ítem A, la probabilidad de que ocurra un ítem B.Veamos los siguientes dos ejemplos:

  - Los clientes que compran leche, probablemente también comprarán cereales.
  - Los alumnos que cursan la asignatura _Machine Learning_, probablemente también cursarán la asignatura _Deep Learning_.

Pero, ¿qué significa y cómo definimos este "probablemente"? Podemos utilizar las medidas de soporte y esperanza:

- **Soporte**. 



