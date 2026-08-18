---
title: "Tree Traversal Techniques"
subject: "Data Structures & C Programming"
topic: "Binary Search Trees"
source: "https://www.geeksforgeeks.org/dsa/tree-traversals-inorder-preorder-and-postorder/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Data Structures & C Programming/Binary Search Trees"
tags:
  - gate/cs
  - subject/data-structures-c-programming
  - topic/binary-search-trees
---


> [!abstract] Tree Traversal Techniques
> 
> **Subject:** `Data Structures & C Programming` &nbsp;|&nbsp; **Topic:** `Binary Search Trees`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/tree-traversals-inorder-preorder-and-postorder/)

---

# Tree Traversal Techniques

Tree traversal refers to the process of visiting or accessing each node of a tree exactly once in a specific order. Unlike linear data structures such as arrays, linked lists, or queues (which have only one logical way of traversal), trees offer multiple ways to traverse their nodes.
Tree traversals are broadly classified into two categories:
![tree_traversal_techniques](assets/tree_traversal_techniques-86f8a784c2.webp)
**Depth-First Traversal (DFT)**
- Explores as far as possible along a branch before exploring the next branch.
- Types: Inorder, Preorder, Postorder
**Breadth-First Traversal (BFT)**
- Explores nodes level by level from top to bottom.
- Type: Level Order Traversal.
- The level order traversal of the above tree is 1, 2, 3, 4, 5, 6, and 7.
![tree_construction_from_given_inorder_and_preorder_traversals_8](assets/tree_construction_from_given_inorder_and-9fb07155e2.webp)
## **Inorder Traversal**
Inorder traversal visits the node in the order:  **Left -> Root -> Right**
**Algorithm for Inorder Traversal**
> Inorder(tree )
> ● Traverse the left subtree, i.e., call Inorder(left->subtree)
> ● Visit the root.
> ● Traverse the right subtree, i.e., call Inorder(right->subtree)
**Uses of Inorder Traversal**
- In the case of binary search trees (BST), Inorder traversal gives nodes in non-decreasing order.
- To get nodes of BST in non-increasing order, a variation of Inorder traversal where Inorder traversal is reversed can be used.
- Inorder traversal can be used to evaluate arithmetic expressions stored in expression trees.
> **Also Check:** Refer [Inorder Traversal of Binary Tree](https://www.geeksforgeeks.org/dsa/inorder-traversal-of-binary-tree/) for more
## **Preorder Traversal**
Preorder traversal visits the node in the order:  **Root -> Left -> Right**
**Algorithm for Preorder Traversal**
> Preorder(tree)
>
> ● Visit the root.
> ● Traverse the left subtree, i.e., call Preorder(left->subtree)
> ● Traverse the right subtree, i.e., call Preorder(right->subtree)
**Uses of Preorder Traversal**
- Preorder traversal is used to create a copy of the tree.
- Preorder traversal is also used to get prefix expressions on an expression tree.
> **Also Check:** Refer [Preorder Traversal of Binary Tree](https://www.geeksforgeeks.org/dsa/preorder-traversal-of-binary-tree/) for more
## **Postorder Traversal**
Postorder traversal visits the node in the order:  **Left -> Right -> Root**
**Algorithm for Postorder Traversal:**
> Postorder(tree)
>
> ●Traverse the left subtree, i.e., call Postorder(left->subtree)
> ● Traverse the right subtree, i.e., call Postorder(right->subtree)
> ● Visit the root
**Uses of Postorder Traversal**
- Postorder traversal is used to delete the tree.
- Postorder traversal is also useful to get the postfix expression of an expression tree.
- Postorder traversal can help in garbage collection algorithms, particularly in systems where manual memory management is used.
> **Also Check**: Refer [Postorder Traversal of Binary Tree](https://www.geeksforgeeks.org/dsa/postorder-traversal-of-binary-tree/) for more
## Level Order Traversal
Level Order Traversal visits all nodes present in the same level completely before visiting the next level.
**Algorithm for Level Order Traversal**
> LevelOrder(tree)
>
> ● Create an empty queue Q
> ● Enqueue the root node of the tree to Q
> ● Loop while Q is not empty
>  ○Dequeue a node from Q and visit it
>  ○ Enqueue the left child of the dequeued node if it exists
>  ○ Enqueue the right child of the dequeued node if it exists .
**Uses of Level Traversal**
1. Level-wise node processing, like finding maximum/minimum at each level.
2. Tree serialization/deserialization for efficient storage and reconstruction.
3. Solving problems like calculating the "maximum width of a tree" by processing nodes level by level.
> **Also Check**: Refer [Level Order Traversal (Breadth First Search or BFS) of Binary Tree](https://www.geeksforgeeks.org/dsa/level-order-tree-traversal/) for more
## Other Tree Traversals
1. Boundary Traversal
2. Diagonal Traversal
### 1. Boundary Traversal
**Boundary Traversal**  of a Tree includes
- left boundary (nodes on left excluding leaf nodes)
- leaves (consist of only the leaf nodes)
- right boundary (nodes on right excluding leaf nodes)
![boundary-traversal](assets/boundary-traversal-560bad6799.png)
> **Also Check:** Refer [Boundary Traversal of binary tree](https://www.geeksforgeeks.org/dsa/boundary-traversal-of-binary-tree/) for more
### 2. Diagonal Traversal
In the Diagonal Traversal of a Tree, all the nodes in a single diagonal will be printed one by one.
![Diagonal-Traversal-of-binary-tree](assets/Diagonal-Traversal-of-binary-tree-0605ed03c4.webp)
> **Also Check:** Refer [Diagonal Traversal of Binary Tree](https://www.geeksforgeeks.org/dsa/diagonal-traversal-of-binary-tree/) for more
### Related Articles
- [Construct Tree from given Inorder and Preorder traversals](https://www.geeksforgeeks.org/dsa/construct-tree-from-given-inorder-and-preorder-traversal/)
- [DSA Tutorial](https://www.geeksforgeeks.org/dsa/dsa-tutorial-learn-data-structures-and-algorithms/)
- [Tree Coding Problems for Interviews](https://www.geeksforgeeks.org/dsa/top-50-tree-coding-problems-for-interviews/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/tree-traversals-inorder-preorder-and-postorder/)

## GATE CS

- Subject: Data Structures & C Programming
- Topic: Binary Search Trees

> [!note] Related notes
>
> - [[I ntroduction to Trees]]
> - [[1D, 2D and 3D Arrays]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
> - [[Data Types in C]]
> - [[Double Hashing]]
> - [[Enum, Struct & Union in C]]
> - [[Functions in C]]
> - [[Introduction to Arrays]]
> - [[Introduction to C Programming]]
> - [[Introduction to Graphs]]
