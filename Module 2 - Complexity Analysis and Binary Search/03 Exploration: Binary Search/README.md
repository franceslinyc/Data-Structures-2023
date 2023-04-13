# 03 Exploration/ Binary Search

## Introduction 

This linear search algorithm, where we must iterate through all of the elements in a collection, has $\mathcal{O}(n)$ complexity - a cost that becomes prohibitive as our collection grows.


## Binary Search Overview 

### Comparing linear search vs binary search

Recall that algorithms like binary search that cut a problem of size n in half at each iteration until the problem size is 0 have $\mathcal{O}(\log(n))$ runtime complexity.

For $n = 1,000,000$,  

linear search would perform on the order of $n = 1,000,000$, whereas 

binary search would perform on the order of $\log(1,000,000) \approx 20$, on average. 

For $n = 4,000,000,000$,  

linear search would perform on the order of $n = 4,000,000,000$, whereas 

binary search would perform on the order of $\log(4,000,000,000) \approx 32$, on average. 


### How binary search works 

At each iteration, we:

- Compare the query value (i.e., the value we are searching for) to the value at the midpoint of the list.

- If this midpoint value matches the query value, immediately return a designated value to indicate that the query value has been found.

- Otherwise: 

  1. If the query value is less than the value at the list’s midpoint, repeat, focusing only on the “lower” half of the list (i.e., the half of the list before the midpoint).

  2. If the query value is greater than the value at the list’s midpoint, repeat, focusing only on the “upper” half of the list (i.e., the half of the list after the midpoint).

  3. If the list under consideration has size 0, we can stop because we have eliminated every index as a possibility. Here, we can either return a designated value to indicate that the query value hasn’t been found (e.g., -1, since it is not a valid index).



















