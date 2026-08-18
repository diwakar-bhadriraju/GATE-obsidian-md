---
title: "Matching (Graph Theory)"
subject: "Discrete Mathematics"
topic: "Graphs"
source: "https://www.geeksforgeeks.org/engineering-mathematics/matching-graph-theory/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Graphs"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/graphs
---


> [!abstract] Matching (Graph Theory)
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Graphs`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/matching-graph-theory/)

---

# Matching (Graph Theory)

In graph theory, a matching is a way of pairing up vertices so that each vertex is included in at most one pair. Matchings are used in various applications, including network design, job assignments, and scheduling.
> A matching in a graph is a set of edges such that no two edges share a common vertex.
![2056958443](assets/2056958443-ec08371d7f.webp)
For a graph G = (V, E), a matching M satisfies the following: M ⊆ E, such that no two edges in M are incident on the same vertex.
**Example:** Consider a graph with vertices V = {A, B, C, D, E, F} and edges E = {AB, BC, CD, DE, EF, FA, AC, BD, BE, CF}. The set M = {AB, DE} is a valid matching because the selected edges do not share any common vertex. Therefore, each vertex is incident to at most one edge in the matching.
### Cardinality of Matching
The number of edges present in a matching is called the cardinality or size of the matching.
If a matching contains (k) edges, then |M| = k.
The size of the largest possible matching in a graph is called the matching number of the graph.
**Properties**
- No two edges in a matching share a common vertex.
- Every perfect matching is a maximum matching.
- A maximal matching need not be a maximum matching.
- Bipartite graphs are commonly used in matching problems.
- Matchings are used to model pairing and allocation problems.
## Types of Matching
### Maximal Matching
A maximal matching is a matching to which no additional edge can be added without violating the matching condition.
A maximal matching is not always the largest possible matching.
### **Maximum Matching**
A maximum matching is a matching that contains the largest possible number of edges.
**Example:** For the same graph G, a maximum matching could be M = {(u1,v1),(u2,v2)}, assuming there are no other edges connecting u3 to V.
### **Perfect Matching**
A perfect matching is a matching where every vertex in the graph is connected to exactly one edge in the matching.
**Example:** For the bipartite graph G = (U, V, E) where U = {u1, u2, u3} and V = {v1, v2, v3}, a perfect matching could be M = {(u1, v1), (u2, v2),(u3, v3)}
### **Maximum Bipartite Matching**
In a bipartite graph, a maximum bipartite matching covers the maximum number of vertices in both partitions.
**Example:** For the bipartite graph G, a maximum bipartite matching could be M={(u1,v1),(u2,v2),(u3,v3)}
## Algorithms for Finding Matchings
**Hungarian Algorithm**: The Hungarian algorithm is used to find the maximum matching in a bipartite graph.
**Steps:**
- Initialize the matching M to be empty.
- Find augmenting paths and increase the size of the matching.
- Repeat until no more augmenting paths can be found.
**Hopcroft-Karp Algorithm**: The Hopcroft-Karp algorithm is an efficient algorithm for finding maximum matchings in bipartite graphs.
**Steps:**
- Perform a breadth-first search to find the shortest augmenting path.
- Perform a depth-first search to augment the matching along the path.
- Repeat until no more augmenting paths can be found.
**Blossom Algorithm**: The Blossom algorithm, developed by Jack Edmonds, is used to find maximum matchings in general graphs (non-bipartite).
**Steps:**
- Find augmenting paths using the concept of blossoms (odd-length cycles).
- Contract blossoms into single vertices.
- Repeat the process until no more augmenting paths can be found.
### Applications
1. **Network Design**: Efficient routing and resource allocation.
2. **Job Assignment**: Assigning jobs to machines or workers.
3. **Scheduling**: Optimal scheduling of tasks.
4. **Resource Allocation:** Resources can be assigned to users or processes without conflicts.
**➢Practice:**[Solved Examples](https://www.geeksforgeeks.org/maths/matching-graph-theory-practice-questions/)
### Related Articles
> - [Bipartite Graph](https://www.geeksforgeeks.org/dsa/what-is-bipartite-graph/)
> - [Graph Theory](https://www.geeksforgeeks.org/dsa/graph-theory-tutorial/)
> - [Graph Theory Basics](https://www.geeksforgeeks.org/engineering-mathematics/mathematics-graph-theory-basics/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/matching-graph-theory/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Graphs

> [!note] Related notes
>
> - [[Euler and Hamiltonian Paths]]
> - [[Graph Isomorphisms and Connectivity]]
> - [[Graph Measurements]]
> - [[Graph Theory Basics]]
> - [[Graph Theory Practice Questions]]
> - [[Havel-Hakimi Theorem]]
> - [[Independent Sets, Covering, and Matching]]
> - [[Introduction to Graphs]]
> - [[Number of Nodes and Height of a Binary Tree]]
> - [[Planar Graphs and Graph Coloring]]
