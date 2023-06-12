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




# Dijkstra’s algorithm: single source lowest-cost paths

