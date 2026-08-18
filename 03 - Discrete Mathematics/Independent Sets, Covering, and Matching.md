---
title: "Independent Sets, Covering and Matching"
subject: "Discrete Mathematics"
topic: "Graphs"
source: "https://www.geeksforgeeks.org/engineering-mathematics/mathematics-independent-sets-covering-and-matching/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Graphs"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/graphs
---


> [!abstract] Independent Sets, Covering and Matching
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Graphs`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/mathematics-independent-sets-covering-and-matching/)

---

# Independent Sets, Covering and Matching

Independent Sets, Covering, and Matching are used to study the relationships between vertices and edges in a graph.
These concepts help solve real-world problems such as network design, scheduling, resource allocation, and assignment tasks in computer science and engineering.
### **Independent Sets**
- A set of vertices I is called an independent set if no two vertices in set I are adjacent to each other; in other words, the set of non-adjacent vertices is called an independent set.
- It is also called a stable set.
- The parameter α₀(G) = max { |I|: I is an independent set in G } is called the independence number of G, i.e., the maximum number of non-adjacent vertices.
- Any independent set I with |I| = α₀(G) is called a maximum independent set.
![5](assets/5-7eaaab6950.webp)
> For the above given graph G, Independent sets are: I1 = {1}, I2 = {2}, I3 = {3}, I4 = {4}I5 = {1, 3} and I6 = {2, 4}
>
> Therefore, the maximum number of non-adjacent vertices i.e Independence number α0(G) = 2.
### **Vertex Covering**
- A set of vertices K which can cover all the edges of graph G is called a vertex cover of G i.e. if every edge of G is covered by a vertex in set K.
- The parameter β0(G) = min { |K|: K is a vertex cover of G } is called the vertex covering a number of G i.e. the minimum number of vertices that can cover all the edges.
- Any vertex cover K with |K| = β0(G) is called a minimum vertex cover.
![5](assets/5-7eaaab6950.webp)
> For above given graph G, Vertex cover is: V1 = {1, 3}, V2 = {2, 4}, V3 = {1, 2, 3}, V4 = {1, 2, 3, 4}, etc.
>
> Therefore, minimum number of vertices which can cover all edges, i.e., Vertex covering number β0(G) = 2.
![3](assets/3-f50696da7e.webp)
**Notes:**
- I is an independent set in G if V(G) - I is vertex cover of G.
- For any graph G, α0(G) + β0(G) = n, where n is number of vertices in G.
### **Edge Covering**
- A set of edges F which can cover all the vertices of graph G is called a edge cover of G i.e. if every vertex in G is incident with a edge in F.
- The parameter β1(G) = min { |F|: F is an edge cover of G } is called edge covering number of G i.e sum of minimum number of edges which can cover all the vertices and number of isolated vertices(if exist).
- Any edge cover F with |F| = β1(G) is called a minimum edge cover.
![4](assets/4-7cedb3fc18.webp)
> For above given graph G, Edge cover is: E1 = {a, b, c, d}, E2 = {a, d} and E3 = {b, c}.
>
> Therefore, minimum number of edges which can cover all vertices, i.e., Edge covering number β1(G) = 2.
![2](assets/2-748863b4b6.webp)
**Note:** For any graph G, α1(G) + β1(G) = n, where n is number of vertices in G.
### **Matching**
- The set of non-adjacent edges is called matching i.e independent set of edges in G such that no two edges are adjacent in the set.
- The parameter α1(G) = max { |M|: M is a matching in G } is called matching number of G i.e the maximum number of non-adjacent edges.
- Any matching M with |M| = α1(G) is called a maximum matching.
![4](assets/4-7cedb3fc18.webp)
> For above given graph G, Matching are: M1 = {a}, M2 = {b}, M3 = {c}, M4 = {d} M5 = {a, d} and M6 = {b, c}
>
> Therefore, maximum number of non-adjacent edges i.e matching number α1(G) = 2.
**Complete Matching:**
A matching of a graph G is complete if it contains all of G'svertices. Sometimes this is also called a perfect matching.
**HALL’S MARRIAGE THEOREM**
The bipartite graph G =(V, E) with bipartition (V1, V2) has a complete matching from V1 to V2 if and only if |N (A)| > |A| for all subsets A of V1. (This is both necessary and sufficient condition for complete matching.)
![3](assets/3-f50696da7e.webp)
**➢Practice:**[Solved Examples](https://www.geeksforgeeks.org/maths/independent-sets-covering-and-matching-practice-questions/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/mathematics-independent-sets-covering-and-matching/)

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
> - [[Introduction to Graphs]]
> - [[Matching in Graph Theory]]
> - [[Number of Nodes and Height of a Binary Tree]]
> - [[Planar Graphs and Graph Coloring]]
