
# FILE: CS3014___Strings.pdf (23 pages)


## CS3014___Strings.pdf - page 1

CS3014 - Estructuras de Datos
Avanzadas
Notas de clase 01
Strings
31 de mayo
de 2026
Prof. V´ ıctor Racs´ o Galv´ an Oyola
1. Notaci´ on
Sea Σ un conjunto ordenado de s´ ımbolos (a partir de ahora,caracteres), el cual llamaremos
alfabeto. Diremos que una secuencia finitaSque consiste de caracteres de Σ es unacadenasobre
el alfabeto Σ. Por convenci´ on, denotaremos la cadena vac´ ıa comoε. Adem´ as, denotaremos la
longitud deSpor|S|, eli-´ esimo caracter (0≤i <|S|) deSporS[i] y una subcadena que
consiste de la concatenaci´ on de los caracteres deSdesde la posici´ onihasta la posici´ onjpor
S[i, j] para cualquier par (i, j) tal que 0≤i≤j <|S|. Denotaremos por Sub(S) al conjunto de
todas las subcadenas deS.
Definici´ on 1 (Prefijo y sufijo de una cadena)
Elprefijode una cadenaSque termina en la posici´ onies la subcadenaS[0, i] y ser´ a denotada
por Pref(S, i).
Elsufijode una cadenaSque comienza en la posici´ onies la subcadenaS[i,|S| −1] y ser´ a
denotada por Suf(S, i).
Un prefijo o sufijo deSes llamadopropiosi su longitud esestrictamente menorque la
deS.
La concatenaci´ on de las cadenasUyVest´ a denotada porU·VoU V. La misma notaci´ on
se extiende para concatenaci´ on de caracter–cadena y caracter–caracter. Para un enterok≥1,
denotamos la concatenaci´ on dekcopias de una cadenaUcomoU k. Adem´ as, la concatenaci´ on
de las cadenasS 1, S2, . . . , Sm se denota como
mQ
i=1
Si.
Denotaremos el conjunto que contiene todas las cadenas de longitud finita sobre el alfabeto Σ
como Σ∗.
Dadas dos cadenasSyT, suprefijo en com´ un m´ as largo(LCP) es la cadenaP∈Σ ∗ m´ as larga
tal queS=P·UyT=P·Vpara alg´ un par de cadenasU, V∈Σ ∗. Lo denotaremos por
LCP(S, T) =P.
Asumiremos que el alfabeto Σ contiene un caracter llamadosentinela($) que precede a todos
los dem´ as s´ ımbolos de Σ y ocurre exclusivamente al final de cada cadena de entrada. Tener un
sentinela simplifica la comparaci´ on de sufijos debido a que evita el tener cadenas vac´ ıas.
Definici´ on 2 Orden lexicogr´ afico
Sea≺el orden total sobre Σ inducido por el orden de sus elementos. Este orden puede ser
extendido a las cadenasS, T∈Σ ∗. Diremos queSes lexicogr´ aficamente menor queTsi se
cumple alguna de las siguientes dos condiciones:
Ses un prefijo propio deT.

## CS3014___Strings.pdf - page 2

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
SyTdifieren en una posici´ on. Seapla menor posici´ on en la que difieren, entonces
S[p]≺T[p].
Por convenci´ on, usaremos comparaci´ on lexicogr´ afica al comparar dos cadenas.
2. Suffix Array
El suffix array es una estructura de indexing cuya caracter´ ıstica principal es la poca cantidad
de memoria que usa a comparaci´ on de las dem´ as estructuras. Consideraremos que tenemos una
cadena de entradaScon longitudn. Esta se define de la siguiente manera:
Definici´ on 1 (Suffix Array)
Dada una cadenaSde longitudn, el suffix array asociado aSes la permutaci´ onAde
tama˜ nontal que:
Suf(S, Ai)≺Suf(S, A i+1),∀i= 0, . . . ,(n−2)
Por lo tanto, requeriremos exactamentenenteros para esta estructura, lo cual es una ventaja
en muchos escenarios.
2.1. Manber y Myers
Manber y Myers fueron quienes propusieron el suffix array por primera vez en [3]; adem´ as
dise˜ naron un algoritmo para su construcci´ on en tiempoO(nlogn).
La idea para la construcci´ on del suffix array enO(nlogn) podr´ ıa decirse que est´ a basada en los
Sparse Tables, as´ ı que primero revisaremos un enfoque que nos permita comparar subcadenas
deSde manera eficiente.
Consideremos que existe una funci´ onσ: Sub(S)→Rque mapee cada subcadena diferente de
Sa un real distinto, entonces es sencillo notar que requeriremos almacenar a lo muchoO(n 2)
reales diferentes para ello, lo cual no es posible para valores muy grandes den.
Si decidimos particionar Sub(S) por longitudℓde cada subcadena (denotemos esto por Sub ℓ(S)),
requeriremosO(n) reales diferentes para un mapeoσ ℓ : Sub ℓ(S)→R, lo cual s´ ı se puede
almacenar. Para no requerir la misma cantidad de memoria que el escenario deσ, vamos a
seleccionar solo un conjunto reducido deℓque nos permita comparar subcadenas en tiempo
eficiente.
Lema 2
Dada la cadenaSde longitudn, basta con elegir el subconjuntoL={2 k : 1≤2 k ≤
n}y los mapeosσ ℓ para todoℓ∈ Lpara poder comparar subcadenas enO(1) con un
preprocesamiento deO(nlogn).
El proceso ser´ ıa el siguiente:
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 2 de 23

## CS3014___Strings.pdf - page 3

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
Algoritmo 1:Construir-Mapeos(S, n)
1k←1 +⌊log 2 n⌋;
2Seamapeo[k][n] un arreglo de enteros ;
3p← {0, . . . , n−1};
4OrdenarpporS i creciente ;
5Asignarmapeo[0] de acuerdo ap;
6parad←1ak−1hacer
7v← {(mapeo[d−1][i], mapeo[d−1][i+ 2 d−1]) : 0≤i≤n−2 d};
8Filtrarppara quedarnos con solo losi∈[0, n−2 d] ;
9Ordenarpporvcreciente usando Radix sort ;
10Asignarmapeo[d] de acuerdo ap;
11devolvermapeo
Sin embargo, es posible realizar una peque˜ na mejora para no necesitar usar Radix sort, para
ello debemos realizar la siguiente observaci´ on:
Observaci´ on 3
El estado depal llegar a la iteraci´ ondya contiene loside dicho nivel ordenados por su
segunda componente env.
La observaci´ on anterior nos da la idea de que podemos iterar sobrepal momento de filtrar los
idel nivel ysolo filtrar aquellos que sean mayores o iguales que2 d−1 y colocarlos como
i−2 d−1 en su posici´ on correcta. Luego de ello, ordenaremosppor el valor demapeo[d−1][i] de
maneraestable(usando counting sort).
Algoritmo 2:Construir-Mapeos(S, n)
1k←1 +⌊log 2 n⌋;
2Seamapeo[k][n] un arreglo de enteros ;
3p← {1, . . . , n};
4OrdenarpporS i creciente ;
5Asignarmapeo[0] de acuerdo ap;
6parad←1ak−1hacer
7Filtrarppara quedarnos con solo losi∈[2 d−1, n−2 d−1] mapeados ai−2 d−1 ;
8Ordenarppormapeo[d−1][i] creciente de manera estable (usando Counting sort) ;
9Asignarmapeo[d] de acuerdo ap;
10devolvermapeo
Veamos un ejemplo para visualizar bien el proceso:
Ejemplo 4
Sea
S=mississippi, n= 11, k= 4.
Luego de ordenar los sufijos seg´ unSi obtenemos:
p= (1,4,7,10,0,8,9,2,3,5,6).
Niveld= 0
El mapeo inicial queda dado por:
i 0 1 2 3 4 5 6 7 8 9 10
mapeo[0] 1 0 3 3 0 3 3 0 2 2 0
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 3 de 23

## CS3014___Strings.pdf - page 4

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
Niveld= 1
Se filtra el vectorpy mapeamosi7→i−2 d−1 =i−1:
(1,4,7,10,8,9,2,3,5,6)− →(0,3,6,9,7,8,1,2,4,5).
Luego de ordenar de manera estable seg´ unmapeo[0], se obtiene:
p= (7,1,4,0,9,8,3,6,2,5).
El nuevo mapeo es:
i 0 1 2 3 4 5 6 7 8 9 10
mapeo[1] 2 1 6 5 1 6 5 0 4 3 ?
Niveld= 2
Se filtrapy mapeamosi7→i−2 d−1 =i−2:
(7,4,9,8,3,6,2,5)− →(5,2,7,6,1,4,0,3).
Luego de ordenar de manera estable seg´ unmapeo[1], se obtiene:
p= (7,1,4,0,6,3,5,2).
El nuevo mapeo es:
i 0 1 2 3 4 5 6 7 8 9 10
mapeo[2] 2 1 6 4 1 5 3 0 ? ? ?
Niveld= 3
Se filtrapy mapeamosi7→i−2 d−1 =i−4:
(7,4,6,5)− →(3,0,2,1).
Luego de ordenar de manera estable seg´ unmapeo[2], se obtiene:
p= (1,0,3,2).
El mapeo final es:
i 0 1 2 3 4 5 6 7 8 9 10
mapeo[3] 1 0 3 2 ? ? ? ? ? ? ?
Entonces, es posible ordenar todos los sufijos deSenO(nlogn) si usamos la funci´ oncompare
como subrutina parastd::sortmanejando adecuadamente las longitudes diferentes en los su-
fijos.
A pesar de que el algoritmo anterior nos permite construir el suffix array enO(nlogn), requiere
O(nlogn) de memoria, lo cual no es tan bueno para la eficiencia.
Ahora, ser´ ıa muy bueno para nosotros si consigui´ eramos definirσ 2m con 2 m ≥ny m´ ınimo
posible, ya que con dichos mapeos podremos comparar absolutamente todos los sufijos entre s´ ı
(bastar´ ıa con compararσ2m de cada sufijo).
Ya que no podemos extender la cadena arbitrariamente esperando que algo as´ ı funcione, no lo
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 4 de 23

## CS3014___Strings.pdf - page 5

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
haremos ... ¿o s´ ı? En realidad es posible extenderSusando 2 m −1 caracteres sentinelas $. Esta
´ ultima condici´ on es necesaria para representar cadenas que originalmente no estar´ ıan completas
(en cuyo caso, la relaci´ on cuando una es prefijo de otra se establece correctamente ya que $
precede a cualquierc∈Σ), as´ ı que el caracter $ funciona como un separador.
De esta manera, cuando construyamos los mapeos, podemos simplemente quedarnos con el nivel
anterior y al final de toda la ejecuci´ on filtrar las posiciones originales deS. Esto nos reduce la
memoria usada aO(n), pero con una constante bastante alta.
Para reducir la memoria usada, podemos aprovechar la propiedad del sentinela como menor
lexicogr´ afico que todo el alfabeto, de manera que en vez de agregar 2m−1 sentinelas, agregaremos
solo uno pero consideraremos las subcadenas comoc´ ıclicascuando calculemosσ 2m.
Lo interesante de esta idea es que podemos mantener siempre todas las posiciones deS·$ e
ir calculando los mapeos y ordenamientos de ellas nivel por nivel. Ya que cada nivel depende
del anterior, no necesitamos almacenar todos los niveles, pues las posiciones finales ordenadas
coincidir´ an con el suffix array deS·$.
Una observaci´ on extra que se puede considerar es que, as´ ı comomapeotiene los mapeos del nivel
correspondiente, las posiciones est´ an ordenadas por dichos mapeos, as´ ı que podemos asignar las
posiciones iniciales de cada bucket del counting sort simplemente iterando de mayor a menor
´ ındice sobre las posiciones y “machacando” los inicios de los buckets. Esto nos permitir´ ıa hacer
el ordenamiento de las posiciones seg´ un la nueva longitud en solo 3 iteraciones.
Usaremos el siguiente pseudoc´ odigo para obtener el suffix array:
Algoritmo 3:Manber-Myers(S)
1n← |S|a← {0, . . . , n−1};
2Ordenaraseg´ unS i creciente ;
3Seanmapeo[n],new mapeo[n],head[n] yby second[n] arreglos de enteros ;
4len←1 ;
5mientraslen < nhacer
6parai←0an−1hacer
7by second[i]←(a[i]−len+n) (m´ odn) ;
8parai←n−1a0hacer
9head[mapeo[a[i]]]←i;
10parai←0an−1hacer
11x←by second[i] ;
12a[head[mapeo[x]]]←x;
13head[mapeo[x]]←head[mapeo[x]] + 1 ;
14Asignar ennew mapeolos mapeos correspondientes aa;
15Intercambiarmapeoconnew mapeo;
16len←2×len;
17devolvera;
Veamos un ejemplo para visualizar bien el proceso:
Ejemplo 5
Sea
S=mississippi$, n= 12.
Luego de ordenar los sufijos seg´ unSi obtenemos:
a= (11,1,4,7,10,0,8,9,2,3,5,6).
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 5 de 23

## CS3014___Strings.pdf - page 6

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
Iteraci´ onlen= 1
El mapeo inicial queda dado por:
i 0 1 2 3 4 5 6 7 8 9 10 11
mapeo 2 1 4 4 1 4 4 1 3 3 1 0
Iteraci´ onlen= 2
Luego de asignar el vectorby second, este queda de la siguiente manera:
i 0 1 2 3 4 5 6 7 8 9 10 11
by second 2 1 4 4 1 4 4 1 3 3 1 0
Y losheadquedar´ ıan de la siguiente manera:
i 0 1 2 3 4 5 6 7 8 9 10 11
head 0 1 5 6 8 0 0 0 0 0 0 0
Luego de ejecutar la l´ ıneas 10-13 del algoritmo, se obtiene:
a= (11,10,7,1,4,0,9,8,3,6,2,5).
El nuevo mapeo es:
i 0 1 2 3 4 5 6 7 8 9 10 11
mapeo 4 3 8 7 3 8 7 2 6 5 1 0
Iteraci´ onlen= 4
Luego de asignar el vectorby second, este queda de la siguiente manera:
i 0 1 2 3 4 5 6 7 8 9 10 11
by second 9 8 5 11 2 10 7 6 1 4 0 3
Y losheadquedar´ ıan de la siguiente manera:
i 0 1 2 3 4 5 6 7 8 9 10 11
head 0 1 2 3 5 6 7 8 10 0 0 0
Luego de ejecutar la l´ ıneas 10-13 del algoritmo, se obtiene:
a= (11,10,7,1,4,0,9,8,6,3,5,2).
El nuevo mapeo es:
i 0 1 2 3 4 5 6 7 8 9 10 11
mapeo 4 3 10 8 3 9 7 2 6 5 1 0
Iteraci´ onlen= 8
Luego de asignar el vectorby second, este queda de la siguiente manera:
i 0 1 2 3 4 5 6 7 8 9 10 11
by second 7 6 3 9 0 8 5 4 2 11 1 10
Y losheadquedar´ ıan de la siguiente manera:
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 6 de 23

