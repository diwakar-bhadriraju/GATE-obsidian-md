---
title: "Relationship between number of nodes and height of binary tree"
subject: "Discrete Mathematics"
topic: "Graphs"
source: "https://www.geeksforgeeks.org/dsa/relationship-number-nodes-height-binary-tree/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Graphs"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/graphs
---


> [!abstract] Relationship between number of nodes and height of binary tree
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Graphs`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/relationship-number-nodes-height-binary-tree/)

---

# Relationship between number of nodes and height of binary tree

**Binary Tree** is a hierarchical data structure in which each node has at most two children, referred to as the left child and the right child. It is commonly used in computer science for efficient storage and retrieval of data, with various operations such as insertion, deletion, and traversal.
Prerequisite - [Binary Tree Data Structure](https://www.geeksforgeeks.org/dsa/binary-tree-data-structure/) 
### Height of Binary Tree
The **height** of the binary tree is the longest path from root **node to any leaf** node in the tree. For example, the height of binary tree shown in Figure 1(b) is 2 as longest path from root node to node 2 is 2. Also, the height of binary tree shown in Figure 1(a) is 4. 
### **Calculating minimum and maximum height from the number of nodes -**
If there are n nodes in a binary tree, the **maximum height** of the binary tree is **n-1,** and the **minimum height** is **floor (log2(n))**. 
For example, the left skewed binary tree shown in Figure 1(a) with 5 nodes has a height of 5-1 = 4, and the binary tree shown in Figure 1(b) with 5 nodes has a height floor(log25) = 2. 
![11](assets/Node_height-b4d5ed64f0.jpg)
### **Calculating minimum and maximum number of nodes from height:**
If binary tree has **height h**, minimum number of **nodes is h+1** (in case of left skewed and right skewed binary tree). For example, the binary tree shown in Figure 2(a) with height 2 has 3 nodes. 
If binary tree has height h, maximum number of nodes will be when all levels are completely full. Total number of nodes will be 2^0 + 2^1 + …. 2^h = **2^(h+1)-1.** For example, the binary tree shown in Figure 2(b) with height 2 has 2^(2+1)-1 = 7 nodes.
![222](assets/Node_height_1-jpg-bbd8160810.jpg)
## Questions on Finding Height of Binary Tree
**Question-1.** **The height of a tree is the length of the longest root-to-leaf path in it. The maximum and the minimum number of nodes in a binary tree of height 5 are:**
- **(A) 63 and 6, respectively**
- **(B) 64 and 5, respectively**
- **(C) 32 and 6, respectively**
- **(D) 31 and 5, respectively**
**Solution:**
> According to formula discussed, 
> max number of nodes = 2^(h+1)-1 = 2^6-1 =63. 
> min number of nodes = h+1 = 5+1 = 6. 
**Question-2.** **Which of the following height is not possible for a binary tree with 50 nodes?**
- **(A) 4**
- **(B**) 5
- **(C)** 6
- **(D)** None
**Solution:**
> According to formula discussed, 
> Minimum height with 50 nodes = floor(log2(50)) = 5. Therefore, height 4 is not possible.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/relationship-number-nodes-height-binary-tree/)

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
> - [[Planar Graphs and Graph Coloring]]
