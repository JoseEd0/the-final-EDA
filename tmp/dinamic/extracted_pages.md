

# CS3014___Heavy_Light_Decomposition.pdf - Page 1
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


# CS3014___Heavy_Light_Decomposition.pdf - Page 2
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


# CS3014___Heavy_Light_Decomposition.pdf - Page 3
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


# CS3014___Heavy_Light_Decomposition.pdf - Page 4
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


# CS3014___Heavy_Light_Decomposition.pdf - Page 5
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


# CS3014___Heavy_Light_Decomposition.pdf - Page 6
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


# eda_slides_08_dynamic_graph.pdf - Page 1
Dynamic Graph
CS3014 - Estructura de Datos Avanzados
Luciano A. Romero Calla
lromeroc@utec.edu.pe
2026-1


# eda_slides_08_dynamic_graph.pdf - Page 2
Overview
1. Warming Up
2. The Dynamic Tree Problem
3. Structural Tool: Preferred Paths
4. Heavy-Light Decomposition (HLD)
5. Summary
2 / 16


# eda_slides_08_dynamic_graph.pdf - Page 3
Warming Up
1.
Warming Up
3 / 16


# eda_slides_08_dynamic_graph.pdf - Page 4
Warming Up
Warming Up
Problem
Remember the problem of
Imperial Roads. Now the king
may want to keep a chosen road.
How does this change your
previous solution?
A
B
C
D
E
F
50
70
80
95
20
30
40
50
60
4 / 16


# eda_slides_08_dynamic_graph.pdf - Page 5
The Dynamic T ree Problem
2.
The Dynamic T ree Problem
5 / 16


# eda_slides_08_dynamic_graph.pdf - Page 6
The Dynamic T ree Problem
The Dynamic T ree Problem
The Challenge:Maintain a forest of rooted trees
under:
▶ Structural updates (Link/Cut).
▶ Connectivity queries (FindRoot).
▶ Path aggregates (Min/Max/Sum).
Efficiency Goal
O(logn)amortized time per operation.
r
v
w
link(v, w)?
6 / 16


# eda_slides_08_dynamic_graph.pdf - Page 7
Structural T ool: Preferred Paths
3.
Structural T ool: Preferred Paths
3.1 Internal Representation: Auxiliary Trees
3.2 The Foundation:access(v)
7 / 16


# eda_slides_08_dynamic_graph.pdf - Page 8
Structural T ool: Preferred Paths
Structural T ool: Preferred Paths
We decompose the tree into vertex-disjoint paths based on
access patterns.
▶ Preferred Child:The childcofvsuch that the last
access inv’s subtree was inc’s subtree.
▶ Preferred Edge:Connection to preferred child.
▶ Preferred Path:Maximal chain of preferred edges.
1
2 3
4 5 6
Preferred Path
Normal Edge
8 / 16


# eda_slides_08_dynamic_graph.pdf - Page 9
Structural T ool: Preferred Paths Internal Representation: Auxiliary T rees
Internal Representation: Auxiliary T rees
Each preferred path is stored in an Auxiliary Tree
(Splay Tree).
▶ Order:Keyed bydepthin the original tree.
▶ Left Subtree:Ancestors (smaller depth).
▶ Right Subtree:Descendants (larger depth).
2
1 4
Splay for Path{1,2,4}
3
6
path-parent
9 / 16


# eda_slides_08_dynamic_graph.pdf - Page 10
Structural T ool: Preferred Paths The Foundation:access(v)
The Foundation:access(v)
This operation forces the root-to- v path to become a single
preferred path.
1. Splayvto the root of its Aux-Tree.
2. Discardv’s right child (it becomes a separate path).
3. Climbvia path-parent tow=pp(v).
4. Splaywand makevits newright child.
5. Repeatuntil the represented root is reached.
Effect
Afteraccess(v), nodevis at the
root of a Splay tree containing exactly
the path fromvto the tree root.
10 / 16


