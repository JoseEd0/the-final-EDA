# ICPC 2017 / Codeforces Gym 101889I - Imperial roads

- Link: https://codeforces.com/gym/101889/problem/I
- Tema: MST, LCA/RMQ, max edge on path.
- Relevancia: maxima por indicacion directa del usuario.

## Resumen del enunciado

Se tiene un grafo ponderado conectado y consultas donde una carretera debe estar incluida en la red final. Para cada consulta se pide el peso minimo posible de una red conectada que incluya esa carretera.

## Idea central

Construir un MST. Si se fuerza una arista `(u,v,w)`, al agregarla al MST aparece un ciclo. Para mantener un arbol, se elimina la arista de mayor peso en el camino `u-v` del MST. La respuesta es `MST + w - maxEdgeOnPath(u,v)`.

## Ver solucion teorica

La solucion completa esta en `../latex/soluciones_teoria_racso.tex`.
