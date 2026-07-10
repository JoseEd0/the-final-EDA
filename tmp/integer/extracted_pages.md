

# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 1
CS3014 Estructuras de Datos Avanzadas
CS3014 Estructuras de Datos Avanzadas
Laboratorio - Semana 9 - Sesión 1
Víctor Racsó Galván Oyola
vgalvan@utec.edu.pe
20 de mayo de 2026
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 1 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 2
CS3014 Estructuras de Datos Avanzadas
¿Qué aprenderemos hoy?
▶Modelos computacional RAM AC 0
▶Fusion Trees
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 2 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 3
CS3014 Estructuras de Datos Avanzadas
¿Qué aprenderemos hoy?
▶Modelos computacional RAM AC 0
▶Fusion Trees
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 2 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 4
CS3014 Estructuras de Datos Avanzadas
¿Qué aprenderemos hoy?
▶Modelos computacional RAM AC 0
▶Fusion Trees
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 2 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 5
Modelos computacional RAM AC 0


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 6
CS3014 Estructuras de Datos Avanzadas
Modelos computacional RAM AC 0
Modelo RAM AC0
▶Permite solo operaciones que se puedan realizar en un circuito de
profundidadO(1)pero sin límite de fan-in y fan-out (compuertas que
entran y salen, respectivamente).
▶Por su definición, no permite multiplicación.
Otras operaciones permitidas
Operaciones bitwise pueden ser realizadas enO(1).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 7
CS3014 Estructuras de Datos Avanzadas
Modelos computacional RAM AC 0
Modelo RAM AC0
▶Permite solo operaciones que se puedan realizar en un circuito de
profundidadO(1)pero sin límite de fan-in y fan-out (compuertas que
entran y salen, respectivamente).
▶Por su definición, no permite multiplicación.
Otras operaciones permitidas
Operaciones bitwise pueden ser realizadas enO(1).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 8
CS3014 Estructuras de Datos Avanzadas
Modelos computacional RAM AC 0
Modelo RAM AC0
▶Permite solo operaciones que se puedan realizar en un circuito de
profundidadO(1)pero sin límite de fan-in y fan-out (compuertas que
entran y salen, respectivamente).
▶Por su definición, no permite multiplicación.
Otras operaciones permitidas
Operaciones bitwise pueden ser realizadas enO(1).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 9
CS3014 Estructuras de Datos Avanzadas
Modelos computacional RAM AC 0
Modelo RAM AC0
▶Permite solo operaciones que se puedan realizar en un circuito de
profundidadO(1)pero sin límite de fan-in y fan-out (compuertas que
entran y salen, respectivamente).
▶Por su definición, no permite multiplicación.
Otras operaciones permitidas
Operaciones bitwise pueden ser realizadas enO(1).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 10
CS3014 Estructuras de Datos Avanzadas
Modelos computacional RAM AC 0
Modelo RAM AC0
▶Permite solo operaciones que se puedan realizar en un circuito de
profundidadO(1)pero sin límite de fan-in y fan-out (compuertas que
entran y salen, respectivamente).
▶Por su definición, no permite multiplicación.
Otras operaciones permitidas
Operaciones bitwise pueden ser realizadas enO(1).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 11
Fusion T rees


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 12
CS3014 Estructuras de Datos Avanzadas
Fusion Trees
Definición
Es una estructura de datos que nos permite consultar el sucesor/predecesor
enO(log w n).
Considerando este resultado y el de vEB y y-fast trees, tendríamos que la
consulta de sucesor predecesor toma
m ´ ın{O(logw),O(logw n)}=O(
p
logn)
Versiones
Veremos la versión estática. Las dinámicas disponibles cumplen:
▶O(log w n+ log logn)usando exponential trees.
▶O(log w n)esperado usando hashing.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 6 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 13
CS3014 Estructuras de Datos Avanzadas
Fusion Trees
Definición
Es una estructura de datos que nos permite consultar el sucesor/predecesor
enO(log w n).
Considerando este resultado y el de vEB y y-fast trees, tendríamos que la
consulta de sucesor predecesor toma
m ´ ın{O(logw),O(logw n)}=O(
p
logn)
Versiones
Veremos la versión estática. Las dinámicas disponibles cumplen:
▶O(log w n+ log logn)usando exponential trees.
▶O(log w n)esperado usando hashing.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 6 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 14
CS3014 Estructuras de Datos Avanzadas
Fusion Trees
Definición
Es una estructura de datos que nos permite consultar el sucesor/predecesor
enO(log w n).
Considerando este resultado y el de vEB y y-fast trees, tendríamos que la
consulta de sucesor predecesor toma
m ´ ın{O(logw),O(logw n)}=O(
p
logn)
Versiones
Veremos la versión estática. Las dinámicas disponibles cumplen:
▶O(log w n+ log logn)usando exponential trees.
▶O(log w n)esperado usando hashing.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 6 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 15
CS3014 Estructuras de Datos Avanzadas
Fusion Trees
Definición
Es una estructura de datos que nos permite consultar el sucesor/predecesor
enO(log w n).
Considerando este resultado y el de vEB y y-fast trees, tendríamos que la
consulta de sucesor predecesor toma
m ´ ın{O(logw),O(logw n)}=O(
p
logn)
Versiones
Veremos la versión estática. Las dinámicas disponibles cumplen:
▶O(log w n+ log logn)usando exponential trees.
▶O(log w n)esperado usando hashing.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 6 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 16
CS3014 Estructuras de Datos Avanzadas
Fusion Trees
Definición
Es una estructura de datos que nos permite consultar el sucesor/predecesor
enO(log w n).
Considerando este resultado y el de vEB y y-fast trees, tendríamos que la
consulta de sucesor predecesor toma
m ´ ın{O(logw),O(logw n)}=O(
p
logn)
Versiones
Veremos la versión estática. Las dinámicas disponibles cumplen:
▶O(log w n+ log logn)usando exponential trees.
▶O(log w n)esperado usando hashing.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 6 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 17
CS3014 Estructuras de Datos Avanzadas
Fusion Trees
Definición
Es una estructura de datos que nos permite consultar el sucesor/predecesor
enO(log w n).
Considerando este resultado y el de vEB y y-fast trees, tendríamos que la
consulta de sucesor predecesor toma
m ´ ın{O(logw),O(logw n)}=O(
p
logn)
Versiones
Veremos la versión estática. Las dinámicas disponibles cumplen:
▶O(log w n+ log logn)usando exponential trees.
▶O(log w n)esperado usando hashing.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 6 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 18
CS3014 Estructuras de Datos Avanzadas
Fusion Trees
Definición
Es una estructura de datos que nos permite consultar el sucesor/predecesor
enO(log w n).
Considerando este resultado y el de vEB y y-fast trees, tendríamos que la
consulta de sucesor predecesor toma
m ´ ın{O(logw),O(logw n)}=O(
p
logn)
Versiones
Veremos la versión estática. Las dinámicas disponibles cumplen:
▶O(log w n+ log logn)usando exponential trees.
▶O(log w n)esperado usando hashing.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 6 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 19
CS3014 Estructuras de Datos Avanzadas
Estructura
Planteamiento inicial
Consideraremos un B-Tree de ordenw
1
5, así que cada nodo tiene a lo mucho
w
1
5 hijos.
Cada nodo manejaw 1+ 1
5 bits, así que no podemos buscar el hijo correspon-
diente enO(1).
Solución - Nodos de fusion tree
▶Almacenamosk=O(w
1
5 )valoresx 0 <x 1 < . . . <x k−1.
▶Debemos poder responder al sucesor o predecesor de un valor enO(1).
▶Requeriremosk O(1) de preprocesamiento.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 7 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 20
CS3014 Estructuras de Datos Avanzadas
Estructura
Planteamiento inicial
Consideraremos un B-Tree de ordenw
1
5, así que cada nodo tiene a lo mucho
w
1
5 hijos.
Cada nodo manejaw 1+ 1
5 bits, así que no podemos buscar el hijo correspon-
diente enO(1).
Solución - Nodos de fusion tree
▶Almacenamosk=O(w
1
5 )valoresx 0 <x 1 < . . . <x k−1.
▶Debemos poder responder al sucesor o predecesor de un valor enO(1).
▶Requeriremosk O(1) de preprocesamiento.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 7 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 21
CS3014 Estructuras de Datos Avanzadas
Estructura
Planteamiento inicial
Consideraremos un B-Tree de ordenw
1
5, así que cada nodo tiene a lo mucho
w
1
5 hijos.
Cada nodo manejaw 1+ 1
5 bits, así que no podemos buscar el hijo correspon-
diente enO(1).
Solución - Nodos de fusion tree
▶Almacenamosk=O(w
1
5 )valoresx 0 <x 1 < . . . <x k−1.
▶Debemos poder responder al sucesor o predecesor de un valor enO(1).
▶Requeriremosk O(1) de preprocesamiento.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 7 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 22
CS3014 Estructuras de Datos Avanzadas
Estructura
Planteamiento inicial
Consideraremos un B-Tree de ordenw
1
5, así que cada nodo tiene a lo mucho
w
1
5 hijos.
Cada nodo manejaw 1+ 1
5 bits, así que no podemos buscar el hijo correspon-
diente enO(1).
Solución - Nodos de fusion tree
▶Almacenamosk=O(w
1
5 )valoresx 0 <x 1 < . . . <x k−1.
▶Debemos poder responder al sucesor o predecesor de un valor enO(1).
▶Requeriremosk O(1) de preprocesamiento.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 7 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 23
CS3014 Estructuras de Datos Avanzadas
Estructura
Planteamiento inicial
Consideraremos un B-Tree de ordenw
1
5, así que cada nodo tiene a lo mucho
w
1
5 hijos.
Cada nodo manejaw 1+ 1
5 bits, así que no podemos buscar el hijo correspon-
diente enO(1).
Solución - Nodos de fusion tree
▶Almacenamosk=O(w
1
5 )valoresx 0 <x 1 < . . . <x k−1.
▶Debemos poder responder al sucesor o predecesor de un valor enO(1).
▶Requeriremosk O(1) de preprocesamiento.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 7 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 24
CS3014 Estructuras de Datos Avanzadas
Estructura
Planteamiento inicial
Consideraremos un B-Tree de ordenw
1
5, así que cada nodo tiene a lo mucho
w
1
5 hijos.
Cada nodo manejaw 1+ 1
5 bits, así que no podemos buscar el hijo correspon-
diente enO(1).
Solución - Nodos de fusion tree
▶Almacenamosk=O(w
1
5 )valoresx 0 <x 1 < . . . <x k−1.
▶Debemos poder responder al sucesor o predecesor de un valor enO(1).
▶Requeriremosk O(1) de preprocesamiento.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 7 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 25
CS3014 Estructuras de Datos Avanzadas
Estructura
Planteamiento inicial
Consideraremos un B-Tree de ordenw
1
5, así que cada nodo tiene a lo mucho
w
1
5 hijos.
Cada nodo manejaw 1+ 1
5 bits, así que no podemos buscar el hijo correspon-
diente enO(1).
Solución - Nodos de fusion tree
▶Almacenamosk=O(w
1
5 )valoresx 0 <x 1 < . . . <x k−1.
▶Debemos poder responder al sucesor o predecesor de un valor enO(1).
▶Requeriremosk O(1) de preprocesamiento.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 7 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 26
CS3014 Estructuras de Datos Avanzadas
Sketching
¿Cómo distinguimosk=O(w
1
5 )valores?
Podemos considerar un trie de las llaves con un alfabeto binario.
Es posible reducir la cantidad total de nodos calculando el auxiliary/virtual
tree del trie correspondiente y mapeamos los niveles involucrados.
Consecuencias
Hayk−1 nodos internos en el trie, así que nos interesan a lo muchok−1
niveles del mismo.
Si almacenamos la información de esosk−1 niveles, entonces manejaremos
O(w
1
5 )bits por cada llave.
En total, manejaremosO(w
2
5 )bits, lo cual si es posible de hacer enO(1).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 27
CS3014 Estructuras de Datos Avanzadas
Sketching
¿Cómo distinguimosk=O(w
1
5 )valores?
Podemos considerar un trie de las llaves con un alfabeto binario.
Es posible reducir la cantidad total de nodos calculando el auxiliary/virtual
tree del trie correspondiente y mapeamos los niveles involucrados.
Consecuencias
Hayk−1 nodos internos en el trie, así que nos interesan a lo muchok−1
niveles del mismo.
Si almacenamos la información de esosk−1 niveles, entonces manejaremos
O(w
1
5 )bits por cada llave.
En total, manejaremosO(w
2
5 )bits, lo cual si es posible de hacer enO(1).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 28
CS3014 Estructuras de Datos Avanzadas
Sketching
¿Cómo distinguimosk=O(w
1
5 )valores?
Podemos considerar un trie de las llaves con un alfabeto binario.
Es posible reducir la cantidad total de nodos calculando el auxiliary/virtual
tree del trie correspondiente y mapeamos los niveles involucrados.
Consecuencias
Hayk−1 nodos internos en el trie, así que nos interesan a lo muchok−1
niveles del mismo.
Si almacenamos la información de esosk−1 niveles, entonces manejaremos
O(w
1
5 )bits por cada llave.
En total, manejaremosO(w
2
5 )bits, lo cual si es posible de hacer enO(1).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 29
CS3014 Estructuras de Datos Avanzadas
Sketching
¿Cómo distinguimosk=O(w
1
5 )valores?
Podemos considerar un trie de las llaves con un alfabeto binario.
Es posible reducir la cantidad total de nodos calculando el auxiliary/virtual
tree del trie correspondiente y mapeamos los niveles involucrados.
Consecuencias
Hayk−1 nodos internos en el trie, así que nos interesan a lo muchok−1
niveles del mismo.
Si almacenamos la información de esosk−1 niveles, entonces manejaremos
O(w
1
5 )bits por cada llave.
En total, manejaremosO(w
2
5 )bits, lo cual si es posible de hacer enO(1).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 30
CS3014 Estructuras de Datos Avanzadas
Sketching
¿Cómo distinguimosk=O(w
1
5 )valores?
Podemos considerar un trie de las llaves con un alfabeto binario.
Es posible reducir la cantidad total de nodos calculando el auxiliary/virtual
tree del trie correspondiente y mapeamos los niveles involucrados.
Consecuencias
Hayk−1 nodos internos en el trie, así que nos interesan a lo muchok−1
niveles del mismo.
Si almacenamos la información de esosk−1 niveles, entonces manejaremos
O(w
1
5 )bits por cada llave.
En total, manejaremosO(w
2
5 )bits, lo cual si es posible de hacer enO(1).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 31
CS3014 Estructuras de Datos Avanzadas
Sketching
¿Cómo distinguimosk=O(w
1
5 )valores?
Podemos considerar un trie de las llaves con un alfabeto binario.
Es posible reducir la cantidad total de nodos calculando el auxiliary/virtual
tree del trie correspondiente y mapeamos los niveles involucrados.
Consecuencias
Hayk−1 nodos internos en el trie, así que nos interesan a lo muchok−1
niveles del mismo.
Si almacenamos la información de esosk−1 niveles, entonces manejaremos
O(w
1
5 )bits por cada llave.
En total, manejaremosO(w
2
5 )bits, lo cual si es posible de hacer enO(1).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 32
CS3014 Estructuras de Datos Avanzadas
Sketching
¿Cómo distinguimosk=O(w
1
5 )valores?
Podemos considerar un trie de las llaves con un alfabeto binario.
Es posible reducir la cantidad total de nodos calculando el auxiliary/virtual
tree del trie correspondiente y mapeamos los niveles involucrados.
Consecuencias
Hayk−1 nodos internos en el trie, así que nos interesan a lo muchok−1
niveles del mismo.
Si almacenamos la información de esosk−1 niveles, entonces manejaremos
O(w
1
5 )bits por cada llave.
En total, manejaremosO(w
2
5 )bits, lo cual si es posible de hacer enO(1).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 33
CS3014 Estructuras de Datos Avanzadas
Trie binario
∅
1
1
0
2
0
3
1
1
0
5
1
0
1
1=001,2=010,3=011,5=101
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 9 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 34
CS3014 Estructuras de Datos Avanzadas
Trie binario + Virtual Tree
∅
1
1
0
2
0
3
1
1
0
5
1
0
1
1=001,2=010,3=011,5=101
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 10 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 35
CS3014 Estructuras de Datos Avanzadas
Sketching perfecto
Definición
Consideraremos una secuencia derenterosb 0 >b 1 > . . . >b r−1 y cada
llave la representaremos como una cadena derbits en la cual eli-ésimo bit
corresponderá al bitbi de la llave.
Denotaremos a dicha cadena binaria comoSketch(x).
Propiedad importante
Sketch(x0)<Sketch(x 1)< . . . <Sketch(x k−1)
Esto se cumplesolo para las llaves.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 11 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 36
CS3014 Estructuras de Datos Avanzadas
Sketching perfecto
Definición
Consideraremos una secuencia derenterosb 0 >b 1 > . . . >b r−1 y cada
llave la representaremos como una cadena derbits en la cual eli-ésimo bit
corresponderá al bitbi de la llave.
Denotaremos a dicha cadena binaria comoSketch(x).
Propiedad importante
Sketch(x0)<Sketch(x 1)< . . . <Sketch(x k−1)
Esto se cumplesolo para las llaves.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 11 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 37
CS3014 Estructuras de Datos Avanzadas
Sketching perfecto
Definición
Consideraremos una secuencia derenterosb 0 >b 1 > . . . >b r−1 y cada
llave la representaremos como una cadena derbits en la cual eli-ésimo bit
corresponderá al bitbi de la llave.
Denotaremos a dicha cadena binaria comoSketch(x).
Propiedad importante
Sketch(x0)<Sketch(x 1)< . . . <Sketch(x k−1)
Esto se cumplesolo para las llaves.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 11 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 38
CS3014 Estructuras de Datos Avanzadas
Sketching perfecto
Definición
Consideraremos una secuencia derenterosb 0 >b 1 > . . . >b r−1 y cada
llave la representaremos como una cadena derbits en la cual eli-ésimo bit
corresponderá al bitbi de la llave.
Denotaremos a dicha cadena binaria comoSketch(x).
Propiedad importante
Sketch(x0)<Sketch(x 1)< . . . <Sketch(x k−1)
Esto se cumplesolo para las llaves.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 11 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 39
CS3014 Estructuras de Datos Avanzadas
Sketching perfecto
Definición
Consideraremos una secuencia derenterosb 0 >b 1 > . . . >b r−1 y cada
llave la representaremos como una cadena derbits en la cual eli-ésimo bit
corresponderá al bitbi de la llave.
Denotaremos a dicha cadena binaria comoSketch(x).
Propiedad importante
Sketch(x0)<Sketch(x 1)< . . . <Sketch(x k−1)
Esto se cumplesolo para las llaves.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 11 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 40
CS3014 Estructuras de Datos Avanzadas
Sketching perfecto
Definición
Consideraremos una secuencia derenterosb 0 >b 1 > . . . >b r−1 y cada
llave la representaremos como una cadena derbits en la cual eli-ésimo bit
corresponderá al bitbi de la llave.
Denotaremos a dicha cadena binaria comoSketch(x).
Propiedad importante
Sketch(x0)<Sketch(x 1)< . . . <Sketch(x k−1)
Esto se cumplesolo para las llaves.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 11 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 41
CS3014 Estructuras de Datos Avanzadas
Consultas
¿Cómo buscamos el sucesor o predecesor de un valorq?
Podemos pensar en calcularSketch(q)y luego buscarlo en la estructura.
Sorpresa:Sketchpreserva el orden entre las llaves, así queSketch(q)
podría caer en cualquier lugar, no necesariamente en su sucesor o predecesor.
¿Qué hacemos?
Supongamos queSketch(x i)≤Sketch(q)<Sketch(x i+1).
Tomamos ellongest common prefixentreqyx i ox i+1.
El nodo al que lleguemos es en donde la búsquedafalla, así que podremos
decidir qué hacer a continuación dependiendo del escenario.
Un ejemplo interesante es con las llaves 0,2,12,15 yq=5.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 42
CS3014 Estructuras de Datos Avanzadas
Consultas
¿Cómo buscamos el sucesor o predecesor de un valorq?
Podemos pensar en calcularSketch(q)y luego buscarlo en la estructura.
Sorpresa:Sketchpreserva el orden entre las llaves, así queSketch(q)
podría caer en cualquier lugar, no necesariamente en su sucesor o predecesor.
¿Qué hacemos?
Supongamos queSketch(x i)≤Sketch(q)<Sketch(x i+1).
Tomamos ellongest common prefixentreqyx i ox i+1.
El nodo al que lleguemos es en donde la búsquedafalla, así que podremos
decidir qué hacer a continuación dependiendo del escenario.
Un ejemplo interesante es con las llaves 0,2,12,15 yq=5.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 43
CS3014 Estructuras de Datos Avanzadas
Consultas
¿Cómo buscamos el sucesor o predecesor de un valorq?
Podemos pensar en calcularSketch(q)y luego buscarlo en la estructura.
Sorpresa:Sketchpreserva el orden entre las llaves, así queSketch(q)
podría caer en cualquier lugar, no necesariamente en su sucesor o predecesor.
¿Qué hacemos?
Supongamos queSketch(x i)≤Sketch(q)<Sketch(x i+1).
Tomamos ellongest common prefixentreqyx i ox i+1.
El nodo al que lleguemos es en donde la búsquedafalla, así que podremos
decidir qué hacer a continuación dependiendo del escenario.
Un ejemplo interesante es con las llaves 0,2,12,15 yq=5.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 44
CS3014 Estructuras de Datos Avanzadas
Consultas
¿Cómo buscamos el sucesor o predecesor de un valorq?
Podemos pensar en calcularSketch(q)y luego buscarlo en la estructura.
Sorpresa:Sketchpreserva el orden entre las llaves, así queSketch(q)
podría caer en cualquier lugar, no necesariamente en su sucesor o predecesor.
¿Qué hacemos?
Supongamos queSketch(x i)≤Sketch(q)<Sketch(x i+1).
Tomamos ellongest common prefixentreqyx i ox i+1.
El nodo al que lleguemos es en donde la búsquedafalla, así que podremos
decidir qué hacer a continuación dependiendo del escenario.
Un ejemplo interesante es con las llaves 0,2,12,15 yq=5.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 45
CS3014 Estructuras de Datos Avanzadas
Consultas
¿Cómo buscamos el sucesor o predecesor de un valorq?
Podemos pensar en calcularSketch(q)y luego buscarlo en la estructura.
Sorpresa:Sketchpreserva el orden entre las llaves, así queSketch(q)
podría caer en cualquier lugar, no necesariamente en su sucesor o predecesor.
¿Qué hacemos?
Supongamos queSketch(x i)≤Sketch(q)<Sketch(x i+1).
Tomamos ellongest common prefixentreqyx i ox i+1.
El nodo al que lleguemos es en donde la búsquedafalla, así que podremos
decidir qué hacer a continuación dependiendo del escenario.
Un ejemplo interesante es con las llaves 0,2,12,15 yq=5.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 46
CS3014 Estructuras de Datos Avanzadas
Consultas
¿Cómo buscamos el sucesor o predecesor de un valorq?
Podemos pensar en calcularSketch(q)y luego buscarlo en la estructura.
Sorpresa:Sketchpreserva el orden entre las llaves, así queSketch(q)
podría caer en cualquier lugar, no necesariamente en su sucesor o predecesor.
¿Qué hacemos?
Supongamos queSketch(x i)≤Sketch(q)<Sketch(x i+1).
Tomamos ellongest common prefixentreqyx i ox i+1.
El nodo al que lleguemos es en donde la búsquedafalla, así que podremos
decidir qué hacer a continuación dependiendo del escenario.
Un ejemplo interesante es con las llaves 0,2,12,15 yq=5.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 47
CS3014 Estructuras de Datos Avanzadas
Consultas
¿Cómo buscamos el sucesor o predecesor de un valorq?
Podemos pensar en calcularSketch(q)y luego buscarlo en la estructura.
Sorpresa:Sketchpreserva el orden entre las llaves, así queSketch(q)
podría caer en cualquier lugar, no necesariamente en su sucesor o predecesor.
¿Qué hacemos?
Supongamos queSketch(x i)≤Sketch(q)<Sketch(x i+1).
Tomamos ellongest common prefixentreqyx i ox i+1.
El nodo al que lleguemos es en donde la búsquedafalla, así que podremos
decidir qué hacer a continuación dependiendo del escenario.
Un ejemplo interesante es con las llaves 0,2,12,15 yq=5.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 48
CS3014 Estructuras de Datos Avanzadas
Consultas
¿Cómo buscamos el sucesor o predecesor de un valorq?
Podemos pensar en calcularSketch(q)y luego buscarlo en la estructura.
Sorpresa:Sketchpreserva el orden entre las llaves, así queSketch(q)
podría caer en cualquier lugar, no necesariamente en su sucesor o predecesor.
¿Qué hacemos?
Supongamos queSketch(x i)≤Sketch(q)<Sketch(x i+1).
Tomamos ellongest common prefixentreqyx i ox i+1.
El nodo al que lleguemos es en donde la búsquedafalla, así que podremos
decidir qué hacer a continuación dependiendo del escenario.
Un ejemplo interesante es con las llaves 0,2,12,15 yq=5.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 49
CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Aprendimos un poco del modelo RAM AC0 .
▶Aprendimos sobre Fusion Trees.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 13 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 50
CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Aprendimos un poco del modelo RAM AC0 .
▶Aprendimos sobre Fusion Trees.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 13 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 51
CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Aprendimos un poco del modelo RAM AC0 .
▶Aprendimos sobre Fusion Trees.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 13 / 14


# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf - Page 52
CS3014 Estructuras de Datos Avanzadas
Gracias
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 14 / 14


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 1
CS3014 Estructuras de Datos Avanzadas
CS3014 Estructuras de Datos Avanzadas
Laboratorio - Semana 9 - Sesión 2
Víctor Racsó Galván Oyola
vgalvan@utec.edu.pe
22 de mayo de 2026
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 1 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 2
CS3014 Estructuras de Datos Avanzadas
¿Qué aprenderemos hoy?
▶Equivalencia entre ordenamiento y colas de prioridad
▶Algunos resultados en ordenamiento de enteros
▶Signature sort
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 2 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 3
CS3014 Estructuras de Datos Avanzadas
¿Qué aprenderemos hoy?
▶Equivalencia entre ordenamiento y colas de prioridad
▶Algunos resultados en ordenamiento de enteros
▶Signature sort
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 2 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 4
CS3014 Estructuras de Datos Avanzadas
¿Qué aprenderemos hoy?
▶Equivalencia entre ordenamiento y colas de prioridad
▶Algunos resultados en ordenamiento de enteros
▶Signature sort
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 2 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 5
CS3014 Estructuras de Datos Avanzadas
¿Qué aprenderemos hoy?
▶Equivalencia entre ordenamiento y colas de prioridad
▶Algunos resultados en ordenamiento de enteros
▶Signature sort
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 2 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 6
Ordenamiento y cola de prioridades


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 7
CS3014 Estructuras de Datos Avanzadas
Equivalencia
Punto inicial
Es sencillo notar que si tenemos una cola de prioridad que soporta las opera-
ciones clásicas enO(f(n,w)), entonces existe un algoritmo de ordenamiento
que tomaO(nf(n,w)).
Punto final
Si existe un algoritmo de ordenamiento que tomaO(T(n,w)), existe una
cola de prioridad que soporta sus operaciones clásicas enO

