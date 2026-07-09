# Codeforces 191C - Fools and Roads

- Link: https://codeforces.com/problemset/problem/191/C
- Tema: LCA, diferencia en arbol, conteo de uso de aristas.
- Relevancia: alta para LCA y tree path queries.

## Resumen del enunciado

Se tiene un arbol y varias rutas entre pares de ciudades. Para cada arista, se pide cuantas rutas pasan por ella.

## Idea central

Usar diferencia sobre arbol: para una ruta `(u,v)`, sumar en `u` y `v`, restar dos veces en `lca(u,v)`, y luego acumular de hojas hacia raiz. El valor acumulado del hijo indica cuantas rutas pasan por la arista padre-hijo.

## Ver solucion teorica

La solucion completa esta en `../latex/soluciones_teoria_racso.tex`.
