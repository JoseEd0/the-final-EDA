# Problemas externos utiles

Estos problemas no estan dentro de la lista filtrada del grupo Racso, pero si sirven para los temas del final y deben conservarse.

## Imperial roads

- Link: https://codeforces.com/gym/101889/problem/I
- Tema: MST + LCA/RMQ.

Idea: construir MST. Para forzar una arista `(u,v,w)`, agregarla al MST crea un ciclo. Se elimina la arista de mayor peso en el camino `u-v` del MST. Respuesta:

`peso_MST + w - maxEdgeOnPath(u,v)`.

## Fools and Roads

- Link: https://codeforces.com/problemset/problem/191/C
- Tema: LCA + diferencia en arbol.

Idea: para cada camino `(u,v)`, hacer `delta[u]++`, `delta[v]++`, `delta[lca(u,v)] -= 2`. Luego acumular postorden; el valor de cada hijo indica cuantas rutas pasan por la arista hacia su padre.

## Frequency of String

- Link: https://codeforces.com/problemset/problem/963/D
- Tema: strings, ocurrencias de patrones, ventanas minimas.

Idea: obtener posiciones de ocurrencia de cada patron. Si las ocurrencias son `p1 < p2 < ... < pt`, la minima ventana con `k` ocurrencias es:

`min_i p[i+k-1] - p[i] + |P|`.

Para muchas consultas, usar Aho-Corasick o estructuras de suffix array segun el enfoque.

## Yosupo - Dynamic Graph Vertex Add Component Sum

- Link: https://judge.yosupo.jp/problem/dynamic_graph_vertex_add_component_sum
- Tema: offline dynamic connectivity + suma de componente.

Idea: segment tree sobre tiempo + DSU rollback con suma por componente.

## Yosupo - Dynamic Tree Subtree Add Subtree Sum

- Link: https://judge.yosupo.jp/problem/dynamic_tree_subtree_add_subtree_sum
- Tema: Euler-tour tree, dynamic tree, subtree aggregate.

Idea: representar cada arbol dinamico por una secuencia Euler en BST balanceado. Link/cut son split/merge; subtree add/sum son operaciones de intervalo con lazy propagation.

## SPOJ - Dynamic Tree Connectivity

- Link: https://www.spoj.com/problems/DYNACON1/
- Tema: dynamic forest connectivity.

Idea: online con Link-Cut Trees o Euler-Tour Trees; offline con segment tree sobre tiempo + DSU rollback.
