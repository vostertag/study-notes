# Bellman-Ford

### Table of Contents

[1. Introduction](#introduction)  
[2. How it works](#how-it-works)
* [2.1. Initialization](#initialization)
* [2.2. Relaxation](#relaxation)
* [2.3. Check for negative-weight cycles](#check-for-negative-weight-cycles)
* [2.4. Example](#example)

[3. Implementation](#implementation)  
[4. Complexity](#complexity)  
[5. Sources](#sources)

## Introduction

Just like [Dijkstra](https://github.com/vostertag/study-notes/blob/master/Graph%20Theory/Algorithms/dijkstra.md)'s algorithm, Bellman-Ford's algorithm **computes shortest paths from a single source vertex to all of the other vertices** in a weighted digraph. The difference here is that, unlike Dijkstra, **graphs with negative weights can be used**.

## How it works

### Initialization

* An **array of distances from the source node** to each node in the graph, with the distance being 0 for the source node and infinity for the other nodes.
* An **null array with the nodes' predecessors** so that we can create a path later.

### Relaxation

For each edge, **if the distance is smaller than the current one**, than **update it** and **change the predecessor**. This is done **|V - 1| times**, with V the number of vertices. 

### Check for negative-weight cycles

For each edge, if we find a **distance that is even smaller than the one we have after the relaxation step**, it means that **there is a negative-weight cycle in the graph**, which makes the problem **impossible** to solve.

### Example

[https://www.youtube.com/watch?v=obWXjtg0L64](https://www.youtube.com/watch?v=obWXjtg0L64)

## Implementation

```python

function BellmanFord(list vertices, list edges, vertex source)
   ::distance[],predecessor[]
   
   // This implementation takes in a graph, represented as
   // lists of vertices and edges, and fills two arrays
   // (distance and predecessor) with shortest-path
   // (less cost/distance/metric) information
   
   // Step 1: initialize graph
   for each vertex v in vertices:
       distance[v] := inf             // At the beginning , all vertices have a weight of infinity
       predecessor[v] := null         // And a null predecessor
   
   distance[source] := 0              // The weight is zero at the source
   
   // Step 2: relax edges repeatedly
   for i from 1 to size(vertices)-1:
       for each edge (u, v) with weight w in edges:
           if distance[u] + w < distance[v]:
               distance[v] := distance[u] + w
               predecessor[v] := u
   
   // Step 3: check for negative-weight cycles
   for each edge (u, v) with weight w in edges:
       if distance[u] + w < distance[v]:
           error "Graph contains a negative-weight cycle"
   
   return distance[], predecessor[]

```

## Complexity

**Time complexity**: O(Number of vertices * Number of edges)  
**Space complexity**: O(Number of vertices)

## Sources

* [https://www.youtube.com/watch?v=obWXjtg0L64](https://www.youtube.com/watch?v=obWXjtg0L64)
* [https://www.youtube.com/watch?v=9PHkk0UavIM](https://www.youtube.com/watch?v=9PHkk0UavIM)
* [https://brilliant.org/wiki/bellman-ford-algorithm/](https://brilliant.org/wiki/bellman-ford-algorithm/)
* [https://en.wikipedia.org/wiki/Bellman%E2%80%93Ford_algorithm](https://en.wikipedia.org/wiki/Bellman%E2%80%93Ford_algorithm)

