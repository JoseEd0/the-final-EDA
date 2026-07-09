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

El grupo requiere sesion de Codeforces, pertenencia al grupo, o ambos.

## Scrape autenticado completado

Luego de que el usuario inicio sesion en el navegador integrado, se pudo leer la pagina:

- `https://codeforces.com/group/AmklRC8lhZ/contests`

Se extrajeron 8 contests visibles y 27 problemas del grupo. El indice final esta en:

- `indices/problemas_mapeados.md`

## Trabajo completado

Se armo un set inicial con los problemas ya identificados por las capturas y por busqueda publica:

- Codeforces 375D - Tree and Queries
- Codeforces 963D - Frequency of String
- Codeforces 191C - Fools and Roads
- ICPC / Codeforces Gym 101889I - Imperial roads
- Yosupo - Dynamic Graph Vertex Add Component Sum
- Yosupo - Dynamic Tree Subtree Add Subtree Sum
- SPOJ DYNACON1 - Dynamic Tree Connectivity

Ademas, se agrego el scrape real del grupo con:

- Semana 10 - RMQ
- Semana 11 - Problemas de strings
- Semana 12 - HLD
- Semana 13 - Offline Dynamic Connectivity
- Proyectos visibles 2, 3, 4 y 5
