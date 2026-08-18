---
title: "Graph Isomorphisms and Connectivity"
subject: "Discrete Mathematics"
topic: "Graphs"
source: "https://www.geeksforgeeks.org/engineering-mathematics/graph-isomorphisms-connectivity/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Graphs"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/graphs
---


> [!abstract] Graph Isomorphisms and Connectivity
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Graphs`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/graph-isomorphisms-connectivity/)

---

# Graph Isomorphisms and Connectivity

Graph theory is a fundamental area in mathematics and computer science that studies structures used to model relationships between objects.
A [graph](https://www.geeksforgeeks.org/maths/mathematics-graph-theory-basics-set-1/) consists of vertices (nodes) and edges (connections) that link pairs of vertices. It provides powerful tools for solving problems in computer science, network analysis, transportation systems, social networks, and many other fields.
## Graph Isomorphism
Graph isomorphism is a concept in [graph theory](https://www.geeksforgeeks.org/dsa/graph-theory-tutorial/) that determines whether two graphs have the same structure, even if their vertices are labeled differently.
> Two graphs are said to be isomorphic if there exists a one-to-one correspondence (bijection) between their vertex sets such that the adjacency (connection between vertices) is preserved.
### Conditions for Two Graphs to be Isomorphic
Two graphs are isomorphic if:
- They have the same number of vertices
- They have the same number of edges
- The degree of corresponding vertices is the same
- The pattern of connections is identical (only labels may differ)
So, if you can rename the vertices of one graph and obtain the other graph, they are isomorphic.
**Example:**
![shape](assets/shape-034b284cba.webp)
The graphs G and H are isomorphic because there is a bijective function f such that f(V1) = V'1, f(V2)=V'2, f(V3) = V'3, f(V4) = V'4, and f(V5) =V'5 preserving adjacency.
### Applications of Graph Isomorphism
**Network Analysis:** Graph isomorphisms are used to identify structurally identical networks, which is crucial in network analysis and optimization.
**Chemical Informatics**: Graph isomorphisms help in comparing molecular structures, which are often represented as graphs.
**Pattern Recognition**: In computer vision and pattern recognition, graph isomorphisms are used to match patterns and shapes.
## Graph Connectivity
Graph connectivity measures the degree to which the vertices of a graph are connected. It can be classified into two main types:
- **Vertex Connectivity(κ(G)):** The minimum number of vertices that need to be removed to disconnect the remaining vertices.
- **Edge Connectivity(λ(G)):** The minimum number of edges that need to be removed to disconnect the remaining vertices.
### Classification of Graphs by Connectivity
**1. Connected Graph:** A graph G is connected if for every pair of vertices u and v, there exists a path from u to v.
**2. Disconnected Graph:** A graph is disconnected if there exists at least one pair of vertices with no path between them.
**Example**
![connected-vs-disconnected-graph](assets/connected-vs-disconnected-graph-7a2787cad1.webp)
In the connected graph shown:
- All vertices (A, B, C, D) are reachable from one another.
- The graph has only one connected component.
In the disconnected graph shown:
- {A, B} form one component.
- {C, D} form another component.
- The graph has two connected components.
### Applications in Engineering
- **Network Reliability**: Graph connectivity is crucial in designing reliable communication networks that remain connected despite failures.
- **Electrical Engineering**: In electrical circuits, connectivity ensures that the circuit remains functional even if some components fail.
- **Transportation Planning**: Connectivity analysis helps in designing transportation networks that remain operational despite disruptions.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/graph-isomorphisms-connectivity/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Graphs

> [!note] Related notes
>
> - [[Euler and Hamiltonian Paths]]
> - [[Graph Measurements]]
> - [[Graph Theory Basics]]
> - [[Graph Theory Practice Questions]]
> - [[Havel-Hakimi Theorem]]
> - [[Independent Sets, Covering, and Matching]]
> - [[Introduction to Graphs]]
> - [[Matching in Graph Theory]]
> - [[Number of Nodes and Height of a Binary Tree]]
> - [[Planar Graphs and Graph Coloring]]