## CS3014___Strings.pdf - page 7

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
i 0 1 2 3 4 5 6 7 8 9 10 11
head 0 1 2 3 5 6 7 8 9 10 11 0
Luego de ejecutar la l´ ıneas 10-13 del algoritmo, se obtiene:
a= (11,10,7,4,1,0,9,8,6,3,5,2).
El nuevo mapeo es:
i 0 1 2 3 4 5 6 7 8 9 10 11
mapeo 5 4 11 9 3 10 8 2 7 6 1 0
Iteraci´ onlen= 16
Luego de asignar el vectorby second, este queda de la siguiente manera:
i 0 1 2 3 4 5 6 7 8 9 10 11
by second 3 2 11 8 5 4 1 0 10 7 9 6
Y losheadquedar´ ıan de la siguiente manera:
i 0 1 2 3 4 5 6 7 8 9 10 11
head 0 1 2 3 4 5 6 7 8 9 10 11
Luego de ejecutar la l´ ıneas 10-13 del algoritmo, se obtiene:
a= (11,10,7,4,1,0,9,8,6,3,5,2).
El nuevo mapeo es:
i 0 1 2 3 4 5 6 7 8 9 10 11
mapeo 5 4 11 9 3 10 8 2 7 6 1 0
Y esta idea es m´ as sencilla a nivel de implementaci´ on.
2.2. Karkkainen, Sanders y Burkhardt
A pesar de que Ko y Aluru fueron los primeros en proponer un algoritmo lineal [2] para la
construcci´ on del suffix array, su c´ odigo no es pr´ actico (el original ten´ ıa m´ as de 1000 l´ ıneas), as´ ı
que presentaremos primero el algoritmo DC3 (Difference Coverm´ odulo 3) [1].
La idea detr´ as del algoritmo se basa en aplicar recursi´ on para reducirSa una cadenaRde
menor longitud, calcular el suffix array deRpara obtener el suffix array deSa partir de dicha
informaci´ on. Notemos quen= 1 es el caso base de la recursi´ on y su respuesta siempre es
A={0}.
El algoritmo propone los siguientes pasos:
1. Definir los conjuntos de posicionesB 0,B 1 yB 2, donde
Bk ={0≤i≤n−1 :i≡k(m´ od 3)}
DeclaramosC=B 1 ∪B 2 y denotamos porS C el conjunto de sufijos deC.
Consideremos que sin≡1 (m´ od 3), entonces se agreganaB 1 para asegurar la presencia
de sentinelas como separadores.
2. Parak= 1,2, consideraremos la cadena formada de la siguiente manera:
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 7 de 23

## CS3014___Strings.pdf - page 8

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
Rk = Suf(S, k) agrupado en grupos de 3 caracteres consecutivos
Consideremos que si alg´ un grupo contiene menos de 3 caracteres, completaremos dichos
caracteres con sentinelas $.
Por ejemplo, paraS=mississippiconn= 11, se dar´ ıa que
R1 =(iss)(iss)(ipp)(i$$)
R2 =(ssi)(ssi)(ppi)
Adem´ as, se defineR=R 1 ·R 2, es decir
R=(iss)(iss)(ipp)(i$$)(ssi)(ssi)(ppi)
Luego, asignaremos mapeo num´ erico a cada terna de caracteres en funci´ on a su posici´ on
lexicogr´ afica, reduciendoRa una secuencia de enterosS ′:
i$$⇒0
ipp⇒1
iss⇒2
ppi⇒3
ssi⇒4
S′ =2210443
Si todos los elementos deS ′ son diferentes, con su mapeo num´ erico podemos obtener el
orden de sus sufijos; en caso contrario, podemos aplicar recursi´ on sobreS′ para obtener el
orden de sus sufijos. Con el orden, podemos asignar un rango (posici´ on ordenada) rankS(i)
a cada sufijo. Notemos que la comparaci´ on de sufijos deS′ va a preservar el orden de cada
sufijo enB 1 yB 2 debido a los sentinelas separadores.
En este ejemplo, tendr´ ıamos
S′
i 2 2 1 0 4 4 3
rankS′(i) 3 2 1 0 6 5 4
Lo cual se traduce a
Si m i s s i s s i p p i
rankS(i) ? 3 6 ? 2 5 ? 1 4 ? 0
3. Para ordenar los sufijos deB 0 entre s´ ı, podemos representar cada posici´ onicomo un par
(Si,rank S(i+ 1)) y usar radix sort.
Para el ejemplo mostrado, tendr´ ıamos
(m,3)≺(p,0)≺(s,1)≺(s,2)
Suf S(0)≺Suf S(9)≺Suf S(6)≺Suf S(3)
4. Ahora tendremos los dos conjuntos de sufijos ordenados, los deB 0 y los deC. Para orde-
narlos entre s´ ı podemos plantear el siguiente m´ etodo de comparaci´ on para los dos posibles
escenarios:
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 8 de 23

## CS3014___Strings.pdf - page 9

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
i∈B 0 yj∈B 1: Comparamos por pares como enB 0.
i∈B 0 yj∈B 2: Comparamos por ternas (Si, Si+1,rank S(i+2)) y (Sj, Sj+1,rank S(j+
2)).
Asumiremos que tendremos una funci´ on llamadaCompare-DC3(i, j, S, rnk) que permita
comparar las posicionesiyjseg´ un este criterio (asumiremos que devuelve una respuesta
en [−1,1] como un comparador cl´ asico de C).
Adaptando el cl´ asicoMergeque se usa en el algoritmo de Merge Sort, obtendremos los
sufijos ordenados enO(n).
Algoritmo 4:Merge-DC3(B 0, AR, S, rnk)
1A← ∅;
2pos C ←0 ;
3parai∈B 0 hacer
4mientraspos C <|A R|yCompare-DC3(i, A R[posC], S, rnk) = 1hacer
5A←A∪ {A R[posC]};
6pos C ←pos C + 1 ;
7A←A∪ {i};
8mientraspos C <|A R|hacer
9A←A∪ {A R[posC]};
10pos C ←pos C + 1 ;
11devolverA
La complejidad del algoritmo se basa en la siguiente recursi´ on:
T(n) =T
2n
3

+O(n)
Ya que la cadenaS ′ tendr´ a un tama˜ no que no excede a2n
3 y todos los dem´ as pasos tomanO(n).
Es sencillo notar que la recursi´ on se resuelve con
T(n) =O(n)
As´ ı que tendremos un algoritmo lineal.
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 9 de 23

## CS3014___Strings.pdf - page 10

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
Algoritmo 5:DC3(n, S)
1SeanB k ={0≤i < n:i≡k(m´ od 3)}parak= 0,1,2 ;
2sin≡1 (m´ od 3)entonces
3B 1 ←B 1 ∪ {n};
4C←B 1 ∪B 2 ;
5OrdenarCpor (S[x], S[x+ 1], S[x+ 2]) conRadix-Sort;
6Crearσ:C7→Z +
0 seg´ un el orden deC;
7R←
2Q
i=1
Q
x∈Bi
σ((S[x], S[x+ 1], S[x+ 2])) ;
8A R ←DC3(|R|, R) ;
9Searnk[0. . . n] un arreglo de enteros ;
10parai←0a|R|- 1hacer
11siA R[i]<|B 1|entonces
12x←B 1[AR[i]]
13en otro caso
14x←B 2[AR[i]− |B 1|]
15rnk[x]←i
16OrdenarB 0 por (S[x], rnk[x+ 1]) conRadix-Sort;
17devolverMerge-DC3(B 0, AR, S, rnk)
Donde los accesos a posiciones que no existen se deben considerar como−1 en valor.
2.3. Ko y Aluru (2003)
En [2], Ko y Aluru presentan, por primera vez, un algoritmo lineal que aprovecha la clasificaci´ on
de sufijos de una cadenaS.
Definici´ on 6 (Clasificaci´ on de sufijos)
Dada una cadenaS, el sufijo Suf(S, i) es clasificado en uno de los dos siguientes tipos:
TipoL, si Suf(S, i)>Suf(S, i+ 1) (en caso exista).
TipoS, si Suf(S, i)<Suf(S, i+ 1) (en caso exista).
El sufijo Suf(S, n−1) puede ser considerado de tipo L o S seg´ un convenga.
Es posible obtener la clasificaci´ on de cada uno de losnsufijos en tiempoO(n) mediante la
siguiente idea:
T[n−1] =SoT[n−1] =Lseg´ un convenga.
SiS[i] =S[i+ 1], entoncesT[i]←T[i].
En caso contrario, entoncesT[i] se define seg´ un la relaci´ on entreS[i] yS[i+ 1].
El algoritmo ser´ ıa el siguiente:
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 10 de 23

## CS3014___Strings.pdf - page 11

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
Algoritmo 6:Classify(n, S)
1SeaT[0. . .(n−1)] un arreglo de tipos ;
2T[n−1]←S;
3parai←n−2a0hacer
4siS[i] =S[i]entonces
5T[i]←T[i+ 1] ;
6en otro caso
7siS[i]< S[i+ 1]entonces
8T[i]←S;
9en otro caso
10T[i]←L;
11devolverT;
Debido a la definici´ on de los tipos, se puede probar el siguiente lema:
Lema 7
Seacel caracter con el que comienza Suf(S, i). SiT[i] =S, entonces Suf(S, i)> ccc . . .;
mientras que siT[i] =L, entonces Suf(S, i)< ccc . . ..
Como un corolario del teorema anterior podemos concluir que:
Corolario 8
Cualquier sufijo de tipoSque comience con el caracterces mayor lexicogr´ aficamente que
cualquier sufijo de tipoLque comience con el mismo caracter.
Con respecto a las posiciones de los sufijos que comienzan con un mismo caracterc, tambi´ en se
obtiene el siguiente corolario:
Corolario 9
Todos los sufijos de tipoSque comienzan con el caractercvan despu´ es de todos los sufijos
de tipoLque tambi´ en comienzan concen el suffix array.
Bajo estas condiciones sobre los tipos, una acci´ on natural ser´ ıa agrupar los sufijos por su letra
inicial (bloques) e intentar ordenar un subconjunto de ellos para obtener las posiciones de todos
los sufijos de alguno de los tipos e inducir el orden de los del otro tipo.
Vamos a asumir que tenemos una subrutina que nos permita calcular los inicios y finales de
cada bloque de sufijos que comience con la misma letra, esta estar´ a basada en el algoritmo de
counting sort y asumir´ a que todos los caracteres deSest´ an en el rango [0, n−1]. Esta subrutina
tendr´ a una complejidad deO(n) bajo la restricci´ on de los caracteres.
Supongamos queXes la secuencia ordenada lexicogr´ aficamente de los sufijos de tipoSdeS,
entonces podemos inducir el orden de todos los sufijos deSnotando lo siguiente:
Observaci´ on 10
SiS i es un sufijo de tipoL(S), entonces el sufijoS i+1 debe aparecer antes (despu´ es) queSi
en el suffix array.
Bajo la observaci´ on anterior, es posible ordenar todos los sufijos siguiendo los pasos a continua-
ci´ on:
1. Colocamos los sufijos deXen sus posiciones correspondientes en el suffix arrayA.
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 11 de 23

## CS3014___Strings.pdf - page 12

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
2. Iteramos de izquierda a derecha (derecha a izquierda) sobre los elementos deA, siS A[i]−1
es de tipoL(S), entonces lo colocamos al frente (final) de su bloque y movemos el puntero
correspondiente.
Es sencillo notar que la complejidad del algoritmo anterior esO(n), ya que podemos mantener
el inicio y el final de cada bloque (para solo sumar o restar 1 cuando asignemos alg´ un sufijo a
una posici´ on) en dos arreglos para procesar cada iteraci´ on enO(1).
Se pueden usar los siguientes algoritmos para ello.
Algoritmo 7:Get-Buckets(n, S)
1Seacnt[0. . .(|Σ| −1)] un arreglo de enteros inicializado en 0 ;
2parai←0an−1hacer
3cnt[S[i]]←cnt[S[i]] + 1 ;
4SeanL[0. . .(|Σ| −1)] yR[0. . .(|Σ| −1)] arreglos de enteros ;
5sum←0 ;
6parai←0a(|Σ| −1)hacer
7sum←sum+cnt[i] ;
8L[i]←sum−cnt[i] + 1 ;
9R[i]←sum;
10devolverL, R
Algoritmo 8:Induce-Order-With-S(n, S, T, X)
1L, R=Get-Buckets(n, S) ;
2SeaA[0. . .(n−1)] un arreglo de enteros inicializado en−1 ;
3parai← |X| −1a0hacer
4c←S[X[i]] ;
5A[R[c]]←X[i] ;
6R[c]←R[c]−1 ;
7parai←0an−1hacer
8siA[i]>0yT[A[i]−1] =Lentonces
9c←S[A[i]−1] ;
10A[L[c]]←A[i]−1 ;
11L[c]←L[c] + 1 ;
12devolverA
Ahora debemos intentar encontrar la manera de ordenar los sufijos de un tipo en particular de
forma eficiente. Notemos que es posible particionarStomando como referencia a sus sufijos de
tipoSoL, definiendo las subcadenas de tipoSyL.
Definici´ on 11 (Subcadena L/S)
Una subcadenaS[i, j] es de tipoxsi y solo si:
Si yS j son de tipox.
No hay ninguni < k < jtal queS k sea de tipox.
Por ejemplo, para la cadena “bdefdfdfbdeddafd$”, se tendr´ ıan los tipos y subcadenas:
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 12 de 23

