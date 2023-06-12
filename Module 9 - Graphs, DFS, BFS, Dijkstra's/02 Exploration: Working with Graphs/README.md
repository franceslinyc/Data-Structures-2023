# Working with Graphs

# Introduction

This class: 

- We are most interested in is if we can get from node $A$ to node $B$.

- We may also be interested in knowing the distance between nodes, and which path is the shortest. 

# Single source reachability

- We might ask: which airports are reachable from PDX?

- We can use a very simple algorithm to answer this question. It looks like this, if we are trying to find reachable vertices from some vertex $v_i$: 

1. Initialize an empty set of reachable vertices.

2. Initialize an empty stack. Add $v_i$ to the stack.

3. If the stack is not empty, pop a vertex $v$ from the stack.

4. If v is not in the set of reachable vertices:

  1. Add it to the set of reachable vertices.

  2. Add each vertex that is direct successor of $v$ to the stack.

5. Repeat from 3.

Finding airports reachable from PDX would look like this:

```{}
reachable: {}
stack: [PDX]


v: PDX
successors: [SEA, SFO]
reachable: {PDX}
stack: [SEA, SFO]


v: SFO
successors: [ORD, PDX]
reachable: {PDX, SFO}
stack: [SEA, ORD, PDX]


v: PDX (already reachable)
successors: --
reachable: {PDX, SFO}
stack: [SEA, ORD]


v: ORD
successors: [MSP, STL]
reachable: {ORD, PDX, SFO}
stack: [SEA, MSP, STL]


v: STL
successors: [LAX, ORD]
reachable: {ORD, PDX, SFO, STL}
stack: [SEA, MSP, LAX, ORD]


v: ORD (already reachable)
successors: --
reachable: {ORD, PDX, SFO, STL}
stack: [SEA, MSP, LAX]


v: LAX
successors: [ORD, SFO]
reachable: {LAX, ORD, PDX, SFO, STL}
stack: [SEA, MSP, ORD, SFO]


v: SFO, ORD (both already reachable)
successors: --
reachable: {LAX, ORD, PDX, SFO, STL}
stack: [SEA, MSP]


v: MSP
successors: [PDX, SFO]
reachable: {LAX, MSP, ORD, PDX, SFO, STL}
stack: [SEA, PDX, SFO]


v: SFO, PDX (both already reachable)
successors: --
reachable: {LAX, MSP, ORD, PDX, SFO, STL}
stack: [SEA]


v: SEA
successors: MSP, PDX
reachable: {LAX, MSP, ORD, PDX, SEA, SFO, STL}
stack: [MSP, PDX]


v: PDX, MSP (both already reachable)
Successors: --
reachable: {LAX, MSP, ORD, PDX, SEA, SFO, STL}
stack: []


Done (stack empty)
reachable: {LAX, MSP, ORD, PDX, SEA, SFO, STL}
```

- We could also use a queue instead of a stack. This would result in a different order of exploration in the graph. 

# Depth-First Search and Breadth-First Search


The general algorithm for DFS and BFS is below. For DFS, we use a stack, and for BFS, we use a queue: 

1. Initialize an empty set of visited vertices.

2. Initialize an empty stack (DFS) or queue (BFS). Add $v_i$ to the stack/queue.

3. If the stack/queue is not empty, pop/dequeue a vertex $v$.

4. Perform any desired processing on $v$.

  1. E.g., check if $v$ meets a desired condition.
  
5. (DFS only): If $v$ is not in the set of visited vertices:

  1. Add $v$ to the set of visited vertices.

  2. Push each vertex that is direct successor of $v$ to the stack.

6. (BFS only):

  1. Add $v$ to the set of visited vertices.

  2. For each direct successor $v^{'}$ of $v$: If $v^{'}$ is not in the set of visited vertices, enqueue it into the queue. 

7. Repeat from 3.


Some comparisons between DFS and BFS:



# Dijkstra’s algorithm: single source lowest-cost paths

- Dijkstra’s algorithm finds the shortest/lowest-cost path from a specified vertex in a graph to all other reachable vertices in the graph.

- Dijkstra’s algorithm is structured very much like DFS and BFS, except in this algorithm, we will use a priority queue to order our search.

  - The priority values used in the queue correspond to the cumulative distance to each vertex added to the priority queue. 

  - Therefore, we are always exploring the remaining node with the minimum cumulative cost.

- Here’s the algorithm, which begins with some source vertex $v_s$:

1. Initialize an empty map/hash table representing visited vertices.

  1. Key is the vertex $v$.

  2. Value is the min distance $d$ to vertex $v$.

2. Initialize an empty priority queue, and insert $v_s$ into it with distance (priority) $0$.

While the priority queue is not empty:

1. Remove the first element (a vertex) from the priority queue and assign it to $v$. Let $d$ be $v$’s distance (priority). 

2. If $v$ is not in the map of visited vertices:

1. Let $d_i$ equal the cost/distance associated with edge $(v, v_i)$.

2. Insert $v_i$ to the priority queue with distance (priority) $d + d_i$.