T(n,w)
n

.
Ejemplo: Quickheap.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 8
CS3014 Estructuras de Datos Avanzadas
Equivalencia
Punto inicial
Es sencillo notar que si tenemos una cola de prioridad que soporta las opera-
ciones clásicas enO(f(n,w)), entonces existe un algoritmo de ordenamiento
que tomaO(nf(n,w)).
Punto final
Si existe un algoritmo de ordenamiento que tomaO(T(n,w)), existe una
cola de prioridad que soporta sus operaciones clásicas enO

T(n,w)
n

.
Ejemplo: Quickheap.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 9
CS3014 Estructuras de Datos Avanzadas
Equivalencia
Punto inicial
Es sencillo notar que si tenemos una cola de prioridad que soporta las opera-
ciones clásicas enO(f(n,w)), entonces existe un algoritmo de ordenamiento
que tomaO(nf(n,w)).
Punto final
Si existe un algoritmo de ordenamiento que tomaO(T(n,w)), existe una
cola de prioridad que soporta sus operaciones clásicas enO

T(n,w)
n

.
Ejemplo: Quickheap.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 10
CS3014 Estructuras de Datos Avanzadas
Equivalencia
Punto inicial
Es sencillo notar que si tenemos una cola de prioridad que soporta las opera-
ciones clásicas enO(f(n,w)), entonces existe un algoritmo de ordenamiento
que tomaO(nf(n,w)).
Punto final
Si existe un algoritmo de ordenamiento que tomaO(T(n,w)), existe una
cola de prioridad que soporta sus operaciones clásicas enO

