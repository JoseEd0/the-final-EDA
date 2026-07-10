# Ejercicios flash - final EDA

Seleccion de emergencia basada en Racso, slides, soluciones previas y lista final del profesor.

## 0. Seleccion de emergencia

Con 1 hora, no conviene intentar aprender todo linealmente. Hay que aprender patrones que se reciclan en preguntas teoricas. Si el examen trae 3 preguntas, una de strings confirmada, la prioridad real es: (1) suffix array/LCP y sus aplicaciones; (2) arboles estaticos con LCA/HLD; (3) dynamic connectivity offline o dynamic forest conceptual; (4) integer como respuesta teorica de modelos, predecessor y sorting.

La forma de responder en papel siempre debe ser: identificar objeto fijo/dinamico, escoger estructura, decir que guarda, transformar la consulta, probar el invariante y cerrar complejidad. Si solo escribes el nombre de la estructura, te faltan puntos.

## 1. Static RMQ - Sparse Table

Problema tipo: arreglo fijo A, muchas consultas min(l,r). Si no hay updates y la operacion es idempotente como min/max/gcd, sparse table es mejor que segment tree para teoria: preprocess O(n log n), query O(1).

Definicion: st[k][i] guarda la respuesta del bloque A[i..i+2^k-1]. Transicion: st[k][i]=op(st[k-1][i], st[k-1][i+2^{k-1}]). Para query de longitud len, k=floor(log2 len). Se combinan dos bloques de longitud 2^k: inicio y final. Para rango cerrado [l,r], len=r-l+1 y ans=op(st[k][l], st[k][r-2^k+1]). Para rango medio abierto [l,r), len=r-l y ans=op(st[k][l], st[k][r-2^k]).

Correctitud: cada st es correcto por induccion sobre k porque el bloque de longitud 2^k se parte en dos mitades de 2^{k-1}. En una query, los dos bloques cubren todo el rango; si se solapan no importa porque min(x,x)=x. Complejidad: O(n log n) memoria y preprocess, O(1) query.

Pseudo: build logs; st[0][i]=A[i]; for k 1..LG: for i valid: st[k][i]=min(st[k-1][i],st[k-1][i+2^{k-1}]); query(l,r): len=r-l+1; k=lg[len]; return min(st[k][l],st[k][r-2^k+1]).

## 2. Suffix Array, Rank, LCP, Kasai

Sufijo: S[i..n-1]. Prefijo: S[0..j] o prefijo de cualquier string. Suffix array SA ordena las posiciones i por el texto S[i..]. rank[i] es el inverso: posicion del sufijo i dentro de SA. LCP[i] es el longest common prefix entre sufijos vecinos SA[i-1] y SA[i].

Manber-Myers: ordena por longitudes 1,2,4,8,... Si ya conozco el rank de prefijos de longitud len, el prefijo de longitud 2*len de sufijo i queda representado por el par (rank[i], rank[i+len]). Ordenar esos pares da el nuevo orden. Pares iguales reciben mismo rank. Esto funciona por induccion porque comparar dos mitades ordenadas equivale a comparar el bloque completo.

Kasai: construye LCP en O(n) despues de SA. Para cada posicion i en el texto, miro el sufijo vecino anterior j=SA[rank[i]-1]. Si el LCP anterior era h, al pasar a i+1 el LCP baja a lo mucho en 1, asi que empiezo en max(h-1,0) y avanzo mientras coincidan caracteres. Esto evita recomparar todo.

Formula clave: si rank[i]=a < b=rank[j], entonces lcp(i,j)=min(LCP[a+1..b]). Por eso se hace RMQ sobre LCP. Esta formula aparece en comparar subcadenas, longest common substring, ordenar substrings y periodicidad.

## 3. Busqueda y conteo de subcadenas

Problema tipo: texto fijo T y muchos patrones P. Todos los sufijos que empiezan con P aparecen consecutivos en SA. Se hacen dos binary searches: L = primer sufijo >= P; R = primer sufijo que ya no tiene prefijo P. Si L=R no aparece. Si no, ocurrencias = R-L y posiciones = SA[L..R-1].