## CS3014___Strings.pdf - page 13

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
b d e f d f d f b d e d d a f d$
Tipo S S S L S L S L S S L L L S L L S/L
Cuadro 1: Tipos de sufijo de la cadena “bdefdfdfbdeddafd$”
Subcadenas S Subcadenas L
afd$
bd
de
dedda
dfb
dfd
efd
d$
daf
dd
ed
fbde
fd
fdf
Cuadro 2: Subcadenas de la cadena “bdefdfdfbdeddafd$”
Si asoci´ aramos cada subcadena a su posici´ on de inicio, entonces se formar´ ıan las siguientes dos
cadenas:
Subcadenas S Subcadenas L
1.bd
2.de
3.efd
4.dfd
5.dfb
6.bd
7.dedda
8.afd$
1.fdf
2.fdf
3.fbde
4.ed
5.dd
6.daf
7.fd
8.d$
Cuadro 3: Partici´ on por tipo de la cadena “bdefdfdfbdeddafd$”
Notemos que en el caso de usar el tipoL, asumimos que el caracter sentinela es de tipoL. Por
otro lado, es posible que un prefijo de la cadena sea ignorado en el mapeo debido a que no es
relevante para ordenar los sufijos del tipo deseado.
Ahora debemos plantear el mapeo que se usar´ a en cada tipo. Para ello, definiremos el siguiente
enfoque:
Enfoque 12
Si se consideran las subcadenas de tipoS(L), una subcadenaXdebe recibir un menor mapeo
queYsi y solo si:
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 13 de 23

## CS3014___Strings.pdf - page 14

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
Existe una posici´ onjtal queX j ̸=Y j yX j ≺Y j.
Y(X) es prefijo propio deX(Y).
A partir de este enfoque, se cumple el siguiente lema.
Lema 13
SeaS ′ la cadena compuesta por los mapeos de las subcadenas elegidas deS, entonces para
dos sufijosS i yS j con sus posiciones correspondientes enS ′
i′ yS ′
j′, respectivamente:
Si ≺S j ⇐ ⇒S ′
i′ ≺S ′
j′
Vamos a reemplazar cada inicio de subcadena por su mapeo correspondiente y dejaremos el
sentinela en la ´ ultima posici´ on. Para el ejemplo mostrado, los dos mapeos ser´ ıan:
Subcadenas S Subcadenas L
1.bd→1
2.de→3
3.efd→6
4.dfd→5
5.dfb→4
6.bd→1
7.dedda→2
8.afd$→0
9. $→$
1.fdf→6
2.fdf→6
3.fbde→4
4.ed→3
5.dd→2
6.daf→1
7.fd→5
8.d$→0
9. $→$
Cuadro 4: Mapeo por tipo de la cadena “bdefdfdfbdeddafd$”
Observemos que la comparaci´ on de los sufijos “defdfdfbdeddafd$” y “deddafd$” es correc-
ta bajo el mapeo de las subcadenas S, as´ ı como tambi´ en lo es la comparaci´ on de los sufijos
“fdfbdeddafd$” y “fd$” bajo el mapeo de las subcadenas L.
Adem´ as, el orden de los sufijos mapeados de la cadenaS′ =13654120$es{8,7,5,0,6,1,4,3,2}
y el orden de todos los sufijos deS(tipo S) correspondientes ser´ ıa{13,8,0,9,1,6,4,2}. Por otro
lado, el orden de los sufijos mapeados de la cadenaS ′ =66432150$es{8,7,5,4,3,2,6,1,0}y
el orden de todos los sufijos deS(tipo L) correspondientes ser´ ıa{13,8,0,9,1,6,4,2}.
Una observaci´ on trivial pero importante es la siguiente:
Observaci´ on 14
El sufijoS n−1 =$siempre ser´ a el primero en el suffix array, as´ ı que se puede colocar
directamente.
2.3.1. Funciones para calcularS ′
Vamos a presentar los algoritmos que se requieren para obtenerS ′ tomando como referencia a
las subcadenas de tipo S. Para el escenario que usa subcadenas de tipo L es sencillo notar qu´ e
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 14 de 23

## CS3014___Strings.pdf - page 15

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
funciones deben modificarse.
Algoritmo 9:Group-By-Character(n, S)
1SeaA[n] un arreglo de enteros ;
2Seahead[n] un arreglo de enteros inicializado en 0 ;
3parai←0an−1hacer
4head[S[i]]←head[S[i]] + 1 ;
5sum←0 ;
6parai←0an−1hacer
7sum←sum+head[i] ;
8head[i]←sum−head[i] ;
9parai←0an−1hacer
10A[head[S[i]]]←i;
11head[S[i]]←head[S[i]] + 1 ;
12devolverA;
Esta funci´ on nos devuelve las posiciones deAordenadas por su primer caracter, desempatando
arbitrariamente.
Los siguientes algoritmos son los principales para obtener el mapeo de las subcadenas elegidas
para la partici´ on deS.
Algoritmo 10:Get-S-Distances(n, S, T)
1SeaDist[n] un arreglo de enteros;
2last S← −1;
3parai←0an−1hacer
4silast S=−1entonces
5Dist[i]←0 ;
6en otro caso
7Dist[i]←i−last S;
8siT i =Sentonces
9last S←i;
10devolverDist;
Algoritmo 11:Prepare-Pointers(n, S, A)
1SeaR[n] un arreglo de enteros ;
2Sealptr[n] un arreglo de enteros ;
3l←0 ;
4mientrasl < nhacer
5r←l;
6mientrasr < nyS[A[l]] =S[A[r]]hacer
7r←r+ 1 ;
8lptr[r−1]←l;
9R[A[r−1]]←r−1 ;
10parai←lar−2hacer
11R[A[i]]←r−1 ;
12lptr[i]←0 ;
13l←r;
14devolverR, lptr
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 15 de 23

## CS3014___Strings.pdf - page 16

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
Algoritmo 12:Move-To-Front(R, lptr, L j, l, r)
1parai←lar−1hacer
2start←L j[i]−j;
3pos bucket←R[start] ;
4f ront bucket←lptr[pos bucket] ;
5sif ront bucket <0entonces
6f ront bucket← ¬f ront bucket;
7lptr[pos bucket]← ¬(f ront bucket+ 1) ;
8sif ront bucket=pos bucketentonces
9lptr[pos bucket]← ¬lptr[pos bucket] ;
10parai←lar−1hacer
11start←L j[i]−j;
12pos bucket←R[start] ;
13silptr[pos bucket]<0entonces
14R[start] = (¬lptr[pos bucket])−1 ;
15lptr[pos bucket]← ¬lptr[pos bucket] ;
16lptr[R[start]]←R[start] + 1 ;
17en otro caso
18R[start]←lptr[pos bucket]−1 ;
19parai←lar−1hacer
20start←L j[i]−j;
21lptr[R[start]]←lptr[R[start]]−1 ;
Algoritmo 13:Sort-Buckets(R, lptr, L, m)
1paraj←1amhacer
2l←0 ;
3mientrasl <|L j|hacer
4r←l;
5mientrasr <|L j|yS[L j[l]] =S[L j[r]]hacer
6r←r+ 1 ;
7Move-To-Front(R, lptr, L j, l, r) ;
8l←r;
Algoritmo 14:Reassign-Mapping(X, R)
1l←0 ;
2id←0 ;
3mientrasl <|X|hacer
4r←l;
5mientrasr <|X|yR[X[l]] =R[X[r]]hacer
6r←r+ 1 ;
7parai←lar−1hacer
8R[X[i]]←id;
9id←id+ 1 ;
10l←r;
Finalmente, el siguiente algoritmo construye la cadena reducida tomando como referencia a las
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 16 de 23

## CS3014___Strings.pdf - page 17

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
posiciones con sufijos de tipo S.
Algoritmo 15:Build-Reduced-String-With-S(n, S, T)
1A←Group-By-Character(n, S) ;
2Dist←Get-S-Distances(n, S, T) ;
3m←
n−1
m´ ax
i=0
{Dist[i]};
4SeanL 1 . . . Lm listas vac´ ıas de enteros ;
5parai←0an−1hacer
6idx←A[i];
7siDist[idx]>0entonces
8Agregaridxal final deL Dist[idx];
9R, lptr←Prepare-Pointers(n, S, A) ;
10Sort-Buckets(R, lptr, L, m) ;
11X← {0≤i < n:T i =S};
12OrdenarXporRcreciente ;
13Reassign-Mapping(X, R) ;
14S ′ ←ε;
15parai←0an−1hacer
16siT i =Sentonces
17S ′ ←S ′ +R[i] ;
18devolverS ′
Es sencillo notar c´ omo se deber´ ıa realizar la implementaci´ on para ordenar las subcadenas de
tipo L en funci´ on al algoritmo para las subcadenas de tipo S.
Finalmente, el algoritmo ser´ ıa el siguiente:
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 17 de 23

## CS3014___Strings.pdf - page 18

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
Algoritmo 16:SAKA(n, S)
1sin= 1entonces
2devolver{0};
3en otro caso
4T←Classify(n, S) ;
5cnt L ← |{0≤i < n−1 :T i =L}|;
6cnt S ←n−1−cnt L ;
7sicnt L < cnt S entonces
8S ′ ←Build-Reduced-String-With-L(n, S, T) ;
9siS ′ tiene todos sus caracteres diferentesentonces
10CalcularXen funci´ on al caracter de cada posici´ on ;
11en otro caso
12X←SAKA(cnt L, S′) ;
13A←Induce-Order-With-L(n, S, T, X) ;
14devolverA;
15en otro caso
16S ′ ←Build-Reduced-String-With-S(n, S, T) ;
17siS ′ tiene todos sus caracteres diferentesentonces
18CalcularXen funci´ on al caracter de cada posici´ on ;
19en otro caso
20X←SAKA(cnt S, S′) ;
21A←Induce-Order-With-S(n, S, T, X) ;
22devolverA;
Este algoritmo tiene importancia debido a que sienta las bases para el algoritmo SAIS de Nong
et al..
2.4. Nonget al.
En [4], Nonget al.proponen una definici´ on nueva sobre las presentadas por Ko y Aluru, los
sufijos LMS:
Definici´ on 15 (Sufijo LMS)
Se define un sufijo LMS como un sufijo Suf(S, i) que es de tipo S bajo la condici´ on de que
Suf(S, i−1) exista y sea de tipo L.
Con esta definici´ on podemos intentar predecir hacia donde se quiere llegar. Consideremos el
orden de los sufijos en el suffix array final y analicemos qu´ e pasa con un sufijoS i de tipo L:
Si+1 es de tipo S:S i+1 es un LMS.
Si+1 es de tipo L:S i+1 es un sufijo que apareceantesqueS i en el suffix array.
Es sencillo notar que si podemos obtener el orden de los sufijos LMS, es posible inducir el
orden de los sufijos de tipo L iterando de atr´ as hacia adelante en el suffix array y con toda esa
informaci´ on podemos inducir el orden de los sufijos de tipo S.
Entonces, el objetivo que se plantea es ordenar los sufijos LMS; para ello, se definen las subca-
denas LMS:
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 18 de 23

## CS3014___Strings.pdf - page 19

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
Definici´ on 16 (Subcadena LMS)
Se define una subcadena LMS como una subcadenaS[i, j] tal que se cumpla alguna de las
siguientes condiciones:
i < jy tanto Suf(S, i) como Suf(S, j) son sufijos LMS y no existe un ´ ındicei < k < j
tal que Suf(S, k) sea un sufijo de tipo LMS.
S[i, j] = Suf(S, n−1).
En la primera condici´ on, el caracterS[j] es llamadooverlapping character, ya que est´ a
compartido entre dos subcadenas LMS.
Denotaremos el conjunto de posiciones LMS comoLMS.
Ejemplo 17
Considerando la cadena “MMIISSIISSIIPPII$”, los tipos de sus sufijos son los siguientes:
i 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16
S[i] M M I I S S I I S S I I P P I I$
T[i] L L S S L L S S L L S S L L L L S
LMS • • • •
Las subcadenas LMS son:
“IISSI”
“IISSI”
“IIPPII$”
“$”
El siguiente lema establece una propiedad importante sobre la cantidad de sufijos LMS en una
cadena.
Lema 18
Dada una cadenaSde longitudn, la cantidad de sufijos LMS enSno excede a
 n−1
2

.
A diferencia del SAKA, el algoritmo SAIS no necesita seleccionar un tipo en espec´ ıfico de sufijos;
en vez de ello, usa los sufijos LMS para simplificar la idea.
Teorema 19 (Nonget al., 2009)
Todos los sufijos de tipo L pueden ser ordenados si el orden de los sufijos LMS es conocido.
El algoritmo 18 se puede usar para inducir el orden de todos los sufijos deSusando el arreglo
Xcomo el conjuntoLMSordenado por los sufijos correspondientes a sus posiciones.
Para ordenar los sufijos LMS podemos obtener una cadena reducida como en el algoritmo SAKA
tomando las subcadenas LMS. El orden establecido para comparar las subcadenas LMS es el
siguiente debido al Corolario 8.
Enfoque 20
Dos subcadenas LMSXyYdeben ser comparadas lexicogr´ aficamente usando el par
(caracter,tipo) en cada posici´ on, siendo el tipoLmenor lexicogr´ aficamente queS.
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 19 de 23

## CS3014___Strings.pdf - page 20

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
Algoritmo 17:Compute-Buckets(n, S, end)
1Seacnt[0. . .(|Σ| −1)] un arreglo de enteros inicializado con 0 ;
2parac∈Shacer
3cnt[c]←cnt[c] + 1 ;
4SeaP[0. . .(|Σ| −1)] un arreglo de enteros ;
5sum←0 ;
6parai←0a|Σ| −1hacer
7siend=F alseentonces
8P[i]←sum;
9sum←sum+cnt[i] ;
10en otro caso
11sum←sum+cnt[i] ;
12P[i]←sum−1 ;
13devolverP
Ejemplo 21
Consideremos la cadenaS= “AABACACBACBCBCB$”, los tipos de los sufijos son los
siguientes:
Index 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15
S A A B A C A C B A C B C B C B$
T ype S S L S L S L L S L S L S L L S
LM S • • • • • •
Las subcadenas LMS ordenadas se acuerdo al Enfoque 20 son:
0. “$”
1. “ACA”
2. “ACBA”
3. “ACB”
4. “BCB$”
5. “BCB”
Notemos que “ACBA” debe recibir un mapeo menor que “ACB” debido a que el caracter
‘B’ en la primera es de tipoLmientras que el que est´ a en la segunda es de tipoS.
Finalmente, la cadena reducida es:
R= 123540.
El siguiente teorema nos se˜ nala c´ omo es posible ordenar las subcadenas LMS usando el algoritmo
Induce-Order.
Teorema 22 (Nonget al., 2009)
Es posible ordenar las subcadenas LMS seg´ un el Enfoque 20 llamando a
Induce-Order(n, S, T,LMS char), dondeLMS char esLMSordenado por el carac-
ter en cada posici´ on correspondiente.
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 20 de 23

