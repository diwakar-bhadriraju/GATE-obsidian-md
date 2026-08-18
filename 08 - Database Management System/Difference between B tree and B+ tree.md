---
title: "Difference between B tree and B+ tree"
subject: "Database Management System"
topic: "File Structures"
source: "https://www.geeksforgeeks.org/dsa/difference-between-b-tree-and-b-tree/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/File Structures"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/file-structures
---


> [!abstract] Difference between B tree and B+ tree
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `File Structures`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/difference-between-b-tree-and-b-tree/)

---

# Difference between B tree and B+ tree

[**B-Tree**](https://www.geeksforgeeks.org/dsa/introduction-of-b-tree-2/)**:** B-Tree is known as a self-balancing tree as its nodes are sorted in the inorder traversal. In B-tree, a node can have more than two children. B-tree has a height of logM N (Where ‘M’ is the order of tree and N is the number of nodes). And the height is adjusted automatically at each update. In the B-tree data is sorted in a specific order, with the lowest value on the left and the highest value on the right. To insert the data or key in B-tree is more complicated than a binary tree. Some conditions must be held by the B-Tree:
- All the leaf nodes of the B-tree must be at the same level.
- Above the leaf nodes of the B-tree, there should be no empty sub-trees.
- B- tree's height should lie as low as possible.
![](assets/Untitled-Diagram111-f79c4211a5.png)
[**B+ Tree**](https://www.geeksforgeeks.org/dbms/introduction-of-b-tree/) B+ tree eliminates the drawback B-tree used for indexing by storing data pointers only at the leaf nodes of the tree. Thus, the structure of leaf nodes of a B+ tree is quite different from the structure of internal nodes of the B tree. It may be noted here that, since data pointers are present only at the leaf nodes, the leaf nodes must necessarily store all the key values along with their corresponding data pointers to the disk file block, to access them. Moreover, the leaf nodes are linked to providing ordered access to the records. The leaf nodes, therefore form the first level of the index, with the internal nodes forming the other levels of a multilevel index. Some of the key values of the leaf nodes also appear in the internal nodes, to simply act as a medium to control the searching of a record. ![](assets/Btree-4caeaff4cc.jpg)
Let's see the difference between B-tree and B+ tree:
| Basis of Comparison | B tree | B+ tree |
| --- | --- | --- |
| **Pointers** | All internal and leaf nodes have data pointers | Only leaf nodes have data pointers |
| **Search** | Since all keys are not available at leaf, search often takes more time. | All keys are at leaf nodes, hence search is faster and more accurate. |
| **Redundant Keys** | No duplicate of keys is maintained in the tree. | Duplicate of keys are maintained and all nodes are present at the leaf. |
| **Insertion** | Insertion takes more time and it is not predictable sometimes. | Insertion is easier and the results are always the same. |
| **Deletion** | Deletion of the internal node is very complex and the tree has to undergo a lot of transformations. | Deletion of any node is easy because all node are found at leaf. |
| **Leaf Nodes** | Leaf nodes are not stored as structural linked list. | Leaf nodes are stored as structural linked list. |
| **Access** | Sequential access to nodes is not possible | Sequential access is possible just like linked list |
| **Height** | For a particular number nodes height is larger | Height is lesser than B tree for the same number of nodes |
| **Application** | B-Trees used in Databases, Search engines | B+ Trees used in Multilevel Indexing, Database indexing |
| **Number of Nodes** | Number of nodes at any intermediary level ‘l’ is 2l. | Each intermediary node can have n/2 to n children. |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/difference-between-b-tree-and-b-tree/)

## GATE CS

- Subject: Database Management System
- Topic: File Structures

> [!note] Related notes
>
> - [[Deletion in B-Tree]]
> - [[File Organization]]
> - [[Hashing in DBMS]]
> - [[Indexing in Databases]]
> - [[Insertion in a B+ tree]]
> - [[Insertion in B-Tree]]
> - [[Introduction to B+ Trees]]
> - [[Introduction to B-Tree]]
> - [[ACID Properties in DBMS]]
> - [[Advantages of DBMS over File system]]
