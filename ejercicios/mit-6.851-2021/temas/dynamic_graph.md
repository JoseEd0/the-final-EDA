# Dynamic Graph

## Fuentes MIT

- Lecture L19: link-cut trees.
- Lecture L20: Euler-tour trees y dynamic connectivity.
- PS11: LCA con link-cut trees.
- No hay solucion oficial enlazada para PS11 en Spring 2021.

## Fuentes locales EDA

- `../../dinamic/eda_slides_08_dynamic_graph.pdf`
- `../../dinamic/eda_slides_09_dynamic_graph.pdf`
- `../../dinamic/CS3014___Heavy_Light_Decomposition.pdf`

## Que debes poder escribir en papel

1. HLD estatica:
   - elegir hijo pesado por mayor subtree.
   - toda ruta raiz-nodo cruza `O(log n)` aristas ligeras.
   - path query/update con segment tree: `O(log^2 n)`.
   - subtree query/update con Euler timestamps: `O(log n)`.
2. Link-cut tree:
   - mantiene forest dinamico.
   - preferred paths representados por splay trees auxiliares.
   - `access(v)` convierte ruta raiz-v en preferred path.
   - operaciones `link`, `cut`, `findRoot`, path aggregate en `O(log n)` amortizado.
3. Euler-tour tree:
   - representa cada arbol por secuencia Euler en BST balanceado/treap.
   - `link` y `cut` son splits/concats.
   - conectividad en forest via raiz del BST.
   - buenos para agregados de componente/subarbol.
4. Fully dynamic connectivity general:
   - mantener bosques expansores por niveles.
   - edge no-tree puede promoverse/demoverse.
   - con ETT por nivel: update `O(log^2 n)` amortizado, query `O(log n)` o mejor segun variante.

## Problemas para resolver

1. PS11: responder LCA usando link-cut tree.
2. DG1: path max dinamico en forest con link/cut.
3. DG2: dynamic graph vertex add component sum con Euler-tour trees.
4. DG3: connectivity fully dynamic general con niveles.
5. DG4: resolver `Tree and Queries`/DSU on tree como extension de heavy-light/small-to-large.

## Comparativa rapida

| Estructura | Caso | Operaciones fuertes | Complejidad |
|---|---|---|---|
| HLD | arbol estatico | path/subtree queries | `O(log^2 n)` path |
| Link-cut tree | forest dinamico | link/cut/path aggregate | `O(log n)` amortizado |
| Euler-tour tree | forest dinamico | connectivity/component aggregate | `O(log n)` |
| Dynamic connectivity general | grafo dinamico | insert/delete/connected | `O(log^2 n)` amortizado |
