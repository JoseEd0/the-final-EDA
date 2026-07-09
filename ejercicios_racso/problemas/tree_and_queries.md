# Codeforces 375D - Tree and Queries

- Link: https://codeforces.com/problemset/problem/375/D
- Tema: DSU on tree, small-to-large, Euler tour, consultas sobre subarbol.
- Relevancia: alta para static trees y tree queries.

## Resumen del enunciado

Se tiene un arbol enraizado con colores en vertices. Cada consulta pregunta, para un subarbol y un entero `k`, cuantos colores aparecen al menos `k` veces dentro de ese subarbol.

## Idea central

Procesar subarboles manteniendo frecuencias de colores. Para evitar recomputar todo, se conserva la informacion del hijo pesado y se agregan temporalmente los hijos ligeros. Esto es la tecnica DSU on tree o small-to-large.

## Ver solucion teorica

La solucion completa esta en `../latex/soluciones_teoria_racso.tex`.
