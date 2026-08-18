---
title: "Planar Graphs and Graph Coloring"
subject: "Discrete Mathematics"
topic: "Graphs"
source: "https://www.geeksforgeeks.org/engineering-mathematics/mathematics-planar-graphs-graph-coloring/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Graphs"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/graphs
---


> [!abstract] Planar Graphs and Graph Coloring
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Graphs`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/mathematics-planar-graphs-graph-coloring/)

---

# Planar Graphs and Graph Coloring

Planar graphs and graph coloring are important concepts in graph theory, which studies graphs and their properties. A planar graph is a graph that can be drawn on a plane without any edges crossing each other.
Graph coloring is the process of assigning colors to vertices so that no two adjacent vertices have the same color. These concepts are widely used in computer science, engineering, networking, scheduling, and map coloring problems.
## Planar Graphs
A planar graph is a graph that can be embedded in the plane such that no edges intersect except at their endpoints. In other words, it can be drawn on a flat surface without any edges crossing.
![Planer-and-Non-Planer-Graphs](assets/Planer-and-Non-Planer-Graphs-1b80181a95.webp)
### Properties of Planar Graphs
- A planar graph can be drawn without edges crossing each other.
- It divides the plane into regions called faces.
- For a connected planar graph: V − E + F = 2
  Here, V = vertices, E = edges, and F = faces.
- In a simple planar graph: E ≤ 3V − 6
- A planar graph does not contain K5 or K3,3 as subgraphs.
- Planar graphs are used in maps, circuits, networks, and scheduling.
## Graph Coloring
Graph coloring is the assignment of colors to vertices of a graph such that no two adjacent vertices share the same color. The minimum number of colors required to color a graph is called its chromatic number.
![2056958230](assets/2056958230-483e2aba67.webp)
### Types of Graph Coloring
- **Vertex Coloring**: Assigning colors to vertices so that no two adjacent vertices have the same color.
- **Edge Coloring**: Assigning colors to edges so that no two edges sharing the same vertex have the same color.
- **Face Coloring**: Assigning colors to faces of a planar graph so that no two faces sharing a boundary have the same color.
## Applications in Engineering
Graph coloring and planar graphs have various applications in engineering, computer science, communication systems, scheduling, map coloring, and circuit design.
- **Frequency Assignment:** Graph coloring is used to assign different frequencies to nearby radio stations and cell towers to avoid interference.
   **Example:** Adjacent cell towers are given different frequencies.
- **Scheduling:** Graph coloring helps in scheduling exams, tasks, and events so that conflicting activities do not occur at the same time.
   **Example:** Students do not get overlapping exams in a timetable.
- **Map Coloring:** Planar graph coloring is used to color maps so that neighboring regions have different colors.
   **Example:** Adjacent countries on a political map are colored differently.
- **Register Allocation:** In computer science, graph coloring is used to assign CPU registers efficiently in compilers.
   **Example:** Variables used at the same time are stored in different registers.
- **Circuit Design:** Graph coloring helps in reducing wire crossings and minimizing layers in circuit boards.
   **Example:** Printed circuit boards are designed more efficiently.
**➢Practice:**[Solved Examples](https://www.geeksforgeeks.org/maths/planar-graphs-and-graph-coloring-practice-questions/)
### Related Articles
> - [Four Color Theorem and Kuratowski’s Theorem](https://www.geeksforgeeks.org/engineering-mathematics/four-color-theorem-and-kuratowskis-theorem-in-discrete-mathematics/)
> - [Fundamentals of Graph Theory](https://www.geeksforgeeks.org/maths/fundamentals-of-graph-theory/)
## **GATE CS Corner Questions**
Practicing the following questions will help you test your knowledge. All questions have been asked in GATE in previous years or in GATE Mock Tests. It is highly recommended that you practice them.
- [GATE CS 2005 Question 10](https://www.geeksforgeeks.org/questions/let-g-be-a-simple-connected-planar-graph-with/)
- [GATE CS 2005, Question 47](https://www.geeksforgeeks.org/questions/which-one-of-the-following-graphs-is-not-planar/)
- [GATE CS 2004, Question 77](https://www.geeksforgeeks.org/questions/the-minimum-number-of-colours-required-to-colour-the/)
- [GATE CS 2002, Question 4](https://www.geeksforgeeks.org/questions/the-minimum-number-of-colours-required-to-colour-the-1/)
- [GATE CS 2015 Set-1, Question 63](https://www.geeksforgeeks.org/questions/let-g-be-a-connected-planar-graph-with-10/)
- [GATE CS 2008, Question 3](https://www.geeksforgeeks.org/questions/what-is-the-chromatic-number-of-the-following-graph/)
- [GATE CS 2016 Set-2, Question 13](https://www.geeksforgeeks.org/questions/the-minimum-number-of-colours-that-is-sufficient-to/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/mathematics-planar-graphs-graph-coloring/)

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
