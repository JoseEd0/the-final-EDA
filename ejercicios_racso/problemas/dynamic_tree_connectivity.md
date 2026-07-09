# SPOJ DYNACON1 - Dynamic Tree Connectivity

- Link: https://www.spoj.com/problems/DYNACON1/
- Tema: dynamic forest connectivity.
- Relevancia: alta para dynamic graph.

## Resumen del enunciado

Se mantiene un bosque inicialmente sin aristas. Las operaciones enlazan vertices, cortan aristas y preguntan si dos vertices estan conectados.

## Idea central

Online se puede resolver con Link-Cut Trees o Euler-Tour Trees. Si todas las operaciones se conocen de antemano, tambien se puede usar segment tree sobre tiempo con DSU rollback.

## Ver solucion teorica

La solucion completa esta en `../latex/soluciones_teoria_racso.tex`.