## CS3014___Strings.pdf - page 21

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
Algoritmo 18:Induce-Order(n, S, T, X)
1SeaA[0. . .(n−1)] un arreglo de enteros inicializado en 0 ;
2R←Compute-Buckets(n, S,True) ;
3parai← |X| −1a0hacer
4c←S[X[i]] ;
5A[R[c]]←X[i] ;
6R[c]←R[c]−1 ;
7L←Compute-Buckets(n, S,F alse) ;
8parai←0an−1hacer
9siA[i]>0andT[A[i]−1] =Lentonces
10c←S[A[i]−1] ;
11A[L[c]]←A[i]−1 ;
12L[c]←L[c] + 1 ;
13R←Compute-Buckets(n, S,True) ;
14parai←n−1a0hacer
15siA[i]>0andT[A[i]−1] =Sentonces
16c←S[A[i]−1] ;
17A[R[c]]←A[i]−1 ;
18R[c]←R[c]−1 ;
19devolverA;
Luego de que las subcadenas LMS est´ en ordenadas, ellas deben recibir su mapeo para la
cadena reducida. El Algoritmo 19 describe como calcular el mapeo en tiempo lineal, donde
X=LMS mapping, dondeLMS mapping esLMSordenado seg´ un el Enfoque 20.
Algoritmo 19:Compute-Mapping(n, S, T, X)
1Seaσ: [0, n−1]7→[0, n−1] un mapeo vac´ ıo ;
2σ(X[0])←0 ;
3names←1 ;
4parak←1a|X| −1hacer
5i←X[k−1] ;
6j←X[k] ;
7L←0 ;
8mientrasi+L < nyj+L < ny(S[i+L], T[i+L]) = (S[j+L], T[j+L])
hacer
9silen >0entonces
10sii+Les LMSoj+Les LMSentonces
11break;
12L←L+ 1 ;
13sii+Les LMSyj+Les LMSentonces
14σ(X[k])←σ(X[k−1]) ;
15en otro caso
16σ(X[k])←σ(X[k−1]) + 1 ;
17names←σ(X[i]) + 1 ;
18devolverσ, names
Ya que cada caracter de la cadena es escaneado a lo mucho dos veces, la complejidad del algoritmo
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 21 de 23

## CS3014___Strings.pdf - page 22

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
esO(n).
El siguiente teorema garantiza la correctitud del algoritmo SAIS.
Teorema 23 (Nonget al., 2009)
Es posible ordenar los sufijos deSllamando aInduce-Order(n, S, T,LMS suf f ix), donde
LMS suf f ix esLMSordenado por el sufijo de cada posici´ on correspondiente.
Para calcularLMS suf f ix, primero construiremos la cadena reducidaRy luego usaremos re-
cursi´ on para determinar su suffix array. Sin embargo, si los caracteres deRson diferentes, la
recursi´ on no es necesaria, ya que podemos calcular el suffix array deRdirectamente por los
caracteres (ya que habr´ a solo 1 posici´ on por cada uno). Luego de calcular el suffix array deR,
se debe remapear las posiciones LMS a sus equivalentes enS.
En resumen, el Algoritmo 20 describe el proceso completo usado por el algoritmo SAIS.
Algoritmo 20:SAIS(n, S)
1T←Compute-Types(n, S) ;
2P← {i >0 :T[i−1] =L∧T[i] =S};
3OrdenarPpor el primer caracterS[P[i]] ;
4A←Induce-Order(n, S, T, P) ;
5OrdenarPseg´ unA;
6σ, names←Compute-Mapping(n, S, T, P) ;
7OrdenarPen orden creciente ;
8SeaRuna secuencia de tama˜ no|P|;
9parai←0a|P| −1hacer
10R[i]←σ(P[i]) ;
11sinames <|P|entonces
12SA 1 ←SAIS(|R|, R) ;
13en otro caso
14CalcularSA 1 como la permutaci´ on inversa deR;
15SA 1 ← {P[SA 1[i]] :i= 0, . . . ,|SA 1| −1};
16SA←Induce-Order(n, S, T, SA 1) ;
17devolverSA
Notemos que la l´ ınea 3 puede ser calculada enO(n) usandoCounting-Sort, y las l´ ıneas 5
y 7 pueden ser ejecutadas en una sola iteraci´ on filtrando las posiciones LMS. Adem´ as, ya que
σmapea enteros en el rango [0, n−1], puede ser almacenado en un arreglo de tama˜ non. En
consecuencia, el algoritmo satisface|R| ≤
l
|S|−1
2
m
gracias al Lema 18. Por lo tanto, la complejidad
satisface la siguiente recurrencia:
T(n) =T
 n
2

+O(n)⇒T(n) =O(n)
Referencias
[1] Juha K¨ arkk¨ ainen, Peter Sanders, and Stefan Burkhardt. Linear work suffix array construc-
tion.Journal of the ACM (JACM), 53(6):918–936, 2006.
[2] Pang Ko and Srinivas Aluru. Space efficient linear time construction of suffix arrays. In
Annual Symposium on Combinatorial Pattern Matching, pages 200–210. Springer, 2003.
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 22 de 23

## CS3014___Strings.pdf - page 23

CS3014 - Estructuras de Datos Avanzadas Notas de clase 01
[3] Udi Manber and Gene Myers. Suffix arrays: a new method for on-line string searches.siam
Journal on Computing, 22(5):935–948, 1993.
[4] Ge Nong, Sen Zhang, and Wai Hong Chan. Linear suffix array construction by almost pure
induced-sorting. In2009 data compression conference, pages 193–202. IEEE, 2009.
Prof. V´ ıctor Racs´ o Galv´ an Oyola P´ agina 23 de 23

# FILE: Estructuras_de_Datos_Avanzadas___Strings_I.pdf (35 pages)


## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 1

CS3014 Estructuras de Datos Avanzadas
CS3014 Estructuras de Datos Avanzadas
Laboratorio - Semana 10 - Sesión 1
Víctor Racsó Galván Oyola
vgalvan@utec.edu.pe
27 de mayo de 2026
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 1 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 2

CS3014 Estructuras de Datos Avanzadas
¿Qué aprenderemos hoy?
▶RMQ y LCA
▶Pattern Matching
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 2 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 3

CS3014 Estructuras de Datos Avanzadas
¿Qué aprenderemos hoy?
▶RMQ y LCA
▶Pattern Matching
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 2 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 4

CS3014 Estructuras de Datos Avanzadas
¿Qué aprenderemos hoy?
▶RMQ y LCA
▶Pattern Matching
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 2 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 5

RMQ y LCA

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 6

CS3014 Estructuras de Datos Avanzadas
RMQ
Range Minimum Query (Codeforces Group - Static RMQ)
Dada una secuenciaAdenenteros, calcular el valor
m ´ ın
l≤i≤r
{Ai }
para múltiples consultas.
Soluciones
Implementaremos primero una versión que tomeO(nlogn)de construcción
yO(1)de consulta.
Luego implementaremos una versión que tomeO(n)de construcción y
O(logn)de consulta.
Finalmente, una versión que tomeO(n)de construcción yO(1)de consulta.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 7

CS3014 Estructuras de Datos Avanzadas
RMQ
Range Minimum Query (Codeforces Group - Static RMQ)
Dada una secuenciaAdenenteros, calcular el valor
m ´ ın
l≤i≤r
{Ai }
para múltiples consultas.
Soluciones
Implementaremos primero una versión que tomeO(nlogn)de construcción
yO(1)de consulta.
Luego implementaremos una versión que tomeO(n)de construcción y
O(logn)de consulta.
Finalmente, una versión que tomeO(n)de construcción yO(1)de consulta.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 8

CS3014 Estructuras de Datos Avanzadas
RMQ
Range Minimum Query (Codeforces Group - Static RMQ)
Dada una secuenciaAdenenteros, calcular el valor
m ´ ın
l≤i≤r
{Ai }
para múltiples consultas.
Soluciones
Implementaremos primero una versión que tomeO(nlogn)de construcción
yO(1)de consulta.
Luego implementaremos una versión que tomeO(n)de construcción y
O(logn)de consulta.
Finalmente, una versión que tomeO(n)de construcción yO(1)de consulta.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 9

CS3014 Estructuras de Datos Avanzadas
RMQ
Range Minimum Query (Codeforces Group - Static RMQ)
Dada una secuenciaAdenenteros, calcular el valor
m ´ ın
l≤i≤r
{Ai }
para múltiples consultas.
Soluciones
Implementaremos primero una versión que tomeO(nlogn)de construcción
yO(1)de consulta.
Luego implementaremos una versión que tomeO(n)de construcción y
O(logn)de consulta.
Finalmente, una versión que tomeO(n)de construcción yO(1)de consulta.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 10

CS3014 Estructuras de Datos Avanzadas
RMQ
Range Minimum Query (Codeforces Group - Static RMQ)
Dada una secuenciaAdenenteros, calcular el valor
m ´ ın
l≤i≤r
{Ai }
para múltiples consultas.
Soluciones
Implementaremos primero una versión que tomeO(nlogn)de construcción
yO(1)de consulta.
Luego implementaremos una versión que tomeO(n)de construcción y
O(logn)de consulta.
Finalmente, una versión que tomeO(n)de construcción yO(1)de consulta.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 11

CS3014 Estructuras de Datos Avanzadas
RMQ
Range Minimum Query (Codeforces Group - Static RMQ)
Dada una secuenciaAdenenteros, calcular el valor
m ´ ın
l≤i≤r
{Ai }
para múltiples consultas.
Soluciones
Implementaremos primero una versión que tomeO(nlogn)de construcción
yO(1)de consulta.
Luego implementaremos una versión que tomeO(n)de construcción y
O(logn)de consulta.
Finalmente, una versión que tomeO(n)de construcción yO(1)de consulta.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 12

CS3014 Estructuras de Datos Avanzadas
LCA
Lowest Common Ancestor
Dado un árbol conNnodos y raíz en el nodo 0, responder aQconsultas
(ui ,v i)con el LCA deu i yv i.
Soluciones
Implementaremos primero la solución conO(NlogN)de construcción y
O(logN)de consulta.
Podemos implementar fácilmente una solución conO(N)de construcción y
O(logN)de consulta.
La implementación de la versiónO(N)de construcción yO(1)de consulta
queda como ejercicio.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 5 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 13

CS3014 Estructuras de Datos Avanzadas
LCA
Lowest Common Ancestor
Dado un árbol conNnodos y raíz en el nodo 0, responder aQconsultas
(ui ,v i)con el LCA deu i yv i.
Soluciones
Implementaremos primero la solución conO(NlogN)de construcción y
O(logN)de consulta.
Podemos implementar fácilmente una solución conO(N)de construcción y
O(logN)de consulta.
La implementación de la versiónO(N)de construcción yO(1)de consulta
queda como ejercicio.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 5 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 14

CS3014 Estructuras de Datos Avanzadas
LCA
Lowest Common Ancestor
Dado un árbol conNnodos y raíz en el nodo 0, responder aQconsultas
(ui ,v i)con el LCA deu i yv i.
Soluciones
Implementaremos primero la solución conO(NlogN)de construcción y
O(logN)de consulta.
Podemos implementar fácilmente una solución conO(N)de construcción y
O(logN)de consulta.
La implementación de la versiónO(N)de construcción yO(1)de consulta
queda como ejercicio.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 5 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 15

CS3014 Estructuras de Datos Avanzadas
LCA
Lowest Common Ancestor
Dado un árbol conNnodos y raíz en el nodo 0, responder aQconsultas
(ui ,v i)con el LCA deu i yv i.
Soluciones
Implementaremos primero la solución conO(NlogN)de construcción y
O(logN)de consulta.
Podemos implementar fácilmente una solución conO(N)de construcción y
O(logN)de consulta.
La implementación de la versiónO(N)de construcción yO(1)de consulta
queda como ejercicio.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 5 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 16

CS3014 Estructuras de Datos Avanzadas
LCA
Lowest Common Ancestor
Dado un árbol conNnodos y raíz en el nodo 0, responder aQconsultas
(ui ,v i)con el LCA deu i yv i.
Soluciones
Implementaremos primero la solución conO(NlogN)de construcción y
O(logN)de consulta.
Podemos implementar fácilmente una solución conO(N)de construcción y
O(logN)de consulta.
La implementación de la versiónO(N)de construcción yO(1)de consulta
queda como ejercicio.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 5 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 17

CS3014 Estructuras de Datos Avanzadas
LCA
Lowest Common Ancestor
Dado un árbol conNnodos y raíz en el nodo 0, responder aQconsultas
(ui ,v i)con el LCA deu i yv i.
Soluciones
Implementaremos primero la solución conO(NlogN)de construcción y
O(logN)de consulta.
Podemos implementar fácilmente una solución conO(N)de construcción y
O(logN)de consulta.
La implementación de la versiónO(N)de construcción yO(1)de consulta
queda como ejercicio.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 5 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 18

Pattern Matching

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 19

CS3014 Estructuras de Datos Avanzadas
Pattern Matching
Definición
Es un problema en el que se tiene una cadenaT, llamada texto, y una cadena
P, llamada patrón, y se desea saber siPocurre enTcomo subcadena.
Su variación llamadaMultiple pattern matchingimplica tener múltiples pa-
tronesP 1, . . . ,Pm.
Aplicaciones
Búsquedas exactas de texto, motores de búsqueda, autocompletar.
Búsqueda inexacta, búsqueda con wildcards, etc.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 7 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 20

CS3014 Estructuras de Datos Avanzadas
Pattern Matching
Definición
Es un problema en el que se tiene una cadenaT, llamada texto, y una cadena
P, llamada patrón, y se desea saber siPocurre enTcomo subcadena.
Su variación llamadaMultiple pattern matchingimplica tener múltiples pa-
tronesP 1, . . . ,Pm.
Aplicaciones
Búsquedas exactas de texto, motores de búsqueda, autocompletar.
Búsqueda inexacta, búsqueda con wildcards, etc.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 7 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 21