Para conteo solo respondes R-L. Para busqueda Yes/No basta revisar si L existe y has_prefix(T[SA[L]..],P). Complejidad simple: construir SA O(n log n), cada patron O(|P| log n). Si el examen pide optimizar, se menciona LCP/RMQ para acelerar comparaciones, pero la idea teorica central es el intervalo contiguo.

Correctitud: orden lexicografico agrupa strings con mismo prefijo porque cualquier sufijo con prefijo P queda entre P y el primer string mayor que todos los que empiezan con P. No puede haber un sufijo sin prefijo P dentro del bloque, porque romperia la propiedad de orden.

## 4. Subcadenas distintas, LCS y ordenar subcadenas

Subcadenas distintas: cada subcadena es prefijo de algun sufijo. El sufijo SA[i] aporta n-SA[i] prefijos, pero los primeros LCP[i] ya aparecieron con el sufijo anterior. Respuesta: n(n+1)/2 - sum LCP[i].

Longest common substring de A y B: construye S=A#B$ con separadores que no aparecen. En SA, mira pares vecinos de origen distinto; el mayor LCP entre ellos es una subcadena comun maxima. Si piden lexicograficamente menor en empate, entre candidatas de misma longitud compara por rank/posicion lexicografica.

Ordenar subcadenas (l1,r1) vs (l2,r2): len1, len2. x=min(lcp(l1,l2),len1,len2) usando RMQ sobre LCP. Si x<minLen, compara S[l1+x] y S[l2+x]. Si una se acaba, la mas corta es menor. Si son iguales como palabra, desempata por el par original (l,r) si el statement lo pide. Complejidad de comparacion O(1) despues de SA+LCP+RMQ; ordenar q substrings O(q log q).

## 5. Imperial Roads - MST forzando una arista

Problema: grafo conectado ponderado. Cada query exige incluir una arista e=(u,v,w). Queremos costo minimo de un arbol conexo que incluya e. Solucion: calcula MST T con peso W. Si agregas e a T, aparece un unico ciclo: e + camino_T(u,v). Para volver a arbol y minimizar costo, quitas la arista mas pesada de ese camino. Respuesta W + w - maxEdgePath(u,v).

Estructura para maxEdgePath: root al MST y binary lifting guardando up[v][j] y mx[v][j] = maximo peso al subir 2^j. Para query, igualas profundidades y subes ambos nodos acumulando maximos hasta LCA.

Correctitud: por propiedad del ciclo del MST, en cualquier ciclo se puede eliminar una arista maxima sin empeorar. Al forzar e, todos los arboles que contienen e se obtienen rompiendo ese ciclo; quitar la maxima minimiza el nuevo peso. Complejidad: Kruskal O(m log m), preprocess O(n log n), query O(log n).

## 6. Fools and Roads - contar caminos que usan cada arista

Problema: arbol y muchas consultas (u,v). Para cada arista, contar cuantas rutas u-v pasan por ella. No recorras cada camino. Usa diferencia en arbol: cnt[u]++, cnt[v]++, cnt[lca(u,v)]-=2. Luego haces DFS postorder; al acumular sumSub[x], ese valor es cuantas rutas cruzan la arista parent[x]-x.

Por que funciona: una ruta u-v sube desde u al lca y baja a v. Al poner +1 en extremos y -2 en el lca, el flujo acumulado sube exactamente por las aristas del camino y se cancela fuera del camino. Complejidad: preprocess LCA O(n log n), cada query O(log n), DFS O(n).

## 7. Practica profesor - subsecuencia en camino de arbol

Enunciado resumido: cada vertice tiene una letra. Query U,V,S. Se forma T con las letras del camino simple U->V en orden. Decidir si S es subsecuencia de T.

