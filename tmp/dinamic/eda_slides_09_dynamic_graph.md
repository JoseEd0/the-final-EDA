# eda_slides_09_dynamic_graph.pdf
Pages: 14

## Page 1
Dynamic Graph
CS3014 - Estructura de Datos Avanzados
Luciano A. Romero Calla
lromeroc@utec.edu.pe
2026-1

## Page 2
Overview
1. Dynamic Connectivity
2. Euler-Tour Trees
2 / 11

## Page 3
Dynamic Connectivity
1.
Dynamic Connectivity
1.1 Problem Categorization
1.2 Tree-Structured Solutions: A Contrast
3 / 11

## Page 4
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

## Page 5
Dynamic Connectivity Problem Categorization
Problem Categorization
Fully Dynamic
Admits arbitrary interleavings of edge insertions and deletions.
Incremental / Decremental
Partially dynamic variants restriction toonlyinsertions oronlydeletions.
5 / 11

## Page 6
Dynamic Connectivity T ree-Structured Solutions: A Contrast
T ree-Structured Solutions: A Contrast
Before considering general graphs, we resolve dynamic connectivity withinforests.
Metric / Feature Link-Cut Trees (Sleator-Tarjan) Euler-Tour Trees (Henzinger-King)
Primary LayoutHeavy-Light Decomposition Flattened Traversal (Euler Tour)
Aggregate BoundsPath Aggregates (O(logn)) Subtree Aggregates (O(logn))
ImplementationComplex splay-tree interlinking Single balanced BST representation
Edge QueriesDifficult to locate arbitrary edges Trivial lookup via sequence positions
6 / 11

## Page 7
Euler-T our T rees
2.
Euler-T our T rees
7 / 11

## Page 8
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

## Page 9
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

## Page 10
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

## Page 11
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

## Page 12
Thanks

## Page 13
References
References
13 / 11

## Page 14
Acknowledgements
Acknowledgements
The course slides are based on the lectures from previous editions and on similar lectures elsewhere.
List of credits: Erick Demaine, Keith Schwarz
14 / 11
