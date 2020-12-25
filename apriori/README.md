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

En la tabla superior podemos ver siete transacciones pertenecientes a una tienda ropa. Podemos representar un **conjunto de ítems** (_item set_) como

<img src="https://render.githubusercontent.com/render/math?math= I=\{i_1, i_2,..., i_k\}">



I=\{T\text- shirt, Trousers, Belt, Jacket, Gloves, Sneakers\}$$




In the table above we can see seven transactions from a clothing store. Each transaction shows items bought in that transaction. We can represent our items as an **item set** as follows:



In our case it corresponds to:


- Una **regla de asociación** nos indica, dado un ítem A, la probabilidad de que ocurra un ítem B. Veamos los siguientes dos ejemplos:

  - Los clientes que compran leche, probablemente también comprarán cereales.
  - Los alumnos que cursan la asignatura _Machine Learning_, probablemente también cursarán la asignatura _Deep Learning_.

Pero, ¿qué significa y cómo definimos este "probablemente"? Podemos utilizar las medidas de soporte y esperanza:

- **Soporte**. 



