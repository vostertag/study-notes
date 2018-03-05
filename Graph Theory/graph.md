# Graph

### Table of Contents

[1. Definition](#definition)  
[2. Vocabulary](#vocabulary)  
[3. Graph representations](#graph-representations)
* [3.1. Adjacency list](#adjacency-list)  
* [3.2. Adjacency matrix](#adjacency-matrix)  
  
[4. Types of graph](#types-of-graph)  
* [4.1. Undirected graph](#undirected-graph)  
* [4.2. Directed graph](#directed-graph)
* [4.3. Weighted graph](#weighted-graph)
* [4.4. Complete graph](#complete-graph)
* [4.5. Simple graph](#simple-graph)
* [4.6. Acyclic graph](#acyclic-graph)
* [4.7. Connected graph](#connected-graph)
* [4.8. Tree](#tree)
* [4.9. Bipartite graph](#bipartite-graph)

[5. Sources](#sources)

## Definition

A **graph data structure** consists of a **finite set of vertices** (or nodes or points), together with a **set of pairs of these vertices**, called **edges** (or arcs, or lines). In *simpler terms*, it is a collection of objects connected together by lines.

**Example:**

![Example of a graph](http://web.cecs.pdx.edu/~sheard/course/Cs163/Graphics/graph1.png)

Set of vertices = {1,2,3,4,5,6}  
The Edge set = {(6,4), (4,5), (4,3), (3,2), (5,2), (2,1), (5,1)} 

## Vocabulary

- **Neighbors**: Vertices that are adjacent (5 and 2 in the figure above for example).
- **Neighborhood** of a vertex: Set of its neighbors.
- **Isolated vertex**: Vertex that has no links to any oder.
- **Distance between 2 vertices**: Length of the shortest path connecting them.
- **Incident edges**: Edges with a common extremity.
- **Eccentricity of a vertex**: Maximum distance involving this vertex.
- **Degree of a vertex**: Number of edges incident to it.
- **Independent edges**: Edges with no common extremity.
- **Parallel edges**: Two or more edges that are incident to the same two vertices.
- **Loop**: Edge that connects a vertex to itself.
- **Order of a graph**: Number of vertices of a graph.
- **Size of a graph**: Number of edges of a graph.
- **Diameter of a graph**: Distance between the two most distant vertices of G.
- **Radius of a graph**: Minimum eccentricity for all the vertices.

## Graph representations

### Adjacency list

An adjacency list is a **collection of unordered lists used to represent a finite graph**. Each list **describes the set of neighbors of a vertex** in the graph.

![Adjacency List](http://lagodiuk.github.io/images/adj_lists/img_2.png)

We mostly use them since they have a much better space complexity than the adjacency matrices.

### Adjacency matrix

An adjacency matrix is a **square matrix used to represent a finite graph**. The elements of the matrix **indicate whether pairs of vertices are adjacent or not** in the graph.

![Adjacency Matrix](http://btechsmartclass.com/DS/images/Graph%20Adjacency%20Matrix%201.jpg)

## Types of graph

### Undirected graph

In an undirected graph, **all the edges are bidirectional**, meaning that we can both ways. When drawing an undirected graph, the edges are typically drawn as lines between pairs of nodes, as illustrated in the following figure.

![Undirected Graph](https://mathinsight.org/media/image/image/small_undirected_network_labeled.png)

### Directed graph

In a directed graph, **all the edges are directed from one vertex to another**. When drawing a directed graph, the edges are typically drawn as arrows indicating the direction, as illustrated in the following figure.

![Directed graph](https://mathinsight.org/media/image/image/small_directed_network_labeled.png)

### Weighted graph

A weighted graph is a graph whose **edges have weights**.

![Weighted graph](https://www.safaribooksonline.com/library/view/php-7-data/9781786463890/assets/image_09_009.png)

### Complete graph

It is an undirected graph in which **every pair of distinct vertices is connected by an edge**, thus they are adjacent.

![Complete graph](https://upload.wikimedia.org/wikipedia/commons/thumb/9/9e/Complete_graph_K7.svg/200px-Complete_graph_K7.svg.png)

A **clique** is a subgraph of a complete graph.

### Simple graph

A simple graph is an **undirected graph with neither multiple (parallel) edges nor self loops**.

### Acyclic graph

A graph **with no cycles**.

### Connected graph

A graph is **connected** when **there is a path between every pair of vertices**. In a connected graph, there are no unreachable vertices. 

### Tree

A tree is a **connected acyclic graph**. More about it [here](https://github.com/vostertag/study-notes/blob/master/Graph%20Theory/tree.md).

![Tree](https://i.stack.imgur.com/HUufp.png)

### Bipartite graph

A bipartite graph or bigraph is a graph whose **vertices are divided into two disjoint sets** U and V (that is, U ∩ V = ∅) such that every edge connects a vertex in U to a vertex one in V.

![Bigraph](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d4/Odd_Cycle_Transversal_of_size_2.png/220px-Odd_Cycle_Transversal_of_size_2.png)

## Sources

* [https://en.wikipedia.org/wiki/Graph_(abstract_data_type)](https://en.wikipedia.org/wiki/Graph_(abstract_data_type))
* [https://www.youtube.com/watch?v=S1Zwhz-MhCs&list=PLGxuz-nmYlQOiIOriTXMEoGoybUC3Jmrn&index=2](https://www.youtube.com/watch?v=S1Zwhz-MhCs&list=PLGxuz-nmYlQOiIOriTXMEoGoybUC3Jmrn&index=2)
* [https://mathinsight.org/image/small_directed_network_labeled](https://mathinsight.org/image/small_directed_network_labeled)
* [https://mathinsight.org/definition/undirected_graph](https://mathinsight.org/definition/undirected_graph)
* [http://web.cecs.pdx.edu/~sheard/course/Cs163/Doc/Graphs.html](http://web.cecs.pdx.edu/~sheard/course/Cs163/Doc/Graphs.html)
* [https://en.wikipedia.org/wiki/Loop_(graph_theory)](https://en.wikipedia.org/wiki/Loop_(graph_theory))
* [https://www.youtube.com/watch?v=QFQlxtz7f6g](https://www.youtube.com/watch?v=QFQlxtz7f6g)
* [https://en.wikipedia.org/wiki/Connectivity_(graph_theory)](https://en.wikipedia.org/wiki/Connectivity_(graph_theory))
* [https://en.wikipedia.org/wiki/Adjacency_list](https://en.wikipedia.org/wiki/Adjacency_list)
* [https://en.wikipedia.org/wiki/Adjacency_matrix](https://en.wikipedia.org/wiki/Adjacency_matrix)
