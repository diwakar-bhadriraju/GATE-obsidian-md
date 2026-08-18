---
title: "Euler and Hamiltonian Paths"
subject: "Discrete Mathematics"
topic: "Graphs"
source: "https://www.geeksforgeeks.org/engineering-mathematics/euler-hamiltonian-paths/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Graphs"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/graphs
---


> [!abstract] Euler and Hamiltonian Paths
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Graphs`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/euler-hamiltonian-paths/)

---

# Euler and Hamiltonian Paths

**Euler and Hamiltonian** paths are fundamental concepts in graph theory, a branch of mathematics that studies the properties and applications of graphs. An Euler path visits every edge of a graph exactly once, while a Hamiltonian path visits every vertex exactly once. These paths have significant applications in various fields, including computer science, engineering, and operations research.
### Graph Example:
![graph](assets/graph-300-c658857838.webp)
### **Path**:
- A path is a sequence of edges where no vertex is repeated (except for starting and ending vertices in a circuit).
- Example in a graph: a path can be: 0 → 2→ 3→ 1.
### Circuit:
- A circuit is a path that starts and ends at the same vertex, forming a loop.
- Example in the same graph: 0 → 2→ 3→ 1→0 is a circuit because it loops back to the starting vertex.
## **Euler Paths and Circuits**
> - An Euler path is a path that uses every edge of a graph **exactly once**.
> - An Euler circuit is a circuit that uses every edge of a graph exactly once.
> - An Euler path starts and ends at different vertices.
> - An Euler circuit starts and ends at the same vertex.
## Conditions for Euler Paths and Circuits
- **Euler Path**: A connected graph has an Euler path if and only if it has exactly zero or two vertices of odd degree.
- **Euler Circuit**: A connected graph has an Euler circuit if and only if every vertex has an even degree.
## Hamiltonian Paths
> - **Hamiltonian Path**: A path in a graph that visits every vertex exactly once.
![Hamiltonian-Path](assets/Hamiltonian-Path-68e94bbd3d.webp)
Unlike Euler paths, there is no simple necessary sufficient condition for the existence of Hamiltonian paths and cycles. However, there are several theorems and heuristics:
- **Dirac's Theorem**: If a graph G has n vertices (with n ≥ 3) and every vertex has a degree of at least n/2 , then G has a Hamiltonian cycle.
- **Ore's Theorem**: If a graph G has n vertices and for every pair of non-adjacent vertices u and v, the sum of their degrees is at least n, then G has a Hamiltonian cycle.
## **Hamiltonian Circuit**
> A simple circuit in a graph G that passes through every vertex exactly once is called a Hamiltonian circuit.
Unlike Euler paths and circuits, there are no simple necessary and sufficient criteria to determine if there are any Hamiltonian paths or circuits in a graph. But there are certain criteria that rule out the existence of a Hamiltonian circuit in a graph, such as if there is a vertex of degree one in a graph then it is impossible for it to have a Hamiltonian circuit. 
![Hamiltonian-Circuit](assets/Hamiltonian-Circuit-9a43eb3d7b.webp)
There are certain theorems which give sufficient but not necessary conditions for the existence of Hamiltonian graphs. 
## **Hamiltonian graph** and **Eulerian graph**
> A **Hamiltonian graph** contains a Hamiltonian circuit, where each vertex is visited exactly once before returning to the starting point.
> And an **Eulerian graph** contains an Eulerian circuit, which traverses each edge exactly once before returning to the starting point.
The image below illustrates four categories of graphs, showing whether they are Hamiltonian, Eulerian, both, or neither.
![Euler-and-Hamiltonian-Paths-copy](assets/Euler-and-Hamiltonian-Paths-copy-ed3fc4721f.webp)
## Applications in Engineering
- **Network Design:** Hamiltonian cycles optimize routing and minimize network costs (e.g., fiber optic networks).
- **Circuit Design**: Euler paths reduce traces on circuit boards (e.g., efficient circuit layouts).
- **DNA Sequencing:** Hamiltonian paths help reconstruct DNA from overlapping fragments.
- **Robotics:** Euler paths plan routes to cover areas without retracing (e.g., robot vacuums).
- **Logistics:** Hamiltonian cycles optimize delivery routes and reduce travel costs.
## Euler and Hamiltonian Paths - Solved Examples
**1. Determine if the following graph has an Euler circuit: A graph with vertices {A, B, C, D} and edges {AB, BC, CD, DA, AC}.**
**Solution:**
> To have an Euler circuit, all vertices must have even degree.
> Degrees: A(3), B(2), C(3), D(2)
>
> Since A and C have odd degrees, this graph does not have an Euler circuit
**2. Does the following graph have an Euler path? A graph with vertices {P, Q, R, S} and edges {PQ, QR, RS, SP, PR}.**
**Solution:**
> For an Euler path, either all vertices have even degree, or exactly two vertices have odd degree.
> Degrees: P(3), Q(2), R(3), S(2)
>
> This graph has an Euler path (but not a circuit) because it has exactly two odd-degree vertices.
> One possible path: P-S-R-Q-P-R
**3. Determine if the following graph has a Hamiltonian cycle: A complete graph K**5** **with 5 vertices.**
> A complete graph Kn always has a Hamiltonian cycle for n ≥ 3.
>
> So yes, K5 has a Hamiltonian cycle.
> One possible cycle: 1-2-3-4-5-1
**4. Does the following graph have a Hamiltonian path? A graph with vertices {A, B, C, D, E} and edges {AB, BC, CD, DE, AE, AC}.**
> this graph does have a Hamiltonian path.
>
> One such path is: A-B-C-D-E
**5. Does the complete bipartite graph K**3**, 3 have: a) An Euler circuit, b) A Hamiltonian cycle**
> a) No Euler circuit. All vertices have odd degree (3).
> b) Yes, it has a Hamiltonian cycle. One possible cycle: 1-a-2-b-3-c-1 (where 1,2,3 are in one partition and a,b,c are in the other)
**6. Consider the Petersen graph. Does it have: a) An Euler circuit, b) A Hamiltonian cycle**
> a) No Euler circuit. All vertices have degree 3 (odd),
> b) No Hamiltonian cycle. The Petersen graph is a well-known example of a 3-regular graph without a Hamiltonian cycle.
**7. Use Ore's theorem to determine if this graph has a Hamiltonian cycle:**
> A graph with 5 vertices where the degree sum of any two non-adjacent vertices is at least 5.
>
> Ore's theorem states that if the sum of degrees of any two non-adjacent vertices is ≥ n (where n is the number of vertices), then the graph has a Hamiltonian cycle.
> Here, n = 5, and the condition is satisfied.
>
> Therefore, this graph has a Hamiltonian cycle.
**8. Apply Dirac's theorem to determine if this graph has a Hamiltonian cycle: A graph with 8 vertices, each having degree at least 4.**
> Dirac's theorem states that if every vertex in a graph with n vertices (n ≥ 3) has degree ≥
>
>
$$
\frac{n}{2}
$$
>
> , then the graph has a Hamiltonian cycle.
> Here, n = 8, and n/2 = 4.
>
> Since each vertex has degree at least 4, Dirac's theorem applies.
> Therefore, this graph has a Hamiltonian cycle.
Related article: [Difference Between Hamiltonian Path and Eulerian Path](https://www.geeksforgeeks.org/dsa/difference-between-hamiltonian-path-and-eulerian-path/)
## Practice Questions - Euler and Hamiltonian Paths
**1.** Determine if the following graph has an Euler circuit: A graph with vertices {A, B, C, D, E} and edges {AB, BC, CD, DE, EA, AC, BD}
2. Does the complete graph K6 have a Hamiltonian cycle? If so, how many distinct Hamiltonian cycles does it have?
3. For a graph G with 7 vertices, each of degree 4, determine if it has: a) An Euler path b) A Hamiltonian path.
4. Consider the Petersen graph. How many edges need to be added to create an Euler circuit?
5. Apply Ore's theorem to determine if this graph has a Hamiltonian cycle: A graph with 6 vertices where the degree sum of any two non-adjacent vertices is at least 6.
6. Does the complete bipartite graph K4,3 have: a) An Euler path, b) A Hamiltonian cycle.
7. In a graph with 8 vertices, what's the minimum number of edges required to guarantee the existence of a Hamiltonian cycle according to Dirac's theorem?
8. A graph G has 10 vertices. Five vertices have degree 4, three vertices have degree 3, and two vertices have degree 5. Does G have an Euler circuit? If not, can it have an Euler path?
9. Prove or disprove: If a graph has a Hamiltonian cycle, it must also have an Euler circuit.
10. Consider a graph G with 5 vertices and 7 edges. Is it possible for G to have both an Euler circuit and a Hamiltonian cycle? Justify your answer.
**What is the difference between an Euler path and a Hamiltonian path?**
> An Euler path visits every edge of a graph exactly once, while a Hamiltonian path visits every vertex of a graph exactly once.
**Is there a simple condition for the existence of Hamiltonian cycles?**
> There is no simple necessary and sufficient condition for Hamiltonian cycles, but theorems like Dirac's and Ore's provide useful criteria.
**How are Hamiltonian paths used in DNA sequencing?**
> Hamiltonian paths are used to reconstruct the original DNA sequence from overlapping fragments by finding a path through the overlap graph of the reads.
**Can Euler paths be used in robotics?**
> Yes, Euler paths are used in robotics for route planning to cover every area of a space without retracing steps.
**How does graph theory help in circuit design?**
> Euler paths are used to design circuits with minimal wire traces, reducing manufacturing complexity.
## **GATE CS Corner Questions**
Practicing the following questions will help you test your knowledge. All questions have been asked in GATE in previous years or in GATE Mock Tests. It is highly recommended that you practice them. 
1. [GATE CS 2007, Question 23](https://www.geeksforgeeks.org/questions/which-of-the-following-graphs-has-an-eulerian-circuit/) 
2. [GATE CS 2005, Question 84](https://www.geeksforgeeks.org/questions/let-s-and-t-be-two-vertices-in-a-1/) 
3. [GATE CS 2008, Question 26](https://www.geeksforgeeks.org/questions/g-is-a-simple-undirected-graph-some-vertices-of/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/euler-hamiltonian-paths/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Graphs

> [!note] Related notes
>
> - [[Graph Isomorphisms and Connectivity]]
> - [[Graph Measurements]]
> - [[Graph Theory Basics]]
> - [[Graph Theory Practice Questions]]
> - [[Havel-Hakimi Theorem]]
> - [[Independent Sets, Covering, and Matching]]
> - [[Introduction to Graphs]]
> - [[Matching in Graph Theory]]
> - [[Number of Nodes and Height of a Binary Tree]]
> - [[Planar Graphs and Graph Coloring]]
