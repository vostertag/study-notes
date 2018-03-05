# Searching in a graph (BFS & DFS)

### Table of Contents

[1. Introduction](#introduction)  
[2. BFS](#bfs)  
[3. DFS](#dfs)  
[4. BFS vs DFS](#bfs-vs-dfs)  
[5. Complexity](#complexity)  
[6. Sources](#sources)

## Introduction

There are two well-known algorithms used for traversing and searching a node in a graph:

* **BFS (Breadth First Search)**
* **DFS (Depth First Search)**

Both algorithms **begin with a given starting node** usually called the **root** or the **source node**. They can also be used to find out whether a node is reachable from a given node or not.

## BFS

The BFS algorithm **explores the neighbor nodes first**, before moving to the next level neighbours. 

**Steps:**

* Visit the adjacent unvisited vertex. Mark it as visited. Display it. Insert it in a queue.
* If no adjacent vertex is found, remove the first vertex from the queue.
* Repeat until the queue is empty

![BFS](https://upload.wikimedia.org/wikipedia/commons/5/5d/Breadth-First-Search-Algorithm.gif)

## DFS

The DFS algorithm **explores as far as possible along each branch** before backtracking.

**Steps:**

* Given a starting active node, visit an adjacent unvisited vertex. Mark this vertex as visited. Push it in a stack. This vertex becomes the active node.
* If no adjacent vertex to the active node is found, pop up the active node from the stack. Pop up all the vertices from the stack, which do not have adjacent unvisited vertices. The first vertex in the stack (if any) which has at least one unvisited adjacent vertex becomes the active node.
* Repeat until the stack is empty.

![DFS](https://upload.wikimedia.org/wikipedia/commons/7/7f/Depth-First-Search.gif)

## BFS vs DFS

Whether one should use BFS or DFS **depends on the tree that is being searched**.

* If you know a solution is not far from the root of the tree, a breadth first search (BFS) might be better.
* If the tree is very deep and solutions are rare, depth first search (DFS) might take an extremely long time, but BFS could be faster.
* If the tree is very wide, a BFS might need too much memory, so it might be completely impractical.
* If solutions are frequent but located deep in the tree, BFS could be impractical.
* If the search tree is very deep you will need to restrict the search depth for depth first search (DFS), anyway (for example with iterative deepening).

## Complexity

**Time**: O(Number of vertices + Number of edges)  
**Space**: O(Number of vertices)

## Sources

* [https://en.wikipedia.org/wiki/Breadth-first_search](https://en.wikipedia.org/wiki/Breadth-first_search)
* [https://en.wikipedia.org/wiki/Depth-first_search](https://en.wikipedia.org/wiki/Depth-first_search)
* [https://stackoverflow.com/a/3332994](https://stackoverflow.com/a/3332994)
