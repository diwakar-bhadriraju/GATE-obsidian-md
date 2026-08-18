---
title: "Variable (or Dynamic) Partitioning in Operating System"
subject: "Operating System"
topic: "Main Memory Management"
source: "https://www.geeksforgeeks.org/operating-systems/variable-or-dynamic-partitioning-in-operating-system/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Main Memory Management"
tags:
  - gate/cs
  - subject/operating-system
  - topic/main-memory-management
---


> [!abstract] Variable (or Dynamic) Partitioning in Operating System
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Main Memory Management`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/variable-or-dynamic-partitioning-in-operating-system/)

---

# Variable (or Dynamic) Partitioning in Operating System

Variable (Dynamic) Partitioning is a contiguous memory allocation technique where memory partitions are created at run-time based on the size of the process requesting memory. Unlike fixed partitioning, partitions are not predefined during system configuration.
This method was introduced to overcome the limitations of fixed partitioning, especially internal fragmentation.
**How Variable Partitioning Works:**
- Initially, the entire RAM is free and unpartitioned.
- When a process arrives, the operating system allocates exactly the amount of memory required by that process.
- Each partition is created dynamically and may differ in size.
- When a process finishes execution, its allocated memory is released and becomes a free hole.
- The number of partitions in memory changes dynamically based on process arrival and termination.
![Dynamic Partitioning](assets/111-10-89f6388721.webp)
Dynamic Partitioning
## **Key Features of Variable Partitioning**
- Partitions are created during run-time, not in advance.
- The partition size equals the process size, avoiding wasted memory.
- The number of partitions is not fixed.
- Memory utilization is more efficient compared to fixed partitioning.
- Processes are loaded until the memory is fully utilized.
### Advantages
1. **No Internal Fragmentation:**  Memory is allocated exactly as per the process size, so no space is wasted inside a partition.
2. **Better Memory Utilization:**  Since internal wastage is eliminated, available RAM is used more efficiently.
3. **No Fixed Partition Size Limitation:**  A process of any size can be loaded as long as sufficient contiguous memory is available.
4. **Higher Degree of Multiprogramming:**  More processes can be accommodated in memory due to flexible partition sizes.
### Disadvantages
1. **External Fragmentation:**  Free memory gets divided into small non-contiguous blocks, making it difficult to allocate memory for large processes.
2. **Complex Implementation:**  Memory allocation and deallocation are done at run-time, making management more complicated than fixed partitioning.
3. **Compaction Overhead:** To reduce external fragmentation, compaction is required, which consumes CPU time and system resources.
4. **Slower Allocation Process:**  Searching for a suitable free block (first fit, best fit, worst fit) increases allocation time.
![No Internal Fragmentation](assets/222-12-033b63211d.webp)
No Internal Fragmentation
Now P5 of size 3 MB cannot be accommodated despite the required available space because in contiguous no spanning is allowed.
## Key Points On Variable (Dynamic) Partitioning in Operating Systems
- Memory partitions are created and resized dynamically.
- The OS maintains a list of free memory holes.
- Allocation algorithms are used to find suitable memory blocks.
- Internal fragmentation is eliminated, but external fragmentation remains.
- Compaction may be required to reduce fragmentation.
- Widely studied for understanding modern memory management concepts.
##
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/variable-or-dynamic-partitioning-in-operating-system/)

## GATE CS

- Subject: Operating System
- Topic: Main Memory Management

> [!note] Related notes
>
> - [[Allocating kernel memory]]
> - [[Buddy System]]
> - [[Buddy System Memory Allocation]]
> - [[Buddy System Memory Deallocation]]
> - [[Demand Paging]]
> - [[Fixed (or static) Partitioning]]
> - [[Inverted Page Table]]
> - [[Logical vs Physical Address in Operating System]]
> - [[Mapping virtual address to physical addresses]]
> - [[Memory Management Partition Allocation Method]]
