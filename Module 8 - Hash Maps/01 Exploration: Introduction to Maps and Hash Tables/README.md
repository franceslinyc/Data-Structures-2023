# Introduction to Maps and Hash Tables

## Introduction

- A map is also known as a dictionary or an associative array. It is built into Python, and you have used it with the syntax `{key1: value1, key2: value3, ...}`.

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

- Often, the hash function computes an index in two steps:

```{}
hash = hash_function(key)
index = hash % array_size
```

The first step computes a value based on the key.

The second step use the `%` operator to make sure the value gets assigned to an index that actually exists in our array.

- An operation like this is known as a folding operation. This can have problems, though:

```{}
"eat" ⇨ 'e' + 'a' + 't' = 101 + 97 + 116 = 314
"ate" ⇨ 'a' + 't' + 'e' = 97 + 116 + 101 = 314
"tea" ⇨ 't' + 'e' + 'a' = 116 + 101 + 97 = 314
```

- We can use a shifting operation, which modifies the individual components of a folding operation based on their position (e.g. multiply by $2^0, 2^1, 2^2, 2^3,  ...$).

```{}
"eat" ⇨ 'e' + 'a' + 't' = 1* 101 + 2* 97 + 4* 116 = 759
"ate" ⇨ 'a' + 't' + 'e' = 1* 97 + 2* 116 + 4* 101 = 733
"tea" ⇨ 't' + 'e' + 'a' = 1* 116 + 2* 101 + 4* 97 = 609
```

- A well-known and widely-used hash function, the DJB2 (Bernstein) hash function (for strings):

```{}
def hash_djb2(s):
    hash = 5381
    for x in s:
        # hash * 33 + c (bitshift left 5 places = * 32)
        hash = ( (hash << 5) + hash ) + ord(x) 
    return hash & 0xFFFFFFFF
```

## Perfect and Minimally Perfect Hash Functions

