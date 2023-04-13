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


### Binary Search Implementation

```{}
def selection_sort(list: list):
    """
    Sorts list in non-descending order
    Complexity:  O(n**2)
    """
    for i in range(len(list) - 1):
        min_index = i
        
        # Loop over the remaining unsorted part of the list 
        # and find the index of the smallest element
        for j in range(i + 1, len(list)):
            if list[j] < list[min_index]:
                min_index = j
        
        # Swap the smallest element found with the current element 
        temp = list[min_index]
        list[min_index] = list[i]
        list[i] = temp
```

```{}
def binary_search(list: list, target: object) -> int:
    """
    Searches for target, returns index where first found else -1
    Complexity:  O(log n)
    Precondition:  List must be sorted in non-descending order
    """

    # set range of possible indices to entire list
    low = 0
    high = len(list) - 1

    while low <= high:
        
        
        mid = (low + high) // 2 # find the midpoint of all indices still possible

        
        if target < list[mid]:   # Since value is lower, if it's there will be left of mid
            high = mid - 1
        
        elif target > list[mid]: # Since value is higher, if it's there will be right of mid
            low = mid + 1
        
        else:                    # Neither higher not lower, it's a match - found
            return mid

    
    return -1  # All indices have been eliminated from consideration, not found
```


**selection_sort is confusing 04/12/2023** 