CS3014 Estructuras de Datos Avanzadas
Pattern Matching
Definición
Es un problema en el que se tiene una cadenaT, llamada texto, y una cadena
P, llamada patrón, y se desea saber siPocurre enTcomo subcadena.
Su variación llamadaMultiple pattern matchingimplica tener múltiples pa-
tronesP 1, . . . ,Pm.
Aplicaciones
Búsquedas exactas de texto, motores de búsqueda, autocompletar.
Búsqueda inexacta, búsqueda con wildcards, etc.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 7 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 22

CS3014 Estructuras de Datos Avanzadas
Pattern Matching
Definición
Es un problema en el que se tiene una cadenaT, llamada texto, y una cadena
P, llamada patrón, y se desea saber siPocurre enTcomo subcadena.
Su variación llamadaMultiple pattern matchingimplica tener múltiples pa-
tronesP 1, . . . ,Pm.
Aplicaciones
Búsquedas exactas de texto, motores de búsqueda, autocompletar.
Búsqueda inexacta, búsqueda con wildcards, etc.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 7 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 23

CS3014 Estructuras de Datos Avanzadas
Pattern Matching
Definición
Es un problema en el que se tiene una cadenaT, llamada texto, y una cadena
P, llamada patrón, y se desea saber siPocurre enTcomo subcadena.
Su variación llamadaMultiple pattern matchingimplica tener múltiples pa-
tronesP 1, . . . ,Pm.
Aplicaciones
Búsquedas exactas de texto, motores de búsqueda, autocompletar.
Búsqueda inexacta, búsqueda con wildcards, etc.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 7 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 24

CS3014 Estructuras de Datos Avanzadas
Pattern Matching
Definición
Es un problema en el que se tiene una cadenaT, llamada texto, y una cadena
P, llamada patrón, y se desea saber siPocurre enTcomo subcadena.
Su variación llamadaMultiple pattern matchingimplica tener múltiples pa-
tronesP 1, . . . ,Pm.
Aplicaciones
Búsquedas exactas de texto, motores de búsqueda, autocompletar.
Búsqueda inexacta, búsqueda con wildcards, etc.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 7 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 25

CS3014 Estructuras de Datos Avanzadas
Escenarios
Pconocido,Tpor conocer
Consideraremos un escenario en el que se nos daPinicialmente, procesaremos
Py luego se nos daTpara hacer el emparejamiento.
Algoritmos: Knuth-Morris-Pratt, Z, Rabin-Karp, Aho-Corasick (multiple).
Tconocido,Ppor conocer
Consideraremos un escenario en el que se nos daTinicialmente,
procesaremosTy luego se nos daPpara hacer el emparejamiento.
Algoritmos: Suffix array, Suffix tree, Suffix automaton.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 26

CS3014 Estructuras de Datos Avanzadas
Escenarios
Pconocido,Tpor conocer
Consideraremos un escenario en el que se nos daPinicialmente, procesaremos
Py luego se nos daTpara hacer el emparejamiento.
Algoritmos: Knuth-Morris-Pratt, Z, Rabin-Karp, Aho-Corasick (multiple).
Tconocido,Ppor conocer
Consideraremos un escenario en el que se nos daTinicialmente,
procesaremosTy luego se nos daPpara hacer el emparejamiento.
Algoritmos: Suffix array, Suffix tree, Suffix automaton.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 27

CS3014 Estructuras de Datos Avanzadas
Escenarios
Pconocido,Tpor conocer
Consideraremos un escenario en el que se nos daPinicialmente, procesaremos
Py luego se nos daTpara hacer el emparejamiento.
Algoritmos: Knuth-Morris-Pratt, Z, Rabin-Karp, Aho-Corasick (multiple).
Tconocido,Ppor conocer
Consideraremos un escenario en el que se nos daTinicialmente,
procesaremosTy luego se nos daPpara hacer el emparejamiento.
Algoritmos: Suffix array, Suffix tree, Suffix automaton.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 28

CS3014 Estructuras de Datos Avanzadas
Escenarios
Pconocido,Tpor conocer
Consideraremos un escenario en el que se nos daPinicialmente, procesaremos
Py luego se nos daTpara hacer el emparejamiento.
Algoritmos: Knuth-Morris-Pratt, Z, Rabin-Karp, Aho-Corasick (multiple).
Tconocido,Ppor conocer
Consideraremos un escenario en el que se nos daTinicialmente,
procesaremosTy luego se nos daPpara hacer el emparejamiento.
Algoritmos: Suffix array, Suffix tree, Suffix automaton.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 29

CS3014 Estructuras de Datos Avanzadas
Escenarios
Pconocido,Tpor conocer
Consideraremos un escenario en el que se nos daPinicialmente, procesaremos
Py luego se nos daTpara hacer el emparejamiento.
Algoritmos: Knuth-Morris-Pratt, Z, Rabin-Karp, Aho-Corasick (multiple).
Tconocido,Ppor conocer
Consideraremos un escenario en el que se nos daTinicialmente,
procesaremosTy luego se nos daPpara hacer el emparejamiento.
Algoritmos: Suffix array, Suffix tree, Suffix automaton.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 30

CS3014 Estructuras de Datos Avanzadas
Escenarios
Pconocido,Tpor conocer
Consideraremos un escenario en el que se nos daPinicialmente, procesaremos
Py luego se nos daTpara hacer el emparejamiento.
Algoritmos: Knuth-Morris-Pratt, Z, Rabin-Karp, Aho-Corasick (multiple).
Tconocido,Ppor conocer
Consideraremos un escenario en el que se nos daTinicialmente,
procesaremosTy luego se nos daPpara hacer el emparejamiento.
Algoritmos: Suffix array, Suffix tree, Suffix automaton.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 31

CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Implementamos RMQ
▶Implementamos LCA
▶Aprendimos de qué trata el problema de Pattern Matching
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 9 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 32

CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Implementamos RMQ
▶Implementamos LCA
▶Aprendimos de qué trata el problema de Pattern Matching
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 9 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 33

CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Implementamos RMQ
▶Implementamos LCA
▶Aprendimos de qué trata el problema de Pattern Matching
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 9 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 34

CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Implementamos RMQ
▶Implementamos LCA
▶Aprendimos de qué trata el problema de Pattern Matching
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 9 / 10

## Estructuras_de_Datos_Avanzadas___Strings_I.pdf - page 35

CS3014 Estructuras de Datos Avanzadas
Gracias
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 10 / 10

# FILE: Estructuras_de_Datos_Avanzadas___Strings_II.pdf (81 pages)


## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 1

CS3014 Estructuras de Datos Avanzadas
CS3014 Estructuras de Datos Avanzadas
Laboratorio - Semana 10 - Sesión 2
Víctor Racsó Galván Oyola
vgalvan@utec.edu.pe
29 de mayo de 2026
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 1 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 2

CS3014 Estructuras de Datos Avanzadas
¿Qué aprenderemos hoy?
▶Strings
▶Suffix array
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 2 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 3

CS3014 Estructuras de Datos Avanzadas
¿Qué aprenderemos hoy?
▶Strings
▶Suffix array
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 2 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 4

CS3014 Estructuras de Datos Avanzadas
¿Qué aprenderemos hoy?
▶Strings
▶Suffix array
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 2 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 5

Strings

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 6

CS3014 Estructuras de Datos Avanzadas
Notación
Notación básica de strings
Una cadena es una secuencia de símbolos llamadoscaracteres, los cuales
pertenecen a un conjunto llamadoalfabetoΣ.
Eli-ésimo caracter de una cadenaSse denota porS[i]y la concatenación de
los caracteres de las posicionesx∈[i,j]se denotar porS[i,j].
Convenciones
▶Se considera comparaciónlexicográficaentre cadena.
▶Las cadenas deben tener como último caracter a un sentinela$∈Σ.
Dependiendo del caso, se podría asumir también que$<c,∀c∈Σ.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 7

CS3014 Estructuras de Datos Avanzadas
Notación
Notación básica de strings
Una cadena es una secuencia de símbolos llamadoscaracteres, los cuales
pertenecen a un conjunto llamadoalfabetoΣ.
Eli-ésimo caracter de una cadenaSse denota porS[i]y la concatenación de
los caracteres de las posicionesx∈[i,j]se denotar porS[i,j].
Convenciones
▶Se considera comparaciónlexicográficaentre cadena.
▶Las cadenas deben tener como último caracter a un sentinela$∈Σ.
Dependiendo del caso, se podría asumir también que$<c,∀c∈Σ.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 8

CS3014 Estructuras de Datos Avanzadas
Notación
Notación básica de strings
Una cadena es una secuencia de símbolos llamadoscaracteres, los cuales
pertenecen a un conjunto llamadoalfabetoΣ.
Eli-ésimo caracter de una cadenaSse denota porS[i]y la concatenación de
los caracteres de las posicionesx∈[i,j]se denotar porS[i,j].
Convenciones
▶Se considera comparaciónlexicográficaentre cadena.
▶Las cadenas deben tener como último caracter a un sentinela$∈Σ.
Dependiendo del caso, se podría asumir también que$<c,∀c∈Σ.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 9

CS3014 Estructuras de Datos Avanzadas
Notación
Notación básica de strings
Una cadena es una secuencia de símbolos llamadoscaracteres, los cuales
pertenecen a un conjunto llamadoalfabetoΣ.
Eli-ésimo caracter de una cadenaSse denota porS[i]y la concatenación de
los caracteres de las posicionesx∈[i,j]se denotar porS[i,j].
Convenciones
▶Se considera comparaciónlexicográficaentre cadena.
▶Las cadenas deben tener como último caracter a un sentinela$∈Σ.
Dependiendo del caso, se podría asumir también que$<c,∀c∈Σ.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 10

CS3014 Estructuras de Datos Avanzadas
Notación
Notación básica de strings
Una cadena es una secuencia de símbolos llamadoscaracteres, los cuales
pertenecen a un conjunto llamadoalfabetoΣ.
Eli-ésimo caracter de una cadenaSse denota porS[i]y la concatenación de
los caracteres de las posicionesx∈[i,j]se denotar porS[i,j].
Convenciones
▶Se considera comparaciónlexicográficaentre cadena.
▶Las cadenas deben tener como último caracter a un sentinela$∈Σ.
Dependiendo del caso, se podría asumir también que$<c,∀c∈Σ.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 11

CS3014 Estructuras de Datos Avanzadas
Notación
Notación básica de strings
Una cadena es una secuencia de símbolos llamadoscaracteres, los cuales
pertenecen a un conjunto llamadoalfabetoΣ.
Eli-ésimo caracter de una cadenaSse denota porS[i]y la concatenación de
los caracteres de las posicionesx∈[i,j]se denotar porS[i,j].
Convenciones
▶Se considera comparaciónlexicográficaentre cadena.
▶Las cadenas deben tener como último caracter a un sentinela$∈Σ.
Dependiendo del caso, se podría asumir también que$<c,∀c∈Σ.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 4 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 12

Suffix array

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 13

CS3014 Estructuras de Datos Avanzadas
Suffix array
Definición
El suffix array de una cadenaScon longitudnes una permutaciónAde sus
posiciones de manera que siiva antes quejenA, entoncesS[i,n−1]<
S[j,n−1].
Denotaremos porSuf(S,i)al sufijo deSque comienza en la posicióni, es
decir,S[i,n−1].
Setup básico
En primer lugar, para cualquier cadenaSque tengamos como argumento,
vamos a considerar que esta tiene concatenado un caracter sentinela, el cual
es lexicográficamente menor que todos los caracteres del alfabeto.
Esto nos ayuda evitando la cadena vacía.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 6 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 14

CS3014 Estructuras de Datos Avanzadas
Suffix array
Definición
El suffix array de una cadenaScon longitudnes una permutaciónAde sus
posiciones de manera que siiva antes quejenA, entoncesS[i,n−1]<
S[j,n−1].
Denotaremos porSuf(S,i)al sufijo deSque comienza en la posicióni, es
decir,S[i,n−1].
Setup básico
En primer lugar, para cualquier cadenaSque tengamos como argumento,
vamos a considerar que esta tiene concatenado un caracter sentinela, el cual
es lexicográficamente menor que todos los caracteres del alfabeto.
Esto nos ayuda evitando la cadena vacía.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 6 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 15

CS3014 Estructuras de Datos Avanzadas
Suffix array
Definición
El suffix array de una cadenaScon longitudnes una permutaciónAde sus
posiciones de manera que siiva antes quejenA, entoncesS[i,n−1]<
S[j,n−1].
Denotaremos porSuf(S,i)al sufijo deSque comienza en la posicióni, es
decir,S[i,n−1].
Setup básico
En primer lugar, para cualquier cadenaSque tengamos como argumento,
vamos a considerar que esta tiene concatenado un caracter sentinela, el cual
es lexicográficamente menor que todos los caracteres del alfabeto.
Esto nos ayuda evitando la cadena vacía.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 6 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 16

CS3014 Estructuras de Datos Avanzadas
Suffix array
Definición
El suffix array de una cadenaScon longitudnes una permutaciónAde sus
posiciones de manera que siiva antes quejenA, entoncesS[i,n−1]<
S[j,n−1].
Denotaremos porSuf(S,i)al sufijo deSque comienza en la posicióni, es
decir,S[i,n−1].
Setup básico
En primer lugar, para cualquier cadenaSque tengamos como argumento,
vamos a considerar que esta tiene concatenado un caracter sentinela, el cual
es lexicográficamente menor que todos los caracteres del alfabeto.
Esto nos ayuda evitando la cadena vacía.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 6 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 17

CS3014 Estructuras de Datos Avanzadas
Suffix array
Definición
El suffix array de una cadenaScon longitudnes una permutaciónAde sus
posiciones de manera que siiva antes quejenA, entoncesS[i,n−1]<
S[j,n−1].
Denotaremos porSuf(S,i)al sufijo deSque comienza en la posicióni, es
decir,S[i,n−1].
Setup básico
En primer lugar, para cualquier cadenaSque tengamos como argumento,
vamos a considerar que esta tiene concatenado un caracter sentinela, el cual
es lexicográficamente menor que todos los caracteres del alfabeto.
Esto nos ayuda evitando la cadena vacía.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 6 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 18

