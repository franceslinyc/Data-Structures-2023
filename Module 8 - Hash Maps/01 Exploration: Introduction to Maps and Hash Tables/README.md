# Introduction to Maps and Hash Tables

## Introduction

- A map is also known as a dictionary or an associative array. It is built into Python, and you have used it with the syntax `{key1: value1, key2: value3...}`.

## Maps

- We could use a simple array, storing key/value structs.

  - This would give us $\mathcal{O}(n)$ insertions and lookups (or $\mathcal{O}(\log n)$ lookups, if we ordered the array by key).

- We could use an AVL tree, also storing key/value structs.

  - This would give us $\mathcal{O}(\log n)$ insertions and lookups.

- We can do better using a hash table. 

## Hash Tables

- A hash table is like an array, with a few important differences:

  - Elements can be indexed by values other than integers.

  - More than one element may share an index.


## Perfect and Minimally Perfect Hash Functions