T(n,w)
n

.
Ejemplo: Quickheap.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 11
CS3014 Estructuras de Datos Avanzadas
Equivalencia
Punto inicial
Es sencillo notar que si tenemos una cola de prioridad que soporta las opera-
ciones clásicas enO(f(n,w)), entonces existe un algoritmo de ordenamiento
que tomaO(nf(n,w)).
Punto final
Si existe un algoritmo de ordenamiento que tomaO(T(n,w)), existe una
cola de prioridad que soporta sus operaciones clásicas enO

T(n,w)
n

.
Ejemplo: Quickheap.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 12
Resultados en ordenamientos de enteros


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 13
CS3014 Estructuras de Datos Avanzadas
Resultados en ordenamiento de enteros
Para ordenarnenteros dewbits, la siguiente tabla resume algunos
resultados históricos.
Método Complejidad Condición
Comparaciones O(nlogn) Sin condiciones
Counting sort O(n+2 w ) O(n)siw= logn
Radix sort O

n w
logn

O(n)siw=O(logn)
van Emde Boas O(nlogw)
Basado en van Emde Boas O(nlog w
logn ) O(nlog logn)siw= log O(1) n
Signature sort O(n) w= Ω(log 2+ε n),∀ε >0
Han (2004) O(nlog logn) modelo RAM AC0
Han y Thorup (2002) O(n
q
log w
logn ) Aleatorizado
Cuadro: Resultados de ordenamiento de enteros
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 6 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 14
CS3014 Estructuras de Datos Avanzadas
Resultados en ordenamiento de enteros
Para ordenarnenteros dewbits, la siguiente tabla resume algunos
resultados históricos.
Método Complejidad Condición
Comparaciones O(nlogn) Sin condiciones
Counting sort O(n+2 w ) O(n)siw= logn
Radix sort O

n w
logn

O(n)siw=O(logn)
van Emde Boas O(nlogw)
Basado en van Emde Boas O(nlog w
logn ) O(nlog logn)siw= log O(1) n
Signature sort O(n) w= Ω(log 2+ε n),∀ε >0
Han (2004) O(nlog logn) modelo RAM AC0
Han y Thorup (2002) O(n
q
log w
logn ) Aleatorizado
Cuadro: Resultados de ordenamiento de enteros
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 6 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 15
CS3014 Estructuras de Datos Avanzadas
Resultados en ordenamiento de enteros
Para ordenarnenteros dewbits, la siguiente tabla resume algunos
resultados históricos.
Método Complejidad Condición
Comparaciones O(nlogn) Sin condiciones
Counting sort O(n+2 w ) O(n)siw= logn
Radix sort O

n w
logn

