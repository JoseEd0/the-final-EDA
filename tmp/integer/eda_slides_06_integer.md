# eda_slides_06_integer.pdf
Pages: 48

## Page 1
Integer I
CS3014 - Estructura de Datos Avanzados
Luciano A. Romero Calla
lromeroc@utec.edu.pe
2026-1

## Page 2
Overview
1. Goals
2. Models
3. Predecesor problem
4. van Emde Boas
5. Tree view
6. Saving space
2/19

## Page 3
Goals
1.
Goals
3/19

## Page 4
Goals
Goals
▶ Explore integer data structures to solve the predecessor problem.
▶ Describe two main data structuresvan Emde BoasandY-fasttrees.
4/19

## Page 5
Goals
Goals
▶ Explore integer data structures to solve the predecessor problem.
▶ Describe two main data structuresvan Emde BoasandY-fasttrees.
4/19

## Page 6
Models
2.
Models
5/19

## Page 7
Models
Models
word
w-bit integer∈U={0,1,2,3, ...,u=2 w −1}
transdichotomous RAM
bridging two worlds machine/problem,w≥lgS
word RAM
transdichotomous RAM with C-style operations
cell probe
count # memory reads & writes, computation-free,
useful for lower bounds
cell probe strong
transdichotomous RAM
word RAM
pointer machine
BST weak
6/19

## Page 8
Models
Models
word
w-bit integer∈U={0,1,2,3, ...,u=2 w −1}
transdichotomous RAM
bridging two worlds machine/problem,w≥lgS
word RAM
transdichotomous RAM with C-style operations
cell probe
count # memory reads & writes, computation-free,
useful for lower bounds
cell probe strong
transdichotomous RAM
word RAM
pointer machine
BST weak
6/19

## Page 9
Models
Models
word
w-bit integer∈U={0,1,2,3, ...,u=2 w −1}
transdichotomous RAM
bridging two worlds machine/problem,w≥lgS
word RAM
transdichotomous RAM with C-style operations
cell probe
count # memory reads & writes, computation-free,
useful for lower bounds
cell probe strong
transdichotomous RAM
word RAM
pointer machine
BST weak
6/19

## Page 10
Models
Models
word
w-bit integer∈U={0,1,2,3, ...,u=2 w −1}
transdichotomous RAM
bridging two worlds machine/problem,w≥lgS
word RAM
transdichotomous RAM with C-style operations
cell probe
count # memory reads & writes, computation-free,
useful for lower bounds
cell probe strong
transdichotomous RAM
word RAM
pointer machine
BST weak
6/19

## Page 11
Models
Models
word
w-bit integer∈U={0,1,2,3, ...,u=2 w −1}
transdichotomous RAM
bridging two worlds machine/problem,w≥lgS
word RAM
transdichotomous RAM with C-style operations
cell probe
count # memory reads & writes, computation-free,
useful for lower bounds
cell probe strong
transdichotomous RAM
word RAM
pointer machine
BST weak
6/19

## Page 12
Predecesor problem
3.
Predecesor problem
7/19

## Page 13
Predecesor problem
Predecesor problem
problem
maintain a setSofnwords
▶ insert(x∈U)
▶ delete(x∈S)
▶ predecessor(x∈U):max{y∈S|y<x}
▶ successor(x∈U):max{y∈S|y>x}
BST
comparison model:O(lgn)/op optimal
word RAM
▶ van Emde Boas:O(lgw)/op,Θ(u)space
▶ Y-fast trees:O(lgw)/op,Θ(n)space
▶ fusion trees:O(log w n)/op,Θ(n)space
cell probe lower bound
O(n polylg n)space,Ω

min

logw n, lgw
lg lgw
lg lgn

pointer machine
▶ word specified by node pointer
▶ van Emde Boas:O(lg lgu)/op,Θ(u)space
▶ lower bound:Ω(lg lgu)/op,Ω(u)space
8/19

## Page 14
Predecesor problem
Predecesor problem
problem
maintain a setSofnwords
▶ insert(x∈U)
▶ delete(x∈S)
▶ predecessor(x∈U):max{y∈S|y<x}
▶ successor(x∈U):max{y∈S|y>x}
BST
comparison model:O(lgn)/op optimal
word RAM
▶ van Emde Boas:O(lgw)/op,Θ(u)space
▶ Y-fast trees:O(lgw)/op,Θ(n)space
▶ fusion trees:O(log w n)/op,Θ(n)space
cell probe lower bound
O(n polylg n)space,Ω

min

logw n, lgw
lg lgw
lg lgn

pointer machine
▶ word specified by node pointer
▶ van Emde Boas:O(lg lgu)/op,Θ(u)space
▶ lower bound:Ω(lg lgu)/op,Ω(u)space
8/19

