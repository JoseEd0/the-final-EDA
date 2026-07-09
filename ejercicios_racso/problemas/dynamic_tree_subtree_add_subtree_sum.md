# Yosupo - Dynamic Tree Subtree Add Subtree Sum

- Link: https://judge.yosupo.jp/problem/dynamic_tree_subtree_add_subtree_sum
- Tema: Euler-tour tree, dynamic trees, subtree lazy aggregate.
- Relevancia: alta para dynamic graph/tree.

## Resumen del enunciado

Se mantiene un arbol dinamico bajo cortes y enlaces, con operaciones de sumar sobre subarboles y consultar suma de subarboles.

## Idea central

Representar cada arbol por una secuencia Euler dinamica en un BST balanceado. Los subarboles corresponden a intervalos de la secuencia bajo una orientacion de raiz adecuada. Los cortes/enlaces son splits y merges; las sumas/updates se manejan con agregados y lazy propagation.

## Ver solucion teorica

La solucion completa esta en `../latex/soluciones_teoria_racso.tex`.
