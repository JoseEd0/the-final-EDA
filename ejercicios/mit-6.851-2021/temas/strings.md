# Strings

## Fuentes MIT

- Lecture L16: string data structures.
- En Spring 2021 no hay problem set publico separado para strings en la lista oficial; por eso esta hoja usa ejercicios propios alineados con L16 y con tus slides.

## Fuentes locales EDA

- `../../statics and strings/CS3014___Strings.pdf`
- `../../statics and strings/Estructuras_de_Datos_Avanzadas___Strings_I.pdf`
- `../../statics and strings/Estructuras_de_Datos_Avanzadas___Strings_II.pdf`

## Que debes poder escribir en papel

1. Definiciones:
   - sufijo, prefijo, subcadena, orden lexicografico, sentinela.
   - suffix array `SA`: permutacion de posiciones con sufijos ordenados.
   - `LCP[i]`: longest common prefix entre sufijos consecutivos en `SA`.
2. Pattern matching con texto fijo:
   - construir `SA`.
   - buscar patron `P` con dos binary searches sobre sufijos.
   - ocurrencias quedan en intervalo contiguo de `SA`.
   - tiempo `O(|P| log n)` directo; con LCP/RMQ se puede mejorar.
3. Conteo de subcadenas distintas:
   - total de subcadenas `n(n+1)/2`.
   - duplicadas capturadas por `sum LCP`.
   - respuesta `n(n+1)/2 - sum_i LCP[i]`.
4. Longest common substring:
   - concatenar `A#B$`.
   - construir `SA` y `LCP`.
   - maximo `LCP` entre sufijos consecutivos que vienen de strings distintos.
5. Manber-Myers:
   - ordenar por clases de equivalencia de longitud `2^k`.
   - cada iteracion duplica longitud.
   - tiempo `O(n log n)` y espacio `O(n)` si se guarda solo nivel actual.
6. DC3:
   - separar posiciones mod 3.
   - ordenar recursivamente `S1 union S2`.
   - deducir `S0`.
   - merge con comparaciones de caracteres y ranks.
   - recurrencia `T(n)=T(2n/3)+O(n)=O(n)`.
7. SA-IS:
   - clasificar sufijos tipo `S` y `L`.
   - LMS son cambios `L -> S`.
   - ordenar LMS y luego inducir orden de todos los sufijos.

## Problemas para resolver

1. STR1: dado `S`, construir `SA` y `LCP` manualmente para una cadena corta.
2. STR2: contar ocurrencias de un patron usando intervalo en `SA`.
3. STR3: contar subcadenas distintas con `SA + LCP`.
4. STR4: longest common substring entre dos strings.
5. STR5: explicar Manber-Myers con pseudocodigo y complejidad.
6. STR6: explicar la idea de DC3 o SA-IS sin implementar todos los detalles.

## Respuesta tipo examen

Si preguntan strings, casi siempre debes cerrar con:

- estructura usada: `SA`, `LCP`, `RMQ sobre LCP` si aplica.
- por que las ocurrencias forman intervalo contiguo.
- complejidad de construccion y consulta.
- prueba corta basada en orden lexicografico de sufijos.
