# Stacks

## Introduction 

- Stacks function much like a stack of pancakes (or a stack of papers, but pancakes are tastier). As the developers finish their pancakes, they refill their plates with the fresh, hot pancakes from the top of the stack. The last pancake added to the stack is the first one consumed. 

- Queues function like the lines at the supermarket where people go to purchase instant pancake mix.

- Deques are a less common ADT with similarities to both of these ADTs. In a deque, items can be added or removed from either end. You can think of them as a combination of a stack and a queue. 

## Stack Operations

- A stack is a linear ADT that imposes a last in, first out (or LIFO) order on elements. I.e., in a stack, the last element that was inserted must always be the first one to be removed. 



### push(x)

- Push an item x onto the top of the stack. This item is now the new top of the stack. 

### pop()

- Remove the top item from the stack and returns its value. 

### peek() or top()

- Return the value of the top item in a stack without removing it.


## Implementing a Stack Using a Linked List

- We can implement a stack using a singly linked list, where the head of the list corresponds to the top of the stack.

e.g.

head -> 4 next -> 2 next -> None

`push(8)`

head -> 8 next -> 4 next -> 2 next -> None

`pop() # remove 8` 

head -> 4 next -> 2 next -> None

`pop() # remove 4` 

head -> 2 next -> None


## Implementing a Stack Using a Dynamic Array

- When using a dynamic array as the underlying storage, it is easiest to have the end of the array represent the top of the stack. Therefore, when a new element is pushed onto a stack that is using a dynamic array for its underlying storage, that element is inserted at the end of the array.

e.g. 

[2 4]

`push(8)`

[2 4 8]

`push(16)` and `push(32)` (in this order)

[2 4 8 16 32]

`pop() # remove 32` 
 
[2 4 8 16]


