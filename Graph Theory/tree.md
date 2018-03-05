# Tree

I would advise to first read the note on [graphs](https://github.com/vostertag/study-notes/blob/master/Graph%20Theory/graph.md) before this one.

### Table of Contents

[1. Definition](#definition)  
[2. Vocabulary](#vocabulary)  
[3. Types of trees](#types-of-trees)  
* [3.1. Binary tree](#binary-tree)
* [3.2. Binary search tree](#binary-search-tree)
* [3.3. Heap](#heap)

[4. Sources](#sources)

## Definition

A tree is a **connected acyclic graph**, meaning that there is no cycles and that there is a path between every pair of vertices.

This is an example of a tree:

![Tree](https://www.cpp.edu/~ftang/courses/CS241/notes/images/trees/tree1.bmp)

But these graphs are **not** trees:

![Not a tree](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a3/Directed_graph_with_branching_SVG.svg/76px-Directed_graph_with_branching_SVG.svg.png)
(There is a cycle, so it cannot be a tree)

![Not a tree](https://upload.wikimedia.org/wikipedia/commons/thumb/7/78/Directed_graph%2C_disjoint.svg/99px-Directed_graph%2C_disjoint.svg.png)
(All the nodes are not connected, so it cannot be a tree)

## Vocabulary

* **Root**: Top node of a tree.
* **Child**: A node directly connected to another node when moving away from the Root.
* **Parent**: The converse notion of a child.
* **Siblings**: A group of nodes with the same parent.
* **Descendant**: A node reachable by repeated proceeding from parent to child.
* **Ancestor**: A node reachable by repeated proceeding from child to parent.
* **Leaf**: A node with no children.
* **Internal Node**: A node with at least one child.
* **Degree**: The number of subtrees of a node.
* **Path**: A sequence of nodes and edges connecting a node with a descendant.
* **Level**: The level of a node is defined by 1 + (the number of connections between the node and the root).
* **Forest**: A forest is a set of n ≥ 0 disjoint trees.

## Types of trees

### Binary tree

A **binary tree** is a tree data structure in which **each node has at most two children**.

![Binary tree](https://camo.githubusercontent.com/cf5457b211eb4517666a33c08385f794b62d955f/68747470733a2f2f692e737461636b2e696d6775722e636f6d2f48557566702e706e67)

### Binary search tree

A **binary search tree** is a **binary tree**, in which the key in each node must be **greater than or equal to any key stored in the left** sub-tree, and **less than or equal to any key stored in the right** sub-tree.

![BST](https://upload.wikimedia.org/wikipedia/commons/thumb/d/da/Binary_search_tree.svg/300px-Binary_search_tree.svg.png)

### Heap

A **heap** is a tree in which a **parent node's key is alway greater or equal (in a max heap) or less than or equal (in a min heap) than its children's key**.

![Heap](https://upload.wikimedia.org/wikipedia/commons/thumb/3/38/Max-Heap.svg/240px-Max-Heap.svg.png)

## Sources

* [https://en.wikipedia.org/wiki/Tree_(data_structure)](https://en.wikipedia.org/wiki/Tree_(data_structure))
* [https://medium.freecodecamp.org/all-you-need-to-know-about-tree-data-structures-bceacb85490c](https://medium.freecodecamp.org/all-you-need-to-know-about-tree-data-structures-bceacb85490c)
* [https://en.wikipedia.org/wiki/Heap_(data_structure)](https://en.wikipedia.org/wiki/Heap_(data_structure))
