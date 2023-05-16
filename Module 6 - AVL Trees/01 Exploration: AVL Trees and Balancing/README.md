# AVL Trees and Balancing

## Introduction

- For BST, time complexity is $\mathcal{O}(h)$, where $h$ is height of the tree. 

- For balanced BST, time complexity is $\mathcal{O}(\log(n))$. 

- For very unbalanced BST, time complexity can be $\mathcal{O}(n)$. 

- **AVL tree** is a type of self-balancing BST. 

## Balance 

- A BST is **height-balanced** if, at every node in the tree, the heights of the node's left and right subtrees **differ by at most 1**. 

- A BST node's **balance factor** can be used to determine if a BST is height-balanced. 

`balanceFactor(N) = height(N.right) - height(N.left)`

- If `balanceFactor(N) < 0`, the node is left-heavy.  

- If `balanceFactor(N) > 0`, the node is right-heavy.  

- If all nodes have a balance factor $-1, 0, 1$, then the tree is height-balanced. 

- Balance needs to be maintained in every node. 




