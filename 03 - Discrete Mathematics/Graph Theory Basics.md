---
title: "Mathematics | Graph Theory Basics - Set 2"
subject: "Discrete Mathematics"
topic: "Graphs"
source: "https://www.geeksforgeeks.org/engineering-mathematics/mathematics-graph-theory-basics/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Graphs"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/graphs
---


> [!abstract] Mathematics | Graph Theory Basics - Set 2
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Graphs`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/mathematics-graph-theory-basics/)

---

# Mathematics | Graph Theory Basics - Set 2

Graph theory is a basic branch of discrete mathematics that mainly focuses on the relationship between objects. These objects are called vertices and these vertices are joined by edges. Graphs are common in computer science, network analysis, and many other everyday uses because they provide a good representation of connection, relationship, and process.
## Graph Theory Basics
A graph is a structure amounting to a set of objects in which some pairs of the objects are in some sense "related". The objects of the graph correspond to vertices and the relations between them correspond to edges. A graph is depicted diagrammatically as a set of dots depicting vertices connected by lines or curves depicting edges. 
Formally, 
A graph G = {V , E } consists of V , a non-empty set of vertices (or nodes), and E, a set of edges. Each edge has either one or two vertices associated with it, called its endpoints.
## **Types of Graph**
There are several types of graphs distinguished on the basis of edges, their direction, their weight etc. 
**Simple graph:** A graph in which each edge connects two different vertices and where no two edges connect the same pair of vertices is called a simple graph. For example, Consider the following graph
![SIMPLE-GRAPH](assets/SIMPLE-GRAPH-768x507-bc51c033dd.jpg)
Simple Graph
The above graph is a simple graph, since no vertex has a self-loop and no two vertices have more than one edge connecting them. The edges are denoted by the vertices that they connect { A,B } is the edge connecting vertices A and B.
**Multigraph:** A graph in which multiple edges may connect the same pair of vertices is called a [multigraph](https://www.geeksforgeeks.org/data-visualization/directed-graphs-multigraphs-and-visualization-in-networkx/). Since there can be multiple edges between the same pair of vertices, the **multiplicity** of edge tells the number of edges between two vertices. 
![](assets/hamiltonian-circuit2-2-f11811b1a9.jpg)
The above graph is a multigraph since there are multiple edges between B and C . The multiplicity of the edge {B,C} is 2. 
In some graphs, unlike the one's shown above, the edges are directed. This means that the relation between the objects is one-way only and not two-way. The direction of the edges may be important in some applications. 
Based on whether the edges are directed or not we can have directed graphs and undirected graphs. This property can be extended to simple graphs and multigraphs to get simple directed or undirected simple graphs and directed or undirected multigraphs. 
### **Basic Graph Terminology**
In the above discussion some terms regarding graphs have already been explained such as vertices, edges, directed and undirected edges etc. There are more terms which describe properties of vertices and edges. 
- **Adjacency**: In a graph G two vertices u and v are said to be adjacent if they are the endpoints of an edge. The edge {**u**,**v** }−**e** is said to be incident with the vertices. In case the edge is directed, u is said to be adjacent to v and v is said to be adjacent from u. Here, u is said to be the initial vertex and v is said to the terminal vertex.
- **Degree:** The degree of a vertex is the number of edges incident with it, except the self-loop which contributes twice to the degree of the vertex. Degree of a vertex u is denoted as deg(u)
- In case of directed graphs, the degree is further classified as in-degree and out-degree. The in-degree of a vertex is the number of edges with the given vertex as the terminal vertex. The out-degree of a vertex is the number of edges with the given vertex as the initial vertex. In-degree is denoted as deg-(u) and out-degree is denoted as deg+(u).
**Note: If a vertex has zero degree, it is called isolated. If the degree is one then it's called** [**pendant.**](https://www.geeksforgeeks.org/dsa/pendant-vertices-non-pendant-vertices-pendant-edges-and-non-pendant-edges-in-graph/)
- **Handshaking Theorem:** What would one get if the degrees of all the vertices of a graph are added. In case of an undirected graph, each edge contributes twice, once for its initial vertex and second for its terminal vertex. So the sum of degrees is equal to twice the number of edges. This fact is stated in the Handshaking Theorem.
> Let
>
>
$$
G = (V, E)
$$
>
>  be an undirected graph with
>
>
$$
e
$$
>
>  edges. Then
> 2**e** = ∑**u** ∈ **V** **deg** ( **u** )
> In case G is a directed graph,
> ∑ **u** ∈ **V** ​**deg**− ( **u** ) = ∑ **u** ∈ **V** **deg**+ ( **u** ) = **|E|**
> The handshaking theorem, for undirected graphs, has an interesting result - An undirected graph has an even number of vertices of odd degree.
> **Proof:** Let V₁ and V₂ be the sets of vertices with even and odd degrees, respectively.
>
> We know from the [Handshaking Theorem](https://www.geeksforgeeks.org/engineering-mathematics/mathematics-graph-theory-basics/) that:
>
> => 2e = sum of degrees of all vertices
>  => 2e = ∑ deg(u) over all u in V
>  => 2e = ∑ deg(u) over u in V₁ + ∑ deg(u) over u in V₂
>
> The sum of degrees of vertices with even degrees is even. The LHS is also even, which means that the sum of degrees of vertices with odd degrees must be even. 
> Thus, the number of vertices with odd degree is even. 
## **Some Special Simple Graphs**
**Complete Graphs:** A [simple graph](https://www.geeksforgeeks.org/dsa/number-of-simple-graph-with-n-vertices-and-m-edges/) of 
$$
n
$$
vertices having exactly one edge between each pair of vertices is called a complete graph. A complete graph of 
$$
n
$$
vertices is denoted by Kn . Total number of edges are n(n-1)/2 with n vertices in complete graph. 
![Complete Graphs, K2, K3.. to K7](assets/complete-graphs-1-c022e6467f.jpg)
**Cycle Graph :**  **Cycles** are simple graphs with **n ≥ 3** vertices and edges: {1, 2}, {2, 3}, ..., {n−1, n}, and {n, 1}. A cycle with **n** vertices is denoted as **Cₙ**. Total number of edges are n with n vertices in cycle graph. 
![](assets/cycles-300x132-6cebded95b.jpg)
**Wheel Graph:** A wheel is just like a cycle, with one additional vertex which is connected to every other vertex. Wheels of 
$$
n
$$
vertices with 1 addition vertex are denoted by Wn . Total number of edges are 2(n-1) with n vertices in [wheel graph.](https://www.geeksforgeeks.org/python/wheel-graph-using-networkx-python/)
![Wheels- W4, W5, W6 and W7](assets/wheel-graph-300x102-5aa4295996.jpg)
**Hypercube:** The [Hypercube](https://www.geeksforgeeks.org/dsa/hypercube-graph/) or n-cube is a graph with 2n vertices each represented by a n-bit string. The vertices which differ by at most 1-bit are connected by edges. A hypercube of 2n vertices is denoted by Qn . Total number of edges are n\* 2 n-1 with 2n vertices in cube graph. 
![](assets/hypercube-2-8b1040c333.jpg)
**Bipartite Graphs:** A simple graph 
$$
G
$$
is said to be bipartite if its vertex set 
$$
V
$$
can be divided into two disjoint sets such that every edge in 
$$
G
$$
has its initial vertex in the first set and the terminal vertex in the second set. Total number of edges are (n\*m) with (n+m) vertices in bipartite graph. 
![Bipartite Graph example](assets/BIPARTITE-2371e0ebee.jpg)
**Theorem:**  A simple graph is bipartite if and only if it is possible to assign one of two different colors to each vertex of the graph so that no two adjacent are assigned the 
same color. 
A bipartite graph with 
$$
m
$$
and 
$$
n
$$
vertices in its two disjoint subsets is said to be complete if there is an edge from every vertex in the first set to every vertex in the second set, for a total of 
$$
mn
$$
edges. A **complete bipartite graph** with 
$$
m
$$
vertices in the first set and 
$$
n
$$
vertices in the second set is denoted as K {m , n} . 
![](assets/complete-graphs-bipartite-deacc95de7.jpg)
## Examples
- **Simple Graph:** Let us take the example of graph that has vertices say {A, B, C, D} and the edges labelled as (A, B), (B, C), (C, D), and (D, A). This is connected and simple graph because there are no one pair of vertices that is connected by more than one edges or self loops.
- **Multigraph:** For instance if there are two arrows connecting A and B and one arrow between B and C, then this diagram is a multigraph.
- **Directed Graph:** In the case of a [directed graph](https://www.geeksforgeeks.org/problems/detect-cycle-in-a-directed-graph/1) there could be a directed arc from A to B and another from B to C.
- **Complete Bipartite Graph:** In one set there should be 3 vertices namely A, B and C; while in the other set there should be only two vertices, namely X and Y. Another graph is complete [bipartite graph](https://www.geeksforgeeks.org/dsa/what-is-bipartite-graph/), in this graph, each vertex of {A, B, C} is connected with each vertex of {X, Y}.
## Sample Problems
#### Problem 1: Find the degree of each vertex in a simple undirected graph with vertices {A, B, C, D} and edges {(A, B), (B, C), (C, D)}.
> The Degree between nodes A & B= 1 The Degree between nodes B & C= 2 The Degree between nodes C & D= 2 The Degree between nodes D & A= 1.
#### Problem 2: Check whether the graph with vertices {A, B, C, D} and edges {(A, B), (B, C), (C, A)} is bipartite.
> The delivered graph turns out to be a cycle of 3 vertices thus can’t be bipartite. Therefore we can concluded that it is not a bipartite graph.
#### Problem 3: Verify the handshaking theorem for a graph with 4 vertices and 3 edges.
> **Degrees of all vertex = where where outside radius + outside radius + outside radius + outside radius = 6. Applying the handshaking theorem here gives that 2e = 6, thus e = 3 Which is the same number of edges we have.**
#### Problem 4: Calculate the number of edges in a complete graph with 5 vertices.
> That of a complete graph is given by 5(5-1)/2 = 10.
#### Problem 5: How many edges are in a wheel graph with 6 vertices (including the central vertex)?
> Edges = 2\*(n-1) = 2 \* (6-1) = 10.
## **GATE CS Corner Questions**
Practicing the following questions will help you test your knowledge. All questions have been asked in GATE in previous years or in GATE Mock Tests. It is highly recommended that you practice them. 
1. [GATE CS 2013, Question 25](https://www.geeksforgeeks.org/questions/which-of-the-following-statements-isare-true-for-undirected/) 
2. [GATE CS 2014 Set-1, Question 61](https://www.geeksforgeeks.org/questions/consider-an-undirected-graph-g-where-self-loops-are-not/) 
3. [GATE CS 2006, Question 71](https://www.geeksforgeeks.org/questions/the-2n-vertices-of-a-graph-g-corresponds-to/) 
4. [GATE CS 2002, Question 25](https://www.geeksforgeeks.org/questions/maximum-number-of-edges-in-a-n-node/) 
5. [GATE CS 2004, Question 37](https://www.geeksforgeeks.org/questions/what-is-the-number-of-vertices-in-an-undirected/) 
6. [GATE CS 2014 Set-2, Question 13](https://www.geeksforgeeks.org/questions/the-maximum-number-of-edges-in-a-bipartite-graph/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/mathematics-graph-theory-basics/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Graphs

> [!note] Related notes
>
> - [[Euler and Hamiltonian Paths]]
> - [[Graph Isomorphisms and Connectivity]]
> - [[Graph Measurements]]
> - [[Graph Theory Practice Questions]]
> - [[Havel-Hakimi Theorem]]
> - [[Independent Sets, Covering, and Matching]]
> - [[Introduction to Graphs]]
> - [[Matching in Graph Theory]]
> - [[Number of Nodes and Height of a Binary Tree]]
> - [[Planar Graphs and Graph Coloring]]