Solucion de examen: HLD descompone el camino U->V en O(log n) segmentos de cadenas pesadas. En el arreglo base de HLD, para cada caracter c guardo la lista ordenada de posiciones donde aparece c. Para consumir S, recorro los segmentos del camino en el orden real: primero U->LCA (direccion hacia arriba, o sea posiciones decrecientes dentro de cada chain), luego LCA->V (direccion hacia abajo). En cada segmento intento ubicar el siguiente caracter pendiente con binary search en la lista de ese caracter, respetando limites y direccion. Si aparece, avanzo el puntero en el segmento y consumo el caracter; si no aparece, paso al siguiente segmento. Si consumo todo S, responde YES.

Correctitud: HLD no cambia el orden del camino; solo lo parte en segmentos contiguos. Las listas por caracter encuentran la primera aparicion valida dentro del segmento. Consumir siempre la aparicion mas temprana es optimo para subsecuencia: deja el mayor sufijo posible del camino para los caracteres restantes. Complejidad: O(log n) segmentos y cada caracter consumido una vez con busqueda O(log n): O((|S|+log n)log n) por query, espacio O(n+26n conceptual).

## 8. Practica profesor - ordenar nodos de trie

Cada nodo representa la cadena formada desde la raiz hasta ese nodo. Para ordenar lexicograficamente todos los nodos, haz DFS desde la raiz visitando primero el nodo actual y luego sus hijos en orden de caracter. Si root representa cadena vacia, va primero.

Por que funciona: en orden lexicografico, una palabra aparece antes que cualquier extension propia; por eso visitamos el nodo antes que sus hijos. Entre ramas con primer caracter distinto, el caracter menor debe aparecer antes; por eso hijos ordenados. Si hay alfabeto lowercase, se puede iterar 'a'..'z' y queda O(n sigma) o O(n) si sigma=26 constante. Si hijos vienen desordenados, ordenar listas cuesta O(n log sigma) o O(n log n) peor, aun menor que O(n^2).

## 9. Practica profesor - caminos con peso <= C en arbol

Interpretacion natural: contar pares de vertices (u,v) cuyo camino tiene peso total <= C. En un arbol hay unico camino. La solucion subcuadratica clasica es centroid decomposition.

En cada centroid c, recolecta distancias desde c hacia los nodos de cada subarbol. Con una lista global D de distancias <= C, ordena D y cuenta pares con suma <= C usando two pointers. Eso cuenta caminos que pasan por c. Pero pares dentro del mismo subarbol no deberian contarse en este nivel, asi que para cada subarbol se resta el conteo interno de sus distancias. Luego recursas en cada componente al quitar c.

Correctitud: todo camino tiene un primer centroid de la recursion que separa sus endpoints o es uno de ellos; se cuenta exactamente en ese nivel y no en otro. Complejidad: cada nivel procesa listas con sort/two pointers; O(n log^2 n) simple, O(n log n) si se optimiza merge/sort. En papel O(n log^2 n) ya cumple menor que O(n^2).

## 10. Dynamic connectivity offline - segment tree sobre tiempo + rollback DSU

Problema tipo: operaciones add edge, remove edge, query connected/component sum. Si puedes leer todas las operaciones antes de responder, es offline. Convierte cada arista en intervalos de vida [l,r] donde esta activa. Inserta cada intervalo en un segment tree de tiempo.

DFS sobre el segment tree: al entrar a un nodo, aplicas union de todas las aristas asignadas a ese intervalo. En hoja t, el DSU contiene exactamente las aristas activas en t, respondes queries. Al salir, haces rollback al snapshot previo. DSU rollback guarda en stack los cambios de parent/size/sum. No uses path compression porque es dificil deshacer; union by size basta.

Correctitud: un intervalo de vida se coloca en nodos que cubren exactamente sus tiempos activos. El camino raiz-hoja t contiene exactamente los intervalos que cubren t. Rollback restaura el estado para no contaminar otra rama. Complejidad: cada intervalo entra en O(log q) nodos; O((m log q) alpha/log n segun DSU sin compression) y memoria O(m log q).

