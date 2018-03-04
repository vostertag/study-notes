# Tree

### Table of Contents

[1. Tree Structure](#tree-structure)  
[2. Definition](#definition)  
[3. Terminology](#terminology)

## Tree Structure

A **tree structure** or **tree diagram** is a way of representing the **hierarchical nature of a structure in a graphical form**. It is named a "tree structure" because the classic representation resembles a tree, even though the chart is generally upside down compared to an actual tree, with the "root" at the top and the "leaves" at the bottom.

![Tree Structure](https://upload.wikimedia.org/wikipedia/commons/thumb/c/cd/Binary_tree_structure.svg/300px-Binary_tree_structure.svg.png)

## Definition

In computer science, a **tree** is an abstract data structure that simulates a hierarchical [tree structure](#tree-structure), with a root value and subtrees of children with a parent node, represented as a set of linked nodes.

![Tree](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f7/Binary_tree.svg/220px-Binary_tree.svg.png)

A **tree does not have any cycle**, can only have **one root**, and each node can only have **one parent**.

So these examples **are _NOT_ trees**:

![not a tree](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e2/Graph_single_node.svg/70px-Graph_single_node.svg.png)

![not a tree](https://upload.wikimedia.org/wikipedia/commons/thumb/1/1c/Directed_graph%2C_cyclic.svg/161px-Directed_graph%2C_cyclic.svg.png)

![not a tree](https://upload.wikimedia.org/wikipedia/commons/thumb/7/78/Directed_graph%2C_disjoint.svg/99px-Directed_graph%2C_disjoint.svg.png)

![not a tree](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a3/Directed_graph_with_branching_SVG.svg/76px-Directed_graph_with_branching_SVG.svg.png)

## Terminology

- **Root**: The top node in a tree.
- **Child**: A node directly connected to another node when moving away from the Root.
- **Parent**: The converse notion of a child.
- **Siblings**: A group of nodes with the same parent.
- **Descendant**: A node reachable by repeated proceeding from parent to child.
- **Ancestor**: A node reachable by repeated proceeding from child to parent.
- **Leaf:** A node with no children.
- **Internal Node**: A node with at least one child.
- **Degree**: The number of subtrees of a node.
- **Edge**: The connection between one node and another.
- **Path**: A sequence of nodes and edges connecting a node with a descendant.
- **Level**: The level of a node is defined by 1 + (the number of connections between the node and the root).
- **Height of a node**: The height of a node is the number of edges on the longest path between that node and a leaf.
- **Height of a tree**: The height of a tree is the height of its root node.
- **Depth**: The depth of a node is the number of edges from the tree's root node to the node.
- **Forest**: A forest is a set of n ≥ 0 disjoint trees.
