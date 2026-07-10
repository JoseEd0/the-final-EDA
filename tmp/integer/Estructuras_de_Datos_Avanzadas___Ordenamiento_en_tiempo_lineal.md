# Estructuras_de_Datos_Avanzadas___Ordenamiento_en_tiempo_lineal.pdf
Pages: 59

## Page 1
CS3014 Estructuras de Datos Avanzadas
CS3014 Estructuras de Datos Avanzadas
Laboratorio - Semana 9 - Sesión 2
Víctor Racsó Galván Oyola
vgalvan@utec.edu.pe
22 de mayo de 2026
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 1 / 15

## Page 2
CS3014 Estructuras de Datos Avanzadas
¿Qué aprenderemos hoy?
▶Equivalencia entre ordenamiento y colas de prioridad
▶Algunos resultados en ordenamiento de enteros
▶Signature sort
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 2 / 15

## Page 3
CS3014 Estructuras de Datos Avanzadas
¿Qué aprenderemos hoy?
▶Equivalencia entre ordenamiento y colas de prioridad
▶Algunos resultados en ordenamiento de enteros
▶Signature sort
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 2 / 15

## Page 4
CS3014 Estructuras de Datos Avanzadas
¿Qué aprenderemos hoy?
▶Equivalencia entre ordenamiento y colas de prioridad
▶Algunos resultados en ordenamiento de enteros
▶Signature sort
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 2 / 15

## Page 5
CS3014 Estructuras de Datos Avanzadas
¿Qué aprenderemos hoy?
▶Equivalencia entre ordenamiento y colas de prioridad
▶Algunos resultados en ordenamiento de enteros
▶Signature sort
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 2 / 15

## Page 6
Ordenamiento y cola de prioridades

## Page 7
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

## Page 8
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

## Page 9
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

## Page 10
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

## Page 11
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

## Page 12
Resultados en ordenamientos de enteros

## Page 13
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

## Page 14
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

## Page 15
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

## Page 16
Signature sort

## Page 17
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

## Page 18
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

## Page 19
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

## Page 20
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

## Page 21
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

## Page 22
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

## Page 23
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

## Page 24
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

## Page 25
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

## Page 26
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

## Page 27
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

## Page 28
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

## Page 29
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

## Page 30
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

## Page 31
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

## Page 32
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

## Page 33
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

## Page 34
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

## Page 35
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

## Page 36
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

## Page 37
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

## Page 38
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

## Page 39
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

## Page 40
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

## Page 41
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

## Page 42
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

## Page 43
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

## Page 44
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

## Page 45
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

## Page 46
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

## Page 47
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

## Page 48
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

## Page 49
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

## Page 50
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

## Page 51
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

## Page 52
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

## Page 53
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

## Page 54
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

## Page 55
CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Aprendimos la equivalencia entre ordenamiento y colas de prioridad.
▶Aprendimos algunos resultados de ordenamientos de enteros.
▶Aprendimos signature sort.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 14 / 15

## Page 56
CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Aprendimos la equivalencia entre ordenamiento y colas de prioridad.
▶Aprendimos algunos resultados de ordenamientos de enteros.
▶Aprendimos signature sort.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 14 / 15

## Page 57
CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Aprendimos la equivalencia entre ordenamiento y colas de prioridad.
▶Aprendimos algunos resultados de ordenamientos de enteros.
▶Aprendimos signature sort.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 14 / 15

## Page 58
CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Aprendimos la equivalencia entre ordenamiento y colas de prioridad.
▶Aprendimos algunos resultados de ordenamientos de enteros.
▶Aprendimos signature sort.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 14 / 15

## Page 59
CS3014 Estructuras de Datos Avanzadas
Gracias
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 15 / 15