# eda_slides_08_dynamic_graph.pdf - Page 11
Heavy-Light Decomposition (HLD)
4.
Heavy-Light Decomposition (HLD)
4.1 HLD: Why the Logarithmic Bound?
4.2 Complexity Proof Sketch
11 / 16


# eda_slides_08_dynamic_graph.pdf - Page 12
Heavy-Light Decomposition (HLD)
Heavy-Light Decomposition (HLD)
To proveO(logn), we use HLD as an analysis tool (not part of the implementation).
Definition
Let size(v)be the number of nodes inv’s subtree.
▶ Edge(u,v)isHeavyif size(v)> 1
2 size(u).
▶ Edge(u,v)isLightotherwise.
Crucial Lemma:Any path from root to node contains at mostlog 2 nlight edges.
12 / 16


# eda_slides_08_dynamic_graph.pdf - Page 13
Heavy-Light Decomposition (HLD) HLD: Why the Logarithmic Bound?
HLD: Why the Logarithmic Bound?
Moving down aLight Edgereduces the subtree size by at least half.
16
9 6
4 4 5
H L (6≤16/2)
Max Light Edges≈log 2(16) =4
13 / 16


# eda_slides_08_dynamic_graph.pdf - Page 14
Heavy-Light Decomposition (HLD) Complexity Proof Sketch
Complexity Proof Sketch
The cost of access(v) is the number of preferred-
edge changes.
Preferred-Child Changes
▶ Light Changes:Accessing a light child.
Onlylognexists on any path.
▶ Heavy Changes:Accessing a heavy child.
Can be many, but theycreatelight edges
for future operations.
Total Cost
By potential function analysis (based on HLD),
the number of heavy-to-light transitions is
bounded. Total:O(logn)amortized.
14 / 16


# eda_slides_08_dynamic_graph.pdf - Page 15
Summary
5.
Summary
15 / 16


# eda_slides_08_dynamic_graph.pdf - Page 16
Summary
Summary
▶ Link-Cut Treessolve dynamic forest problems inO(logn).
▶ Key Subroutine:access(v)handles the path logic.
▶ Analysis:Heavy-Light Decomposition provides the amortized guarantee.
Operation Mechanism Complexity
Access(v) Climbing Aux TreesO(logn)
Link(v, w) Access + pp linkO(logn)
Cut(v) Access + remove leftO(logn)
PathSum(v) Access + Splay AggregateO(logn)
16 / 16


# eda_slides_08_dynamic_graph.pdf - Page 17
Thanks


# eda_slides_08_dynamic_graph.pdf - Page 18
References
References
18 / 16


# eda_slides_08_dynamic_graph.pdf - Page 19
Acknowledgements
Acknowledgements
The course slides are based on the lectures from previous editions and on similar lectures elsewhere.
List of credits: Erick Demaine, Keith Schwarz
19 / 16


# eda_slides_09_dynamic_graph.pdf - Page 1
Dynamic Graph
CS3014 - Estructura de Datos Avanzados
Luciano A. Romero Calla
lromeroc@utec.edu.pe
2026-1


# eda_slides_09_dynamic_graph.pdf - Page 2
Overview
1. Dynamic Connectivity
2. Euler-Tour Trees
2 / 11


# eda_slides_09_dynamic_graph.pdf - Page 3
Dynamic Connectivity
1.
Dynamic Connectivity
1.1 Problem Categorization
1.2 Tree-Structured Solutions: A Contrast
3 / 11


# eda_slides_09_dynamic_graph.pdf - Page 4
Dynamic Connectivity
Dynamic Connectivity
Goal
Maintain an undirected graph subject to updates and
queries.
Operations
▶ insert(u, v): Add edge(u,v).
▶ delete(u, v): Remove edge(u,v).
▶ connected(u, v): Areuandvin the same
connected component?
u
w
v
insert(u,v)
4 / 11


