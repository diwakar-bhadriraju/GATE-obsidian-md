---
title: "Graph-Based Algorithms for GATE Exam [2024]"
subject: "Algorithms"
topic: "Graph Algorithms"
source: "https://www.geeksforgeeks.org/dsa/graph-based-algorithms-for-gate-exam/#1-breadth-first-search-or-bfs-for-a-graph-bfs-"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Algorithms/Graph Algorithms"
tags:
  - gate/cs
  - subject/algorithms
  - topic/graph-algorithms
---


> [!abstract] Graph-Based Algorithms for GATE Exam [2024]
> 
> **Subject:** `Algorithms` &nbsp;|&nbsp; **Topic:** `Graph Algorithms`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/graph-based-algorithms-for-gate-exam/#1-breadth-first-search-or-bfs-for-a-graph-bfs-)

---

# Graph-Based Algorithms for GATE Exam [2024]

Ever wondered how computers figure out the best path in a maze or create efficient networks like a pro? That's where Graph-Based Algorithms come into play! Think of them as your digital navigation toolkit. As you prepare for GATE 2024, let these algorithms be your allies, unraveling the intricacies of graphs and leading you to success.
Table of Content
- [Depth First Search or DFS for a Graph](#2-depth-first-search-or-dfs-for-a-graph)
- [Detect Cycle in a Directed Graph](#3-detect-cycle-in-a-directed-graph)
- [Topological Sorting](#4-topological-sorting)
- [Bellman–Ford Algorithm](#5-bellmanford-algorithm)
- [Floyd Warshall Algorithm](#6-floyd-warshall-algorithm)
- [Shortest path with exactly k edges in a directed and weighted graph](#7-shortest-path-with-exactly-k-edges-in-a-directed-and-weighted-graph)
- [Biconnected graph](#8-biconnected-graph)
- [Articulation Points (or Cut Vertices) in a Graph](#9-articulation-points-or-cut-vertices-in-a-graph)
- [Check if a graph is strongly connected (Kosaraju’s Theorem)](#10-check-if-a-graph-is-strongly-connected-kosarajus-theorem)
- [Bridges in a graph](#11-bridges-in-a-graph)
- [Transitive closure of a graph](#12-transitive-closure-of-a-graph)
- [Previously Asked GATE Questions on Graph-Based Algorithms](#previously-asked-gate-questions-on-graphbased-algorithms)
A Graph is a **non-linear data structure** consisting of **vertices** and **edges**. The vertices are sometimes also referred to as nodes and the edges are lines or arcs that connect any two nodes in the graph. More formally a Graph is composed of a set of **vertices( V )** and a set of **edges( E ).** The graph is denoted by **G(E, V)**.
In this comprehensive guide, we will explore key graph algorithms, providing detailed algorithm steps with its applications, which are relevance for the GATE Exam.
## 1. [Breadth First Search or BFS for a Graph (BFS)](https://www.geeksforgeeks.org/dsa/breadth-first-search-or-bfs-for-a-graph/):
> BFS explores a graph level by level, visiting all neighbours of a node before moving on to the next level. It uses a queue data structure to maintain the order in which nodes are visited.
**Algorithm Steps:**
1. Enqueue the starting node into the queue.
2. While the queue is not empty, dequeue a node and visit it.
3. Enqueue all unvisited neighbors of the current node.
4. Repeat steps 2-3 until the queue is empty.
**Applications:**
- Shortest path finding in unweighted graphs.
- Connectivity analysis in networks.
- Web crawling and indexing.
## 2. [Depth First Search or DFS for a Graph](https://www.geeksforgeeks.org/dsa/depth-first-search-or-dfs-for-a-graph/):
> DFS explores a graph by going as deep as possible along one branch before backtracking. It uses a stack (or recursion) to keep track of the visited nodes.
**Algorithm Steps:**
1. Start at the initial node and mark it as visited.
2. Explore one adjacent node as deeply as possible before backtracking.
3. Repeat step 2 until all paths are explored.
**Applications:**
- Topological sorting of directed acyclic graphs.
- Detecting cycles in a graph.
- Solving puzzles and games.
## 3. [Detect Cycle in a Directed Graph:](https://www.geeksforgeeks.org/dsa/detect-cycle-in-a-graph/)
> Detecting cycles in a directed graph is a common problem with wide-ranging applications in various domains such as network analysis, scheduling, and resource allocation. The algorithmic approach involves traversing the graph using depth-first search (DFS) and identifying back edges. If a back edge is encountered during the traversal, it indicates the presence of a cycle.
**Algorithm Steps:**
- Initialize arrays for visited vertices and recursion stack.
- Start DFS from each unvisited vertex.
- Mark the current vertex as visited and add it to the recursion stack.
- For each adjacent vertex:
  - If the vertex is not visited, recursively call DFS.
  - If the vertex is in the recursion stack, a cycle is detected.
- Remove the current vertex from the recursion stack upon backtracking.
**Applications:**
- Task scheduling in project management.
- Resource allocation in computer systems.
## 4. [Topological Sorting:](https://www.geeksforgeeks.org/dsa/topological-sorting/)
> Topological sorting is vital for scheduling tasks with dependencies, and it is often used in project management and task scheduling. The algorithm involves linearly ordering the vertices of a directed acyclic graph (DAG) in such a way that for every directed edge 'uv,' vertex 'u' comes before 'v' in the ordering.
**Algorithm Steps:**
- Start DFS from any unvisited vertex.
- Mark the current vertex as visited.
- Recursively call DFS for each adjacent vertex.
- Add the current vertex to the topological order after recursion.
- The final order is the reverse of the order in which vertices are added.
**Applications:**
- Task scheduling with dependencies.
- Build systems to determine order of compilation.
## 5. [Bellman–Ford Algorithm:](https://www.geeksforgeeks.org/dsa/bellman-ford-algorithm-dp-23/)
> The Bellman–Ford algorithm is employed for finding the shortest paths from a single source vertex to all other vertices in a weighted graph, even if the graph contains negative weight edges. This algorithm is particularly useful in scenarios where Dijkstra's algorithm might fail due to negative weights.
**Algorithm Steps:**
1. Initialize distances from the source vertex to all others as infinity.
2. Set the distance to the source as 0.
3. Relax edges iteratively:
   - For each edge (u, v), if distance[u] + weight(u, v) < distance[v], update distance[v].
4. Repeat step 3 for V-1 times, where V is the number of vertices.
5. Detect negative cycles by checking for further relaxation after V-1 iterations.
**Applications:**
- Single-source shortest path with negative weight edges.
- Network routing protocols.
## 6. [Floyd Warshall Algorithm:](https://www.geeksforgeeks.org/dsa/floyd-warshall-algorithm-dp-16/)
> The Floyd Warshall algorithm is a dynamic programming approach to find the shortest paths between all pairs of vertices in a weighted graph. It works well for dense graphs and is capable of handling graphs with both positive and negative weights.
**Algorithm Steps:**
- Initialize a matrix with direct edge weights.
- Update the matrix with shorter paths found through intermediate vertices:
  - For each pair of vertices (i, j), if distance[i][k] + distance[k][j] < distance[i][j], update distance[i][j].
**Applications:**
- All-pairs shortest path in a weighted graph.
- Routing algorithms in computer networks.
## 7. [Shortest path with exactly k edges in a directed and weighted graph:](https://www.geeksforgeeks.org/dsa/shortest-path-exactly-k-edges-directed-weighted-graph/)
> This problem involves finding the shortest path with a specific number of edges in a directed and weighted graph. The solution often relies on dynamic programming techniques to calculate the shortest paths for varying numbers of edges.
**Algorithm Steps:**
- Initialize a 3D array to store shortest paths for different numbers of edges.
- Use dynamic programming to fill the array:
  - dp[i][j][e] represents the shortest path from i to j with exactly e edges.
  - dp[i][j][e] = min(dp[i][j][e], dp[i][k][e-1] + dp[k][j][1]) for each vertex k.
**Applications:**
- Optimization problems involving specific edge constraints.
## 8. [Biconnected graph:](https://www.geeksforgeeks.org/dsa/biconnectivity-in-a-graph/)
> A biconnected graph is a graph that remains connected even after the removal of any single vertex (and its incident edges). Biconnected graphs are crucial in designing robust network structures, and algorithms for identifying them are essential for network reliability.
**Algorithm Steps:**
- Use DFS to traverse the graph, maintaining information about discovery time and low value for each vertex.
- For each edge (u, v), if v is not visited, recursively call DFS for v.
- Update the low value of u based on the low value of v.
- If the low value of v is greater than or equal to the discovery time of u, u is an articulation point.
- If u is the root of the DFS tree and has more than one child, it is an articulation point.
**Applications:**
- Designing robust network structures.
- Fault-tolerant systems.
## 9. [Articulation Points (or Cut Vertices) in a Graph:](https://www.geeksforgeeks.org/dsa/articulation-points-or-cut-vertices-in-a-graph/)
> Articulation points are vertices whose removal would disconnect a graph. Detecting these points is essential in network design to ensure robustness and fault tolerance. Algorithms for finding articulation points often use depth-first search.
**Algorithm Steps:**
- Use DFS to traverse the graph, maintaining information about discovery time and low value for each vertex.
- For each edge (u, v), if v is not visited, recursively call DFS for v.
- Update the low value of u based on the low value of v.
- If the low value of v is greater than or equal to the discovery time of u, u is an articulation point.
**Applications:**
- Network design for robustness.
- Fault detection in systems.
## 10. [Check if a graph is strongly connected (Kosaraju’s Theorem):](https://www.geeksforgeeks.org/dsa/strongly-connected-components/)
> Kosaraju’s Theorem provides an efficient algorithm for checking whether a directed graph is strongly connected, meaning there is a directed path from every vertex to every other vertex.
**Algorithm Steps:**
- Perform DFS on the original graph, keeping track of finishing times.
- Transpose the graph (reverse all edges).
- Perform DFS on the transposed graph in decreasing order of finishing times.
- If all vertices are visited in the second DFS, the graph is strongly connected.
**Applications:**
- Web page ranking algorithms.
- Social network analysis.
## 11. [Bridges in a graph:](https://www.geeksforgeeks.org/dsa/bridge-in-a-graph/)
> Bridges, also known as cut edges, are edges whose removal increases the number of connected components in a graph. Detecting bridges is crucial for network design and ensuring connectivity.
**Algorithm Steps:**
- Use DFS to traverse the graph, maintaining information about discovery time and low value for each vertex.
- For each edge (u, v), if v is not visited, recursively call DFS for v.
- Update the low value of u based on the low value of v.
- If the low value of v is greater than the discovery time of u, the edge (u, v) is a bridge.
**Applications:**
- Network design for reliability.
- Critical infrastructure analysis.
## 12. [Transitive closure of a graph:](https://www.geeksforgeeks.org/dsa/transitive-closure-of-a-graph/)
> The transitive closure of a graph involves determining all pairs of vertices reachable from each other. Algorithms for transitive closure are vital in optimizing graph-related queries and analyses.
**Algorithm Steps:**
- Initialize a matrix to represent the transitive closure.
- Perform a DFS from each vertex to mark reachable vertices.
- The matrix entry (i, j) is true if there is a path from i to j in the graph.
**Applications:**
- Query optimization in databases.
- Compiler optimizations.
## 13. Minimum Spanning Tree (MST):
> A minimum spanning tree (MST) of a connected undirected graph is a subgraph that includes the all the vertices of graph with the minimum possible total edge weight. The MSTs have the various applications in the network design, circuit wiring and clustering algorithms.
### Algorithm Steps:
- Start with the any vertex as the initial tree.
- At each step, add the minimum weight edge that connects a vertex in the tree to the vertex outside the tree.
- Repeat the process until all vertices are included in tree.
### Applications:
- Network design to minimize infrastructure costs.
- Circuit design to the minimize wire usage.
- Cluster analysis in the data mining and machine learning.
## Previously Asked GATE Questions on Graph-Based Algorithms:
**Question 1:** Which of the following statements is/are TRUE for an undirected graph?
P: Number of odd degree vertices is even
Q: Sum of degrees of all vertices is even
A) P Only
B) Q Only
C) Both P and Q
D) Neither P nor Q
> **Answer:** **(C)**
>
> **Explanation:** Q is true: Since the graph is undirected, every edge increases the sum of degrees by 2.
> P is true: If we consider sum of degrees and subtract all even degrees, we get an even number (because Q is true). So total number of odd degree vertices must be even.
**Question 2:** Consider an undirected random graph of eight vertices. The probability that there is an edge between a pair of vertices is 1/2. What is the expected number of unordered cycles of length three?
(A) 1/8
(B) 1
(C) 7
(D) 8
> **Answer:** **(C)**
>
> **Explanation:** A cycle of length 3 can be formed with 3 vertices. There can be total 8C3 ways to pick 3 vertices from 8. The probability that there is an edge between two vertices is 1/2. So expected number of unordered cycles of length 3 = (8C3)\*(1/2)^3 = 7
**Question 3:** What is the time complexity of Bellman-Ford single-source shortest path algorithm on a complete graph of n vertices?
(A) Θ(n2)
(B) Θ(n2 Logn)
(C) Θ(n3)
(D) Θ(n3 Logn)
> **Answer:** **(C)**
>
> **Explanation:** Time complexity of Bellman-Ford algorithm is Θ(VE) where V is number of vertices and E is number edges (See [this](https://www.geeksforgeeks.org/dsa/bellman-ford-algorithm-dp-23/)). If the graph is complete, the value of E becomes Θ(V2). So overall time complexity becomes Θ(V3)
**Question 4:**Which of the following statements are TRUE?
(1) The problem of determining whether there exists a cycle in an undirected graph is in P.
(2) The problem of determining whether there exists a cycle in an undirected graph is in NP.
(3) If a problem A is NP-Complete, there exists a non-deterministic polynomial time algorithm to solve A.
(A) 1,2 and 3
(B) 1 and 2 only
(C) 2 and 3 only
(D) 1 and 3 only
> **Answer:** **(A)**
>
> **Explanation:** **1**is true because cycle detection can be done in polynomial time using DFS (See [this](https://www.geeksforgeeks.org/dsa/detect-cycle-in-a-graph/)).
> **2**is true because P is a subset of NP.
> **3**is true because NP complete is also a subset of NP and NP means **N**on-deterministic **P**olynomial time solution exists. (See [this](https://en.wikipedia.org/wiki/NP_(complexity)))
**Question 5:**Consider a complete undirected graph with vertex set {0, 1, 2, 3, 4}. Entry Wij in the matrix W below is the weight of the edge {i, j}.
![undirected graph with vertex set](assets/2010-f06bb37788.gif)What is the minimum possible weight of a spanning tree T in this graph such that vertex 0 is a leaf node in the tree T?
(A) 7
(B) 8
(C) 9
(D) 10
> **Answer:** **(D)**
>
> **Explanation:** To get the minimum spanning tree with vertex 0 as leaf, first remove 0th row and 0th column and then get the minimum spanning tree (MST) of the remaining graph. Once we have MST of the remaining graph, connect the MST to vertex 0 with the edge with minimum weight (we have two options as there are two 1s in 0th row).
**Question 6:** In the graph given in question 1, what is the minimum possible weight of a path P from vertex 1 to vertex 2 in this graph such that P contains at most 3 edges?
(A) 7
(B) 8
(C) 9
(D) 10
> **Answer:** **(B)**
>
> **Explanation:** Path: 1 -> 0 -> 4 -> 2
> Weight: 1 + 4 + 3
**Question 7:**The degree sequence of a simple graph is the sequence of the degrees of the nodes in the graph in decreasing order. Which of the following sequences can not be the degree sequence of any graph?
I. 7, 6, 5, 4, 4, 3, 2, 1
II. 6, 6, 6, 6, 3, 3, 2, 2
III. 7, 6, 6, 4, 4, 3, 2, 2
IV. 8, 7, 7, 6, 4, 2, 1, 1
(A) I and II
(B) III and IV
(C) IV only
(D) II and IV
> **Answer:** **(D)**
>
> **Explanation:** In sequence IV, we have a vertex with degree 8 which is not possible in a [simple graph](https://mathworld.wolfram.com/SimpleGraph.html) (no self loops and no multiple edges) with total vertex count as 8. Maximum possible degree in such a graph is 7.
>
> In sequence II, four vertices are connected to 6 other vertices, but remaining 4 vertices have degrees as 3, 3, 2 and 2 which are not possible in a simple graph (no self loops and no multiple edges).
**Question 8:**In an unweighted, undirected connected graph, the shortest path from a node S to every other node is computed most efficiently, in terms of time complexity by 
(A) Dijkstra’s algorithm starting from S. 
(B) Warshall’s algorithm 
(C) Performing a DFS starting from S. 
(D) Performing a BFS starting from S.
> **Answer:** **(D)**
>
> **Explanation:**
>   \* Time Complexity of the [Dijkstra’s algorithm](https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm) is O(|V|^2 + E)
>  \* Time Complexity of the [Warshall’s algorithm](https://en.wikipedia.org/wiki/Floyd%E2%80%93Warshall_algorithm) is O(|V|^3)
>  \* [DFS](https://en.wikipedia.org/wiki/Depth-first_search) cannot be used for finding shortest paths
>  \* [BFS](https://en.wikipedia.org/wiki/Breadth-first_search) can be used for unweighted graphs. Time Complexity for BFS is O(|E| + |V|)
**Question 9:**For a graph with E edges and V vertices what is the time complexity of Dijkstra algorithm using array as data structure for storing non-finalized vertices. Graph is undirected and represented as adjacency list? 
(A) O(VE) 
(B) O(ElogV) 
(C) O(V^2 ) 
(D) O(E^2log V)
> **Answer:**(C)
>
> **Explanation:**
> Given data structure used is array so initialization of all nodes in array (setting infinity to all nodes which are not reachable), this operation takes O(V) 
> At each step we have to delete minimum from the array. For one such operation it takes O(V), using selection sort first pass. We have V such steps. So total complexity due to deletion of minimum element at each step = V\*O(V) = O(V^2) 
> After a minimum is selected at each step we have to check its adjacent and perform decrease key to the neighbors of selected node. It takes total O(2E) to check adjacents for all steps. Also the decrease key of all the steps is E. O(1) = O(E) . Since the array is unsorted we don’t have to sort the array at each step. 
> Total complexity = O(V) + O(V^2) + O(2E) + O(E) = O(V^2) 
> Note: For a simple graph V^2 is always >= E 
**Question 10:** To implement Dijkstra’s shortest path algorithm on unweighted graphs so that it runs in linear time, the data structure to be used is:
(A) Queue
(B) Stack
(C) Heap
(D) B-Tree
> **Answer:** **(A)**
>
> **Explanation:** The shortest path in an un-weighted graph means the smallest number of edges that must be traversed in order to reach the destination in the graph. This is the same problem as solving the weighted version where all the weights happen to be 1. If we use Queue (FIFO) instead of Priority Queue (Min Heap), we get the shortest path in linear time O(|V| + |E|). Basically we do [BFS](https://en.wikipedia.org/wiki/Breadth-first_search)traversal of the graph to get the shortest paths.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/graph-based-algorithms-for-gate-exam/#1-breadth-first-search-or-bfs-for-a-graph-bfs-)

## GATE CS

- Subject: Algorithms
- Topic: Graph Algorithms

> [!note] Related notes
>
> - [[Applications of Depth First Search]]
> - [[Introduction to Graph Algorithms]]
> - [[Asymptotic Notations]]
> - [[Binary Search]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
> - [[Dijkstra’s Algorithm for Adjacency List Representation]]
> - [[Efficient Huffman Coding for Sorted Input]]
> - [[Fractional Knapsack Problem]]
> - [[Introduction of Algorithms]]
> - [[Introduction to Divide and Conquer]]
