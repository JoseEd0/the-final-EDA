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

Se extrajeron 8 contests visibles y 27 problemas del grupo. Luego se filtro el material para conservar solo los 6 contests utiles de la captura:

- Proyecto 5
- Semana 13 - Clase 1 - Offline Dynamic Connectivity
- Semana 12 - Clase 1 - HLD
- Semana 11 - Problemas de strings
- Proyecto 4
- Semana 10 - Clase 1 - RMQ

El indice final esta en:

- `indices/problemas_mapeados.md`

## Trabajo completado

Se dejo solo el scrape real del grupo con los contests utiles para el final:

- Semana 10 - RMQ
- Semana 11 - Problemas de strings
- Semana 12 - HLD
- Semana 13 - Offline Dynamic Connectivity
- Proyecto 4 y Proyecto 5

Se quitaron Proyecto 2/Efecto cascada y Proyecto 3/BST implicito por no servir para la ruta actual del final.
