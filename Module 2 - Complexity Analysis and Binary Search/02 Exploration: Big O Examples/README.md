# Exploration: Big O Examples


## $\mathcal{O}(1)$ - Constant Complexity

To identify code that runs in $\mathcal{O}(1)$ time complexity look for code that:

- Does not include any loops based on input size

- Is not recursive

- Does not call any functions which contain operations that scale with input size

e.g.

```{}
def insert_at_n(l,n):
    l[n] = "Hello"
```

## $\mathcal{O}(\log(n))$ - Logarithmic Complexity

To identify code that runs in $\mathcal{O}(\log(n))$ time complexity look for code that:

- Has a loop where the loop counter is divided by a constant

- Moves markers that represent the start or end of a segment of a list so that the working list is divided by a constant at every step

- Traverses once through a data structure that stores data in a branching hierarchy (like a binary tree)

- Is most often seen when working with trees or when you are using binary search to find elements within a sorted list

- e.g. binary search

e.g. 

```{}
def split_in_two(i):
    while i > 1:
        i = i/2
```

## $\mathcal{O}(\sqrt(n))$ (= $\mathcal{O}(n^c)$, $0 < c < 1$) - Fractional Power Complexity 

To identify code that runs in $\mathcal{O}(\sqrt(n))$ time complexity look for code that:

- Has a loop where the loop counts up to the square root of 

- Each iteration takes $\mathcal{O}(1)$ time 

e.g. 

```{}
def is_prime(i):
    k = 2
    while k*k <= i:
      if (i%k == 0):
       return False
      k = k + 1
```

Note. Even numbers are not prime except for 2, so odd numbers within the range $[2, \sqrt(n)]$. 

## $\mathcal{O}(n)$ - Linear Complexity

To identify code that runs in $\mathcal{O}(n)$ time complexity look for code that:

- Contains a loop that does constant time work and is based directly on the input size

- e.g. linear search 


## $\mathcal{O}(n \log(n))$ - Log-Linear or Linearithmic Complexity

To identify code that runs in $\mathcal{O}(n \log(n))$ time complexity look for code that:

- Has an outer loop that is based on $n$

- Also has an inner loop or recursive call that follow the rules of $\mathcal{O}(\log(n))$ time complexity

- Has an outer loop that is like an $\mathcal{O}(\log(n))$ function but then has an inner loop that loops on all the elements in the input

- Is pretty common in things like sorts, but can be tricky because it often involves some recursion. 

- Is typically some combination of a standard loop and another iteration that divides things in half.

e.g. fastest possible comparison sort 

e.g. 

```{}
def split_in_two(i):
  for j in range (i):
    k=i
    while k > 1:
        k = k/2
```


## $\mathcal{O}(n^2)$ - Quadratic Complexity

To identify code that runs in $\mathcal{O}(n^2)$ time complexity look for code that: 

- Has nested $\mathcal{O}(n)$ loops, assuming the code in the innermost loop runs in constant time

- e.g. bubble sort, insertion sort 

e.g. 

```{}
def bubble(arr):
    l = len(arr)        
    for a in range(l):
        for b in range(l-1):
            if (arr[a] < arr[b]):
                arr[a], arr[b] = arr[b], arr[a]
    return arr 
```


e.g. 

```{}
for i in range(n):
  for j in range(i):
   ...
```

Note. 

$0 + 1 + ... + (n - 1) = \sum_{i=0}^{n - 1} i = \frac{n (n - 1)} {2} = \frac{1}{2} n^2 - \frac{1}{2} n.$

## $\mathcal{O}(2^n)$ $(= \mathcal{O}(2^{\text{poly}(n)}))$ - Exponential Complexity

e.g. $2^n$, $2^{n^2}$

To identify code that runs in $\mathcal{O}(2^n)$ time complexity look for code that: 

- Has a recursive call which decrements a count by a constant factor and calls itself more than once 

- Is typically implemented recursively 

- e.g. matrix chain multiplication via brute-force search

e.g.

```{}
def fibonacci(number):
    if number == 0: return 0
    elif number == 1:
        return 1
    else:
        return fibonacci(number-1) + fibonacci(number-2)
```


## $\mathcal{O}(n!)$ - Factorial Complexity

- Is another class to stay away from if possible

- e.g. traveling salesman problem via brute-force search
