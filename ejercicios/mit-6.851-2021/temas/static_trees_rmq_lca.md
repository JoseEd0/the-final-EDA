# Static Trees, RMQ y LCA

## Fuentes MIT

- Lecture L15: static trees, RMQ, LCA, level ancestor.
- PS10: succinct +-1 RMQ.
- No hay solucion oficial enlazada para PS10 en Spring 2021.

## Fuentes locales EDA

- `../../statics and strings/eda_slides_08_rmq.pdf`
- `../../statics and strings/Estructuras_de_Datos_Avanzadas___Strings_I.pdf`

## Que debes poder escribir en papel

1. Sparse table RMQ:
   - preprocess `O(n log n)`.
   - query idempotente `min` en `O(1)` usando dos bloques.
2. Cartesian tree:
   - root es minimo del arreglo.
   - inorder preserva indices.
   - `RMQ_A(i,j) = LCA_T(i,j)`.
3. LCA a RMQ:
   - Euler tour del arbol.
   - arreglo de profundidades.
   - `LCA(u,v)` es el nodo de minima profundidad entre primeras apariciones.
4. Propiedad `+-1 RMQ`:
   - en Euler tour, profundidades consecutivas cambian por `+1` o `-1`.
5. Four Russians para RMQ:
   - bloques de tamano `b = 1/2 log n`.
   - macro sparse table sobre minimos de bloque.
   - micro tablas por forma de bloque.
   - espacio `O(n)`, query `O(1)`.
6. Level ancestor:
   - binary lifting `O(n log n), O(log n)`.
   - versiones optimas usan ladder/macro-micro.

## Imperial Roads

Patron clave:

1. Construir MST con Kruskal.
2. Preprocesar el MST para max edge on path.
3. Para una arista consultada `(u,v,w)`, si se fuerza su inclusion:
   `respuesta = peso(MST) + w - maxEdgeOnPath(u,v)`.
4. Correctitud por propiedad del ciclo: al agregar `(u,v)`, se forma un ciclo; para mantener arbol se elimina la arista mas pesada del camino.

## Problemas para resolver

1. PS10: succinct `+-1 RMQ`.
2. Imperial Roads: MST + LCA/RMQ para max edge path.
3. Problema propio S1: probar `RMQ <-> LCA` por Cartesian tree.
4. Problema propio S2: disenar LCA `O(n log n), O(log n)` y luego explicar como llegar a `O(n), O(1)` conceptualmente.
