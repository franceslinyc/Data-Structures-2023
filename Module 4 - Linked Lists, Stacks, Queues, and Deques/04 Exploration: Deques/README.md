# Deques

Support

- add front, add back 

- remove front, remove back

## Deque Operations

- `add_front(x)` / `add_back(x)` 

- `remove_front() / remove_back()` 


### Implementing a Deque Using a Linked List

- To add an element to the front of a linked list-based deque like this one, we simply insert a new node after the front sentinel (but before the node immediately following the front sentinel).  

- To add an element to the back of such a deque, we simply have to insert a new node before the back sentinel (but again, after the node immediately prior to the back sentinel).

- Similarly, removing a value would entail removing the node directly after the front sentinel, and removing a value from the back would entail removing the node directly before the back sentinel.

- ......

## Review

As Dynamic Array

push(x)

pop()

enqueue(x)

dequeue()

add_front(x) / add_back(x)

remove_front() / remove_back()

As Linked List 

push(x)

pop()

enqueue(x)

dequeue()

add_front(x) / add_back(x)

remove_front() / remove_back()