## Page 15
Predecesor problem
Predecesor problem
problem
maintain a setSofnwords
▶ insert(x∈U)
▶ delete(x∈S)
▶ predecessor(x∈U):max{y∈S|y<x}
▶ successor(x∈U):max{y∈S|y>x}
BST
comparison model:O(lgn)/op optimal
word RAM
▶ van Emde Boas:O(lgw)/op,Θ(u)space
▶ Y-fast trees:O(lgw)/op,Θ(n)space
▶ fusion trees:O(log w n)/op,Θ(n)space
cell probe lower bound
O(n polylg n)space,Ω

min

logw n, lgw
lg lgw
lg lgn

pointer machine
▶ word specified by node pointer
▶ van Emde Boas:O(lg lgu)/op,Θ(u)space
▶ lower bound:Ω(lg lgu)/op,Ω(u)space
8/19

## Page 16
Predecesor problem
Predecesor problem
problem
maintain a setSofnwords
▶ insert(x∈U)
▶ delete(x∈S)
▶ predecessor(x∈U):max{y∈S|y<x}
▶ successor(x∈U):max{y∈S|y>x}
BST
comparison model:O(lgn)/op optimal
word RAM
▶ van Emde Boas:O(lgw)/op,Θ(u)space
▶ Y-fast trees:O(lgw)/op,Θ(n)space
▶ fusion trees:O(log w n)/op,Θ(n)space
cell probe lower bound
O(n polylg n)space,Ω

min

logw n, lgw
lg lgw
lg lgn

pointer machine
▶ word specified by node pointer
▶ van Emde Boas:O(lg lgu)/op,Θ(u)space
▶ lower bound:Ω(lg lgu)/op,Ω(u)space
8/19

## Page 17
Predecesor problem
Predecesor problem
problem
maintain a setSofnwords
▶ insert(x∈U)
▶ delete(x∈S)
▶ predecessor(x∈U):max{y∈S|y<x}
▶ successor(x∈U):max{y∈S|y>x}
BST
comparison model:O(lgn)/op optimal
word RAM
▶ van Emde Boas:O(lgw)/op,Θ(u)space
▶ Y-fast trees:O(lgw)/op,Θ(n)space
▶ fusion trees:O(log w n)/op,Θ(n)space
cell probe lower bound
O(n polylg n)space,Ω

min

logw n, lgw
lg lgw
lg lgn

pointer machine
▶ word specified by node pointer
▶ van Emde Boas:O(lg lgu)/op,Θ(u)space
▶ lower bound:Ω(lg lgu)/op,Ω(u)space
8/19

## Page 18
van Emde Boas
4.
van Emde Boas
4.1 Definition
4.2 Operations
9/19

## Page 19
van Emde Boas Definition
Definition
idea
T(u) =T( √u) +O(1)
hierarchical coordinates
wordx=⟨c,i⟩
recursive vEBVof sizeu
▶ V.cluster[i] =vEB of size √u
▶ V.summary[i] =vEB of size √u
▶ V.min=minimum element inV
▶ V.max=maximum element inV
10/19

## Page 20
van Emde Boas Definition
Definition
idea
T(u) =T( √u) +O(1)
hierarchical coordinates
wordx=⟨c,i⟩
recursive vEBVof sizeu
▶ V.cluster[i] =vEB of size √u
▶ V.summary[i] =vEB of size √u
▶ V.min=minimum element inV
▶ V.max=maximum element inV
10/19

## Page 21
van Emde Boas Definition
Definition
idea
T(u) =T( √u) +O(1)
hierarchical coordinates
wordx=⟨c,i⟩
recursive vEBVof sizeu
▶ V.cluster[i] =vEB of size √u
▶ V.summary[i] =vEB of size √u
▶ V.min=minimum element inV
▶ V.max=maximum element inV
10/19

## Page 22
van Emde Boas Definition
Definition
idea
T(u) =T( √u) +O(1)
hierarchical coordinates
wordx=⟨c,i⟩
recursive vEBVof sizeu
▶ V.cluster[i] =vEB of size √u
▶ V.summary[i] =vEB of size √u
▶ V.min=minimum element inV
▶ V.max=maximum element inV
10/19

## Page 23
van Emde Boas Definition
Definition
idea
T(u) =T( √u) +O(1)
hierarchical coordinates
wordx=⟨c,i⟩
recursive vEBVof sizeu
▶ V.cluster[i] =vEB of size √u
▶ V.summary[i] =vEB of size √u
▶ V.min=minimum element inV
▶ V.max=maximum element inV
10/19

## Page 24
van Emde Boas Definition
Definition
idea
T(u) =T( √u) +O(1)
hierarchical coordinates
wordx=⟨c,i⟩
recursive vEBVof sizeu
▶ V.cluster[i] =vEB of size √u
▶ V.summary[i] =vEB of size √u
▶ V.min=minimum element inV
▶ V.max=maximum element inV
10/19

