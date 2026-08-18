---
title: "Representation of Relation in Graphs and Matrices"
subject: "Discrete Mathematics"
topic: "Algebraic and Set-Theoretic Structures"
source: "https://www.geeksforgeeks.org/engineering-mathematics/relation-and-their-representations/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Algebraic and Set-Theoretic Structures"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/algebraic-and-set-theoretic-structures
---


> [!abstract] Representation of Relation in Graphs and Matrices
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Algebraic and Set-Theoretic Structures`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/relation-and-their-representations/)

---

# Representation of Relation in Graphs and Matrices

A [relation](https://www.geeksforgeeks.org/maths/relation-in-maths/) is a mathematical concept that describes the connection between elements of two sets.
Relations can be represented using graphs and matrices, which provide a clear and systematic way to visualize and analyze these connections.
## 1. Representing Using Graphs
There are different types of graphs used for this purpose, including directed graphs (digraphs) and undirected graphs. Let R be a relation on a set A. If (a, b) ∈ R, then the digraph contains a directed edge (an arrow) from vertex a to vertex b.
### Directed Graphs (Digraphs)
A directed graph consists of nodes or vertices connected by directed edges or arcs.
**Example:** The relation R = {(a, a), (a, b), (b, b), (b, c), (c, c), (c, b), (c, a)} is represented as
![xx](assets/xx-3e66c91379.webp)
> Since there is a loop at every vertex
>
> - Relation is reflexive.
> - It is not symmetric because (a, b) ∈ R but (b, a) ∉ R.
> - It is not antisymmetric because both (b, c) and (c, b) belong to R, where b ≠ c.
> - The relation is not transitive because (a, b) and (b, c) belong to R, but (a, c) ∉ R.
**Properties**
1. A relation R is reflexive if there is a loop at every node of a directed graph.
2. A relation R is irreflexive if there is no loop at any node of directed graphs.
3. A relation R is symmetric if, for every edge between distinct nodes, an edge is always present in the opposite direction.
4. A relation R is asymmetric if there are never two edges in opposite directions between distinct nodes.
5. A relation R is transitive if there is an edge from a to b and b to c, then there is always an edge from a to c.
### Undirected Graphs
In an undirected graph, edges have no direction. This type of representation is used when the relation is symmetric, meaning if a is related to b, then b is also related to a.
**Example: If** the relation R on set A = {1, 2, 3} is such that R = {(1, 2), (2, 3)}, the undirected graph will have vertices 1, 2, and 3, with edges between 1 and 2, and 2 and 3.
![x](assets/x-fb9554acf9.webp)
## 2. Representing Using a Matrix
An adjacency matrix (also called a relation matrix) is a matrix used to represent a relation between two finite sets. It provides a simple and organized way to show whether a relation exists between the elements of the sets.
Suppose
- A = {a₁, a₂, ..., aₘ} is a finite set with m elements.
- B = {b₁, b₂, ..., bₙ} is a finite set with n elements.
- R is a relation from set A to set B.
The relation R can be represented by an m × n matrix, where:
>
$$
R_{ij}=\begin{cases}1, & \text{if } a_i\,r\,b_j,\\0, & \text{otherwise}.\end{cases}
$$
Thus, each row represents an element of set A, each column represents an element of set B, and the entries (0 or 1) indicate whether a relation exists between the corresponding elements.
**Example:** Let A = {2, 5, 6} and let R = {(2, 2), (2, 5), (5, 6), (6, 6)} be a relation on A. Represent the relation R using an adjacency matrix.
**Solution:**
> Since the relation is defined on the same set A, the rows and columns of the matrix are labeled in the order 2, 5, 6.
>
> Check each ordered pair in the relation:
>
> - (2, 2) ∈ R, so R₁₁ = 1
> - (2, 5) ∈ R, so R₁₂ = 1
> - (2, 6) ∉ R, so R₁₃ = 0
> - (5, 2) ∉ R, so R₂₁ = 0
> - (5, 5) ∉ R, so R₂₂ = 0
> - (5, 6) ∈ R, so R₂₃ = 1
> - (6, 2) ∉ R, so R₃₁ = 0
> - (6, 5) ∉ R, so R₃₂ = 0
> - (6, 6) ∈ R, so R₃₃ = 1
>
> Therefore, the adjacency matrix of the relation is:
>
>
$$
R=\begin{pmatrix}1 & 1 & 0\\0 & 0 & 1\\0 & 0 & 1\end{pmatrix}
$$
### Applications in Engineering
Relations help in analyzing connections, organizing data, and solving complex problems efficiently.
1. **Network Analysis**: Graphs and matrices are used to study communication networks, transportation systems, and electrical circuits. They help engineers understand connections and the flow of information or resources.
2. **Control Systems**: In control engineering, graphs and matrices represent system states and transitions, making it easier to analyze and design control systems.
3. **Data Structures and Algorithms**: Graphs and matrices are widely used in computer science for designing algorithms related to searching, pathfinding, optimization, and data organization.
4. **Database Management**: Relations are the foundation of relational databases, where tables are used to store, organize, and manage data efficiently.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/relation-and-their-representations/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Algebraic and Set-Theoretic Structures

> [!note] Related notes
>
> - [[Cartesian Product of Two Sets]]
> - [[Classes of Functions]]
> - [[Closure of Relations]]
> - [[Composition of Functions]]
> - [[Equivalence Relations]]
> - [[Groups]]
> - [[Hasse Diagrams]]
> - [[Introduction to Set Theory]]
> - [[Inverse Functions]]
> - [[Modular Addition]]
