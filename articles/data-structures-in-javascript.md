# Data Structures in Javascript

## Arrays

Collection of items stored in contiguous memory locations

Javascript allows values of any type in the same array, and length of 
array is dynamic

Adding items to the array is easy by default (index + 1), but adding to 
the beginning or middle of the array requires indexes of items being 
changed - computational cost

Great for when we have to store individual values and add/delete values 
from the end of the data structure

## Objects

Collection of key-value pairs. Also referred to as map, dictionary, or 
hash-table

Can store values and functions - values are referred to as 'properties', 
and functions as 'methods'

Refer to an object method by it's key (e.g. prop3) as obj.prop3()

Objects are good for grouping related data together

## Stacks

Data structure of a list - LIFO

Example includes undo/redo functionality in a program

Insertion and removal (push, pop) is O(1) as it's always the first element 
in the list

Searching and accessing is O(n) as we must traverse the full list

## Queues

Data structure similar to stack, but FIFO

Example includes printing

Insertion and removal (push, shift) is O(1)

Searching and accessing is O(n)

## Linked Lists

Stores values in form of list, where each value is a 'node'

Each node is connected with the following value in the list (or null if 
last in the list) via a 'pointer'

Singly linked list has [value | pointer] where pointer is to next node, 
doubly linked list has [pointer | value | pointer] where pointers for 
prior and subsequent nodes

First element of the list is the 'head', and last element is the 'tail'

In linked lists, there are no indexes - so we can't access arbitrary 
values via indexes and must instead traverse the linked list

The benefit of no indexes is insertion/deletion in any part of the list is 
more efficient than with arrays - only dealing with the neighbour values 
rather than re-indexing the full array

### Singly linked lists

Insertion is O(1)

Removal, search, and access is O(n)

### Doubly linked lists

This consumes more memory than singly linked lists as we're storing 2 
pointers per value instead of one)

Insertion and removal is O(1)

Search and access is O(n)

## Trees

Data structure that links nodes in a parent/child relationship

Only valid connection between nodes is from parent to child - siblings and 
child-to-parent are not alloweed in trees

Trees must only have one root

Examples include DOM model, and file folders in OS's

### Binary trees

Type of tree where each node has maximum of 2 children

Especially useful in searching, where a binary search tree (BST) is used

Search complexity of BST is O(log(n)) but only if the BST is balanced so 
that roughly half of nodes are discarded per step

### Heaps

Two main types of heaps - MaxHeaps and MinHeaps

In MaxHeaps, parent nodes are always greater than their children, and 
inverse is true with MinHeaps

Only guarantee is this above rule - siblings share no greater 
relationship.

New children are put into the left spaces of the tree first

Binary heaps are frequently used to implement priority queues - used in 
algorithms like Dijkstra's path-finding algorithm

Priority queues are data structures where each element has an associated 
priority, and elements with a higher priority are presented first

## Graphs

Data structure formed by nodes with certain connections between them

Not like trees - no root or leaf nodes, no head or tail

Typically used for social networks and recommendation systems

### Undirected and directed graphs

Graph is undirected if there's no implicit direction in connections 
between nodes - with directed being the inverse

### Weighted and unweighted graphs

Graphs are weighted if connections between nodes have an assigned weight - 
this weight is about the connection, not about the nodes

This is useful for say geolocation data, where weights are distances 
between nodes (locations)

### Representing graphs

Two main methods for coding graphs: adjacency matrix and an adjacency list

Adjacency matrix is a 2D structure representing nodes in graph and 
connections between them - can be stored just as a multi-dismensional 
array where each element of the array is the connections possible from 
that node

e.g. for node A where connections are made to B and C: [0, 1, 1, 0] - 
multidimensional array is effectively rows and columns

Adjacency list is a key-value pair structure where keys represent the node 
on the graph, and values are the connections this node has

e.g. first pair in object is A: ["B", "C"]

Matrices are more efficient when querying for specific connections between 
nodes, and lists are more efficient when adding or removing nodes
