# Semana 13 - Offline Dynamic Connectivity

Contest:

- https://codeforces.com/group/AmklRC8lhZ/contest/698987

Problemas:

- A: Connect and Disconnect
- B: Addition on Segments

## Que aprender

- Por que DSU normal no soporta borrar aristas.
- Convertir cada arista en intervalos de vida.
- Segment tree sobre tiempo.
- DSU con rollback.
- Procesar queries en hojas y deshacer al volver.

## Idea base

Si una arista se agrega en tiempo `l` y se elimina en tiempo `r`, entonces esta activa en `[l, r)`. Ese intervalo se coloca en un segment tree temporal. Al recorrer el arbol, agregas aristas al DSU; cuando sales, haces rollback.