CS3014 Estructuras de Datos Avanzadas
Construcción del suffix array
La siguiente tabla muestra algunos algoritmos de construcción de suffix
array (SACA) importantes históricamente.
Autor(es) Algoritmo Complejidad Idea
Manber & Myers Sin nombre O(nlogn) Doubling
Itoh & Tanaka Sin nombre Superlineal Ordenamiento inducido
Ko & Aluru SAKA O(n) Ordenamiento inducido
Karkkainen et. al. DC3 O(n) Ordenamiento inducido
Nong et. al. SAIS O(n) Ordenamiento inducido
Cuadro: SACA más conocidos
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 7 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 19

CS3014 Estructuras de Datos Avanzadas
Construcción del suffix array
La siguiente tabla muestra algunos algoritmos de construcción de suffix
array (SACA) importantes históricamente.
Autor(es) Algoritmo Complejidad Idea
Manber & Myers Sin nombre O(nlogn) Doubling
Itoh & Tanaka Sin nombre Superlineal Ordenamiento inducido
Ko & Aluru SAKA O(n) Ordenamiento inducido
Karkkainen et. al. DC3 O(n) Ordenamiento inducido
Nong et. al. SAIS O(n) Ordenamiento inducido
Cuadro: SACA más conocidos
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 7 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 20

CS3014 Estructuras de Datos Avanzadas
DC3 (Karkkainen et. al.)
Idea
Particionamos las posiciones según su residuo respecto a 3.
Denotamos los tres conjuntos
S0 ={0≤i≤n−1:i=3k,para algúnk∈Z}
S1 ={0≤i≤n−1:i=3k+1,para algúnk∈Z}
S2 ={0≤i≤n−1:i=3k+2,para algúnk∈Z}
Teorema (Karkkainen et. al.)
Si se sabe el orden de los sufijos en los elementos deS1 yS 2, entonces se
puede deducir el orden de todos los sufijos deS.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 21

CS3014 Estructuras de Datos Avanzadas
DC3 (Karkkainen et. al.)
Idea
Particionamos las posiciones según su residuo respecto a 3.
Denotamos los tres conjuntos
S0 ={0≤i≤n−1:i=3k,para algúnk∈Z}
S1 ={0≤i≤n−1:i=3k+1,para algúnk∈Z}
S2 ={0≤i≤n−1:i=3k+2,para algúnk∈Z}
Teorema (Karkkainen et. al.)
Si se sabe el orden de los sufijos en los elementos deS1 yS 2, entonces se
puede deducir el orden de todos los sufijos deS.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 22

CS3014 Estructuras de Datos Avanzadas
DC3 (Karkkainen et. al.)
Idea
Particionamos las posiciones según su residuo respecto a 3.
Denotamos los tres conjuntos
S0 ={0≤i≤n−1:i=3k,para algúnk∈Z}
S1 ={0≤i≤n−1:i=3k+1,para algúnk∈Z}
S2 ={0≤i≤n−1:i=3k+2,para algúnk∈Z}
Teorema (Karkkainen et. al.)
Si se sabe el orden de los sufijos en los elementos deS1 yS 2, entonces se
puede deducir el orden de todos los sufijos deS.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 23

CS3014 Estructuras de Datos Avanzadas
DC3 (Karkkainen et. al.)
Idea
Particionamos las posiciones según su residuo respecto a 3.
Denotamos los tres conjuntos
S0 ={0≤i≤n−1:i=3k,para algúnk∈Z}
S1 ={0≤i≤n−1:i=3k+1,para algúnk∈Z}
S2 ={0≤i≤n−1:i=3k+2,para algúnk∈Z}
Teorema (Karkkainen et. al.)
Si se sabe el orden de los sufijos en los elementos deS1 yS 2, entonces se
puede deducir el orden de todos los sufijos deS.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 24

CS3014 Estructuras de Datos Avanzadas
DC3 (Karkkainen et. al.)
Idea
Particionamos las posiciones según su residuo respecto a 3.
Denotamos los tres conjuntos
S0 ={0≤i≤n−1:i=3k,para algúnk∈Z}
S1 ={0≤i≤n−1:i=3k+1,para algúnk∈Z}
S2 ={0≤i≤n−1:i=3k+2,para algúnk∈Z}
Teorema (Karkkainen et. al.)
Si se sabe el orden de los sufijos en los elementos deS1 yS 2, entonces se
puede deducir el orden de todos los sufijos deS.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 8 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 25

CS3014 Estructuras de Datos Avanzadas
Algoritmo
Partición
ParaS 1 yS 2, vamos a tomar los bloques de 3 elementos en adelante desde
cada posición. Ya que podrían faltar elementos, se hace padding con sentinelas
$.
Por ejemplo, para “banana$”, se tendrían los siguientes bloques:
S1 →(ana)(na$)
S2 →(nan)(a$$)
Notemos que es posible mapear cada uno de estos bloques a surankentre
todos los bloques enO(n)usando radix sort.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 9 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 26

CS3014 Estructuras de Datos Avanzadas
Algoritmo
Partición
ParaS 1 yS 2, vamos a tomar los bloques de 3 elementos en adelante desde
cada posición. Ya que podrían faltar elementos, se hace padding con sentinelas
$.
Por ejemplo, para “banana$”, se tendrían los siguientes bloques:
S1 →(ana)(na$)
S2 →(nan)(a$$)
Notemos que es posible mapear cada uno de estos bloques a surankentre
todos los bloques enO(n)usando radix sort.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 9 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 27

CS3014 Estructuras de Datos Avanzadas
Algoritmo
Partición
ParaS 1 yS 2, vamos a tomar los bloques de 3 elementos en adelante desde
cada posición. Ya que podrían faltar elementos, se hace padding con sentinelas
$.
Por ejemplo, para “banana$”, se tendrían los siguientes bloques:
S1 →(ana)(na$)
S2 →(nan)(a$$)
Notemos que es posible mapear cada uno de estos bloques a surankentre
todos los bloques enO(n)usando radix sort.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 9 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 28

CS3014 Estructuras de Datos Avanzadas
Algoritmo
Partición
ParaS 1 yS 2, vamos a tomar los bloques de 3 elementos en adelante desde
cada posición. Ya que podrían faltar elementos, se hace padding con sentinelas
$.
Por ejemplo, para “banana$”, se tendrían los siguientes bloques:
S1 →(ana)(na$)
S2 →(nan)(a$$)
Notemos que es posible mapear cada uno de estos bloques a surankentre
todos los bloques enO(n)usando radix sort.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 9 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 29

CS3014 Estructuras de Datos Avanzadas
Algoritmo
¿Y ahora qué hacemos?
Podemosreemplazarcadabloqueporsurespectivorankyseterminancreando
dos cadenas nuevas.
S1 →R 1 =12
S2 →R 2 =30
Si concatenamos estas dos cadenas nuevas, tendremos una cadenaR=R1R2
de longitud≈ 2n
3 .
Aplicando recursión
Podemos usar recursión para obtener el suffix array de la cadenaR, de esta
manera obtendremos el orden relativo entre cada par de sufijos deR1 yR 2.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 10 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 30

CS3014 Estructuras de Datos Avanzadas
Algoritmo
¿Y ahora qué hacemos?
Podemosreemplazarcadabloqueporsurespectivorankyseterminancreando
dos cadenas nuevas.
S1 →R 1 =12
S2 →R 2 =30
Si concatenamos estas dos cadenas nuevas, tendremos una cadenaR=R1R2
de longitud≈ 2n
3 .
Aplicando recursión
Podemos usar recursión para obtener el suffix array de la cadenaR, de esta
manera obtendremos el orden relativo entre cada par de sufijos deR1 yR 2.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 10 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 31

CS3014 Estructuras de Datos Avanzadas
Algoritmo
¿Y ahora qué hacemos?
Podemosreemplazarcadabloqueporsurespectivorankyseterminancreando
dos cadenas nuevas.
S1 →R 1 =12
S2 →R 2 =30
Si concatenamos estas dos cadenas nuevas, tendremos una cadenaR=R1R2
de longitud≈ 2n
3 .
Aplicando recursión
Podemos usar recursión para obtener el suffix array de la cadenaR, de esta
manera obtendremos el orden relativo entre cada par de sufijos deR1 yR 2.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 10 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 32

CS3014 Estructuras de Datos Avanzadas
Algoritmo
¿Y ahora qué hacemos?
Podemosreemplazarcadabloqueporsurespectivorankyseterminancreando
dos cadenas nuevas.
S1 →R 1 =12
S2 →R 2 =30
Si concatenamos estas dos cadenas nuevas, tendremos una cadenaR=R1R2
de longitud≈ 2n
3 .
Aplicando recursión
Podemos usar recursión para obtener el suffix array de la cadenaR, de esta
manera obtendremos el orden relativo entre cada par de sufijos deR1 yR 2.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 10 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 33

CS3014 Estructuras de Datos Avanzadas
Algoritmo
¿Y ahora qué hacemos?
Podemosreemplazarcadabloqueporsurespectivorankyseterminancreando
dos cadenas nuevas.
S1 →R 1 =12
S2 →R 2 =30
Si concatenamos estas dos cadenas nuevas, tendremos una cadenaR=R1R2
de longitud≈ 2n
3 .
Aplicando recursión
Podemos usar recursión para obtener el suffix array de la cadenaR, de esta
manera obtendremos el orden relativo entre cada par de sufijos deR1 yR 2.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 10 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 34

CS3014 Estructuras de Datos Avanzadas
Algoritmo
¿Y ahora qué hacemos?
Podemosreemplazarcadabloqueporsurespectivorankyseterminancreando
dos cadenas nuevas.
S1 →R 1 =12
S2 →R 2 =30
Si concatenamos estas dos cadenas nuevas, tendremos una cadenaR=R1R2
de longitud≈ 2n
3 .
Aplicando recursión
Podemos usar recursión para obtener el suffix array de la cadenaR, de esta
manera obtendremos el orden relativo entre cada par de sufijos deR1 yR 2.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 10 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 35

CS3014 Estructuras de Datos Avanzadas
Algoritmo
¿Y como ordeno todo?
Vamos a tener escenarios en los cuales todo se va a reducir a comparar una
cantidadO(1)de caracteres y una comparación de ranks de los sufijos deS1
yS 2.
▶x∈ S 0 vsy∈ S 1: Podemos tomar el primer caracter de cada sufijo, de
manera que la comparación se reduce a comparar los pares
(S[i],rank(Suf(S,i+1)))parai=x,y.
Notemos quex+1∈ S 1 yy+1∈ S 2, así que sus ranks están definidos.
▶x∈ S 0 vsy∈ S 2: Podemos tomar el primer caracter de cada sufijo, de
manera que la comparación se reduce a comparar las tuplas
(S[i],S[i+1],rank(Suf(S,i+2)))parai=x,y.
Notemos quex+2∈ S 2 yy+2∈ S 1, así que sus ranks están definidos.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 11 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 36

CS3014 Estructuras de Datos Avanzadas
Algoritmo
¿Y como ordeno todo?
Vamos a tener escenarios en los cuales todo se va a reducir a comparar una
cantidadO(1)de caracteres y una comparación de ranks de los sufijos deS1
yS 2.
▶x∈ S 0 vsy∈ S 1: Podemos tomar el primer caracter de cada sufijo, de
manera que la comparación se reduce a comparar los pares
(S[i],rank(Suf(S,i+1)))parai=x,y.
Notemos quex+1∈ S 1 yy+1∈ S 2, así que sus ranks están definidos.
▶x∈ S 0 vsy∈ S 2: Podemos tomar el primer caracter de cada sufijo, de
manera que la comparación se reduce a comparar las tuplas
(S[i],S[i+1],rank(Suf(S,i+2)))parai=x,y.
Notemos quex+2∈ S 2 yy+2∈ S 1, así que sus ranks están definidos.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 11 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 37

CS3014 Estructuras de Datos Avanzadas
Algoritmo
¿Y como ordeno todo?
Vamos a tener escenarios en los cuales todo se va a reducir a comparar una
cantidadO(1)de caracteres y una comparación de ranks de los sufijos deS1
yS 2.
▶x∈ S 0 vsy∈ S 1: Podemos tomar el primer caracter de cada sufijo, de
manera que la comparación se reduce a comparar los pares
(S[i],rank(Suf(S,i+1)))parai=x,y.
Notemos quex+1∈ S 1 yy+1∈ S 2, así que sus ranks están definidos.
▶x∈ S 0 vsy∈ S 2: Podemos tomar el primer caracter de cada sufijo, de
manera que la comparación se reduce a comparar las tuplas
(S[i],S[i+1],rank(Suf(S,i+2)))parai=x,y.
Notemos quex+2∈ S 2 yy+2∈ S 1, así que sus ranks están definidos.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 11 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 38

CS3014 Estructuras de Datos Avanzadas
Complejidad
Análisis
Ya que es posible hacer la comparación de pares y tuplas enO(n)usando
radix sort, obtenemos una recurrencia de la siguiente forma:
T(n) =T
2n
3

+O(n)
Es sencillo notar queT(n) =O(n).
Generalización
Se planteó en investigaciones posteriores la posibilidad de tomar módulok
en vez de módulo 3.
El módulok=7 es considerado uno de los mejores rendimientos.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 39

CS3014 Estructuras de Datos Avanzadas
Complejidad
Análisis
Ya que es posible hacer la comparación de pares y tuplas enO(n)usando
radix sort, obtenemos una recurrencia de la siguiente forma:
T(n) =T
2n
3

+O(n)
Es sencillo notar queT(n) =O(n).
Generalización
Se planteó en investigaciones posteriores la posibilidad de tomar módulok
en vez de módulo 3.
El módulok=7 es considerado uno de los mejores rendimientos.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 40

CS3014 Estructuras de Datos Avanzadas
Complejidad
Análisis
Ya que es posible hacer la comparación de pares y tuplas enO(n)usando
radix sort, obtenemos una recurrencia de la siguiente forma:
T(n) =T
2n
3

+O(n)
Es sencillo notar queT(n) =O(n).
Generalización
Se planteó en investigaciones posteriores la posibilidad de tomar módulok
en vez de módulo 3.
El módulok=7 es considerado uno de los mejores rendimientos.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 41

CS3014 Estructuras de Datos Avanzadas
Complejidad
Análisis
Ya que es posible hacer la comparación de pares y tuplas enO(n)usando
radix sort, obtenemos una recurrencia de la siguiente forma:
T(n) =T
2n
3

+O(n)
Es sencillo notar queT(n) =O(n).
Generalización
Se planteó en investigaciones posteriores la posibilidad de tomar módulok
en vez de módulo 3.
El módulok=7 es considerado uno de los mejores rendimientos.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 42

