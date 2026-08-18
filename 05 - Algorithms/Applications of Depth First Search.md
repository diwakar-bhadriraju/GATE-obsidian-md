---
title: "Applications, Advantages and Disadvantages of Depth First Search (DFS)"
subject: "Algorithms"
topic: "Graph Algorithms"
source: "https://www.geeksforgeeks.org/dsa/applications-of-depth-first-search/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Algorithms/Graph Algorithms"
tags:
  - gate/cs
  - subject/algorithms
  - topic/graph-algorithms
---


> [!abstract] Applications, Advantages and Disadvantages of Depth First Search (DFS)
> 
> **Subject:** `Algorithms` &nbsp;|&nbsp; **Topic:** `Graph Algorithms`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/applications-of-depth-first-search/)

---

# Applications, Advantages and Disadvantages of Depth First Search (DFS)

[Depth First Search](https://www.geeksforgeeks.org/dsa/depth-first-search-or-dfs-for-a-graph/) is a widely used algorithm for traversing a graph. Here we have discussed some applications, advantages, and disadvantages of the algorithm.
## Applications of Depth First Search:
**1. Detecting cycle in a graph:** A graph has a cycle if and only if we see a back edge during DFS. So we can run DFS for the graph and check for back edges.
**2. Path Finding:** We can specialize the DFS algorithm to find a path between two given vertices u and z. 
- Call DFS(G, u) with u as the start vertex.
- Use a stack S to keep track of the path between the start vertex and the current vertex.
- As soon as destination vertex z is encountered, return the path as the contents of the stack
**3. Topological Sorting:** [Topological Sorting](https://www.geeksforgeeks.org/dsa/topological-sorting/) is mainly used for scheduling jobs from the given dependencies among jobs. In computer science, applications of this type arise in instruction scheduling, ordering of formula cell evaluation when recomputing formula values in spreadsheets, logic synthesis, determining the order of compilation tasks to perform in makefiles, data serialization, and resolving symbol dependencies in linkers.
**4. To** [**test if a graph is bipartite**](https://www.geeksforgeeks.org/dsa/check-if-a-given-graph-is-bipartite-using-dfs/)**:** We can augment either BFS or DFS when we first discover a new vertex, color it opposite its parents, and for each other edge, check it doesn't link two vertices of the same color. The first vertex in any connected component can be red or black.
**5. Finding Strongly Connected Components of a graph:** A directed graph is called strongly connected if there is a path from each vertex in the graph to every other vertex. (See [**this**](https://www.geeksforgeeks.org/dsa/strongly-connected-components/) for DFS-based algo for finding Strongly Connected Components)
**6. Solving puzzles with only one solution:** such as mazes. (DFS can be adapted to find all solutions to a maze by only including nodes on the current path in the visited set.).
**7. Web crawlers:** Depth-first search can be used in the implementation of web crawlers to explore the links on a website.
**8. Maze generation:** Depth-first search can be used to generate random mazes.
**9. Model checking:** Depth-first search can be used in model checking, which is the process of checking that a model of a system meets a certain set of properties.
**10. Backtracking:** Depth-first search can be used in backtracking algorithms.
## Advantages of Depth First Search:
- Memory requirement is only linear with respect to the search graph. This is in contrast with breadth-first search which requires more space. The reason is that the algorithm only needs to store a stack of nodes on the path from the root to the current node.
- The time complexity of a depth-first Search to depth d and branching factor b (the number of children at each node, the outdegree) is O(bd) since it generates the same set of nodes as breadth-first search, but simply in a different order. Thus practically depth-first search is time-limited rather than space-limited.
- If depth-first search finds solution without exploring much in a path then the time and space it takes will be very less.
- DFS requires less memory since only the nodes on the current path are stored. By chance DFS may find a solution without examining much of the search space at all.
## Disadvantages of Depth First Search:
- The disadvantage of Depth-First Search is that there is a possibility that it may down the left-most path forever. Even a finite graph can generate an infinite solution to this problem is to impose a cutoff depth on the search. Although ideal cutoff is the solution depth d and this value is rarely known in advance of actually solving the problem. If the chosen cutoff depth is less than d, the algorithm will fail to find a solution, whereas if the cutoff depth is greater than d, a large price is paid in execution time, and the first solution found may not be an optimal one.
- Depth-First Search is not guaranteed to find the solution.
- And there is no guarantee to find a minimal solution, if more than one solution.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/applications-of-depth-first-search/)

## GATE CS

- Subject: Algorithms
- Topic: Graph Algorithms

> [!note] Related notes
>
> - [[Breadth First Traversal or BFS for a Graph]]
> - [[Introduction to Graph Algorithms]]
> - [[Asymptotic Notations]]
> - [[Binary Search]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
> - [[Dijkstra’s Algorithm for Adjacency List Representation]]
> - [[Efficient Huffman Coding for Sorted Input]]
> - [[Fractional Knapsack Problem]]
> - [[Introduction of Algorithms]]
> - [[Introduction to Divide and Conquer]]
