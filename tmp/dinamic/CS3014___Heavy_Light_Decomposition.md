# CS3014___Heavy_Light_Decomposition.pdf
Pages: 6

## Page 1
CS3014 - Estructuras de Datos
Avanzadas
Notas de clase 01
Dynamic Graphs - Heavy-light Decomposition
8 de junio de
2026
Prof. V´ ıctor Racs´ o Galv´ an Oyola
1. Descomposiciones de ´ arboles
Hasta ahora hemos tenido algunas ideas para poder realizar consultas espec´ ıficas (Euler Tour
para LCA) o consultas/modificaciones en sub´ arboles (DFS Timestamps) de manera eficiente.
Sin embargo, tambi´ en es posible recibir consultas/modificaciones sobre las aristas/nodos del
camino entre un par de nodos.
Para ello, podemos usar una descomposici´ on de ´ arboles llamadaheavy-light decomposition.
1.1. Heavy-Light Decomposition
Esta descomposici´ on define 2 tipos de arista: pesada (heavy) y liviana (light), de manera que con-
catenaremos las pesadas en caminos y las livianas estar´ an libres. Siempre se define el significado
de arista pesada y las livianas son las aristas restantes.
Figura 1: Heavy-Light Decomposition
Hay 2 definiciones de ambos tipos de arista, lo cual no cambia la complejidad de las opera-
ciones pero s´ ı la estructura de los caminos. Veremos ambas y analizaremos sus complejidades

## Page 2
CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
respectivas.
1.1.1. Mayor que la mitad
Arista pesada:Aquella arista (u, v) tal que el tama˜ no del sub´ arbol deves mayor que la
mitad el tama˜ no del sub´ arbol deu. (2subtree[v]> subtree[u]).
1.1.2. Mayor que sus hermanos
Arista pesada:Aquella arista (u, v) tal que el tama˜ no del sub´ arbol deves mayor que
los tama˜ nos de los sub´ arboles de sus hermanosw, si hay alg´ un empate, se considera solo
una como pesada. (subtree[v]≥subtree[w],∀w∈children[u]\{v}).
Proposici´ on 1
En cualquiera de las dos definiciones, al bajar por una arista liviana (u, v) se cumple que
subtree[v]≤ subtree[u]
2 .
Demostraci´ on.1. Mayor que la mitad: Una arista liviana est´ a definida como (u, v) tal que
2subtree[v]≤subtree[u]→subtree[v]≤ subtree[u]
2 .
2. Mayor que sus hermanos: Una arista liviana (u, v) existe siutiene al menos 2 hijos, por
lo tantosubtree[v]≤subtree[w], dondewes el hijo de la arista pesada (u, w). Entonces,
tendremos que:
subtree[v]≤subtree[w]→2subtree[v]≤subtree[v]+subtree[w]≤subtree[u]−1< subtree[u]
2subtree[v]< subtree[u]
subtree[v]< subtree[u]
2
Gracias a la prueba anterior, podemos deducir que para llegar desde cualquier nodoxhasta
la ra´ ız del ´ arbol tendremos que pasar por un m´ aximo deO(logn) aristas livianas y, como
consecuencia, porO(logn) **caminos de aristas pesadas**.
Si usamos alguna estructura logar´ ıtmica (Segment Tree suele ser el m´ as usado) para almacenar
la informaci´ on de los caminos de aristas pesadas, tendremos una complejidad deO(log2 n) tanto
para consulta como para modificaci´ on.
La implementaci´ on siguiente es de la definici´ on ”Mayor que sus hermanos”, esta realiza la des-
composici´ on luego de un preprocesamiento de los tama˜ nos de sub´ arboles.
1int T = 0;
2
3void DFS(int u, int p = -1){
4subtree[u] = 1;
5for(int i = 0; i < G[u].size(); i++){
6if(G[u][i] == p){
7swap(G[u].back(), G[u][i]);
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 2 de 6

## Page 3
CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
8}
9int v = G[u][i];
10if(v == p) continue;
11DFS(v, u);
12if(subtree[v] > subtree[G[u][0]]){
13swap(G[u][i], G[u][0]);
14}
15subtree[u] += subtree[v];
16}
17if(p != -1){
18G[u].pop_back();
19}
20}
21
22void HLD(int u){
23in[u] = T++;
24for(int v : G[u]){
25par[v] = u;
26nxt[v] = (v == G[u][0] ? nxt[u] : v);
27h[v] = h[u] + 1;
28HLD(v);
29}
30out[u] = T - 1;
31}
Notemos que estaremos guardando algunos arreglos extra:
inyoutson los timestamps de entrada y salida seg´ un el Euler Tour.
nxt[u] es el inicio de la cadena deu(si el nodo pertenece a una arista liviana,nxt[u] =u).
hson las profundidades de cada nodo.
Propiedad 2
El rango [in[nxt[u]], in[u]] contiene todos los nodos desde el inicio de la cadena del nodo
uhasta si mismo. Esto se da porque estamos colocando al nodo de la arista pesada como
primero en la lista de adyacencia.
1.1.3. Consultas
Para consultar informaci´ on sobre un caminou⇝vuno pensar´ ıa en obtener el LCAlde ambos
nodos y luego obtener las respuestas parciales de cada subcaminou⇝lyv⇝l; sin embargo,
es m´ as sencillo hacer la siguiente observaci´ on:
Observaci´ on 3
El LCA deuyvpertenece a una sola cadena, a la cual llegar´ an eventualmente los nodosu
yva medida que asciendan en el ´ arbol. Adem´ as, esta cadena es la m´ as alta a la que podr´ an
llegar sin salirse del caminou⇝v.
Gracias a la observaci´ on anterior, podemos considerar el mover hacia arriba a cada nodo hasta
que estos est´ en en la misma cadena (f´ acilmente identificable, pues esto se dar´ a cuandonxt[u] =
nxt[v]). Entonces, podemos aplicar el algoritmo greedy de subir lo m´ as que se pueda a aquel que
tenganxtcon menorh.
La siguiente implementaci´ on est´ a hecha para consultar el m´ aximo valor de alg´ un nodo en el
caminoa⇝b, dado que tenemos un segment tree sobre el Euler Tour del ´ arbol.
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 3 de 6