O(n)siw=O(logn)
van Emde Boas O(nlogw)
Basado en van Emde Boas O(nlog w
logn ) O(nlog logn)siw= log O(1) n
Signature sort O(n) w= Ω(log 2+ε n),∀ε >0
Han (2004) O(nlog logn) modelo RAM AC0
Han y Thorup (2002) O(n
q
log w
logn ) Aleatorizado
Cuadro: Resultados de ordenamiento de enteros
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 6 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 16
Signature sort


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 17
CS3014 Estructuras de Datos Avanzadas
Signature sort
Condición base
Asumiremos quew≥log 2+ε nlog lognpor ser conveniente.
Paso 1
Particionamos cada entero enlogε nbloques de tamaños iguales que serán
dígitos.
Notemos que estos bloques tendrán tamaño de al menoslog2 n.
Esto es equivalente a tomar una baseB≈ w
logε n y representar cada entero
en baseB.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 18
CS3014 Estructuras de Datos Avanzadas
Signature sort
Condición base
Asumiremos quew≥log 2+ε nlog lognpor ser conveniente.
Paso 1
Particionamos cada entero enlogε nbloques de tamaños iguales que serán
dígitos.
Notemos que estos bloques tendrán tamaño de al menoslog2 n.
Esto es equivalente a tomar una baseB≈ w
logε n y representar cada entero
en baseB.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 19
CS3014 Estructuras de Datos Avanzadas
Signature sort
Condición base
Asumiremos quew≥log 2+ε nlog lognpor ser conveniente.
Paso 1
Particionamos cada entero enlogε nbloques de tamaños iguales que serán
dígitos.
Notemos que estos bloques tendrán tamaño de al menoslog2 n.
Esto es equivalente a tomar una baseB≈ w
logε n y representar cada entero
en baseB.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 20
CS3014 Estructuras de Datos Avanzadas
Signature sort
Condición base
Asumiremos quew≥log 2+ε nlog lognpor ser conveniente.
Paso 1
Particionamos cada entero enlogε nbloques de tamaños iguales que serán
dígitos.
Notemos que estos bloques tendrán tamaño de al menoslog2 n.
Esto es equivalente a tomar una baseB≈ w
logε n y representar cada entero
en baseB.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 21
CS3014 Estructuras de Datos Avanzadas
Signature sort
Condición base
Asumiremos quew≥log 2+ε nlog lognpor ser conveniente.
Paso 1
Particionamos cada entero enlogε nbloques de tamaños iguales que serán
dígitos.
Notemos que estos bloques tendrán tamaño de al menoslog2 n.
Esto es equivalente a tomar una baseB≈ w
logε n y representar cada entero
en baseB.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 22
CS3014 Estructuras de Datos Avanzadas
Signature sort
Condición base
Asumiremos quew≥log 2+ε nlog lognpor ser conveniente.
Paso 1
Particionamos cada entero enlogε nbloques de tamaños iguales que serán
dígitos.
Notemos que estos bloques tendrán tamaño de al menoslog2 n.
Esto es equivalente a tomar una baseB≈ w
logε n y representar cada entero
en baseB.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 23
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 2
Ya que hay pocos posibles dígitos almacenados para un universo muy grande
(nlog 1+ε n<<2 log2 n), reemplazamos cada bloque por un hash perfecto de
O(logn)bits. Notemos que podríamos elegir una constante grande para evitar
colisiones con alta probabilidad.
Podemos multiplicar cada dígito por un enteromy luego obtener las máscaras
reducidas de cada uno. Esto tomaráO(1)por dígito.
Esto preserva la identidad pero no preserva el orden.
Paso 3
Notemos que ahora la cantidad de bits usados esO(nlog1+ε n), debido a
que tenemosnenteros conlog ε ndígitos delognbits.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 9 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 24
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 2
Ya que hay pocos posibles dígitos almacenados para un universo muy grande
(nlog 1+ε n<<2 log2 n), reemplazamos cada bloque por un hash perfecto de
O(logn)bits. Notemos que podríamos elegir una constante grande para evitar
colisiones con alta probabilidad.
Podemos multiplicar cada dígito por un enteromy luego obtener las máscaras
reducidas de cada uno. Esto tomaráO(1)por dígito.
Esto preserva la identidad pero no preserva el orden.
Paso 3
Notemos que ahora la cantidad de bits usados esO(nlog1+ε n), debido a
que tenemosnenteros conlog ε ndígitos delognbits.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 9 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 25
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 2
Ya que hay pocos posibles dígitos almacenados para un universo muy grande
(nlog 1+ε n<<2 log2 n), reemplazamos cada bloque por un hash perfecto de
O(logn)bits. Notemos que podríamos elegir una constante grande para evitar
colisiones con alta probabilidad.
Podemos multiplicar cada dígito por un enteromy luego obtener las máscaras
reducidas de cada uno. Esto tomaráO(1)por dígito.
Esto preserva la identidad pero no preserva el orden.
Paso 3
Notemos que ahora la cantidad de bits usados esO(nlog1+ε n), debido a
que tenemosnenteros conlog ε ndígitos delognbits.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 9 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 26
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 2
Ya que hay pocos posibles dígitos almacenados para un universo muy grande
(nlog 1+ε n<<2 log2 n), reemplazamos cada bloque por un hash perfecto de
O(logn)bits. Notemos que podríamos elegir una constante grande para evitar
colisiones con alta probabilidad.
Podemos multiplicar cada dígito por un enteromy luego obtener las máscaras
reducidas de cada uno. Esto tomaráO(1)por dígito.
Esto preserva la identidad pero no preserva el orden.
Paso 3
Notemos que ahora la cantidad de bits usados esO(nlog1+ε n), debido a
que tenemosnenteros conlog ε ndígitos delognbits.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 9 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 27
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 2
Ya que hay pocos posibles dígitos almacenados para un universo muy grande
(nlog 1+ε n<<2 log2 n), reemplazamos cada bloque por un hash perfecto de
O(logn)bits. Notemos que podríamos elegir una constante grande para evitar
colisiones con alta probabilidad.
Podemos multiplicar cada dígito por un enteromy luego obtener las máscaras
reducidas de cada uno. Esto tomaráO(1)por dígito.
Esto preserva la identidad pero no preserva el orden.
Paso 3
Notemos que ahora la cantidad de bits usados esO(nlog1+ε n), debido a
que tenemosnenteros conlog ε ndígitos delognbits.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 9 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 28
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 2
Ya que hay pocos posibles dígitos almacenados para un universo muy grande
(nlog 1+ε n<<2 log2 n), reemplazamos cada bloque por un hash perfecto de
O(logn)bits. Notemos que podríamos elegir una constante grande para evitar
colisiones con alta probabilidad.
Podemos multiplicar cada dígito por un enteromy luego obtener las máscaras
reducidas de cada uno. Esto tomaráO(1)por dígito.
Esto preserva la identidad pero no preserva el orden.
Paso 3
Notemos que ahora la cantidad de bits usados esO(nlog1+ε n), debido a
que tenemosnenteros conlog ε ndígitos delognbits.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 9 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 29
CS3014 Estructuras de Datos Avanzadas
Signature sort
Packed sort
Es un algoritmo que nos permite ordenarnenteros debbits enO(n)si el
tamaño de la palabra cumplew= Ω(blognlog logn).
El paso 2 nos dejó con enteros deO(log1+ε n)bits, así que cumplimos la con-
dición sin problemas sobre los hashes/signatures. Por lo tanto, ordenaremos
los hashes enO(n).
Paso 4
Construimos un trie comprimido sobre los hashes, de manera que el inorder
traversal del mismo nos da los hashes ordenados.
Esto tomaO(n)de espacio y es posible construirlo enO(n)también.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 10 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 30
CS3014 Estructuras de Datos Avanzadas
Signature sort
Packed sort
Es un algoritmo que nos permite ordenarnenteros debbits enO(n)si el
tamaño de la palabra cumplew= Ω(blognlog logn).
El paso 2 nos dejó con enteros deO(log1+ε n)bits, así que cumplimos la con-
dición sin problemas sobre los hashes/signatures. Por lo tanto, ordenaremos
los hashes enO(n).
Paso 4
Construimos un trie comprimido sobre los hashes, de manera que el inorder
traversal del mismo nos da los hashes ordenados.
Esto tomaO(n)de espacio y es posible construirlo enO(n)también.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 10 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 31
CS3014 Estructuras de Datos Avanzadas
Signature sort
Packed sort
Es un algoritmo que nos permite ordenarnenteros debbits enO(n)si el
tamaño de la palabra cumplew= Ω(blognlog logn).
El paso 2 nos dejó con enteros deO(log1+ε n)bits, así que cumplimos la con-
dición sin problemas sobre los hashes/signatures. Por lo tanto, ordenaremos
los hashes enO(n).
Paso 4
Construimos un trie comprimido sobre los hashes, de manera que el inorder
traversal del mismo nos da los hashes ordenados.
Esto tomaO(n)de espacio y es posible construirlo enO(n)también.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 10 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 32
CS3014 Estructuras de Datos Avanzadas
Signature sort
Packed sort
Es un algoritmo que nos permite ordenarnenteros debbits enO(n)si el
tamaño de la palabra cumplew= Ω(blognlog logn).
El paso 2 nos dejó con enteros deO(log1+ε n)bits, así que cumplimos la con-
dición sin problemas sobre los hashes/signatures. Por lo tanto, ordenaremos
los hashes enO(n).
Paso 4
Construimos un trie comprimido sobre los hashes, de manera que el inorder
traversal del mismo nos da los hashes ordenados.
Esto tomaO(n)de espacio y es posible construirlo enO(n)también.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 10 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 33
CS3014 Estructuras de Datos Avanzadas
Signature sort
Packed sort
Es un algoritmo que nos permite ordenarnenteros debbits enO(n)si el
tamaño de la palabra cumplew= Ω(blognlog logn).
El paso 2 nos dejó con enteros deO(log1+ε n)bits, así que cumplimos la con-
dición sin problemas sobre los hashes/signatures. Por lo tanto, ordenaremos
los hashes enO(n).
Paso 4
Construimos un trie comprimido sobre los hashes, de manera que el inorder
traversal del mismo nos da los hashes ordenados.
Esto tomaO(n)de espacio y es posible construirlo enO(n)también.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 10 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 34
CS3014 Estructuras de Datos Avanzadas
Signature sort
Packed sort
Es un algoritmo que nos permite ordenarnenteros debbits enO(n)si el
tamaño de la palabra cumplew= Ω(blognlog logn).
El paso 2 nos dejó con enteros deO(log1+ε n)bits, así que cumplimos la con-
dición sin problemas sobre los hashes/signatures. Por lo tanto, ordenaremos
los hashes enO(n).
Paso 4
Construimos un trie comprimido sobre los hashes, de manera que el inorder
traversal del mismo nos da los hashes ordenados.
Esto tomaO(n)de espacio y es posible construirlo enO(n)también.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 10 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 35
CS3014 Estructuras de Datos Avanzadas
Signature sort
Trie comprimido
Tomaremos cada nodo del trie con alfabeto{0,1, . . . ,B−1}que no tiene al
menos dos hijos almacenados y lo “uniremos” con su padre.
Debido a lo anterior, tendremosO(n)nodos en la versión comprimida, com-
parado con losO(nlog ε n)que tendríamos en la versión completa.
Problemática
Tenemos todos los enteros originales ordenados según sus hashes, así que en
realidad no tenemos ningún orden correcto todavía.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 11 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 36
CS3014 Estructuras de Datos Avanzadas
Signature sort
Trie comprimido
Tomaremos cada nodo del trie con alfabeto{0,1, . . . ,B−1}que no tiene al
menos dos hijos almacenados y lo “uniremos” con su padre.
Debido a lo anterior, tendremosO(n)nodos en la versión comprimida, com-
parado con losO(nlog ε n)que tendríamos en la versión completa.
Problemática
Tenemos todos los enteros originales ordenados según sus hashes, así que en
realidad no tenemos ningún orden correcto todavía.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 11 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 37
CS3014 Estructuras de Datos Avanzadas
Signature sort
Trie comprimido
Tomaremos cada nodo del trie con alfabeto{0,1, . . . ,B−1}que no tiene al
menos dos hijos almacenados y lo “uniremos” con su padre.
Debido a lo anterior, tendremosO(n)nodos en la versión comprimida, com-
parado con losO(nlog ε n)que tendríamos en la versión completa.
Problemática
Tenemos todos los enteros originales ordenados según sus hashes, así que en
realidad no tenemos ningún orden correcto todavía.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 11 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 38
CS3014 Estructuras de Datos Avanzadas
Signature sort
Trie comprimido
Tomaremos cada nodo del trie con alfabeto{0,1, . . . ,B−1}que no tiene al
menos dos hijos almacenados y lo “uniremos” con su padre.
Debido a lo anterior, tendremosO(n)nodos en la versión comprimida, com-
parado con losO(nlog ε n)que tendríamos en la versión completa.
Problemática
Tenemos todos los enteros originales ordenados según sus hashes, así que en
realidad no tenemos ningún orden correcto todavía.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 11 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 39
CS3014 Estructuras de Datos Avanzadas
Signature sort
Trie comprimido
Tomaremos cada nodo del trie con alfabeto{0,1, . . . ,B−1}que no tiene al
menos dos hijos almacenados y lo “uniremos” con su padre.
Debido a lo anterior, tendremosO(n)nodos en la versión comprimida, com-
parado con losO(nlog ε n)que tendríamos en la versión completa.
Problemática
Tenemos todos los enteros originales ordenados según sus hashes, así que en
realidad no tenemos ningún orden correcto todavía.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 11 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 40
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 5
Ordenaremos las aristas del trie recursivamente usando
(Índice del nodo,Primer digito,Índice del hijo).
De esta manera, si el nivel actual tiene enteros dew′ bits, estamos reducién-
dolos a una tupla de(O(logn),O( w ′
logε n ),O(logn)), así que la cantidad de
bits se reduce a w ′
logε n +O(logn)
Luego de 1
ε +1 niveles de recursión se tendrá que la cantidad de bits de cada
entero esb=O( 1
ε logn+ w ′
log1+ε n ) =O( w
lognlog logn ).
Sobre este escenario podemos usar packed sort y ordenar todo enO(n)como
caso base.
Paso 6
Permutaremos los hijos de cada nodo según el orden de sus aristas.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 41
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 5
Ordenaremos las aristas del trie recursivamente usando
(Índice del nodo,Primer digito,Índice del hijo).
De esta manera, si el nivel actual tiene enteros dew′ bits, estamos reducién-
dolos a una tupla de(O(logn),O( w ′
logε n ),O(logn)), así que la cantidad de
bits se reduce a w ′
logε n +O(logn)
Luego de 1
ε +1 niveles de recursión se tendrá que la cantidad de bits de cada
entero esb=O( 1
ε logn+ w ′
log1+ε n ) =O( w
lognlog logn ).
Sobre este escenario podemos usar packed sort y ordenar todo enO(n)como
caso base.
Paso 6
Permutaremos los hijos de cada nodo según el orden de sus aristas.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 42
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 5
Ordenaremos las aristas del trie recursivamente usando
(Índice del nodo,Primer digito,Índice del hijo).
De esta manera, si el nivel actual tiene enteros dew′ bits, estamos reducién-
dolos a una tupla de(O(logn),O( w ′
logε n ),O(logn)), así que la cantidad de
bits se reduce a w ′
logε n +O(logn)
Luego de 1
ε +1 niveles de recursión se tendrá que la cantidad de bits de cada
entero esb=O( 1
ε logn+ w ′
log1+ε n ) =O( w
lognlog logn ).
Sobre este escenario podemos usar packed sort y ordenar todo enO(n)como
caso base.
Paso 6
Permutaremos los hijos de cada nodo según el orden de sus aristas.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 43
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 5
Ordenaremos las aristas del trie recursivamente usando
(Índice del nodo,Primer digito,Índice del hijo).
De esta manera, si el nivel actual tiene enteros dew′ bits, estamos reducién-
dolos a una tupla de(O(logn),O( w ′
logε n ),O(logn)), así que la cantidad de
bits se reduce a w ′
logε n +O(logn)
Luego de 1
ε +1 niveles de recursión se tendrá que la cantidad de bits de cada
entero esb=O( 1
ε logn+ w ′
log1+ε n ) =O( w
lognlog logn ).
Sobre este escenario podemos usar packed sort y ordenar todo enO(n)como
caso base.
Paso 6
Permutaremos los hijos de cada nodo según el orden de sus aristas.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 44
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 5
Ordenaremos las aristas del trie recursivamente usando
(Índice del nodo,Primer digito,Índice del hijo).
De esta manera, si el nivel actual tiene enteros dew′ bits, estamos reducién-
dolos a una tupla de(O(logn),O( w ′
logε n ),O(logn)), así que la cantidad de
bits se reduce a w ′
logε n +O(logn)
Luego de 1
ε +1 niveles de recursión se tendrá que la cantidad de bits de cada
entero esb=O( 1
ε logn+ w ′
log1+ε n ) =O( w
lognlog logn ).
Sobre este escenario podemos usar packed sort y ordenar todo enO(n)como
caso base.
Paso 6
Permutaremos los hijos de cada nodo según el orden de sus aristas.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 45
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 5
Ordenaremos las aristas del trie recursivamente usando
(Índice del nodo,Primer digito,Índice del hijo).
De esta manera, si el nivel actual tiene enteros dew′ bits, estamos reducién-
dolos a una tupla de(O(logn),O( w ′
logε n ),O(logn)), así que la cantidad de
bits se reduce a w ′
logε n +O(logn)
Luego de 1
ε +1 niveles de recursión se tendrá que la cantidad de bits de cada
entero esb=O( 1
ε logn+ w ′
log1+ε n ) =O( w
lognlog logn ).
Sobre este escenario podemos usar packed sort y ordenar todo enO(n)como
caso base.
Paso 6
Permutaremos los hijos de cada nodo según el orden de sus aristas.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 46
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 5
Ordenaremos las aristas del trie recursivamente usando
(Índice del nodo,Primer digito,Índice del hijo).
De esta manera, si el nivel actual tiene enteros dew′ bits, estamos reducién-
dolos a una tupla de(O(logn),O( w ′
logε n ),O(logn)), así que la cantidad de
bits se reduce a w ′
logε n +O(logn)
Luego de 1
ε +1 niveles de recursión se tendrá que la cantidad de bits de cada
entero esb=O( 1
ε logn+ w ′
log1+ε n ) =O( w
lognlog logn ).
Sobre este escenario podemos usar packed sort y ordenar todo enO(n)como
caso base.
Paso 6
Permutaremos los hijos de cada nodo según el orden de sus aristas.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 47
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 7
Ya que ahora tendremos los hijos de cada nodo del trie comprimido correc-
tamente ordenados según el valor original de sus datos, podemos ordenar
calculando el inorder traversal del trie.
En resumen
1. Dividimos cada entero en dígitos para poder tener valores más
pequeños.
2. Aplicamos hashing para poder reducir el espacio usado para representar
los dígitos.
3. Usamos un trie comprimido para “ordenar” los hashes
4. Ordenamos recursivamente las aristas del trie comprimido para
ordenarlos según el valor original.
5. Acomodamos el trie según dicho orden y calculamos el inorder traversal.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 13 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 48
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 7
Ya que ahora tendremos los hijos de cada nodo del trie comprimido correc-
tamente ordenados según el valor original de sus datos, podemos ordenar
calculando el inorder traversal del trie.
En resumen
1. Dividimos cada entero en dígitos para poder tener valores más
pequeños.
2. Aplicamos hashing para poder reducir el espacio usado para representar
los dígitos.
3. Usamos un trie comprimido para “ordenar” los hashes
4. Ordenamos recursivamente las aristas del trie comprimido para
ordenarlos según el valor original.
5. Acomodamos el trie según dicho orden y calculamos el inorder traversal.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 13 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 49
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 7
Ya que ahora tendremos los hijos de cada nodo del trie comprimido correc-
tamente ordenados según el valor original de sus datos, podemos ordenar
calculando el inorder traversal del trie.
En resumen
1. Dividimos cada entero en dígitos para poder tener valores más
pequeños.
2. Aplicamos hashing para poder reducir el espacio usado para representar
los dígitos.
3. Usamos un trie comprimido para “ordenar” los hashes
4. Ordenamos recursivamente las aristas del trie comprimido para
ordenarlos según el valor original.
5. Acomodamos el trie según dicho orden y calculamos el inorder traversal.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 13 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 50
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 7
Ya que ahora tendremos los hijos de cada nodo del trie comprimido correc-
tamente ordenados según el valor original de sus datos, podemos ordenar
calculando el inorder traversal del trie.
En resumen
1. Dividimos cada entero en dígitos para poder tener valores más
pequeños.
2. Aplicamos hashing para poder reducir el espacio usado para representar
los dígitos.
3. Usamos un trie comprimido para “ordenar” los hashes
4. Ordenamos recursivamente las aristas del trie comprimido para
ordenarlos según el valor original.
5. Acomodamos el trie según dicho orden y calculamos el inorder traversal.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 13 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 51
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 7
Ya que ahora tendremos los hijos de cada nodo del trie comprimido correc-
tamente ordenados según el valor original de sus datos, podemos ordenar
calculando el inorder traversal del trie.
En resumen
1. Dividimos cada entero en dígitos para poder tener valores más
pequeños.
2. Aplicamos hashing para poder reducir el espacio usado para representar
los dígitos.
3. Usamos un trie comprimido para “ordenar” los hashes
4. Ordenamos recursivamente las aristas del trie comprimido para
ordenarlos según el valor original.
5. Acomodamos el trie según dicho orden y calculamos el inorder traversal.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 13 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 52
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 7
Ya que ahora tendremos los hijos de cada nodo del trie comprimido correc-
tamente ordenados según el valor original de sus datos, podemos ordenar
calculando el inorder traversal del trie.
En resumen
1. Dividimos cada entero en dígitos para poder tener valores más
pequeños.
2. Aplicamos hashing para poder reducir el espacio usado para representar
los dígitos.
3. Usamos un trie comprimido para “ordenar” los hashes
4. Ordenamos recursivamente las aristas del trie comprimido para
ordenarlos según el valor original.
5. Acomodamos el trie según dicho orden y calculamos el inorder traversal.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 13 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 53
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 7
Ya que ahora tendremos los hijos de cada nodo del trie comprimido correc-
tamente ordenados según el valor original de sus datos, podemos ordenar
calculando el inorder traversal del trie.
En resumen
1. Dividimos cada entero en dígitos para poder tener valores más
pequeños.
2. Aplicamos hashing para poder reducir el espacio usado para representar
los dígitos.
3. Usamos un trie comprimido para “ordenar” los hashes
4. Ordenamos recursivamente las aristas del trie comprimido para
ordenarlos según el valor original.
5. Acomodamos el trie según dicho orden y calculamos el inorder traversal.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 13 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 54
CS3014 Estructuras de Datos Avanzadas
Signature sort
Paso 7
Ya que ahora tendremos los hijos de cada nodo del trie comprimido correc-
tamente ordenados según el valor original de sus datos, podemos ordenar
calculando el inorder traversal del trie.
En resumen
1. Dividimos cada entero en dígitos para poder tener valores más
pequeños.
2. Aplicamos hashing para poder reducir el espacio usado para representar
los dígitos.
3. Usamos un trie comprimido para “ordenar” los hashes
4. Ordenamos recursivamente las aristas del trie comprimido para
ordenarlos según el valor original.
5. Acomodamos el trie según dicho orden y calculamos el inorder traversal.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 13 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 55
CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Aprendimos la equivalencia entre ordenamiento y colas de prioridad.
▶Aprendimos algunos resultados de ordenamientos de enteros.
▶Aprendimos signature sort.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 14 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 56
CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Aprendimos la equivalencia entre ordenamiento y colas de prioridad.
▶Aprendimos algunos resultados de ordenamientos de enteros.
▶Aprendimos signature sort.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 14 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 57
CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Aprendimos la equivalencia entre ordenamiento y colas de prioridad.
▶Aprendimos algunos resultados de ordenamientos de enteros.
▶Aprendimos signature sort.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 14 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 58
CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Aprendimos la equivalencia entre ordenamiento y colas de prioridad.
▶Aprendimos algunos resultados de ordenamientos de enteros.
▶Aprendimos signature sort.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 14 / 15


# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf - Page 59
CS3014 Estructuras de Datos Avanzadas
Gracias
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 15 / 15


# eda_slides_06_integer.pdf - Page 1
Integer I
CS3014 - Estructura de Datos Avanzados
Luciano A. Romero Calla
lromeroc@utec.edu.pe
2026-1


# eda_slides_06_integer.pdf - Page 2
Overview
1. Goals
2. Models
3. Predecesor problem
4. van Emde Boas
5. Tree view
6. Saving space
2/19


# eda_slides_06_integer.pdf - Page 3
Goals
1.
Goals
3/19


# eda_slides_06_integer.pdf - Page 4
Goals
Goals
▶ Explore integer data structures to solve the predecessor problem.
▶ Describe two main data structuresvan Emde BoasandY-fasttrees.
4/19


# eda_slides_06_integer.pdf - Page 5
Goals
Goals
▶ Explore integer data structures to solve the predecessor problem.
▶ Describe two main data structuresvan Emde BoasandY-fasttrees.
4/19


# eda_slides_06_integer.pdf - Page 6
Models
2.
Models
5/19


# eda_slides_06_integer.pdf - Page 7
Models
Models
word
w-bit integer∈U={0,1,2,3, ...,u=2 w −1}
transdichotomous RAM
bridging two worlds machine/problem,w≥lgS
word RAM
transdichotomous RAM with C-style operations
cell probe
count # memory reads & writes, computation-free,
useful for lower bounds
cell probe strong
transdichotomous RAM
word RAM
pointer machine
BST weak
6/19


