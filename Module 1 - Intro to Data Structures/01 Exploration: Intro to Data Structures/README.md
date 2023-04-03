# Exploration: Intro to Data Structures

## Course Overview

In this course, we’ll have two primary goals:

- To become familiar with a collection of foundational data structures that you’ll use frequently as a programmer, and that will be useful in a wide variety of contexts. These include lists, queues, stacks, trees, hash tables, graphs, and more.

- To understand how to analyze and manage the complexity associated with data structures and their operations. This will allow us to keep our programs’ running times and memory usage under control.

None of the data structures we’ll see in this class (nor any beyond this class) is a perfect data structure for all situations. Each one involves trade-offs in terms of the following things:

- How long its operations take to run

- How much space it requires to store a collection of data of a given size

- How hard it is to implement

With the understanding you’ll gain in this class about data structures and how to analyze them, you’ll be able to compare data structures and choose/design the best one for a particular task.

Along the way, we’ll also learn a few other things, such as the distinctions between abstract data types (ADTs) and data structures. 

## Abstract Data Types (ADTs) vs Data Dtructures

- ADTs are data types modeled from the point of view of the user of that data type (e.g., a Python programmer using a dictionary).

  - For example, a hash table can be implemented with either a single list or a collection of lists. The user of the hash table doesn’t need to know (or care about) how it’s implemented, only how it behaves.
  
- Data structures are concrete representations of data, i.e., a data type from the point of view of the implementer. The user may not care how the hash table is implemented, but it might make a lot of difference to the developer of that hash table.

