---
title: "Graph Measurements"
subject: "Discrete Mathematics"
topic: "Graphs"
source: "https://www.geeksforgeeks.org/engineering-mathematics/graph-measurements-length-distance-diameter-eccentricity-radius-center/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Graphs"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/graphs
---


> [!abstract] Graph Measurements
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Graphs`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/graph-measurements-length-distance-diameter-eccentricity-radius-center/)

---

# Graph Measurements

A **graph** is defined as a set of points known as 'Vertices' and a line joining these points is known as 'Edges'. It is a set consisting of where 'V' is the vertices and 'E' is edges. 
![graph_1](assets/graph_1-6916fff7b8.webp)
**Vertices:** {A, B, C, D, E, F} 
**Edges:** {{A, B}, {A, D}, {A, E}, {B, C}, {C, E}, {C, F}, {D, E}, {E, F}} 
**Graph Measurements:** There are a few graph measurement methods available: 
**1. Length -** 
The length of the graph is defined as the number of edges contained in the graph. 
![Graph](assets/Graph-de1d868f20.webp)
> Length of the graph: 8
> AB, BC, CD, DE, EF, FA, AC, CE 
**2. The distance between two Vertices -** 
The distance between two vertices in a graph is the number of edges in a shortest or minimal path. It gives the available minimum distance between two edges. There can exist more than one shortest path between two vertices.  
![graph_2](assets/graph_2-a86ba8f6af.webp)
> Shortest Distance between 1 - 5 is **2**
> 1 → 2 → 5 
**3. Eccentricity of graph -** 
It is defined as the maximum distance of one vertex from another vertex. The maximum distance between a vertex to all other vertices is considered as the eccentricity of the vertex. It is denoted by e(V). 
![graph_3](assets/graph_3-97f7f4658a.webp)
> Eccentricity from:
> (A, A) = 0
> (A, B) = 1
> (A, C) = 2
> (A, D) = 1
> Maximum value  is 2, So Eccentricity is **2**
**4. Diameter of graph -** 
The diameter of a graph is the maximum distance between any pair of vertices. It can also be defined as the maximal distance between a pair of vertices. A way to solve it is to find all the paths and then find the maximum of all. It can also be found by finding the maximum value of eccentricity from all the vertices.
![graph_4](assets/graph_4-e862f74a4e.webp)
> Diameter: **3**
> BC → CF → FG  
> Here the eccentricity of the vertex B is 3 since (B,G) = 3. (Maximum Eccentricity of Graph)
**5. Radius of graph -**
A radius of the graph exists only if it has a diameter. The minimum among all the maximum distances between a vertex to all other vertices is considered as the radius of the Graph G. It is denoted as r(G). It can also be found by finding the minimum value of eccentricity from all the vertices.
![graph_5](assets/graph_5-7023b3f37a.webp)
> Radius: **2**
> All available minimum radius: 
> BC → CF,
> BC → CE,
> BC → CD,
> BC → CA
**6. Centre of graph -** 
It consists of all the vertices whose eccentricity is minimum. Here, the eccentricity is equal to the radius. For example, if the school is at the center of town, it will reduce the distance buses have to travel. If the eccentricity of two vertices is the same and minimum among all other both of them can be the center of the graph.
![graph_6](assets/graph_6-e14f251b29.webp)
> Centre: **A**  
> Inorder to find the center of the graph, we need to find the eccentricity of each vertex and find the minimum among all of them. 
> The minimum eccentricity vertex will be considered as the center.
### Also Check
> **Understanding graph measurements** is crucial for various algorithmic problems, especially in competitive exams like GATE. If you're preparing for **GATE** and want to dive deeper into graph theory concepts, the[**GATE CS Self-Paced Course**](https://www.geeksforgeeks.org/courses/category/gate?utm_source=test_series&utm_medium=cse/) offers comprehensive coverage on graph algorithms and measurements. This course is designed to simplify complex topics with clear explanations and practical examples, making graph theory easier to grasp.
## Practices Problems
**Question 1:** Path Length Calculation:
- Given a simple undirected graph, find the length of the path between vertices A and D: A-B-C-D.
- Assume the graph has the following edges with equal weights of 1: A-B, B-C, and C-D.
**Question 2:** Shortest Path Distance:
In the following weighted graph, compute the shortest path distance between vertices A and E:
![Graph-1](assets/Graph-1-8e4fd04f47.webp)
**Question 3**: Graph Diameter
For the graph below, determine its diameter. The diameter is the longest shortest path between any two vertices.
```sql
A -- B -- C -- D -- E
```
**Question 4**: Eccentricity Calculation
Find the eccentricity of vertex C in the graph below. The eccentricity of a vertex is the greatest distance from that vertex to any other vertex.
```sql
   A -- B -- C -- D -- E
```
**Question 5**: Graph Radius
Calculate the radius of the following graph. The radius is the minimum eccentricity of any vertex in the graph.
```sql
    A -- B -- C -- D -- E
```
**Question 6**: Graph Center
Identify the center of the given graph. The center consists of the vertices with eccentricity equal to the radius.
```sql
   A -- B -- C -- D -- E
```
**Question 7:** Weighted Graph Path Length
In a weighted graph, calculate the length of the path from vertex A to vertex F given the following edges with weights: A-B(2), B-C(3), C-D(1), D-E(4), and E-F(2).
**Question 8**: Maximal Distance Calculation
For the graph below, determine the maximum distance (longest shortest path) from vertex A to any other vertex.
![Graph-2](assets/Graph-2-9095d6c889.webp)
**Question 9**: Determining Eccentricity in a Star Graph
For a star graph with a central vertex connected to 4 outer vertices, compute the eccentricity of the central vertex and one of the outer vertices.
**Question 10**: Graph Center and Radius for Complete Graph
For a complete graph ( K5 ) (5 vertices, each connected to every other vertex), determine the graph's radius and identify its center.
### Related Articles
> - [Basic Properties of a Graph](https://www.geeksforgeeks.org/dsa/basic-properties-of-a-graph/)
> - [Graph Theory Tutorial](https://www.geeksforgeeks.org/dsa/graph-theory-tutorial/)
> - [Mathematics | Graph Theory Basics - Set 2](https://www.geeksforgeeks.org/engineering-mathematics/mathematics-graph-theory-basics/)
> - [Check whether a given graph is Bipartite or not](https://www.geeksforgeeks.org/dsa/bipartite-graph/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/graph-measurements-length-distance-diameter-eccentricity-radius-center/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Graphs

> [!note] Related notes
>
> - [[Euler and Hamiltonian Paths]]
> - [[Graph Isomorphisms and Connectivity]]
> - [[Graph Theory Basics]]
> - [[Graph Theory Practice Questions]]
> - [[Havel-Hakimi Theorem]]
> - [[Independent Sets, Covering, and Matching]]
> - [[Introduction to Graphs]]
> - [[Matching in Graph Theory]]
> - [[Number of Nodes and Height of a Binary Tree]]
> - [[Planar Graphs and Graph Coloring]]