CS3014 Estructuras de Datos Avanzadas
Complejidad
Análisis
Ya que es posible hacer la comparación de pares y tuplas enO(n)usando
radix sort, obtenemos una recurrencia de la siguiente forma:
T(n) =T
2n
3

+O(n)
Es sencillo notar queT(n) =O(n).
Generalización
Se planteó en investigaciones posteriores la posibilidad de tomar módulok
en vez de módulo 3.
El módulok=7 es considerado uno de los mejores rendimientos.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 43

CS3014 Estructuras de Datos Avanzadas
Complejidad
Análisis
Ya que es posible hacer la comparación de pares y tuplas enO(n)usando
radix sort, obtenemos una recurrencia de la siguiente forma:
T(n) =T
2n
3

+O(n)
Es sencillo notar queT(n) =O(n).
Generalización
Se planteó en investigaciones posteriores la posibilidad de tomar módulok
en vez de módulo 3.
El módulok=7 es considerado uno de los mejores rendimientos.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 44

CS3014 Estructuras de Datos Avanzadas
Complejidad
Análisis
Ya que es posible hacer la comparación de pares y tuplas enO(n)usando
radix sort, obtenemos una recurrencia de la siguiente forma:
T(n) =T
2n
3

+O(n)
Es sencillo notar queT(n) =O(n).
Generalización
Se planteó en investigaciones posteriores la posibilidad de tomar módulok
en vez de módulo 3.
El módulok=7 es considerado uno de los mejores rendimientos.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 12 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 45

CS3014 Estructuras de Datos Avanzadas
SAIS (Nong et. al.)
Idea
Clasificar los sufijos deSen tipoSyL.
Un sufijoSuf(S,i)es de tipo
▶S, siSuf(S,i)<Suf(S,i+1).
▶L, siSuf(S,i)>Suf(S,i+1).
Un sufijoSuf(S,i)es de tipo LMS si el sufijoSuf(S,i−1)es de tipoLy el
sufijoSuf(S,i)es de tipoS.
Notemos que hay a lo muchon−1
2 sufijos de tipo LMS.
Teorema (Nong et. al.)
Si se sabe el orden relativo de los sufijos de tipo LMS, entonces se puede
inducir el orden de todos los sufijos deS.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 13 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 46

CS3014 Estructuras de Datos Avanzadas
SAIS (Nong et. al.)
Idea
Clasificar los sufijos deSen tipoSyL.
Un sufijoSuf(S,i)es de tipo
▶S, siSuf(S,i)<Suf(S,i+1).
▶L, siSuf(S,i)>Suf(S,i+1).
Un sufijoSuf(S,i)es de tipo LMS si el sufijoSuf(S,i−1)es de tipoLy el
sufijoSuf(S,i)es de tipoS.
Notemos que hay a lo muchon−1
2 sufijos de tipo LMS.
Teorema (Nong et. al.)
Si se sabe el orden relativo de los sufijos de tipo LMS, entonces se puede
inducir el orden de todos los sufijos deS.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 13 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 47

CS3014 Estructuras de Datos Avanzadas
SAIS (Nong et. al.)
Idea
Clasificar los sufijos deSen tipoSyL.
Un sufijoSuf(S,i)es de tipo
▶S, siSuf(S,i)<Suf(S,i+1).
▶L, siSuf(S,i)>Suf(S,i+1).
Un sufijoSuf(S,i)es de tipo LMS si el sufijoSuf(S,i−1)es de tipoLy el
sufijoSuf(S,i)es de tipoS.
Notemos que hay a lo muchon−1
2 sufijos de tipo LMS.
Teorema (Nong et. al.)
Si se sabe el orden relativo de los sufijos de tipo LMS, entonces se puede
inducir el orden de todos los sufijos deS.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 13 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 48

CS3014 Estructuras de Datos Avanzadas
SAIS (Nong et. al.)
Idea
Clasificar los sufijos deSen tipoSyL.
Un sufijoSuf(S,i)es de tipo
▶S, siSuf(S,i)<Suf(S,i+1).
▶L, siSuf(S,i)>Suf(S,i+1).
Un sufijoSuf(S,i)es de tipo LMS si el sufijoSuf(S,i−1)es de tipoLy el
sufijoSuf(S,i)es de tipoS.
Notemos que hay a lo muchon−1
2 sufijos de tipo LMS.
Teorema (Nong et. al.)
Si se sabe el orden relativo de los sufijos de tipo LMS, entonces se puede
inducir el orden de todos los sufijos deS.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 13 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 49

CS3014 Estructuras de Datos Avanzadas
SAIS (Nong et. al.)
Idea
Clasificar los sufijos deSen tipoSyL.
Un sufijoSuf(S,i)es de tipo
▶S, siSuf(S,i)<Suf(S,i+1).
▶L, siSuf(S,i)>Suf(S,i+1).
Un sufijoSuf(S,i)es de tipo LMS si el sufijoSuf(S,i−1)es de tipoLy el
sufijoSuf(S,i)es de tipoS.
Notemos que hay a lo muchon−1
2 sufijos de tipo LMS.
Teorema (Nong et. al.)
Si se sabe el orden relativo de los sufijos de tipo LMS, entonces se puede
inducir el orden de todos los sufijos deS.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 13 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 50

CS3014 Estructuras de Datos Avanzadas
SAIS (Nong et. al.)
Idea
Clasificar los sufijos deSen tipoSyL.
Un sufijoSuf(S,i)es de tipo
▶S, siSuf(S,i)<Suf(S,i+1).
▶L, siSuf(S,i)>Suf(S,i+1).
Un sufijoSuf(S,i)es de tipo LMS si el sufijoSuf(S,i−1)es de tipoLy el
sufijoSuf(S,i)es de tipoS.
Notemos que hay a lo muchon−1
2 sufijos de tipo LMS.
Teorema (Nong et. al.)
Si se sabe el orden relativo de los sufijos de tipo LMS, entonces se puede
inducir el orden de todos los sufijos deS.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 13 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 51

CS3014 Estructuras de Datos Avanzadas
Algoritmo
Partición
Se realiza la partición deStomando en cuenta las posiciones de los sufijos
LMS y se ordenan según(caracter,tipo)para calcular el rank. Es posible
realizar esto enO(n).
Reducción
Se obtiene una cadena reducidaRen base a la partición por LMS, se calcula
el suffix array deRy se puede inducir el orden de todos los sufijos deS.
Complejidad
Ya que|R| ≤ n
2, se tiene que
T(n) =T
 n
2

+O(n)→T(n) =O(n)
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 14 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 52

CS3014 Estructuras de Datos Avanzadas
Algoritmo
Partición
Se realiza la partición deStomando en cuenta las posiciones de los sufijos
LMS y se ordenan según(caracter,tipo)para calcular el rank. Es posible
realizar esto enO(n).
Reducción
Se obtiene una cadena reducidaRen base a la partición por LMS, se calcula
el suffix array deRy se puede inducir el orden de todos los sufijos deS.
Complejidad
Ya que|R| ≤ n
2, se tiene que
T(n) =T
 n
2

+O(n)→T(n) =O(n)
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 14 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 53

CS3014 Estructuras de Datos Avanzadas
Algoritmo
Partición
Se realiza la partición deStomando en cuenta las posiciones de los sufijos
LMS y se ordenan según(caracter,tipo)para calcular el rank. Es posible
realizar esto enO(n).
Reducción
Se obtiene una cadena reducidaRen base a la partición por LMS, se calcula
el suffix array deRy se puede inducir el orden de todos los sufijos deS.
Complejidad
Ya que|R| ≤ n
2, se tiene que
T(n) =T
 n
2

+O(n)→T(n) =O(n)
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 14 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 54

CS3014 Estructuras de Datos Avanzadas
Algoritmo
Partición
Se realiza la partición deStomando en cuenta las posiciones de los sufijos
LMS y se ordenan según(caracter,tipo)para calcular el rank. Es posible
realizar esto enO(n).
Reducción
Se obtiene una cadena reducidaRen base a la partición por LMS, se calcula
el suffix array deRy se puede inducir el orden de todos los sufijos deS.
Complejidad
Ya que|R| ≤ n
2, se tiene que
T(n) =T
 n
2

+O(n)→T(n) =O(n)
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 14 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 55

CS3014 Estructuras de Datos Avanzadas
Algoritmo
Partición
Se realiza la partición deStomando en cuenta las posiciones de los sufijos
LMS y se ordenan según(caracter,tipo)para calcular el rank. Es posible
realizar esto enO(n).
Reducción
Se obtiene una cadena reducidaRen base a la partición por LMS, se calcula
el suffix array deRy se puede inducir el orden de todos los sufijos deS.
Complejidad
Ya que|R| ≤ n
2, se tiene que
T(n) =T
 n
2

+O(n)→T(n) =O(n)
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 14 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 56

CS3014 Estructuras de Datos Avanzadas
Algoritmo
Partición
Se realiza la partición deStomando en cuenta las posiciones de los sufijos
LMS y se ordenan según(caracter,tipo)para calcular el rank. Es posible
realizar esto enO(n).
Reducción
Se obtiene una cadena reducidaRen base a la partición por LMS, se calcula
el suffix array deRy se puede inducir el orden de todos los sufijos deS.
Complejidad
Ya que|R| ≤ n
2, se tiene que
T(n) =T
 n
2

+O(n)→T(n) =O(n)
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 14 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 57

CS3014 Estructuras de Datos Avanzadas
Calculando el LCP
LCP array
Es un arreglo en el cual se almacenan los Longest Common Prefix (LCP) entre
cada par de posiciones adyacentes del suffix array
Ventajas
▶Ya queaestá ordenado, nos permite calcular el LCP entre cualquier par
de posiciones en un tiempo prudente si nos apoyamos en alguna
estructura de datos.
▶Ya queaestá ordenado, nos permite buscar las ocurrencias de cualquier
cadenatenO(|t|logn).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 15 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 58

CS3014 Estructuras de Datos Avanzadas
Calculando el LCP
LCP array
Es un arreglo en el cual se almacenan los Longest Common Prefix (LCP) entre
cada par de posiciones adyacentes del suffix array
Ventajas
▶Ya queaestá ordenado, nos permite calcular el LCP entre cualquier par
de posiciones en un tiempo prudente si nos apoyamos en alguna
estructura de datos.
▶Ya queaestá ordenado, nos permite buscar las ocurrencias de cualquier
cadenatenO(|t|logn).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 15 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 59

CS3014 Estructuras de Datos Avanzadas
Calculando el LCP
LCP array
Es un arreglo en el cual se almacenan los Longest Common Prefix (LCP) entre
cada par de posiciones adyacentes del suffix array
Ventajas
▶Ya queaestá ordenado, nos permite calcular el LCP entre cualquier par
de posiciones en un tiempo prudente si nos apoyamos en alguna
estructura de datos.
▶Ya queaestá ordenado, nos permite buscar las ocurrencias de cualquier
cadenatenO(|t|logn).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 15 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 60

CS3014 Estructuras de Datos Avanzadas
Calculando el LCP
LCP array
Es un arreglo en el cual se almacenan los Longest Common Prefix (LCP) entre
cada par de posiciones adyacentes del suffix array
Ventajas
▶Ya queaestá ordenado, nos permite calcular el LCP entre cualquier par
de posiciones en un tiempo prudente si nos apoyamos en alguna
estructura de datos.
▶Ya queaestá ordenado, nos permite buscar las ocurrencias de cualquier
cadenatenO(|t|logn).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 15 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 61

CS3014 Estructuras de Datos Avanzadas
Calculando el LCP
LCP array
Es un arreglo en el cual se almacenan los Longest Common Prefix (LCP) entre
cada par de posiciones adyacentes del suffix array
Ventajas
▶Ya queaestá ordenado, nos permite calcular el LCP entre cualquier par
de posiciones en un tiempo prudente si nos apoyamos en alguna
estructura de datos.
▶Ya queaestá ordenado, nos permite buscar las ocurrencias de cualquier
cadenatenO(|t|logn).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 15 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 62

CS3014 Estructuras de Datos Avanzadas
Calculando el LCP
¿Y cómo se calcula?
Una implementación ingenua podría tomar hastaO(n2)de complejidad, así
que usaremos el algoritmo de Kasai para calcularlo en un mejor tiempo.
Algoritmo de Kasai
Su principal observación es que si tenemos dos sufijos que son adyacentes en
a, seanxyysus posiciones iniciales, con LCP igual ak, entoncesx+1 y
y+1 tienen LCP de al menosk−1.
Para recorrer de esa manera losx, se itera de sufijo de mayor longitud a
sufijo de menor longitud.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 16 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 63

CS3014 Estructuras de Datos Avanzadas
Calculando el LCP
¿Y cómo se calcula?
Una implementación ingenua podría tomar hastaO(n2)de complejidad, así
que usaremos el algoritmo de Kasai para calcularlo en un mejor tiempo.
Algoritmo de Kasai
Su principal observación es que si tenemos dos sufijos que son adyacentes en
a, seanxyysus posiciones iniciales, con LCP igual ak, entoncesx+1 y
y+1 tienen LCP de al menosk−1.
Para recorrer de esa manera losx, se itera de sufijo de mayor longitud a
sufijo de menor longitud.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 16 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 64

CS3014 Estructuras de Datos Avanzadas
Calculando el LCP
¿Y cómo se calcula?
Una implementación ingenua podría tomar hastaO(n2)de complejidad, así
que usaremos el algoritmo de Kasai para calcularlo en un mejor tiempo.
Algoritmo de Kasai
Su principal observación es que si tenemos dos sufijos que son adyacentes en
a, seanxyysus posiciones iniciales, con LCP igual ak, entoncesx+1 y
y+1 tienen LCP de al menosk−1.
Para recorrer de esa manera losx, se itera de sufijo de mayor longitud a
sufijo de menor longitud.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 16 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 65

CS3014 Estructuras de Datos Avanzadas
Calculando el LCP
¿Y cómo se calcula?
Una implementación ingenua podría tomar hastaO(n2)de complejidad, así
que usaremos el algoritmo de Kasai para calcularlo en un mejor tiempo.
Algoritmo de Kasai
Su principal observación es que si tenemos dos sufijos que son adyacentes en
a, seanxyysus posiciones iniciales, con LCP igual ak, entoncesx+1 y
y+1 tienen LCP de al menosk−1.
Para recorrer de esa manera losx, se itera de sufijo de mayor longitud a
sufijo de menor longitud.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 16 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 66