# eda_slides_06_integer.pdf - Page 8
Models
Models
word
w-bit integer∈U={0,1,2,3, ...,u=2 w −1}
transdichotomous RAM
bridging two worlds machine/problem,w≥lgS
word RAM
transdichotomous RAM with C-style operations
cell probe
count # memory reads & writes, computation-free,
useful for lower bounds
cell probe strong
transdichotomous RAM
word RAM
pointer machine
BST weak
6/19


# eda_slides_06_integer.pdf - Page 9
Models
Models
word
w-bit integer∈U={0,1,2,3, ...,u=2 w −1}
transdichotomous RAM
bridging two worlds machine/problem,w≥lgS
word RAM
transdichotomous RAM with C-style operations
cell probe
count # memory reads & writes, computation-free,
useful for lower bounds
cell probe strong
transdichotomous RAM
word RAM
pointer machine
BST weak
6/19


# eda_slides_06_integer.pdf - Page 10
Models
Models
word
w-bit integer∈U={0,1,2,3, ...,u=2 w −1}
transdichotomous RAM
bridging two worlds machine/problem,w≥lgS
word RAM
transdichotomous RAM with C-style operations
cell probe
count # memory reads & writes, computation-free,
useful for lower bounds
cell probe strong
transdichotomous RAM
word RAM
pointer machine
BST weak
6/19


# eda_slides_06_integer.pdf - Page 11
Models
Models
word
w-bit integer∈U={0,1,2,3, ...,u=2 w −1}
transdichotomous RAM
bridging two worlds machine/problem,w≥lgS
word RAM
transdichotomous RAM with C-style operations
cell probe
count # memory reads & writes, computation-free,
useful for lower bounds
cell probe strong
transdichotomous RAM
word RAM
pointer machine
BST weak
6/19


# eda_slides_06_integer.pdf - Page 12
Predecesor problem
3.
Predecesor problem
7/19


# eda_slides_06_integer.pdf - Page 13
Predecesor problem
Predecesor problem
problem
maintain a setSofnwords
▶ insert(x∈U)
▶ delete(x∈S)
▶ predecessor(x∈U):max{y∈S|y<x}
▶ successor(x∈U):max{y∈S|y>x}
BST
comparison model:O(lgn)/op optimal
word RAM
▶ van Emde Boas:O(lgw)/op,Θ(u)space
▶ Y-fast trees:O(lgw)/op,Θ(n)space
▶ fusion trees:O(log w n)/op,Θ(n)space
cell probe lower bound
O(n polylg n)space,Ω

min

logw n, lgw
lg lgw
lg lgn

pointer machine
▶ word specified by node pointer
▶ van Emde Boas:O(lg lgu)/op,Θ(u)space
▶ lower bound:Ω(lg lgu)/op,Ω(u)space
8/19


# eda_slides_06_integer.pdf - Page 14
Predecesor problem
Predecesor problem
problem
maintain a setSofnwords
▶ insert(x∈U)
▶ delete(x∈S)
▶ predecessor(x∈U):max{y∈S|y<x}
▶ successor(x∈U):max{y∈S|y>x}
BST
comparison model:O(lgn)/op optimal
word RAM
▶ van Emde Boas:O(lgw)/op,Θ(u)space
▶ Y-fast trees:O(lgw)/op,Θ(n)space
▶ fusion trees:O(log w n)/op,Θ(n)space
cell probe lower bound
O(n polylg n)space,Ω

min

logw n, lgw
lg lgw
lg lgn

pointer machine
▶ word specified by node pointer
▶ van Emde Boas:O(lg lgu)/op,Θ(u)space
▶ lower bound:Ω(lg lgu)/op,Ω(u)space
8/19


# eda_slides_06_integer.pdf - Page 15
Predecesor problem
Predecesor problem
problem
maintain a setSofnwords
▶ insert(x∈U)
▶ delete(x∈S)
▶ predecessor(x∈U):max{y∈S|y<x}
▶ successor(x∈U):max{y∈S|y>x}
BST
comparison model:O(lgn)/op optimal
word RAM
▶ van Emde Boas:O(lgw)/op,Θ(u)space
▶ Y-fast trees:O(lgw)/op,Θ(n)space
▶ fusion trees:O(log w n)/op,Θ(n)space
cell probe lower bound
O(n polylg n)space,Ω

min

logw n, lgw
lg lgw
lg lgn

pointer machine
▶ word specified by node pointer
▶ van Emde Boas:O(lg lgu)/op,Θ(u)space
▶ lower bound:Ω(lg lgu)/op,Ω(u)space
8/19


# eda_slides_06_integer.pdf - Page 16
Predecesor problem
Predecesor problem
problem
maintain a setSofnwords
▶ insert(x∈U)
▶ delete(x∈S)
▶ predecessor(x∈U):max{y∈S|y<x}
▶ successor(x∈U):max{y∈S|y>x}
BST
comparison model:O(lgn)/op optimal
word RAM
▶ van Emde Boas:O(lgw)/op,Θ(u)space
▶ Y-fast trees:O(lgw)/op,Θ(n)space
▶ fusion trees:O(log w n)/op,Θ(n)space
cell probe lower bound
O(n polylg n)space,Ω

min

logw n, lgw
lg lgw
lg lgn

