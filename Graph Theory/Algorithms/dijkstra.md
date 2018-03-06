# Dijkstra's algorithm

### Table of Contents

[1. Introduction](#introduction)  
[2. How it works](#how-it-works)  
* [2.1. Initialization](#initialization)
* [2.2. Algorithm](#algorithm)
* [2.3. Example](#example)

[3. Implementation](#implementation)  
[4. Complexity](#complexity)  
[5. Sources](#sources)


## Introduction

Dijkstra's algorithm is an algorithm for **finding the shortest paths between nodes in a graph**. The original variant found the shortest path between two nodes, but a more common variant fixes a single node as the source node and finds shortest paths from the source to all other nodes in the graph, producing a **shortest-path tree**.

It works for both **directed and undirected graphs**.

## How it works

### Initialization

* An **array of distances from the source node** to each node in the graph, with the distance being 0 for the source node and infinity for the other nodes.
* A **queue with all of the nodes of the graph**, which will be empty at the end of the algorithm.
* An **empty set in which we will put all of the nodes the algorithm visisted**.

### Algorithm

While the queue of nodes is not empty:

* **Take the node with the smallest distance** from the source in the queue
* **Add it to the set** of visited nodes.
* **For each of its adjacent nodes**, **update their distance** if it is smaller than the existing one.

At the end of this while loop, the array of distances now contains the **shortest path tree from source**.

### Example 

![Dijkstra](https://upload.wikimedia.org/wikipedia/commons/5/57/Dijkstra_Animation.gif)

### Implementation

```python
function Dijkstra(Graph, source):
       dist[source]  := 0                     // Distance from source to source is set to 0
       for each vertex v in Graph:            // Initializations
           if v ≠ source
               dist[v]  := infinity           // Unknown distance function from source to each node set to infinity
           add v to Q                         // All nodes initially in Q

      while Q is not empty:                  // The main loop
          v := vertex in Q with min dist[v]  // In the first run-through, this vertex is the source node
          remove v from Q 

          for each neighbor u of v:           // where neighbor u has not yet been removed from Q.
              alt := dist[v] + length(v, u)
              if alt < dist[u]:               // A shorter path to u has been found
                  dist[u]  := alt            // Update distance of u 

      return dist[]
  end function

```

## Complexity

**Time Complexity**: O(Number of Edges	+	Number of Vertices.log(Number of Vertices))  
**Space Complexity**: O(Number of Vertices²)

## Sources

* [https://brilliant.org/wiki/dijkstras-short-path-finder](https://brilliant.org/wiki/dijkstras-short-path-finder)
* [https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm](https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm)