## Page 25
van Emde Boas Definition
Definition
Figure 1:van Emde Boas structure 1
1Demaine 2021.
11/19

## Page 26
van Emde Boas Operations
Operations
Successor(V,x=⟨c,i⟩)
▶ ifx<V.min returnV.min
▶ ifi<V.cluster[c].max
return⟨c,Successor(V.cluster[c],i)⟩
▶ elsec ′ =Successor(V.summary,c)
return⟨c ′,V.cluster[c ′].min⟩
12/19

## Page 27
Tree view
5.
Tree view
5.1 Indirection
13/19

## Page 28
Tree view
Tree view
Figure 2:van Emde Boas tree view 2
2Demaine 2021.
14/19

## Page 29
Tree view Indirection
Indirection
▶ fromO(lgw)query,O(w)update DS
▶ reduce toO(lgw)update: splitnelements into chuncks of sizeΘ(w)
15/19

## Page 30
Tree view Indirection
Indirection
▶ fromO(lgw)query,O(w)update DS
▶ reduce toO(lgw)update: splitnelements into chuncks of sizeΘ(w)
15/19

## Page 31
Saving space
6.
Saving space
6.1 X-fast trees
6.2 Y-fast trees
16/19

## Page 32
Saving space
Saving space
▶ don’t store empty clusters vEB
▶ V.clusters = hash table
▶ charge each table entry to min in child
▶ space boundΘ(n)via indirection
17/19

## Page 33
Saving space
Saving space
▶ don’t store empty clusters vEB
▶ V.clusters = hash table
▶ charge each table entry to min in child
▶ space boundΘ(n)via indirection
17/19

## Page 34
Saving space
Saving space
▶ don’t store empty clusters vEB
▶ V.clusters = hash table
▶ charge each table entry to min in child
▶ space boundΘ(n)via indirection
17/19

## Page 35
Saving space
Saving space
▶ don’t store empty clusters vEB
▶ V.clusters = hash table
▶ charge each table entry to min in child
▶ space boundΘ(n)via indirection
17/19

## Page 36
Saving space X-fast trees
X-fast trees
▶ don’t store 0s
▶ store a hash table of root-to-1 path
▶ O(lgw)query binary search
▶ Θ(w)update
▶ Θ(nw)space
18/19

## Page 37
Saving space X-fast trees
X-fast trees
▶ don’t store 0s
▶ store a hash table of root-to-1 path
▶ O(lgw)query binary search
▶ Θ(w)update
▶ Θ(nw)space
18/19

## Page 38
Saving space X-fast trees
X-fast trees
▶ don’t store 0s
▶ store a hash table of root-to-1 path
▶ O(lgw)query binary search
▶ Θ(w)update
▶ Θ(nw)space
18/19

## Page 39
Saving space X-fast trees
X-fast trees
▶ don’t store 0s
▶ store a hash table of root-to-1 path
▶ O(lgw)query binary search
▶ Θ(w)update
▶ Θ(nw)space
18/19

## Page 40
Saving space X-fast trees
X-fast trees
▶ don’t store 0s
▶ store a hash table of root-to-1 path
▶ O(lgw)query binary search
▶ Θ(w)update
▶ Θ(nw)space
18/19

## Page 41
Saving space Y-fast trees
Y-fast trees
▶ = X-fast trees
▶ + indirection
▶ O(lgw)query binary search
▶ O(lgw)update amortized
▶ O(lgw)space
19/19

## Page 42
Saving space Y-fast trees
Y-fast trees
▶ = X-fast trees
▶ + indirection
▶ O(lgw)query binary search
▶ O(lgw)update amortized
▶ O(lgw)space
19/19

## Page 43
Saving space Y-fast trees
Y-fast trees
▶ = X-fast trees
▶ + indirection
▶ O(lgw)query binary search
▶ O(lgw)update amortized
▶ O(lgw)space
19/19

## Page 44
Saving space Y-fast trees
Y-fast trees
▶ = X-fast trees
▶ + indirection
▶ O(lgw)query binary search
▶ O(lgw)update amortized
▶ O(lgw)space
19/19

## Page 45
Saving space Y-fast trees
Y-fast trees
▶ = X-fast trees
▶ + indirection
▶ O(lgw)query binary search
▶ O(lgw)update amortized
▶ O(lgw)space
19/19

## Page 46
Thanks

## Page 47
References
References
Demaine, Erik (2021).6.851: Advanced Data Structures (Spring’21).url: https://courses.
csail.mit.edu/6.851/spring21/.
21/19

## Page 48
Acknowledgements
Acknowledgements
The course slides are based on the lectures from previous editions and on similar lectures elsewhere.
List of credits: Erick Demaine, Keith Schwarz
22/19
