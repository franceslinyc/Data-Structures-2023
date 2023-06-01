# Hash Table Collisions

## Introduction

- Sometimes, hash functions will generate the same output for two different inputs. This is called a collision. 

- There are two ways to accommodate. 

  1. via chaining (use linked list-based buckets or chains)

  2. via open addressing (store directly in hash table array)

## Collision resolution with chaining

- The linked lists are commonly referred to as buckets or chains, and this technique of collision resolution is known as chaining. 

![](chaining.png)

- In a chained hash table, accessing the value for a particular key would follow this procedure:

  - Compute the element’s bucket using the hash function

  - Search the data structure at that bucket for the element using the key (e.g., iterate through the items in the linked list).

- Adding or removing an element would follow a similar process, except we would add or remove the element to or from the appropriate bucket’s data structure.

- The load factor of a hash table is the average number of elements in each bucket:

$\lambda = n / m$, 
where 

  - $\lambda$ is the load factor,

  - $n$ is the total number of elements stored in the table,

  - $m$ is the number of buckets.


## Collision resolution with open addressing



- The procedure for inserting an element in an open addressing-based hash table looks like this: 

- This process of searching for an empty position is called probing. There are many different probing schemes:

![](probing.png)

## Complexity Analysis of Open Address Hashing