# eda_slides_09_dynamic_graph.pdf - Page 5
Dynamic Connectivity Problem Categorization
Problem Categorization
Fully Dynamic
Admits arbitrary interleavings of edge insertions and deletions.
Incremental / Decremental
Partially dynamic variants restriction toonlyinsertions oronlydeletions.
5 / 11


# eda_slides_09_dynamic_graph.pdf - Page 6
Dynamic Connectivity T ree-Structured Solutions: A Contrast
T ree-Structured Solutions: A Contrast
Before considering general graphs, we resolve dynamic connectivity withinforests.
Metric / Feature Link-Cut Trees (Sleator-Tarjan) Euler-Tour Trees (Henzinger-King)
Primary LayoutHeavy-Light Decomposition Flattened Traversal (Euler Tour)
Aggregate BoundsPath Aggregates (O(logn)) Subtree Aggregates (O(logn))
ImplementationComplex splay-tree interlinking Single balanced BST representation
Edge QueriesDifficult to locate arbitrary edges Trivial lookup via sequence positions
6 / 11


# eda_slides_09_dynamic_graph.pdf - Page 7
Euler-T our T rees
2.
Euler-T our T rees
7 / 11


# eda_slides_09_dynamic_graph.pdf - Page 8
Euler-T our T rees
Euler-T our T ree Mechanics
Concept:Convert a treeTinto a sequential format by tracking its traversal boundary. Every
undirected edge is spanned exactly twice (downward and upward).
▶ Each node visit maps to an index
in a sequence.
▶ Sequence backed by a balanced
BST (e.g., Treap, AVL).
▶ Keys are implicitly defined by
sequential array order.
1
2 3
Sequence:1→2→2→1→3→3→1
8 / 11


# eda_slides_09_dynamic_graph.pdf - Page 9
Euler-T our T rees
Structural Mutations: Link & Cut
By tracking pointers to the first and last occurrence of nodev, we manipulate subtrees inO(logn)
time via basic BST splits and concatenations.
Cut(v)
Removes the subtree rooted atv.
1.Identifyv’s first and last visit in the BST.
2.Split sequence into three:Before-v,
Subtree-v,After-v.
3.ConcatenateBefore-vandAfter-v.
Link(u, v)
Attachesu’s tree as a child ofv.
1.Splitv’s sequence right before its final
occurrence.
2.Splice the entire sequence ofuinto the
gap.
3.Merge everything back into a unified BST.
Beforev Subtree SequenceT v Afterv
split split
9 / 11


# eda_slides_09_dynamic_graph.pdf - Page 10
Euler-T our T rees
Fully Dynamic Connectivity in General Graphs
How do we handle general graphs rather than isolated trees?
▶ Maintain spanning forests of the graph.
▶ Partition edges intolognlevels based on assigned "weights" or frequencies.
▶ Use an Euler-Tour tree to maintain the spanning forest of each level.
▶ Amortized Cost:O(log 2 n)for updates,O(logn)for queries.
LeveliForest (BST) Leveli+1 Forest
edge push
10 / 11


# eda_slides_09_dynamic_graph.pdf - Page 11
Euler-T our T rees
Summary & Lower Bounds
Key Takeaways:
▶ Euler-tour trees are simpler to implement and analyze than Link-Cut trees for aggregate subtree
information.
▶ General graph dynamic connectivity can be achieved inO(log2 n)time using level-partitioned
Euler-Tour trees.
Lower Bounds (Pˇ atraşcu & Demaine):
▶ O(xlogn)update requiresΩ(logn/logx)query time.
▶ O(xlogn)query requiresΩ(lognlogx)update time.
▶ Conclusion:There is an inherent trade-off in dynamic graph structures!
11 / 11


# eda_slides_09_dynamic_graph.pdf - Page 12
Thanks


# eda_slides_09_dynamic_graph.pdf - Page 13
References
References
13 / 11


# eda_slides_09_dynamic_graph.pdf - Page 14
Acknowledgements
Acknowledgements
The course slides are based on the lectures from previous editions and on similar lectures elsewhere.
List of credits: Erick Demaine, Keith Schwarz
14 / 11