# Exploration: Big O Examples

## $\mathcal{O}(1)$ - Constant Complexity

To identify code that runs in $\mathcal{O}(1)$ time complexity look for code that:

- Does not include any loops based on input size

- Is not recursive

- Does not call any functions which contain operations that scale with input size



## $\mathcal{O}(\log(n))$ - Logarithmic Complexity

To identify code that runs in $\mathcal{O}(\log(n))$ time complexity look for code that:

- Has a loop where the loop counter is divided by a constant

- Moves markers that represent the start or end of a segment of a list so that the working list is divided by a constant at every step

- Traverses once through a data structure that stores data in a branching hierarchy (like a binary tree)

- e.g. binary search algorithm


## $\mathcal{O}(\sqrt(n))$ - Fractional Power Complexity

To identify code that runs in $\mathcal{O}(\sqrt(n))$ time complexity look for code that:

- Has a loop where the loop counts up to the square root of 

- Each iteration takes $\mathcal{O}(1)$ time


## $\mathcal{O}(n)$ - Linear Complexity

To identify code that runs in $\mathcal{O}(n)$ time complexity look for code that:

- Contains a loop that does constant time work and is based directly on the input size

- e.g. linear search algorithm


## $\mathcal{O}(n \log(n))$ - Log-Linear or Linearithmic Complexity

To identify code that runs in $\mathcal{O}(n \log(n))$ time complexity look for code that:

- Has an outer loop that is based on $n$

- Also has an inner loop or recursive call that follow the rules of $\mathcal{O}(\log(n))$ time complexity

- Has an outer loop that is like an $\mathcal{O}(\log(n))$ function but then has an inner loop that loops on all the elements in the input


## $\mathcal{O}(n^2)$ - Quadratic Complexity

To identify code that runs in $\mathcal{O}(n^2)$ time complexity look for code that: 

- Has nested $\mathcal{O}(n)$ loops, assuming the code in the innermost loop runs in constant time


## $\mathcal{O}(2^n)$ - Exponential Complexity

## $\mathcal{O}(n!)$ - Factorial Complexity




**To be continue 04/12/2023** 

