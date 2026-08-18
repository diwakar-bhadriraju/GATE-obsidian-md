---
title: "Walks, Trails, Paths, Cycles and Circuits in Graph"
subject: "Discrete Mathematics"
topic: "Graphs"
source: "https://www.geeksforgeeks.org/engineering-mathematics/walks-trails-paths-cycles-and-circuits-in-graph/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Graphs"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/graphs
---


> [!abstract] Walks, Trails, Paths, Cycles and Circuits in Graph
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Graphs`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/walks-trails-paths-cycles-and-circuits-in-graph/)

---

# Walks, Trails, Paths, Cycles and Circuits in Graph

Walks, trails, paths, cycles, and circuits in a graph are sequences of vertices and edges with different properties. Some allow repetition of vertices and edges, while others do not.
## Walk
A walk in a graph is a sequence of vertices and edges where both edges and vertices can be repeated. The length of the walk refers to the number of edges covered in the sequence. A graph can contain multiple walks.
There are two key points to note about a walk:
1. Edges can be repeated.
2. Vertices can be repeated.
![graph-5](assets/graph-5-bf5d3a53eb.webp)
> - Here, 1-> 2-> 3-> 4-> 2-> 1-> 3 is a walk.
>
> Walk can be open or closed.
**Types of Walks:**
**1. Open Walk:** An open walk is a walk in which the starting and ending vertices are different. In other words, for a walk to be considered open, the origin and terminal vertices must not be the same. Additionally, the length of the walk must be greater than 0.
**2. Closed Walk:** A closed walk occurs when the starting and ending vertices are identical, meaning the walk starts and ends at the same vertex. For a walk to be classified as closed, the origin and terminal vertices must be the same. Similar to an open walk, the length of the walk must be greater than 0.
> In the above diagram: 
>
> - 1-> 2-> 3-> 4-> 5-> 3 is an open walk.
> - 1-> 2-> 3-> 4-> 5-> 3-> 1 is a closed walk.
## **Trail**
A trail is an open walk in which no edge is repeated, though vertices may be repeated.
There are two types of trails:
1. **Open Trail**: A trail is considered an open trail if the starting and ending vertices are different.
2. **Closed Trail**: A trail is a closed trail if the starting and ending vertices are the same.
In a trail, the key point to remember is that: Edges cannot be repeated, but vertices can be repeated.
![graph-3](assets/graph-3-88d712c3f2.webp)
Here 1-> 3-> 8-> 6-> 3-> 2 is trail 
Also 1-> 3-> 8-> 6-> 3-> 2-> 1 will be a closed trail 
## **Circuit**
A circuit can be described as a closed trail in graph theory, where no edge is repeated, but vertices can be repeated.
Thus, the key characteristics of a circuit are:
- Edges cannot be repeated.
- Vertices can be repeated.
In other words, a circuit is a closed traversal of a graph where each edge is used exactly once, but a vertex may appear more than once.
Here 1-> 2-> 4-> 3-> 6-> 8-> 3-> 1 is a circuit.
Circuit is a closed trail.
## **Path**
A path is a trail in which neither vertices nor edges are repeated.
In other words, when traversing a graph along a path, each vertex and each edge is visited exactly once. Since a path is also a trail, it is inherently an open walk unless stated otherwise.
Another definition of a path is a walk with no repeated vertices. This automatically implies that no edges are repeated, making it unnecessary to explicitly mention edge repetition in the definition.
Key characteristics of a path:
- **Vertices are not repeated.**
- **Edges are not repeated.**
![graph-4](assets/graph-4-878b2af30a.webp)
Here 6->8->3->1->2->4 is a Path 
## **Cycle**
A cycle in graph is a closed path, meaning that it starts and ends at the same vertex while ensuring that no other vertices or edges are repeated.
In other words, a cycle is formed by traversing a graph such that: No vertex is repeated, except for the starting and ending vertex, which must be the same and No edge is repeated.
Key characteristics of a cycle:
- Edges cannot be repeated.
- Vertices cannot be repeated, except for the first and last vertex, which must be the same.
![graph-2](assets/graph-2-64d4276e08.webp)
Here 1->2->4->3->1 is a cycle. 
Cycle is a closed path.
## Table for Walk, Trail and Path
The table below represents the repetition of edges and vertices in walk, trail and path.
| Category | Edges | Vertices |
| --- | --- | --- |
| Walk | Can be repeated | Can be repeated |
| Trail | Cannot be repeated | Can be repeated |
| Path | Cannot be repeated | Cannot be repeated |
**➢Practice:**[Solved Examples](https://www.geeksforgeeks.org/maths/walks-trails-paths-cycles-and-circuits-in-graph-practice-questions/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/walks-trails-paths-cycles-and-circuits-in-graph/)

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
> - [[Matching in Graph Theory]]
> - [[Number of Nodes and Height of a Binary Tree]]
