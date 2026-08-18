---
title: "Optimal File Merge Patterns"
subject: "Algorithms"
topic: "Greedy Techniques"
source: "https://www.geeksforgeeks.org/dsa/optimal-file-merge-patterns/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Algorithms/Greedy Techniques"
tags:
  - gate/cs
  - subject/algorithms
  - topic/greedy-techniques
---


> [!abstract] Optimal File Merge Patterns
> 
> **Subject:** `Algorithms` &nbsp;|&nbsp; **Topic:** `Greedy Techniques`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/optimal-file-merge-patterns/)

---

# Optimal File Merge Patterns

Given n number of sorted files, the task is to find the minimum computations done to reach the Optimal Merge Pattern. 
When two or more sorted files are to be merged altogether to form a single file, the minimum computations are done to reach this file are known as **Optimal Merge Pattern**.
If more than 2 files need to be merged then it can be done in pairs. For example, if need to merge 4 files A, B, C, D. First Merge A with B to get X1, merge X1 with C to get X2, merge X2 with D to get X3 as the output file.
If we have two files of sizes m and n, the total computation time will be m+n. Here, we use the [greedy](https://www.geeksforgeeks.org/dsa/greedy-algorithms/) strategy by merging the two smallest size files among all the files present.
**Examples:** 
Given 3 files with sizes 2, 3, 4 units. Find an optimal way to combine these files
> **Input:** n = 3, size = {2, 3, 4} 
> **Output:** 14 
> **Explanation:** There are different ways to combine these files: 
> **Method 1:** Optimal method 
>
> ![](assets/Optimal-File-Merge-Patterns-method-1-215-d9cc4439ae.jpg)
>
> **Method 2:** 
>
> ![](assets/Optimal-File-Merge-Patterns-method-2-217-7952df16de.jpg)
>
> **Method 3:** 
>
> ![](assets/Optimal-File-Merge-Patterns-method-3-215-cae764c61a.jpg)
>
> **Input:** n = 6, size = {2, 3, 4, 5, 6, 7} 
> **Output:** 68 
> **Explanation:** Optimal way to combine these files 
>
> ![](assets/Optimal-File-Merge-Patterns-example-2-1--1db3a5d9da.jpg)
>
> **Input:** n = 5, size = {5,10,20,30,30} 
> **Output:** 205
>
> **Input:** n = 5, size = {8,8,8,8,8} 
> **Output:** 96
**Observations:**
From the above results, we may conclude that for finding the minimum cost of computation we need to have our array always sorted, i.e., add the minimum possible computation cost and remove the files from the array. We can achieve this optimally using a min-heap(priority-queue) data structure.
**Approach:** 
> Node represents a file with a given size also given nodes are greater than 2
>
> 1. Add all the nodes in a priority queue (Min Heap).{pq.poll = file size}
> 2. Initialize count = 0 // variable to store file computations.
> 3. Repeat while (size of priority Queue is greater than 1)
>    1. int weight = pq.poll(); pq.pop;//pq denotes priority queue, remove 1st smallest and pop(remove) it out
>    2. weight+=pq.poll()  && pq.pop(); // add the second element and then pop(remove) it out
>    3. count +=weight;
>    4. pq.add(weight) // add this combined cost to priority queue;
> 4. count is the final answer
Below is the implementation of the above approach:
````cpp
// C++ program to implement
// Optimal File Merge Pattern
#include <bits/stdc++.h>
using namespace std;
// Function to find minimum computation
int minComputation(int size, int files[])
{
    // Create a min heap
    priority_queue<int, vector<int>, greater<int> > pq;
    for (int i = 0; i < size; i++) {
        // Add sizes to priorityQueue
        pq.push(files[i]);
    }
    // Variable to count total Computation
    int count = 0;
    while (pq.size() > 1) {
        // pop two smallest size element
        // from the min heap
        int first_smallest = pq.top();
        pq.pop();
        int second_smallest = pq.top();
        pq.pop();
        int temp = first_smallest + second_smallest;
        // Add the current computations
        // with the previous one's
        count += temp;
        // Add new combined file size
        // to priority queue or min heap
        pq.push(temp);
    }
    return count;
}
// Driver code
int main()
{
    // No of files
    int n = 6;
    // 6 files with their sizes
    int files[] = { 2, 3, 4, 5, 6, 7 };
    // Total no of computations
    // do be done final answer
    cout << "Minimum Computations = "
         << minComputation(n, files);
    return 0;
}
// This code is contributed by jaigoyal1328
````
````Java
// Java program to implement
// Optimal File Merge Pattern
import java.util.PriorityQueue;
import java.util.Scanner;
public class OptimalMergePatterns {
    // Function to find minimum computation
    static int minComputation(int size, int files[])
    {
        // create a min heap
        PriorityQueue<Integer> pq = new PriorityQueue<>();
        for (int i = 0; i < size; i++) {
            // add sizes to priorityQueue
            pq.add(files[i]);
        }
        // variable to count total computations
        int count = 0;
        while (pq.size() > 1) {
            // pop two smallest size element
            // from the min heap
            int temp = pq.poll() + pq.poll();
            // add the current computations
            // with the previous one's
            count += temp;
            // add new combined file size
            // to priority queue or min heap
            pq.add(temp);
        }
        return count;
    }
    public static void main(String[] args)
    {
        // no of files
        int size = 6;
        // 6 files with their sizes
        int files[] = new int[] { 2, 3, 4, 5, 6, 7 };
        // total no of computations
        // do be done final answer
        System.out.println("Minimum Computations = "
                           + minComputation(size, files));
    }
}
````
````python3
# Python Program to implement
# Optimal File Merge Pattern
class Heap():
    # Building own implementation of Min Heap
    def __init__(self):
        self.h = []
    def parent(self, index):
        # Returns parent index for given index
        if index > 0:
            return (index - 1) // 2
    def lchild(self, index):
        # Returns left child index for given index
        return (2 * index) + 1
    def rchild(self, index):
        # Returns right child index for given index
        return (2 * index) + 2
    def addItem(self, item):
        # Function to add an item to heap
        self.h.append(item)
        if len(self.h) == 1:
            # If heap has only one item no need to heapify
            return
        index = len(self.h) - 1
        parent = self.parent(index)
        # Moves the item up if it is smaller than the parent
        while index > 0 and item < self.h[parent]:
            self.h[index], self.h[parent] = self.h[parent], self.h[parent]
            index = parent
            parent = self.parent(index)
    def deleteItem(self):
        # Function to add an item to heap
        length = len(self.h)
        self.h[0], self.h[length-1] = self.h[length-1], self.h[0]
        deleted = self.h.pop()
        # Since root will be violating heap property
        # Call moveDownHeapify() to restore heap property
        self.moveDownHeapify(0)
        return deleted
    def moveDownHeapify(self, index):
        # Function to make the items follow Heap property
        # Compares the value with the children and moves item down
        lc, rc = self.lchild(index), self.rchild(index)
        length, smallest = len(self.h), index
        if lc < length and self.h[lc] <= self.h[smallest]:
            smallest = lc
        if rc < length and self.h[rc] <= self.h[smallest]:
            smallest = rc
        if smallest != index:
            # Swaps the parent node with the smaller child
            self.h[smallest], self.h[index] = self.h[index], self.h[smallest]
            # Recursive call to compare next subtree
            self.moveDownHeapify(smallest)
    def increaseItem(self, index, value):
        # Increase the value of 'index' to 'value'
        if value <= self.h[index]:
            return
        self.h[index] = value
        self.moveDownHeapify(index)
class OptimalMergePattern():
    def __init__(self, n, items):
        self.n = n
        self.items = items
        self.heap = Heap()
    def optimalMerge(self):
        # Corner cases if list has no more than 1 item
        if self.n <= 0:
            return 0
        if self.n == 1:
            return self.items[0]
        # Insert items into min heap
        for _ in self.items:
            self.heap.addItem(_)
        count = 0
        while len(self.heap.h) != 1:
            tmp = self.heap.deleteItem()
            count += (tmp + self.heap.h[0])
            self.heap.increaseItem(0, tmp + self.heap.h[0])
        return count
# Driver Code
if __name__ == '__main__':
    OMP = OptimalMergePattern(6, [2, 3, 4, 5, 6, 7])
    ans = OMP.optimalMerge()
    print(ans)
# This code is contributed by Rajat Gupta
````
````csharp
using System;
using System.Collections.Generic;
public class OptimalMergePatterns
{
  // Function to find minimum computation
  static int MinComputation(int size, int[] files)
  {
    // create a list to store file sizes
    List<int> fileList = new List<int>(files);
    // variable to count total computations
    int count = 0;
    while (fileList.Count > 1) {
      // sort the file sizes in ascending order
      fileList.Sort();
      // get the two smallest file sizes
      int file1 = fileList[0];
      int file2 = fileList[1];
      // calculate the combined file size
      int combinedFileSize = file1 + file2;
      // add the current computations
      // with the previous one's
      count += combinedFileSize;
      // remove the two smallest file sizes
      fileList.RemoveAt(0);
      fileList.RemoveAt(0);
      // add new combined file size
      // to the list of file sizes
      fileList.Add(combinedFileSize);
    }
    return count;
  }
  public static void Main(string[] args)
  {
    // no of files
    int size = 6;
    // 6 files with their sizes
    int[] files = new int[] { 2, 3, 4, 5, 6, 7 };
    // total no of computations
    // do be done final answer
    Console.WriteLine("Minimum Computations = "
                      + MinComputation(size, files));
  }
}
// This code is contributed by phasing17.
````
````javascript
// JavaScript program to implement
// Optimal File Merge Pattern
class Heap {
    // Building own implementation of Min Heap
    constructor() {
        this.h = [];
    }
    parent(index) {
        // Returns parent index for given index
        if (index > 0) {
            return Math.floor((index - 1) / 2);
        }
    }
    lchild(index) {
        // Returns left child index for given index
        return 2 * index + 1;
    }
    rchild(index) {
        // Returns right child index for given index
        return 2 * index + 2;
    }
    addItem(item) {
        // Function to add an item to heap
        this.h.push(item);
        if (this.h.length === 1) {
            // If heap has only one item no need to heapify
            return;
        }
        let index = this.h.length - 1;
        let parent = this.parent(index);
        // Moves the item up if it is smaller than the parent
        while (index > 0 && item < this.h[parent]) {
            [this.h[index], this.h[parent]] = [this.h[parent], this.h[index]];
            index = parent;
            parent = this.parent(index);
        }
    }
    deleteItem() {
        // Function to add an item to heap
        const length = this.h.length;
        [this.h[0], this.h[length - 1]] = [this.h[length - 1], this.h[0]];
        const deleted = this.h.pop();
        // Since root will be violating heap property
        // Call moveDownHeapify() to restore heap property
        this.moveDownHeapify(0);
        return deleted;
    }
    moveDownHeapify(index) {
        // Function to make the items follow Heap property
        // Compares the value with the children and moves item down
        const lc = this.lchild(index);
        const rc = this.rchild(index);
        const length = this.h.length;
        let smallest = index;
        if (lc < length && this.h[lc] <= this.h[smallest]) {
            smallest = lc;
        }
        if (rc < length && this.h[rc] <= this.h[smallest]) {
            smallest = rc;
        }
        if (smallest !== index) {
            // Swaps the parent node with the smaller child
            [this.h[smallest], this.h[index]] = [this.h[index], this.h[smallest]];
            // Recursive call to compare next subtree
            this.moveDownHeapify(smallest);
        }
    }
    increaseItem(index, value) {
        // Increase the value of 'index' to 'value'
        if (value <= this.h[index]) {
            return;
        }
        this.h[index] = value;
        this.moveDownHeapify(index);
    }
}
class OptimalMergePattern {
    constructor(n, items) {
        this.n = n;
        this.items = items;
        this.heap = new Heap();
    }
    optimalMerge() {
        // Corner cases if list has no more than 1 item
        if (this.n <= 0) {
            return 0;
        }
        if (this.n === 1) {
            return this.items[0];
        }
        // Insert items into min heap
        for (const item of this.items) {
            this.heap.addItem(item);
        }
        let count = 0;
        while (this.heap.h.length !== 1) {
            const tmp = this.heap.deleteItem();
            count += tmp + this.heap.h[0];
            this.heap.increaseItem(0, tmp + this.heap.h[0])
        }
        return count
    }
}
// Driver Code
let OMP = new OptimalMergePattern(6, [2, 3, 4, 5, 6, 7])
let ans = OMP.optimalMerge()
console.log("Minimum Computations =", ans)
// This code is contributed by phasing17
````
**Output**
```
Minimum Computations = 68
```
**Time Complexity:** O(nlogn)
**Auxiliary Space:** O(n)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/optimal-file-merge-patterns/)

## GATE CS

- Subject: Algorithms
- Topic: Greedy Techniques

> [!note] Related notes
>
> - [[Dijkstra’s Algorithm for Adjacency List Representation]]
> - [[Efficient Huffman Coding for Sorted Input]]
> - [[Fractional Knapsack Problem]]
> - [[Introduction to Greedy Algorithms]]
> - [[Prim’s Minimum Spanning Tree]]
> - [[Prim’s MST for Adjacency List Representation]]
> - [[Applications of Depth First Search]]
> - [[Asymptotic Notations]]
> - [[Binary Search]]
> - [[Breadth First Traversal or BFS for a Graph]]
