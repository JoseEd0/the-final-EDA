# Integer Data Structures

## Fuentes MIT

- Lecture L11: van Emde Boas, x-fast trees, y-fast trees.
- Lecture L12: fusion trees.
- Lecture L14: integer sorting y signature sort.
- PS7: espacio de van Emde Boas.
- PS8: compresion de signatures.
- Soluciones oficiales disponibles: `../originales/solutions/ps7sol.pdf`, `../originales/solutions/ps8sol.pdf`.

## Que debes poder escribir en papel

1. Definir el predecessor problem: mantener un conjunto dinamico `S` en universo `U = {0, ..., 2^w - 1}` con `insert`, `delete`, `predecessor`, `successor`.
2. Comparar modelos:
   - BST por comparaciones: `O(log n)`.
   - word RAM: permite operaciones de palabra en `O(1)`.
   - cell probe: cuenta lecturas/escrituras, util para lower bounds.
3. vEB:
   - divide universo en `sqrt(u)` clusters de tamano `sqrt(u)`.
   - mantiene `min`, `max`, `summary`, `cluster`.
   - recurrencia de tiempo `T(u) = T(sqrt(u)) + O(1) = O(log log u) = O(log w)`.
4. x-fast:
   - guarda prefijos de elementos en hash tables por nivel.
   - query con busqueda binaria de prefijo: `O(log w)`.
   - espacio alto: `Theta(nw)`.
5. y-fast:
   - usa x-fast sobre representantes y buckets balanceados por indireccion.
   - query/update amortizado `O(log w)` con espacio lineal esperado/amortizado.
6. fusion trees:
   - B-tree de grado `w^{1/5}`.
   - dentro de un nodo usa sketches de bits relevantes para predecessor en `O(1)`.
   - query `O(log_w n)`.
7. signature sort:
   - divide palabras en chunks, hashea chunks, comprime signatures, ordena con recursion/trie comprimido.
   - resultado lineal bajo supuestos de tamano de palabra.

## Problemas para resolver

1. PS7: espacio de vEB con version "saving space".
2. PS8: comprimir signatures en `O(1)` word RAM.
3. Problema propio I1: disenar y-fast a nivel de bloques y justificar espacio lineal.
4. Problema propio I2: comparar vEB vs fusion tree y decidir cual conviene segun `n`, `u`, `w`.

## Plantilla de respuesta

Para cada problema integer, responde en este orden:

1. Modelo asumido (`word RAM`, palabra de `w` bits).
2. Invariante estructural.
3. Operacion critica (`predecessor` casi siempre).
4. Recurrencia o conteo de niveles.
5. Complejidad de tiempo y espacio.
