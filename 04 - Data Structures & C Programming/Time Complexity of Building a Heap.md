---
title: "Time Complexity of building a heap"
subject: "Data Structures & C Programming"
topic: "Binary Heaps"
source: "https://www.geeksforgeeks.org/dsa/time-complexity-of-building-a-heap/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Data Structures & C Programming/Binary Heaps"
tags:
  - gate/cs
  - subject/data-structures-c-programming
  - topic/binary-heaps
---


> [!abstract] Time Complexity of building a heap
> 
> **Subject:** `Data Structures & C Programming` &nbsp;|&nbsp; **Topic:** `Binary Heaps`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/time-complexity-of-building-a-heap/)

---

# Time Complexity of building a heap

Consider the following algorithm for [building a Heap](https://www.geeksforgeeks.org/dsa/building-heap-from-array/) of an input array A. 
A quick look over the above implementation suggests that the running time is 
$$
O(n * lg(n))
$$
 since each call to **Heapify** costs 
$$
O(lg(n))
$$
and **Build-Heap** makes 
$$
O(n)
$$
such calls. 
This upper bound, though correct, is not asymptotically tight. 
We can derive a tighter bound by observing that the running time of **Heapify** depends on the height of the tree ‘h’ (which is equal to log n, where n is a number of nodes) and the heights of most sub-trees are small. The height ’h’ increases as we move upwards along the tree. Line-3 of **Build-Heap** runs a loop from the index of the last internal node (heapsize/2) with height=1, to the index of root(1) with height = lg(n). Hence, **Heapify** takes a different time for each node, which is:
For finding the Time Complexity of building a heap, we must know the number of nodes having height h. For this we use the fact that, A heap of size n has at most 
$$
\left \lceil \frac{n}{2^{h+1}} \right \rceil
$$
nodes with height h. 
a  to derive the time complexity, we express the total cost of **Build-Heap** as-
$$
T(n) = \sum_{h = 0}^{lg(n)}\left \lceil \frac{n}{2^{h+1}} \right \rceil * O(h)= O(n * \sum_{h = 0}^{lg(n)}\frac{h}{2^{h}})= O(n * \sum_{h = 0}^{\infty}\frac{h}{2^{h}})
$$
Step 2 uses the properties of the Big-Oh notation to ignore the ceiling function and the constant 2(
$$
2^{h+1} = 2.2^h
$$
). Similarly in Step three, the upper limit of the summation can be increased to infinity since we are using Big-Oh notation. Sum of infinite G.P. (x < 1)
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
Hence the Time complexity for Building a Binary Heap is 
$$
O(n)
$$
.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/time-complexity-of-building-a-heap/)

## GATE CS

- Subject: Data Structures & C Programming
- Topic: Binary Heaps

> [!note] Related notes
>
> - [[Introduction to Heap]]
> - [[1D, 2D and 3D Arrays]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
> - [[Data Types in C]]
> - [[Double Hashing]]
> - [[Enum, Struct & Union in C]]
> - [[Functions in C]]
> - [[I ntroduction to Trees]]
> - [[Introduction to Arrays]]
> - [[Introduction to C Programming]]
