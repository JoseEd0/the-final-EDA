# Codeforces 963D - Frequency of String

- Link: https://codeforces.com/problemset/problem/963/D
- Tema: strings, ocurrencias de patrones, Aho-Corasick, suffix structures.
- Relevancia: maxima porque strings esta confirmado.

## Resumen del enunciado

Para un texto fijo y muchas consultas `(k, patron)`, se pide la minima longitud de una subcadena del texto que contenga al patron al menos `k` veces. Si el patron aparece menos de `k` veces, la respuesta es `-1`.

## Idea central

Primero obtener todas las posiciones de ocurrencia de cada patron. Luego, para cada patron, si sus ocurrencias ordenadas son `p_1, ..., p_t`, la minima ventana con `k` ocurrencias se obtiene revisando pares `p_i` y `p_{i+k-1}`. La longitud candidata considera el inicio de la primera ocurrencia y el final de la ultima.

## Ver solucion teorica

La solucion completa esta en `../latex/soluciones_teoria_racso.tex`.
