# 03 Exploration/ Binary Search

## Introduction 

This linear search algorithm, where we must iterate through all of the elements in a collection, has $\mathcal{O}(n)$ complexity - a cost that becomes prohibitive as our collection grows.



## Binary Search Overview 


Recall that algorithms like binary search that cut a problem of size n in half at each iteration until the problem size is 0 have $\mathcal{O}(\log(n))$ runtime complexity.

For $n = 1,000,000$,  

linear search would perform on the order of $n = 1,000,000$, whereas 

binary search would perform on the order of $log(1,000,000) \approx 20$, on average. 

For $n = 4,000,000,000$,  

linear search would perform on the order of $n = 4,000,000,000$, whereas 

binary search would perform on the order of $log(4,000,000,000) \approx 32$, on average. 



