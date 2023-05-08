# Dynamic Arrays

## Introduction 

## Dynamic Arrays

The following are the typical operations: 
 
- get()

- set()

- insert()

- remove()


To implement a dynamic array, we need to keep track of three things:

- `data` 

- `size` (the number of elements currently stored in the array)

- `capacity` (the total number of elements the underlying data storage array has space for before it must be resized)


## Inserting

## Time Complexity

- `append()` or `insert()` amortized $\mathcal{O}(1)$ 

need to resize when array is full 

worst case $\mathcal{O}(n)$ 

- `resize()` $\mathcal{O}(n)$ 

- `get()` $\mathcal{O}(1)$

- `set()` $\mathcal{O}(1)$

- `remove()` $\mathcal{O}(n)$ 

need to fill empty space when deleting an element 









