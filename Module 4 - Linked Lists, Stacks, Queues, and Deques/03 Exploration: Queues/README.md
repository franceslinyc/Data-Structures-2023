# Queues (first in, first out (or FIFO))

## Queue Operations

- A queue is a data structure that imposes a **first in, first out (or FIFO)** ordering on the elements it stores.

- Unlike a stack, the first element to be removed from a queue is the first one that was placed into it. 

- The queue ADT specifies an abstract structure with two ends: a front and a back. Every time a new element is inserted into the queue, it is inserted at the back, and every time an element is removed from the queue, it is removed from the front.


### `enqueue(x)`

- Add $x$ to the back of the queue. This item now represents the back of the queue.

### `dequeue()`

- Remove the first item in the queue and returns its value. The item behind it is now at the front of the queue. 


![](queue.png)


## Implementing a Queue Using a Linked List

e.g.

`                            tail`

`                            |`

`head -> 1 next -> 3 next -> 5 next -> None`

`enqueue(7) # Add 7`

`                                      tail`

`                                      |`

`head -> 1 next -> 3 next -> 5 next -> 7 next -> None`

`dequeue() # Remove 1` 

`head -> 3 next -> 5 next -> 7 next -> None`

`dequeue() # Remove 3`

`head -> 5 next -> 7 next -> None`


## Implementing a Queue Using a Dynamic Array
























