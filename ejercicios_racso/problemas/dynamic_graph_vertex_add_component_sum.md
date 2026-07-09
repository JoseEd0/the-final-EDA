# Yosupo - Dynamic Graph Vertex Add Component Sum

- Link: https://judge.yosupo.jp/problem/dynamic_graph_vertex_add_component_sum
- Tema: dynamic connectivity, rollback DSU, segment tree over time.
- Relevancia: alta para dynamic graph.

## Resumen del enunciado

Se mantiene un grafo dinamico con pesos en vertices. Hay operaciones de agregar/quitar aristas, sumar a un vertice y consultar la suma de la componente conexa de un vertice.

## Idea central

Si se procesa offline, cada arista vive en intervalos de tiempo. Se insertan esos intervalos en un segment tree sobre el tiempo. Se recorre el arbol temporal con un DSU con rollback, agregando aristas activas, respondiendo consultas en hojas y deshaciendo al volver.

## Ver solucion teorica

La solucion completa esta en `../latex/soluciones_teoria_racso.tex`.
