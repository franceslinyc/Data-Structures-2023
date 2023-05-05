# Introduction to Linked Lists

## Introduction

## Choosing Linked Lists

## Linked Lists

### Doubly Linked Lists

- Each node keeps track of both the next node and the previous node.

- Unlike singly linked list, it is easy to iterate both forward and backward.

### Sentinels

- Sentinel nodes (or nodes or headers) help us handle special cases, such as operations at the start of a linked list, or when a linked list is empty.



## Operations

- A major concern is not breaking the chain and losing track of a node. 

### 1. Get by Value

- It's a linear (i.e. sequential) search.


### 2. Get by Index (Worse vs. Arrays)

- This is the same as get by value, except we just advance $n$ times where $n$ is the index we are looking for. 

- This is the **major downside** to linked lists compared to arrays. We must traverse over all n links before we can access the data, whereas with dynamic arrays, we can directly access any index. 


### 3. Add




- In a **doubly linked list**, we need to update the `prev` references as well. 

### 4. Remove




- In a **doubly linked list**, we would also need to update b’s previous property to point to a.