CS3014 Estructuras de Datos Avanzadas
Calculando el LCP
¿Y cómo se calcula?
Una implementación ingenua podría tomar hastaO(n2)de complejidad, así
que usaremos el algoritmo de Kasai para calcularlo en un mejor tiempo.
Algoritmo de Kasai
Su principal observación es que si tenemos dos sufijos que son adyacentes en
a, seanxyysus posiciones iniciales, con LCP igual ak, entoncesx+1 y
y+1 tienen LCP de al menosk−1.
Para recorrer de esa manera losx, se itera de sufijo de mayor longitud a
sufijo de menor longitud.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 16 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 67

CS3014 Estructuras de Datos Avanzadas
Calculando el LCP
Pero podrían no ser adyacentes
Eso es cierto, pero si su LCP es al menosk−1, eso implica que todas las
posiciones entre ellos también tienen LCP de al menosk−1 con cualquiera
de los dos.
Complejidad
Sikse reduce en 1 cada vez que comparamos un par de posiciones dea, este
es reducido a lo muchon−1 veces (ya que la última posición no tiene un
sucesor). Además,kdebe permanecer en el rango[0,n], así que si usamos
una iteración ingenua para cadaxyy, tendremos una complejidad deO(n).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 17 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 68

CS3014 Estructuras de Datos Avanzadas
Calculando el LCP
Pero podrían no ser adyacentes
Eso es cierto, pero si su LCP es al menosk−1, eso implica que todas las
posiciones entre ellos también tienen LCP de al menosk−1 con cualquiera
de los dos.
Complejidad
Sikse reduce en 1 cada vez que comparamos un par de posiciones dea, este
es reducido a lo muchon−1 veces (ya que la última posición no tiene un
sucesor). Además,kdebe permanecer en el rango[0,n], así que si usamos
una iteración ingenua para cadaxyy, tendremos una complejidad deO(n).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 17 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 69

CS3014 Estructuras de Datos Avanzadas
Calculando el LCP
Pero podrían no ser adyacentes
Eso es cierto, pero si su LCP es al menosk−1, eso implica que todas las
posiciones entre ellos también tienen LCP de al menosk−1 con cualquiera
de los dos.
Complejidad
Sikse reduce en 1 cada vez que comparamos un par de posiciones dea, este
es reducido a lo muchon−1 veces (ya que la última posición no tiene un
sucesor). Además,kdebe permanecer en el rango[0,n], así que si usamos
una iteración ingenua para cadaxyy, tendremos una complejidad deO(n).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 17 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 70

CS3014 Estructuras de Datos Avanzadas
Calculando el LCP
Pero podrían no ser adyacentes
Eso es cierto, pero si su LCP es al menosk−1, eso implica que todas las
posiciones entre ellos también tienen LCP de al menosk−1 con cualquiera
de los dos.
Complejidad
Sikse reduce en 1 cada vez que comparamos un par de posiciones dea, este
es reducido a lo muchon−1 veces (ya que la última posición no tiene un
sucesor). Además,kdebe permanecer en el rango[0,n], así que si usamos
una iteración ingenua para cadaxyy, tendremos una complejidad deO(n).
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 17 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 71

CS3014 Estructuras de Datos Avanzadas
Calculando el LCP
Suffix Index LCP
$ 6 –
A$ 5 0
ANA$ 3 1
ANANA$ 1 3
BANANA$ 0 0
NA$ 4 0
NANA$ 2 2
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 18 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 72

CS3014 Estructuras de Datos Avanzadas
Propiedades
RMQ
Se puede calcular el LCP entre un par de sufijos deSmediante una consulta
de RMQ sobre el LCP array.
(Spoiler) El suffix tree es equivalente al auxiliary/tree de todos los sufijos y
el LCA representa al LCP entre cada par de hojas.
Conclusiones
Los suffix array son estructuras poderosas que permiten obtener casi tanta
información como otras estructuras (suffix tree, suffix automaton) pero
normalmente usa menos memoria, lo cual es una ventaja.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 19 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 73

CS3014 Estructuras de Datos Avanzadas
Propiedades
RMQ
Se puede calcular el LCP entre un par de sufijos deSmediante una consulta
de RMQ sobre el LCP array.
(Spoiler) El suffix tree es equivalente al auxiliary/tree de todos los sufijos y
el LCA representa al LCP entre cada par de hojas.
Conclusiones
Los suffix array son estructuras poderosas que permiten obtener casi tanta
información como otras estructuras (suffix tree, suffix automaton) pero
normalmente usa menos memoria, lo cual es una ventaja.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 19 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 74

CS3014 Estructuras de Datos Avanzadas
Propiedades
RMQ
Se puede calcular el LCP entre un par de sufijos deSmediante una consulta
de RMQ sobre el LCP array.
(Spoiler) El suffix tree es equivalente al auxiliary/tree de todos los sufijos y
el LCA representa al LCP entre cada par de hojas.
Conclusiones
Los suffix array son estructuras poderosas que permiten obtener casi tanta
información como otras estructuras (suffix tree, suffix automaton) pero
normalmente usa menos memoria, lo cual es una ventaja.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 19 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 75

CS3014 Estructuras de Datos Avanzadas
Propiedades
RMQ
Se puede calcular el LCP entre un par de sufijos deSmediante una consulta
de RMQ sobre el LCP array.
(Spoiler) El suffix tree es equivalente al auxiliary/tree de todos los sufijos y
el LCA representa al LCP entre cada par de hojas.
Conclusiones
Los suffix array son estructuras poderosas que permiten obtener casi tanta
información como otras estructuras (suffix tree, suffix automaton) pero
normalmente usa menos memoria, lo cual es una ventaja.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 19 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 76

CS3014 Estructuras de Datos Avanzadas
Propiedades
RMQ
Se puede calcular el LCP entre un par de sufijos deSmediante una consulta
de RMQ sobre el LCP array.
(Spoiler) El suffix tree es equivalente al auxiliary/tree de todos los sufijos y
el LCA representa al LCP entre cada par de hojas.
Conclusiones
Los suffix array son estructuras poderosas que permiten obtener casi tanta
información como otras estructuras (suffix tree, suffix automaton) pero
normalmente usa menos memoria, lo cual es una ventaja.
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 19 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 77

CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Aprendimos suffix array
▶Aprendimos el algoritmo DC3 y SAIS
▶Aprendimos LCP array
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 20 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 78

CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Aprendimos suffix array
▶Aprendimos el algoritmo DC3 y SAIS
▶Aprendimos LCP array
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 20 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 79

CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Aprendimos suffix array
▶Aprendimos el algoritmo DC3 y SAIS
▶Aprendimos LCP array
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 20 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 80

CS3014 Estructuras de Datos Avanzadas
Resumen de la sesión
▶Aprendimos suffix array
▶Aprendimos el algoritmo DC3 y SAIS
▶Aprendimos LCP array
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 20 / 21

## Estructuras_de_Datos_Avanzadas___Strings_II.pdf - page 81

CS3014 Estructuras de Datos Avanzadas
Gracias
Víctor Racsó Galván Oyola Universidad de Ingeniería y Tecnología 21 / 21

# FILE: eda_slides_08_rmq.pdf (27 pages)


## eda_slides_08_rmq.pdf - page 1

Static T rees
CS3014 - Estructura de Datos Avanzados
Luciano A. Romero Calla
lromeroc@utec.edu.pe
2026-1

## eda_slides_08_rmq.pdf - page 2

Overview
1. Goals
2. RMQ
3. RMQ & LCA
4. Solving RMQ
5. Level Ancestor
6. Related
7. Summary
2 / 20

## eda_slides_08_rmq.pdf - page 3

Goals
1.
Goals
3 / 20

## eda_slides_08_rmq.pdf - page 4

Goals
Goals
Warming up!
Problem I - Latin American Regional ACM ICPC 2017
https://maratona.sbc.org.br/hist/2017/resultados/contest.pdf
Do it yourself! (homework)https://judge.beecrowd.com/en/problems/view/2703
4 / 20

## eda_slides_08_rmq.pdf - page 5

Goals
Goals
Warming up!
Problem I - Latin American Regional ACM ICPC 2017
https://maratona.sbc.org.br/hist/2017/resultados/contest.pdf
Do it yourself! (homework)https://judge.beecrowd.com/en/problems/view/2703
4 / 20

## eda_slides_08_rmq.pdf - page 6

Goals
Goals
▶ Solve the RMQ problem query inO(1)
▶ Explore different structures and analyze their performance.
▶ Be able to reduce the LCA problem to RMQ and solve it.
▶ Solve the Level Ancestor (LA) problem.
5 / 20

## eda_slides_08_rmq.pdf - page 7

Goals
Goals
▶ Solve the RMQ problem query inO(1)
▶ Explore different structures and analyze their performance.
▶ Be able to reduce the LCA problem to RMQ and solve it.
▶ Solve the Level Ancestor (LA) problem.
5 / 20

## eda_slides_08_rmq.pdf - page 8

Goals
Goals
▶ Solve the RMQ problem query inO(1)
▶ Explore different structures and analyze their performance.
▶ Be able to reduce the LCA problem to RMQ and solve it.
▶ Solve the Level Ancestor (LA) problem.
5 / 20

## eda_slides_08_rmq.pdf - page 9

Goals
Goals
▶ Solve the RMQ problem query inO(1)
▶ Explore different structures and analyze their performance.
▶ Be able to reduce the LCA problem to RMQ and solve it.
▶ Solve the Level Ancestor (LA) problem.
5 / 20

## eda_slides_08_rmq.pdf - page 10

Goals
Goals
Problem Scenario Preprocessing Space Query Time
Range Minimum Query (RMQ)O(n)O(n)O(1)
Lowest Common Ancestor (LCA)O(n)O(n)O(1)
Level Ancestor (LA)O(n)O(n)O(1)
Goal: Achieve optimal linear preprocessing and constant time queries across all structures.
6 / 20

## eda_slides_08_rmq.pdf - page 11

RMQ
2.
RMQ
7 / 20

## eda_slides_08_rmq.pdf - page 12

RMQ
RMQ
Problem
Given an arrayAof n numbers (to preprocess). In a query, the goal is to find the minimum
element in a range spanned byA[i]andA[j]:
RMQ(i,j) = arg min{A[i],A[i+1], ...,A[j]}=k
wherei≤k≤jandA[k]is minimized
8 / 20

## eda_slides_08_rmq.pdf - page 13

RMQ & LCA
3.
RMQ & LCA
3.1 Cartesian trees
3.2 LCA to±1RMQ: Euler Tour
9 / 20

## eda_slides_08_rmq.pdf - page 14

RMQ & LCA Cartesian trees
Cartesian trees
Rules:
▶ Root = Minimum elementA[m]
▶ Left / Right subtrees built recursively.
▶ Preservesmin-heap property.
Identity
RMQA(i,j)≡LCA T (i,j)
A= [7,8,2,6,9,4]
2
7
8
4
6
9
10 / 20

## eda_slides_08_rmq.pdf - page 15

RMQ & LCA Cartesian trees
Cartesian trees
Linear time algorithm
▶ Scan array left to right.
▶ Walk up theright spineuntil findingA[v]<A[i].
▶ InsertA[i]as right child; old subtree becomes left
child ofA[i].
▶ Amortized Cost:Nodes enter/leave spine ≤ 1 time
=⇒O(n).
2
4
7
5
11 / 20

## eda_slides_08_rmq.pdf - page 16

RMQ & LCA LCA to±1RMQ: Euler T our
LCA to±1RMQ: Euler T our
A
B
D
C
Euler Tour (E):A B D B A C A
Depth Array (D): 0 1 2 1 0 1 0
The±1Property
Consecutive depth steps change by exactly+1 or−1:
|D[i]−D[i−1]|=1
LCA(u,v) =
min value inDbetween indices ofuandv.
12 / 20

## eda_slides_08_rmq.pdf - page 17

Solving RMQ
4.
Solving RMQ
13 / 20

## eda_slides_08_rmq.pdf - page 18

Solving RMQ
Solving RMQ
Block partition size:b= 1
2 log2 n.
1. Macro-Structure (Across Blocks)
▶ Sparse Table over block minimums.
▶ Space:O( n
b log n
b ) =O(n).
2. Micro-Structure (Inside Blocks)
▶ Max unique shapes = 2b−1 =O( √n).
▶ Precomputeb×blookup tables.
▶ Space:O( √n·b 2) =o(n).
Total Performance:O(n)Space / O(1)Query Time
14 / 20

## eda_slides_08_rmq.pdf - page 19

Level Ancestor
5.
Level Ancestor
15 / 20

## eda_slides_08_rmq.pdf - page 20

Level Ancestor
Level Ancestor
Strategy / Name Preprocessing Query Time Core T echnique
Full Table LookupO(n 2)O(1)Complete DP lookup table
Jump PointersO(nlogn)O(logn)Binary lifting (powers of 2)
Longest Path DecompositionO(n)O( √n)Disjoint root-to-leaf path arrays
Ladder DecompositionO(n)O(logn)Overlapping path extensions (doubled length)
Jump + LadderO(nlogn)O(1)1 Jump pointer step + 1 Ladder step
Macro-Micro Tree (Dietz)O(n)O(1)Leaf trimming & Method of Four Russians
16 / 20

## eda_slides_08_rmq.pdf - page 21

Related
6.
Related
17 / 20

## eda_slides_08_rmq.pdf - page 22

Related
Related
Dynamic
Segment tree, Fenwick tree, ...
18 / 20

## eda_slides_08_rmq.pdf - page 23

Summary
7.
Summary
19 / 20

## eda_slides_08_rmq.pdf - page 24

Summary
Summary
Problem Scenario Preprocessing Space Query Time
Range Minimum Query (RMQ)O(n)O(n)O(1)
Lowest Common Ancestor (LCA)O(n)O(n)O(1)
Level Ancestor (LA)O(n)O(n)O(lgn),O(1)
Goal: Achieve optimal linear preprocessing and constant time queries across all structures.
20 / 20

## eda_slides_08_rmq.pdf - page 25

Thanks

## eda_slides_08_rmq.pdf - page 26

References
References
22 / 20

## eda_slides_08_rmq.pdf - page 27

Acknowledgements
Acknowledgements
The course slides are based on the lectures from previous editions and on similar lectures elsewhere.
List of credits: Erick Demaine, Keith Schwarz
23 / 20
