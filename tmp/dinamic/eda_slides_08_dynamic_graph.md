# eda_slides_08_dynamic_graph.pdf
Pages: 19

## Page 1
Dynamic Graph
CS3014 - Estructura de Datos Avanzados
Luciano A. Romero Calla
lromeroc@utec.edu.pe
2026-1

## Page 2
Overview
1. Warming Up
2. The Dynamic Tree Problem
3. Structural Tool: Preferred Paths
4. Heavy-Light Decomposition (HLD)
5. Summary
2 / 16

## Page 3
Warming Up
1.
Warming Up
3 / 16

## Page 4
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

## Page 5
The Dynamic T ree Problem
2.
The Dynamic T ree Problem
5 / 16

## Page 6
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

## Page 7
Structural T ool: Preferred Paths
3.
Structural T ool: Preferred Paths
3.1 Internal Representation: Auxiliary Trees
3.2 The Foundation:access(v)
7 / 16

## Page 8
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

## Page 9
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

## Page 10
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

## Page 11
Heavy-Light Decomposition (HLD)
4.
Heavy-Light Decomposition (HLD)
4.1 HLD: Why the Logarithmic Bound?
4.2 Complexity Proof Sketch
11 / 16

## Page 12
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

## Page 13
Heavy-Light Decomposition (HLD) HLD: Why the Logarithmic Bound?
HLD: Why the Logarithmic Bound?
Moving down aLight Edgereduces the subtree size by at least half.
16
9 6
4 4 5
H L (6≤16/2)
Max Light Edges≈log 2(16) =4
13 / 16

## Page 14
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

## Page 15
Summary
5.
Summary
15 / 16

## Page 16
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

## Page 17
Thanks

## Page 18
References
References
18 / 16

## Page 19
Acknowledgements
Acknowledgements
The course slides are based on the lectures from previous editions and on similar lectures elsewhere.
List of credits: Erick Demaine, Keith Schwarz
19 / 16
