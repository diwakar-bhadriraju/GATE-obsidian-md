---
title: "Searching and Sorting Algorithm Notes for GATE Exam [2024]"
subject: "Algorithms"
topic: "Searching, Sorting, Technique-based Theorem and Hashing"
source: "https://www.geeksforgeeks.org/dsa/searching-and-sorting-algorithm-notes-for-gate-exam/#introduction-to-searching-algorithm"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Algorithms/Searching, Sorting, Technique-based Theorem and Hashing"
tags:
  - gate/cs
  - subject/algorithms
  - topic/searching-sorting-technique-based-theorem-and-hashing
---


> [!abstract] Searching and Sorting Algorithm Notes for GATE Exam [2024]
> 
> **Subject:** `Algorithms` &nbsp;|&nbsp; **Topic:** `Searching, Sorting, Technique-based Theorem and Hashing`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/searching-and-sorting-algorithm-notes-for-gate-exam/#introduction-to-searching-algorithm)

---

# Searching and Sorting Algorithm Notes for GATE Exam [2024]

As you gear up for the GATE Exam 2024, it's time to dive into the world of searching and sorting algorithms. Think of these algorithms as the super-smart tools that help computers find stuff quickly and organize data neatly. These notes are here to guide you through the ins and outs of these algorithms, breaking down how they work, when to use them, and why they're essential for acing the GATE exam.
Table of Content
- [Introduction to Searching Algorithm:](#introduction-to-searching-algorithm)
- [Types of Searching Algorithm:](#types-of-searching-algorithm)
- [Introduction to Sorting Algorithm:](#introduction-to-sorting-algorithm)
- [Types of Sorting Algorithm:](#types-of-sorting-algorithm)
- [Previously Asked Problems of Searching and Sorting on GATE:](#previously-asked-problems-of-searching-and-sorting-on-gate)
## Introduction to Searching Algorithm:
[Searching Algorithms](https://www.geeksforgeeks.org/dsa/searching-algorithms/) are designed to check for an element or retrieve an element from any data structure where it is stored. Searching algorithms are methods or procedures that are used to locate a specific item or element within a set of data. These algorithms are widely used in computer science and are essential for tasks such as searching for a specific record in a database, locating an element in a sorted list, and locating a file on a computer.
## Types of Searching Algorithm:
### 1. [Linear Search:](https://www.geeksforgeeks.org/dsa/linear-search/)
> Linear Search is defined as a sequential [search algorithm](https://www.geeksforgeeks.org/dsa/searching-algorithms/) that starts at one end and goes through each element of a list until the desired element is found otherwise, the search continues till the end of the data set.
#### Key Points:
- Linear search, also known as **sequential search,** is a simple searching algorithm.
- It sequentially checks each element of the list until a match is found or the entire list has been searched.
- The Time Complexity of Linear search is **O(n)**, where 'n' is the number of elements in the list.
- In the **worst case**, a linear search may have to scan the entire list.
- Linear search is **efficient** for small lists, but its efficiency decreases for larger lists.
- Linear search can be applied to any collection of elements that can be traversed sequentially, such as arrays or linked lists.
![](assets/Linear-Search1-3b666e4db1.png)
Linear Search
### 2. [Binary Search:](https://www.geeksforgeeks.org/dsa/binary-search/)
> **Binary Search** is defined as a [searching algorithm](https://www.geeksforgeeks.org/dsa/searching-algorithms/) used in a sorted array by **repeatedly dividing the search interval in half**. The idea of binary search is to use the information that the array is sorted and reduce the time complexity to O(log N). 
#### Key Points:
- Binary search is a [**divide-and-conquer**](https://www.geeksforgeeks.org/dsa/introduction-to-divide-and-conquer-algorithm/) algorithm used for searching in sorted lists.
- It repeatedly divides the search interval in **half** until the target element is found or the interval is empty.
- The list must be sorted for binary search to work effectively.
- Time Complexity of Binary Search is **O(log n)**, where 'n' is the number of elements in the list.
- Binary search is **more efficient** than linear search for large, sorted datasets.
- Binary search is **highly efficient,** especially for large datasets, as it reduces the search space exponentially with each step.
![](assets/BinarySearch-6f21861635.png)
Binary Search
### [Linear Search vs Binary Search:](https://www.geeksforgeeks.org/dsa/linear-search-vs-binary-search/)
| **Linear Search** | **Binary Search** |
| In linear search input data need not to be in sorted. | In binary search input data need to be in **sorted order**. |
| It is also called **sequential search**. | It is also called **half-interval search**. |
| The time complexity of linear search **O(n)**. | The time complexity of binary search**O(log n)**. |
| **Multidimensional** array can be used. | Only **single dimensional** array is used. |
| Linear search performs equality comparisons | Binary search performs ordering comparisons |
| It is less complex. | It is more complex. |
| It is very slow process. | It is very fast process. |
## Introduction to Sorting Algorithm:
A [Sorting Algorithm](https://www.geeksforgeeks.org/dsa/sorting-algorithms/) is used to rearrange a given array or list of elements according to a comparison operator on the elements. The comparison operator is used to decide the new order of elements in the respective data structure.
## Types of Sorting Algorithm:
### 1. [Selection Sort:](https://www.geeksforgeeks.org/dsa/selection-sort-algorithm-2/)
> **Selection sort** is a simple and efficient sorting algorithm that works by repeatedly selecting the smallest (or largest) element from the unsorted portion of the list and moving it to the sorted portion of the list. 
The algorithm repeatedly selects the smallest (or largest) element from the unsorted portion of the list and swaps it with the first element of the unsorted part. This process is repeated for the remaining unsorted portion until the entire list is sorted. 
#### Key Points:
- Selection sort is a **comparison-based** sorting algorithm.
- It divides the input list into a sorted and an unsorted region. In each iteration, it selects the smallest (or largest, depending on the order) element from the unsorted region and swaps it with the first unsorted element.
- Selection sort is an **in-place sorting** algorithm, meaning it doesn't require additional memory space for sorting.
- Selection sort is **not stable**. Stable sorting algorithms maintain the relative order of equal elements in the sorted output.
- The time complexity of selection sort is **O(n**2**)**, where 'n' is the number of elements in the list.
- Selection sort is simple but less **efficient** than some other sorting algorithms like merge sort or quicksort, especially for large datasets.
### 2. [Bubble Sort:](https://www.geeksforgeeks.org/dsa/bubble-sort-algorithm/)
> **Bubble Sort** is the simplest [sorting algorithm](https://www.geeksforgeeks.org/dsa/sorting-algorithms/) that works by repeatedly swapping the adjacent elements if they are in the wrong order. This algorithm is not suitable for large data sets as its average and worst-case time complexity is quite high.
#### Key Points:
- Bubble sort is a **simple comparison-based** sorting algorithm.
- It repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order. This process is repeated until the list is sorted.
- Bubble sort is an **in-place sorting** algorithm, meaning it doesn't require additional memory space for sorting.
- Bubble sort is **stable**. Stable sorting algorithms maintain the relative order of equal elements in the sorted output.
- The time complexity of bubble sort is **O(n**2**)**, where 'n' is the number of elements in the list.
### 3. [Insertion Sort:](https://www.geeksforgeeks.org/dsa/insertion-sort-algorithm/)
> **Insertion sort** is a simple sorting algorithm that works similar to the way you sort playing cards in your hands. The array is virtually split into a sorted and an unsorted part. Values from the unsorted part are picked and placed at the correct position in the sorted part.
#### Key Points:
- Insertion sort is a **simple comparison-based** sorting algorithm.
- It builds the final sorted array one element at a time. It takes each element from the unsorted part of the array and inserts it into its correct position in the sorted part.
- Insertion sort is an **in-place sorting** algorithm, meaning it doesn't require additional memory space for sorting.
- Insertion sort is **stable**. Stable sorting algorithms maintain the relative order of equal elements in the sorted output.
- The time complexity of insertion sort is **O(n**2**)** in the worst case, where 'n' is the number of elements in the list.
![](assets/insertionsort-47bef56923.png)
Insertion Sort
### 4. [Merge Sort:](https://www.geeksforgeeks.org/dsa/merge-sort/)
> **Merge sort** is defined as a [sorting algorithm](https://www.geeksforgeeks.org/dsa/sorting-algorithms/) that works by dividing an array into smaller subarrays, sorting each subarray, and then merging the sorted subarrays back together to form the final sorted array.
In simple terms, we can say that the process of merge sort is to divide the array into **two halves**, sort each half, and then merge the sorted halves back together. This process is repeated until the entire array is sorted.
#### Key Points:
- Merge sort is a **divide-and-conquer** algorithm used for sorting.
- It divides the unsorted list into 'n' sublists, each containing one element, and then repeatedly merges sublists to produce new sorted sublists until there is only one sublist remaining.
- Merge sort follows the divide-and-conquer strategy, breaking the problem into smaller subproblems, solving them independently, and then combining the solutions.
- Merge sort is **stable**. Stable sorting algorithms maintain the relative order of equal elements in the sorted output.
- The time complexity of merge sort is **O(n log n)**, where 'n' is the number of elements in the list.
- Merge sort has a space complexity of **O(n)** as it requires additional space for merging.
### 5. [Quick Sort:](https://www.geeksforgeeks.org/dsa/quick-sort-algorithm/)
> **QuickSort** is a sorting algorithm based on the[Divide and Conquer algorithm](https://www.geeksforgeeks.org/dsa/introduction-to-divide-and-conquer-algorithm/) that picks an element as a pivot and partitions the given array around the picked pivot by placing the pivot in its correct position in the sorted array.
#### Key Points:
- QuickSort follows the **divide-and-conque**r strategy, breaking the problem into smaller subproblems, solving them independently, and then combining the solutions.
- It works by selecting a '**pivot**' element from the array and partitioning the other elements into two sub-arrays according to whether they are less than or greater than the pivot. The process is then applied recursively to the sub-arrays.
- QuickSort is an **in-place sorting** algorithm, meaning it doesn't require additional memory space for sorting.
- The **average** and **best-case** time complexity of QuickSort is **O(n log n)**, where 'n' is the number of elements in the list.
- The **worst-case** time complexity is **O(n**2**),** but this is rare and can be mitigated by using various strategies for pivot selection.
- QuickSort has a space complexity of **O(log n)** due to the **recursive nature** of the algorithm.
### 6. [Heap Sort:](https://www.geeksforgeeks.org/dsa/heap-sort/)
> **Heap sort** is a comparison-based sorting technique based on [Binary Heap](https://www.geeksforgeeks.org/dsa/binary-heap/) data structure. It is similar to the [selection sort](https://www.geeksforgeeks.org/dsa/selection-sort-algorithm-2/) where we first find the minimum element and place the minimum element at the beginning. Repeat the same process for the remaining elements.
#### Key Points:
- Heap Sort is a **comparison-based** sorting algorithm that uses a binary heap data structure.
- It builds a binary heap from the input data and repeatedly extracts the maximum (for max-heap) or minimum (for min-heap) element from the heap and reconstructs the heap until the entire input is sorted.
- Heap Sort is an **in-place sorting** algorithm, meaning it doesn't require additional memory space for sorting, apart from a small constant amount.
- The time complexity of Heap Sort is **O(n log n)**, where 'n' is the number of elements in the list.
- Heap Sort has a space complexity of **O(1)** because it uses a constant amount of extra space.
### 7. [Counting Sort:](https://www.geeksforgeeks.org/dsa/counting-sort/)
> **Counting Sort**is a **non-comparison-based** sorting algorithm that works well when there is limited range of input values. It is particularly efficient when the range of input values is small compared to the number of elements to be sorted. The basic idea behind **Counting Sort** is to count the **frequency** of each distinct element in the input array and use that information to place the elements in their correct sorted positions.
#### Key Points:
- Counting Sort is an **integer sorting** algorithm.
- It works by counting the number of occurrences of each element and then using this information to reconstruct a sorted sequence.
- Counting Sort is **stable**. Stable sorting algorithms maintain the relative order of equal elements in the sorted output.
- The time complexity of Counting Sort is **O(n + k)**, where 'n' is the number of elements in the list, and 'k' is the range of input values.
- Counting Sort has a space complexity of **O(k)**, where 'k' is the range of input values. Additional space is required for the count array.
## Previously Asked Problems of Searching and Sorting on GATE:
**Question** **1**.** **[GATE-CS-2019]**
An array of 25 distinct elements is to be sorted using quicksort. Assume that the pivot element is chosen uniformly at random. The probability that the pivot element gets placed in the worst possible location in the first round of partitioning (rounded off to 2 decimal places) is \_\_\_.
> **Answer**:** 0.08
**Question** 2. [GATE-CS-2016]
Assume that the algorithms considered here sort the input sequences in ascending order. If the input is already in ascending order, which of the following are TRUE?
I. Quicksort runs in Θ(n2) time
II. Bubble sort runs in Θ(n2) time
III. Mergesort runs in Θ(n) time
IV. Insertion sort runs in Θ(n) time
(A) I and II only
(B) I and III only
(C) II and IV only
(D) I and IV only
> **Answer**:** (D) I and IV only
**Question** 3. [GATE-CS-2015]
Assume that a mergesort algorithm, in the worst case, takes 30 seconds for an input of size 64. Which of the following most closely approximates the maximum input size of a problem that can be solved in 6 minutes?
(A) 256
(B) 512
(C) 1024
(D) 2048
> **Answer**:** (B) 512
**Question** 4. [GATE-CS-1996]
The average number of key comparisons done in a successful sequential search in a list of length n is
(A) log n
(B) (n-1)/2
(C) n/2
(D) (n+1)/2
> **Answer**:** (D) (n+1)/2
**Question** 5. [GATE-CS-2006]
Which one of the following in place sorting algorithms needs the minimum number of swaps?
(A) Quick Sort
(B) Insertion Sort
(C) Selection Sort
(D) Heap Sort
> **Answer**:** (C) Selection Sort
**Question** 6. [GATE-CS-1994]
The recurrence relation that can arise in relation to the complexity of the binary search algorithm is:
(A) T(n) = 2T(n/2) + c, where c is constant.
(B) T(n) = T(n/2) + c, where c is constant.
(C) T(n) = T(n/2) + log n.
(D) T(n) = T(n/2) + n.
> **Answer**:** (B) T(n) = T(n/2) + c, where c is constant.
**Question** 7. [GATE-CS-2013]
Which one of the following is the tightest upper bound that represents the time complexity of inserting an object into a binary search tree of n nodes?
(A) O(1)
(B) O(log n)
(C) O(n)
(D) O(n log n)
> **Answer**:** (C) O(n)
**Question** 8. [GATE-CS-2013]
Suppose we have a balanced binary search tree **T** holding **n** numbers. We are given two numbers **L** and **H,** and wish to sum up all the numbers in **T** that lie between **L** and H. Suppose there are m such numbers in **T**. If the tightest upper bound on time to compute the sum is 0(**n**a logb**n** + mc logd**n**), the value of **a** + 10**b** + 100**c** + 1000**d** is \_\_.
> **Answer**: 110
**Question** 9. [GATE-CS-2009]
What is the number of swaps required to sort n elements using selection sort, in the worst case?
(A) O(n)
(B) O(nlogn)
(C) O(n2)
(D) O(n2logn)
> **Answer**:** (A) O(n)
**Question** 10. [GATE-CS-2007]
Which of the following sorting algorithms has the lowest worst-case complexity?
(A) Merge Sort
(B) Bubble Sort
(C) Quick Sort
(D) Selection Sort
> **Answer**:** (A) Merge Sort
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/searching-and-sorting-algorithm-notes-for-gate-exam/#introduction-to-searching-algorithm)

## GATE CS

- Subject: Algorithms
- Topic: Searching, Sorting, Technique-based Theorem and Hashing

> [!note] Related notes
>
> - [[Binary Search]]
> - [[Linear Search]]
> - [[Linear Search vs Binary Search]]
> - [[Applications of Depth First Search]]
> - [[Asymptotic Notations]]
> - [[Breadth First Traversal or BFS for a Graph]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
> - [[Dijkstra’s Algorithm for Adjacency List Representation]]
> - [[Efficient Huffman Coding for Sorted Input]]
> - [[Fractional Knapsack Problem]]