## 11. Dynamic forest conceptual - Euler-tour tree vs Link-cut tree

Si el grafo dinamico siempre es bosque y piden link/cut/connected: Euler-tour tree representa cada arbol por su tour Euler dentro de un BST balanceado. Link y cut se vuelven split/merge de secuencias. Es natural para conectividad, size y agregados de componente/subarbol.

Si piden agregados en camino de un arbol dinamico: Link-cut tree. Idea: partir el arbol en preferred paths, cada path se guarda en un splay auxiliar. access(v) convierte el camino raiz-v en una preferred path; con makeroot/access puedes exponer u-v y leer el agregado en la raiz del splay. Operaciones link/cut/path query O(log n) amortizado.

Regla rapida: arbol fijo + path query -> HLD. Arbol cambia + path query -> Link-cut. Arbol cambia + componente/subtree -> Euler-tour tree. Grafo general offline -> rollback DSU. Solo inserciones -> DSU.

## 12. Integer - predecessor y modelos

Problema predecessor: mantener conjunto S de enteros de w bits; insert/delete/member/predecessor/successor. Variables: n numero de llaves, u=2^w universo, w bits por palabra. En modelo comparaciones, BST da O(log n). En word RAM puedes usar bits.

vEB: divide universo en high/low de tamano sqrt(u). Guarda min,max, summary de clusters no vacios y clusters. Recurrencia T(u)=T(sqrt(u))+O(1)=O(log log u)=O(log w). Problema: espacio Theta(u) si no se comprime.

Y-fast: combina hashing de prefijos (estilo X-fast) con buckets balanceados de tamano O(w). Tiene espacio O(n) y operaciones esperadas/amortizadas O(log w)=O(log log u). Respuesta teorica segura cuando el universo es grande y no quieres espacio u.

Fusion tree: en word RAM fuerte, usa branching alto B=w^{1/5}; dentro de un nodo compara varias llaves en paralelo con sketches de bits criticos. Altura O(log_w n), predecessor teorico rapido. Menciona condicion de modelo: algunas versiones usan multiplicacion; en AC0 RAM hay cuidado.

## 13. Integer sorting - counting/radix/signature

La cota Omega(n log n) es solo para comparaciones. Si las llaves son enteros puedes mirar digitos. Counting sort cuesta O(n+U) para universo U del digito. Radix sort parte cada llave en digitos de b bits y hace counting estable por cada digito. Si b=Theta(log n), cada pasada cuesta O(n) porque hay n^{Theta(1)} valores; numero de pasadas = ceil(w/b).

Si w=O(log n), radix/counting da O(n). Si w es mayor, signature sort reduce llaves a firmas/hashes de O(log n) bits por niveles y luego usa packed/radix. Para examen suele bastar explicar: romper comparaciones usando representacion binaria, elegir digitos de log n bits, estabilidad y complejidad O(n*w/log n).

## 14. Mini bloque de metricas por si aparece

Una metrica d cumple: no negatividad d(x,y)>=0, identidad d(x,y)=0 iff x=y, simetria d(x,y)=d(y,x), desigualdad triangular d(x,z)<=d(x,y)+d(y,z). Suma de metricas: si d1 y d2 son metricas, d3=d1+d2 es metrica porque cada propiedad se preserva sumando; triangular sale de d1(x,z)+d2(x,z)<=d1(x,y)+d1(y,z)+d2(x,y)+d2(y,z).

Para verificar funciones: cuadrados suelen fallar triangular, por ejemplo d(0,2)=4 pero d(0,1)+d(1,2)=2. |x-y|, L1, L2, L_infty y pesos positivos de L1 son metricas. sqrt(|x-y|) es metrica porque sqrt(a+b)<=sqrt(a)+sqrt(b). min(1,|x-y|) tambien es metrica por truncamiento subaditivo. Funciones con mezcla |x-y|+|f(x)-f(y)| son metricas si f no destruye identidad; como incluye |x-y|, identidad queda.
