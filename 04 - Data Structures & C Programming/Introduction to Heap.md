---
title: "Binary Heap Notes for GATE Exam [2024]"
subject: "Data Structures & C Programming"
topic: "Binary Heaps"
source: "https://www.geeksforgeeks.org/dsa/binary-heap-notes-for-gate-exam/#introduction-to-heap"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Data Structures & C Programming/Binary Heaps"
tags:
  - gate/cs
  - subject/data-structures-c-programming
  - topic/binary-heaps
---


> [!abstract] Binary Heap Notes for GATE Exam [2024]
> 
> **Subject:** `Data Structures & C Programming` &nbsp;|&nbsp; **Topic:** `Binary Heaps`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/binary-heap-notes-for-gate-exam/#introduction-to-heap)

---

# Binary Heap Notes for GATE Exam [2024]

In the GATE Exam, understanding binary heaps is like having a secret weapon. Questions might ask you to pick the right tool for a job, and heaps are often the superheroes of quick and efficient data organization.
Table of Content
- [Introduction to Heap:](#introduction-to-heap)
- [Types of heaps:](#types-of-heaps)
- [Representation of Binary Heap:](#representation-of-binary-heap)
- [Operations on Binary Heaps:](#operations-on-binary-heaps)
- [Advantages of Heap Data Structure:](#advantages-of-heap-data-structure)
- [Disadvantages of Heap Data Structure:](#disadvantages-of-heap-data-structure)
- [Previously Asked GATE Questions on Binary Heap](#previously-asked-gate-questions-on-binary-heap)
## Introduction to Heap:
> **Binary heap** **is a complete binary tree where the root of any subtree has a higher (or lower based on the type of heap) value than all the nodes in its subtree.**
## Types of heaps:
There are 2 types of heaps:
1. Max-Heap
2. Min-Heap
### **1.** [**Max-Heap:**](https://www.geeksforgeeks.org/dsa/introduction-to-max-heap-data-structure/)
In a Max-Heap, the key at the root node must be the greatest among the keys present at all its children. The same property must be recursively true for all sub-trees in that Binary Tree.
### 2**.** [**Min-Heap:**](https://www.geeksforgeeks.org/dsa/introduction-to-min-heap-data-structure/)
In a Min-Heap the key at the root node must be minimum among the keys present at all of it’s children. The same property must be recursively true for all sub-trees in that Binary Tree.
## Representation of Binary Heap:
A Binary Heap is a **Complete Binary Tree**. A binary heap is typically represented as an array.
- The root element will be at Arr[0].
- The below table shows indices of other nodes for the ith node, i.e., Arr[i]:
| Arr[(i-1)/2] | Returns the parent node |
| Arr[(2\*i)+1] | Returns the left child node |
| Arr[(2\*i)+2] | Returns the right child node |
![binaryheap](assets/binaryheap-03a817d0a9.png)
Binary Heap
## Operations on Binary Heaps:
The common operation involved using heaps are:
1. **Heapify:** Process to rearrange the heap in order to maintain heap-property.
2. **Insertion:** Add a new item in the heap.
3. **Deletion:** Delete an item from the heap.
4. **Find-max (or Find-min):** find a maximum item of a max-heap, or a minimum item of a min-heap, respectively.
### 1. Heapify:
It is the process to rearrange the elements to maintain the property of heap data structure. It is done when a certain node creates an imbalance in the heap due to some operations on that node. It takes **O(log N)**to balance the tree. 
### 2. Insertion:
If we insert a new element into the heap since we are adding a new element into the heap so it will distort the properties of the heap so we need to perform the **heapify** operation so that it maintains the property of the heap. This operation also takes **O(logN)** time.
**Example :**
> Assume initially heap(taking **max-heap**) is as follows
>
>            8
>         /   \
>      4     5
>    / \
> 1   2
>
> Now if we insert 10 into the heap
>              8
>         /      \
>       4       5
>    /  \      /
> 1    2  10 
>
> After heapify operation final heap will be look like this
>            10
>          /    \
>       4      8
>    /  \     /
> 1    2  5
### 3. Deletion:
If we delete the element from the heap it always deletes the root element of the tree and replaces it with the last element of the tree. Since we delete the root element from the heap it will distort the properties of the heap so we need to perform heapify operations so that it maintains the property of the heap. It takes **O(logN)** time.
**Example:**
> Assume initially heap(taking max-heap) is as follows
>            15
>          /   \
>       5     7
>    /  \
> 2     3
>
> Now if we delete 15 into the heap it will be replaced by leaf node of the tree for temporary.
>            3
>         /   \
>      5     7
>    /    
> 2
>
> After heapify operation final heap will be look like this
>            7
>         /   \
>      5     3
>    /   
> 2
### 4. **Find-max (or Find-min)**:
It finds the maximum element or minimum element for **max-heap** and **min-heap** respectively and as we know minimum and maximum elements will always be the root node itself for min-heap and max-heap respectively. It takes **O(1)** time.
# [Time Complexity of building a heap](https://www.geeksforgeeks.org/dsa/time-complexity-of-building-a-heap/):
### Algorithm for building a Heap of an input array A:
> BUILD-HEAP(A) 
>
>     heapsize := size(A); 
>
>     for i := floor(heapsize/2) downto 1 
>
>         do HEAPIFY(A, i); 
>
>     end for 
>
> END
A quick look over the above algorithm suggests that the running time is O(n\*log(n)) since each call to **Heapify** costs O(log(n)) and and **Build-Heap** makes O(n) such calls but this upper bound, though correct, is not asymptotically tight.  
We can derive a tighter bound by observing that the running time of **Heapify** depends on the height of the tree ‘h’ (which is equal to log(n), where n is a number of nodes) and the heights of most sub-trees are small.. Line-3 of **Build-Heap** runs a loop from the index of the last internal node (heapsize/2) to the index of root(1) . Hence, **Heapify** takes a different time for each node, which is:
For finding the Time Complexity of building a heap, we must know the number of nodes having height h. For this we use the fact that, A heap of size n has at most nodes
$$
\left \lceil \frac{n}{2^{h+1}} \right \rceil
$$
 with height h. 
To derive the time complexity, we express the total cost of **Build-Heap** as- 
$$
T(n) = \sum_{h = 0}^{lg(n)}\left \lceil \frac{n}{2^{h+1}} \right \rceil * O(h)= O(n * \sum_{h = 0}^{lg(n)}\frac{h}{2^{h}})= O(n * \sum_{h = 0}^{\infty}\frac{h}{2^{h}})
$$
Step 2 uses the properties of the Big-Oh notation to ignore the ceiling function and the constant
$$
2(2^{h+1} = 2.2^h)
$$
. Similarly in Step three, the upper limit of the summation can be increased to infinity since we are using Big-Oh notation. Sum of infinite G.P. (x < 1) 
$$
\sum_{n = 0}^{\infty}{x}^{n} = \frac{1}{1-x}
$$
On differentiating both sides and multiplying by x, we get 
$$
\sum_{n = 0}^{\infty}n{x}^{n} = \frac{x}{(1-x)^{2}}
$$
Putting the result obtained in (3) back in our derivation (1), we get
$$
= O(n * \frac{\frac{1}{2}}{(1 - \frac{1}{2})^2})= O(n * 2)= O(n)
$$
Hence Proved that the Time complexity for Building a Binary Heap is 
$$
O(n)
$$
. 
## [Advantages of Heap **Data Structure**:](https://www.geeksforgeeks.org/dsa/applications-advantages-and-disadvantages-of-heap/)
- **Efficient insertion and deletion:**The heap data structure allows efficient insertion and deletion of elements. When a new element is added to the heap, it is placed at the bottom of the heap and moved up to its correct position using the heapify operation. Similarly, when an element is removed from the heap, it is replaced by the bottom element, and the heap is restructured using the heapify operation.
- **Efficient priority queue:** The heap data structure is commonly used to implement a priority queue, where the highest priority element is always at the top of the heap. The heap allows constant-time access to the highest priority element, making it an efficient data structure for implementing priority queues.
- **Guaranteed access to the maximum or minimum element**: In a max-heap, the top element is always the maximum element, and in a min-heap, the top element is always the minimum element. This provides guaranteed access to the maximum or minimum element in the heap, making it useful in algorithms that require access to the extreme values.
- **Space efficiency:**The heap data structure requires less memory compared to other data structures, such as linked lists or arrays, as it stores elements in a complete binary tree structure.
- **Heap-sort algorithm**: The heap data structure forms the basis for the heap-sort algorithm, which is an efficient sorting algorithm that has a worst-case time complexity of O(n log n).
## [**Disadvantages of Heap Data Structure:**](https://www.geeksforgeeks.org/dsa/applications-advantages-and-disadvantages-of-heap/)
- **Lack of flexibility:** The heap data structure is not very flexible, as it is designed to maintain a specific order of elements. This means that it may not be suitable for some applications that require more flexible data structures.
- **Not ideal for searching:**While the heap data structure allows efficient access to the top element, it is not ideal for searching for a specific element in the heap. Searching for an element in a heap requires traversing the entire tree, which has a time complexity of O(n).
- **Not a stable data structure:**The heap data structure is not a stable data structure, which means that the relative order of equal elements may not be preserved when the heap is constructed or modified.
- **Memory management:**The heap data structure requires dynamic memory allocation, which can be a challenge in some systems with limited memory. In addition, managing the memory allocated to the heap can be complex and error-prone.
- **Complexity:** While the heap data structure allows efficient insertion, deletion, and priority queue implementation, it has a worst-case time complexity of O(n log n), which may not be optimal for some applications that require faster algorithms.
## Previously Asked GATE Questions on Binary Heap
**Question 1:** The elements 32, 15, 20, 30, 12, 25, 16 are inserted one by one in the given order into a Max Heap. The resultant Max Heap is.
![tree](assets/tree-3a4782d5b2.gif)
> #### Answer: (a)
**Question 2:**In a heap with n elements with the smallest element at the root, the 7th smallest element can be found in time (GATE CS 2003)
a) Θ(n log n)
b) Θ(n)
c) Θ(log n)
d) Θ(1)
> #### Answer: (d)
>
> **Explanation:**The 7th smallest element must be in first 7 levels. Total number of nodes in any Binary Heap in first 7 levels is at most 1 + 2 + 4 + 8 + 16 + 32 + 64 which is a constant. Therefore we can always find 7th smallest element in Θ(1) time.
**Question 3:**The number of elements that can be sorted in Θ(logn) time using heap sort is
(a) Θ(1)
(b) Θ(sqrt(logn))
(c) Θ(Log n/(Log Log n))
(d) Θ(Log n)
> **Answer:** **(c)**
>
> **Explanation:** Time complexity of Heap Sort is Θ(mLogm) for m input elements. For m = Θ(Log n/(Log Log n)), the value of Θ(m \* Logm) will be Θ( [Log n/(Log Log n)] \* [Log (Log n/(Log Log n))] ) which will be Θ( [Log n/(Log Log n)] \* [ Log Log n - Log Log Log n] ) which is Θ(Log n)
**Question** 4: A max-heap is a heap where the value of each parent is greater than or equal to the values of its children. Which of the following is a max-heap?
![](assets/gate_2011_2-72ffa7c777.gif)
> **Answer:** **(B)**
> A binary tree is max-heap if it is a complete binary tree (A complete binary tree is a binary tree in which every level, except possibly the last, is completely filled, and all nodes are as far left as possible) and it follows the max-heap property (value of each parent is greater than or equal to the values of its children).
>
> A) is not a max-heap because it is not a complete binary tree
> B) is a max-heap because it is complete binary tree and follows max-heap property.
> C) is not a max-heap because 8 is a chile of 5 in this tree, so violates the max-heap property.
> D) is not a max-heap because 8 is a chile of 5 in this tree, so violates the max-heap property. There are many other nodes in this tree which violate max-heap property in this tree
**Question 5:**A 3-ary max heap is like a binary max heap, but instead of 2 children, nodes have 3 children. A 3-ary heap can be represented by an array as follows: The root is stored in the first location, a[0], nodes in the next level, from left to right, is stored from a[1] to a[3]. The nodes from the second level of the tree from left to right are stored from a[4] location onward. An item x can be inserted into a 3-ary heap containing n items by placing x in the location a[n] and pushing it up the tree to satisfy the heap property.
Which one of the following is a valid sequence of elements in an array representing 3-ary max heap?
(a) 1, 3, 5, 6, 8, 9
(b) 9, 6, 3, 1, 8, 5
(c) 9, 3, 6, 8, 5, 1
(d) 9, 5, 6, 8, 3, 1
> **Answer:** **(d)**
**Question 6:** Suppose the elements 7, 2, 10 and 4 are inserted, in that order, into the valid 3- ary max heap found in the above question, Which one of the following is the sequence of items in the array representing the resultant heap?
(a) 10, 7, 9, 8, 3, 1, 5, 2, 6, 4
(b) 10, 9, 8, 7, 6, 5, 4, 3, 2, 1
(c) 10, 9, 4, 5, 7, 6, 8, 2, 1, 3
(d) 10, 8, 6, 9, 7, 2, 3, 4, 1, 5
> **Answer:** **(a)**
**Question** **7:**Consider the process of inserting an element into a Max Heap, where the Max Heap is represented by an array. Suppose we perform a binary search on the path from the new leaf to the root to find the position for the newly inserted element, the number of comparisons performed is: 
(a) Θ(logn) 
(b) Θ(LogLogn ) 
(c) Θ(n) 
(d) Θ(nLogn)
> **Answer:** **(b)**
>
> Explanation: The height of a Max Heap is Θ(logn). If we perform binary search for finding the correct position then we need to do Θ(LogLogn) comparisons.
**Question 8:** In a binary max heap containing n numbers, the smallest element can be found in time (GATE CS 2006)
(a) 0(n)
(b) O(logn)
(c) 0(loglogn)
(d) 0(1)
> **Answer:** **(a)**
>
> In a max heap, the smallest element is always present at a leaf node. So we need to check for all leaf nodes for the minimum value. Worst case complexity will be O(n)
>
> ```
         12        /  \      /      \    8         7   / \        / \ /     \    /     \2      3   4       5
```
**Question 9:**A priority queue is implemented as a Max-Heap. Initially, it has 5 elements. The level-order traversal of the heap is: 10, 8, 5, 3, 2. Two new elements 1 and 7 are inserted into the heap in that order. The level-order traversal of the heap after the insertion of the elements is:
(a) 10, 8, 7, 3, 2, 1, 5
(b) 10, 8, 7, 2, 3, 1, 5
(c) 10, 8, 7, 1, 2, 3, 5
(d) 10, 8, 7, 5, 3, 2, 1
> **Answer:** **(a)**
**Question 10:**Consider a max heap, represented by the array: 40, 30, 20, 10, 15, 16, 17, 8, 4.
| Array Index | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
| Value | 40 | 30 | 20 | 10 | 15 | 16 | 17 | 8 | 7 |
Now consider that a value 35 is inserted into this heap. After insertion, the new heap is
(a) 40, 30, 20, 10, 15, 16, 17, 8, 4, 35
(b) 40, 35, 20, 10, 30, 16, 17, 8, 4, 15
(c) 40, 30, 20, 10, 35, 16, 17, 8, 4, 15
(d) 40, 35, 20, 10, 15, 16, 17, 8, 4, 30
> **Answer:** **(b)**
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/binary-heap-notes-for-gate-exam/#introduction-to-heap)

## GATE CS

- Subject: Data Structures & C Programming
- Topic: Binary Heaps

> [!note] Related notes
>
> - [[Time Complexity of Building a Heap]]
> - [[1D, 2D and 3D Arrays]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
> - [[Data Types in C]]
> - [[Double Hashing]]
> - [[Enum, Struct & Union in C]]
> - [[Functions in C]]
> - [[I ntroduction to Trees]]
> - [[Introduction to Arrays]]
> - [[Introduction to C Programming]]
