# Ejercicios Racso - EDA Final

Material orientado al final de EDA, usando los problemas del grupo de Codeforces indicado por el usuario y los problemas visibles/identificados en capturas previas.

## Estado del scrape del grupo

URL objetivo:

- https://codeforces.com/group/AmklRC8lhZ/contests

Desde terminal, Codeforces devuelve un challenge de Cloudflare. Desde el navegador integrado, la pagina redirige al home sin mostrar el grupo porque no hay sesion activa. Por eso no se pudo listar automaticamente todos los contests del grupo en esta pasada.

Para completar el scrape exacto del grupo:

1. Abre Codeforces en el navegador integrado.
2. Inicia sesion y entra al grupo si hace falta.
3. Avisame "ya entre al grupo".
4. Yo continuo y extraigo la tabla de contests/problemas visibles.

## Restriccion importante

No se copian enunciados completos de Codeforces/Yosupo/SPOJ en archivos editables. Se guarda:

- link exacto del problema;
- resumen fiel del enunciado;
- teoria necesaria;
- estrategia de solucion;
- prueba de correctitud;
- analisis de complejidad;
- comparacion con estructuras alternativas.

Los enunciados oficiales completos quedan referenciados por URL.

## Archivos principales

- `indices/problemas_mapeados.md`: lista inicial de problemas relevantes.
- `latex/soluciones_teoria_racso.tex`: workbook teorico extenso sin codigo.
- `latex/soluciones_teoria_racso.pdf`: PDF compilado.

## Prioridad de estudio

1. Strings: `Frequency of String`.
2. Static trees / RMQ / LCA: `Imperial roads`, `Fools and Roads`.
3. Dynamic graph/tree: Yosupo dynamic graph/tree y SPOJ dynamic tree connectivity.
4. Tree offline / small-to-large: `Tree and Queries`.
