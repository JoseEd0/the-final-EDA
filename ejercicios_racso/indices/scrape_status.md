# Estado del scrape

## Intentos realizados

1. `curl` a `https://codeforces.com/group/AmklRC8lhZ/contests`
   - Resultado: Cloudflare challenge.
   - No se obtuvo HTML util.

2. Navegador integrado a la misma URL.
   - Resultado: redireccion a `https://codeforces.com/`.
   - La pagina mostro estado anonimo: `Enter | Register`.
   - No se pudo leer la lista del grupo.

## Conclusion

El grupo requiere sesion de Codeforces, pertenencia al grupo, o ambos. Se necesita que el usuario inicie sesion en el navegador integrado para completar el scrape real.

## Trabajo parcial completado

Se armo un set inicial con los problemas ya identificados por las capturas y por busqueda publica:

- Codeforces 375D - Tree and Queries
- Codeforces 963D - Frequency of String
- Codeforces 191C - Fools and Roads
- ICPC / Codeforces Gym 101889I - Imperial roads
- Yosupo - Dynamic Graph Vertex Add Component Sum
- Yosupo - Dynamic Tree Subtree Add Subtree Sum
- SPOJ DYNACON1 - Dynamic Tree Connectivity

Este set cubre los temas confirmados: strings, static trees/RMQ/LCA, dynamic graph/tree, y tree queries.