## Page 4
CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
1int path(int a, int b){
2int res = -2e9;
3while(nxt[a] != nxt[b]){
4if(h[nxt[a]] < h[nxt[b]]) swap(a, b);
5res = max(res, query(in[nxt[a]], in[a]));
6a = par[nxt[a]];
7}
8if(h[a] > h[b]) swap(a, b);
9res = max(res, query(in[a], in[b]));
10return res;
11}
Es sencillo notar que el bucle se ejecutar´ a hasta que est´ en ambos nodos en la misma cadena,
para lo cual realizamos una consulta extra para cubrir dicho rango de nodos. La complejidad de
este algoritmo es deO(log 2 n).
1.1.4. Modificaciones
Para realizar modificaciones sobre un camino podemos considerar el mismo algoritmo de consulta
pero aplicando las actualizaciones:
1void changePath(int a, int b, int w){
2while(nxt[a] != nxt[b]){
3if(h[nxt[a]] < h[nxt[b]]) swap(a, b);
4update(in[nxt[a]], in[a], w);
5a = par[nxt[a]];
6}
7if(h[a] > h[b]) swap(a, b);
8update(in[a], in[b], w);
9return res;
10}
Cuya complejidad ser´ a la misma deO(log 2 n). Por otro lado, si queremos modificar sobre un
sub´ arbol, podemos usar el mismo Segment Tree (si se trabaja sobre las mismas propiedades) y
modificar el rango [in[u], out[u]]. Este segundo tipo de modificaci´ on tomar´ aO(logn).
Podemos notar que esta forma de implementaci´ on es bastante flexible y potente.
Nota:Si las modificaciones e informaci´ on son sobre las aristas y no sobre los nodos, podemos
considerar que la posici´ on del nodourepresenta a la arista (par[u], u) y realizar las modificaciones
correspondientes a las funciones.
1.1.5. Problemas para implementar
Query on a tree
Subtrees And Paths
Can you answer these queries VII
Queries on tree again!
1.2. Extendiendo el HLD: Small to Large Trick
Con Heavy-Light Decomposition consideramos asignar tipos a las aristas, definiendo dichos tipos
para que se cumplan ciertas condiciones sobre el camino desde la raiz de un ´ arbol hasta cada
nodou.
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 4 de 6

