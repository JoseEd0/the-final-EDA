# Estructuras_de_Datos_Avanzadas___Modelo_de_enteros_II.pdf
Pages: 52

## Page 1
CS3014 Estructuras de Datos Avanzadas
CS3014 Estructuras de Datos Avanzadas
Laboratorio - Semana 9 - Sesión 1
Víctor Racsó Galván Oyola
vgalvan@utec.edu.pe
20 de mayo de 2026
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 1 / 14

## Page 2
CS3014 Estructuras de Datos Avanzadas
¿Qué aprenderemos hoy?
▶Modelos computacional RAM AC 0
▶Fusion Trees
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 2 / 14

## Page 3
CS3014 Estructuras de Datos Avanzadas
¿Qué aprenderemos hoy?
▶Modelos computacional RAM AC 0
▶Fusion Trees
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 2 / 14

## Page 4
CS3014 Estructuras de Datos Avanzadas
¿Qué aprenderemos hoy?
▶Modelos computacional RAM AC 0
▶Fusion Trees
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 2 / 14

## Page 5
Modelos computacional RAM AC 0

## Page 6
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

## Page 7
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

## Page 8
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

## Page 9
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

## Page 10
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

## Page 11
Fusion T rees

## Page 12
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

## Page 13
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

## Page 14
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

## Page 15
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

## Page 16
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

## Page 17
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

## Page 18
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

## Page 19
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

## Page 20
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

## Page 21
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

## Page 22
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

## Page 23
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

## Page 24
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

## Page 25
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

## Page 26
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

## Page 27
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

## Page 28
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

## Page 29
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

## Page 30
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

## Page 31
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

## Page 32
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

## Page 33
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

## Page 34
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

## Page 35
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

## Page 36
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

## Page 37
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

## Page 38
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

## Page 39
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

## Page 40
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

## Page 41
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

## Page 42
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

## Page 43
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

## Page 44
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

## Page 45
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

## Page 46
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

## Page 47
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

## Page 48
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

## Page 49
CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Aprendimos un poco del modelo RAM AC0 .
▶Aprendimos sobre Fusion Trees.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 13 / 14

## Page 50
CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Aprendimos un poco del modelo RAM AC0 .
▶Aprendimos sobre Fusion Trees.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 13 / 14

## Page 51
CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Aprendimos un poco del modelo RAM AC0 .
▶Aprendimos sobre Fusion Trees.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 13 / 14

## Page 52
CS3014 Estructuras de Datos Avanzadas
Gracias
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 14 / 14