pointer machine
▶ word specified by node pointer
▶ van Emde Boas:O(lg lgu)/op,Θ(u)space
▶ lower bound:Ω(lg lgu)/op,Ω(u)space
8/19


# eda_slides_06_integer.pdf - Page 17
Predecesor problem
Predecesor problem
problem
maintain a setSofnwords
▶ insert(x∈U)
▶ delete(x∈S)
▶ predecessor(x∈U):max{y∈S|y<x}
▶ successor(x∈U):max{y∈S|y>x}
BST
comparison model:O(lgn)/op optimal
word RAM
▶ van Emde Boas:O(lgw)/op,Θ(u)space
▶ Y-fast trees:O(lgw)/op,Θ(n)space
▶ fusion trees:O(log w n)/op,Θ(n)space
cell probe lower bound
O(n polylg n)space,Ω

min

logw n, lgw
lg lgw
lg lgn

pointer machine
▶ word specified by node pointer
▶ van Emde Boas:O(lg lgu)/op,Θ(u)space
▶ lower bound:Ω(lg lgu)/op,Ω(u)space
8/19


# eda_slides_06_integer.pdf - Page 18
van Emde Boas
4.
van Emde Boas
4.1 Definition
4.2 Operations
9/19


# eda_slides_06_integer.pdf - Page 19
van Emde Boas Definition
Definition
idea
T(u) =T( √u) +O(1)
hierarchical coordinates
wordx=⟨c,i⟩
recursive vEBVof sizeu
▶ V.cluster[i] =vEB of size √u
▶ V.summary[i] =vEB of size √u
▶ V.min=minimum element inV
▶ V.max=maximum element inV
10/19


# eda_slides_06_integer.pdf - Page 20
van Emde Boas Definition
Definition
idea
T(u) =T( √u) +O(1)
hierarchical coordinates
wordx=⟨c,i⟩
recursive vEBVof sizeu
▶ V.cluster[i] =vEB of size √u
▶ V.summary[i] =vEB of size √u
▶ V.min=minimum element inV
▶ V.max=maximum element inV
10/19


# eda_slides_06_integer.pdf - Page 21
van Emde Boas Definition
Definition
idea
T(u) =T( √u) +O(1)
hierarchical coordinates
wordx=⟨c,i⟩
recursive vEBVof sizeu
▶ V.cluster[i] =vEB of size √u
▶ V.summary[i] =vEB of size √u
▶ V.min=minimum element inV
▶ V.max=maximum element inV
10/19


# eda_slides_06_integer.pdf - Page 22
van Emde Boas Definition
Definition
idea
T(u) =T( √u) +O(1)
hierarchical coordinates
wordx=⟨c,i⟩
recursive vEBVof sizeu
▶ V.cluster[i] =vEB of size √u
▶ V.summary[i] =vEB of size √u
▶ V.min=minimum element inV
▶ V.max=maximum element inV
10/19


# eda_slides_06_integer.pdf - Page 23
van Emde Boas Definition
Definition
idea
T(u) =T( √u) +O(1)
hierarchical coordinates
wordx=⟨c,i⟩
recursive vEBVof sizeu
▶ V.cluster[i] =vEB of size √u
▶ V.summary[i] =vEB of size √u
▶ V.min=minimum element inV
▶ V.max=maximum element inV
10/19


# eda_slides_06_integer.pdf - Page 24
van Emde Boas Definition
Definition
idea
T(u) =T( √u) +O(1)
hierarchical coordinates
wordx=⟨c,i⟩
recursive vEBVof sizeu
▶ V.cluster[i] =vEB of size √u
▶ V.summary[i] =vEB of size √u
▶ V.min=minimum element inV
▶ V.max=maximum element inV
10/19


# eda_slides_06_integer.pdf - Page 25
van Emde Boas Definition
Definition
Figure 1:van Emde Boas structure 1
1Demaine 2021.
11/19


# eda_slides_06_integer.pdf - Page 26
van Emde Boas Operations
Operations
Successor(V,x=⟨c,i⟩)
▶ ifx<V.min returnV.min
▶ ifi<V.cluster[c].max
return⟨c,Successor(V.cluster[c],i)⟩
▶ elsec ′ =Successor(V.summary,c)
return⟨c ′,V.cluster[c ′].min⟩
12/19


# eda_slides_06_integer.pdf - Page 27
Tree view
5.
Tree view
5.1 Indirection
13/19


# eda_slides_06_integer.pdf - Page 28
Tree view
Tree view
Figure 2:van Emde Boas tree view 2
2Demaine 2021.
14/19


# eda_slides_06_integer.pdf - Page 29
Tree view Indirection
Indirection
▶ fromO(lgw)query,O(w)update DS
▶ reduce toO(lgw)update: splitnelements into chuncks of sizeΘ(w)
15/19


# eda_slides_06_integer.pdf - Page 30
Tree view Indirection
Indirection
▶ fromO(lgw)query,O(w)update DS
▶ reduce toO(lgw)update: splitnelements into chuncks of sizeΘ(w)
15/19


# eda_slides_06_integer.pdf - Page 31
Saving space
6.
Saving space
6.1 X-fast trees
6.2 Y-fast trees
16/19


# eda_slides_06_integer.pdf - Page 32
Saving space
Saving space
▶ don’t store empty clusters vEB
▶ V.clusters = hash table
▶ charge each table entry to min in child
▶ space boundΘ(n)via indirection
17/19


# eda_slides_06_integer.pdf - Page 33
Saving space
Saving space
▶ don’t store empty clusters vEB
▶ V.clusters = hash table
▶ charge each table entry to min in child
▶ space boundΘ(n)via indirection
17/19


# eda_slides_06_integer.pdf - Page 34
Saving space
Saving space
▶ don’t store empty clusters vEB
▶ V.clusters = hash table
▶ charge each table entry to min in child
▶ space boundΘ(n)via indirection
17/19


# eda_slides_06_integer.pdf - Page 35
Saving space
Saving space
▶ don’t store empty clusters vEB
▶ V.clusters = hash table
▶ charge each table entry to min in child
▶ space boundΘ(n)via indirection
17/19


# eda_slides_06_integer.pdf - Page 36
Saving space X-fast trees
X-fast trees
▶ don’t store 0s
▶ store a hash table of root-to-1 path
▶ O(lgw)query binary search
▶ Θ(w)update
▶ Θ(nw)space
18/19


# eda_slides_06_integer.pdf - Page 37
Saving space X-fast trees
X-fast trees
▶ don’t store 0s
▶ store a hash table of root-to-1 path
▶ O(lgw)query binary search
▶ Θ(w)update
▶ Θ(nw)space
18/19


# eda_slides_06_integer.pdf - Page 38
Saving space X-fast trees
X-fast trees
▶ don’t store 0s
▶ store a hash table of root-to-1 path
▶ O(lgw)query binary search
▶ Θ(w)update
▶ Θ(nw)space
18/19


# eda_slides_06_integer.pdf - Page 39
Saving space X-fast trees
X-fast trees
▶ don’t store 0s
▶ store a hash table of root-to-1 path
▶ O(lgw)query binary search
▶ Θ(w)update
▶ Θ(nw)space
18/19


# eda_slides_06_integer.pdf - Page 40
Saving space X-fast trees
X-fast trees
▶ don’t store 0s
▶ store a hash table of root-to-1 path
▶ O(lgw)query binary search
▶ Θ(w)update
▶ Θ(nw)space
18/19


# eda_slides_06_integer.pdf - Page 41
Saving space Y-fast trees
Y-fast trees
▶ = X-fast trees
▶ + indirection
▶ O(lgw)query binary search
▶ O(lgw)update amortized
▶ O(lgw)space
19/19


# eda_slides_06_integer.pdf - Page 42
Saving space Y-fast trees
Y-fast trees
▶ = X-fast trees
▶ + indirection
▶ O(lgw)query binary search
▶ O(lgw)update amortized
▶ O(lgw)space
19/19


# eda_slides_06_integer.pdf - Page 43
Saving space Y-fast trees
Y-fast trees
▶ = X-fast trees
▶ + indirection
▶ O(lgw)query binary search
▶ O(lgw)update amortized
▶ O(lgw)space
19/19


# eda_slides_06_integer.pdf - Page 44
Saving space Y-fast trees
Y-fast trees
▶ = X-fast trees
▶ + indirection
▶ O(lgw)query binary search
▶ O(lgw)update amortized
▶ O(lgw)space
19/19


# eda_slides_06_integer.pdf - Page 45
Saving space Y-fast trees
Y-fast trees
▶ = X-fast trees
▶ + indirection
▶ O(lgw)query binary search
▶ O(lgw)update amortized
▶ O(lgw)space
19/19


# eda_slides_06_integer.pdf - Page 46
Thanks


# eda_slides_06_integer.pdf - Page 47
References
References
Demaine, Erik (2021).6.851: Advanced Data Structures (Spring’21).url: https://courses.
csail.mit.edu/6.851/spring21/.
21/19


# eda_slides_06_integer.pdf - Page 48
Acknowledgements
Acknowledgements
The course slides are based on the lectures from previous editions and on similar lectures elsewhere.
List of credits: Erick Demaine, Keith Schwarz
22/19