## Page 5
CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
Consideremos ahora el caso en el que se nos da un ´ arbolT, sobre el cual nosotros queremos
responder a cierta informaci´ on de cada uno de sus nodosu, considerando que dicha informaci´ on
depende del sub´ arbol deu.
Es importante recordar la definici´ on de arista pesada y ligera, pues debido a esta se da que existen
una cantidad deO(logn) aristas ligeras en el camino desde la ra´ ız del ´ arbol hasta cualquier nodo
u.
Entonces, si pudi´ eramos procesar cada nodo dicha cantidad de aristas ligeras y una vez por cada
cadena pesada, tendr´ ıamos una complejidad deO(nlogn).
Es ahora que podemos plantear la siguiente idea:
Si procesamos con un DFS cada nodo, considerando que no borraremos la informaci´ on del
sub´ arbol al cual accedemos mediante una arista pesada y aplicamos el mismo criterio en la
recursi´ on, el trabajo hecho sobre cada nodo esO(logn).
Para que sea m´ as sencillo de ver, propondremos el pseudoc´ odigo:
1solve(u, keep):
2bigChild = -1
3for v in G[u]:
4if v is pi[u]: continue
5if (u, v) is light-edge:
6solve(v, false) // Resolvemos cada hijo de arista ligera pero sin guardar
la informaci´ on,→
7else:
8bigChild = v
9if bigChild != -1:
10solve(bigChild, true) // Resolvemos el hijo de arista pesada guardando la
informaci´ on,→
11addInfo(u) // Agregamos la informaci´ on de todos los hijos de arista ligera y u
12// Resolver el nodo u con la informaci´ on disponible
13if not keep:
14removeInfo(u) // Quitamos la informaci´ on de todos los hijos de u y u
Si analizamos el proceso, es f´ acil notar que:
1. Si bajamos por una arista ligera, la informaci´ on es procesada 1 vez y borrada luego de ello.
2. Si bajamos por una arista pesada, la informaci´ on es procesada 1 vez y se mantiene.
Debido a lo anterior, como borramos la informaci´ on del nodoupor cada arista ligera, tendremos
que reponerla la misma cantidad de veces, en total procesaremos la informaci´ on del nodou
O(logn) veces. Finalmente, la complejidad ser´ a deO(nlogn) inserciones y eliminaciones de
informaci´ on.
1.2.1. Implementaci´ on
Se puede plantear la implementaci´ on del pseudoc´ odigo en base al preprocesamiento del Heavy-
Light Decomposition que ya tenemos, con el cual coloc´ abamos al hijo pesado en la primera
posici´ on de la lista de adyacencia y elimin´ abamos al padre.
1void DFS(int u, int p = -1){
2subtree[u] = 1;
3for(int i = 0; i < G[u].size(); i++){
4if(G[u][i] == p){
5swap(G[u].back(), G[u][i]);
6}
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 5 de 6

## Page 6
CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
7int v = G[u][i];
8if(v == p) continue;
9DFS(v, u);
10if(subtree[v] > subtree[G[u][0]]){
11swap(G[u][i], G[u][0]);
12}
13subtree[u] += subtree[v];
14}
15if(p != -1){
16G[u].pop_back();
17}
18}
19
20void add(int u, int val, int start){
21if(val == 1) agregarInfo(u);
22else quitarInfo(u);
23for(int i = start; i < G[u].size(); i++){
24add(G[u][i], val, 0); // Solo debemos restringir en el primer nivel
25}
26}
27
28void solve(int u, int keep){
29for(int i = 1; i < G[u].size(); i++){
30solve(G[u][i], 0);
31}
32if(!G[u].empty()) solve(G[u][0], 1);
33add(u, 1, 1);
34// Resolver con la informaci´ on disponible
35if(!keep){
36add(u, -1, 0);
37}
38}
Aprovechando la naturaleza de la lista de adyacencia, planteamos la funci´ on ‘add‘ con una
variablestartque define si ignoramos o consideramos el hijo pesado, de manera que solo debemos
restringir las aristas del primer nivel de descendientes (hijos directos), as´ ı que en la recursi´ on
deberemos llamar para cada hijo constart= 0.
1.2.2. Problemas para practicar
Summing in a Tree
Lomsat gelral
Tree Requests
Tree and Queries
Referencias
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 6 de 6
