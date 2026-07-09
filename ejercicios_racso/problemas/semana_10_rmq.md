# Semana 10 - RMQ

Problema:

- Static RMQ: https://codeforces.com/group/AmklRC8lhZ/contest/694840/problem/A

## Que aprender

- Que es una consulta RMQ.
- Sparse table.
- Por que `min` permite responder con dos bloques solapados.
- Complejidad: preproceso `O(n log n)`, query `O(1)`.

## Si no sabes nada

Empieza por entender esta idea: como el arreglo no cambia, vale la pena guardar respuestas de bloques de tamanos `1, 2, 4, 8, ...`. Luego cualquier rango se cubre con dos bloques grandes.
