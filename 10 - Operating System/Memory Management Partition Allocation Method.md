---
title: "Partition Allocation Methods in Memory Management"
subject: "Operating System"
topic: "Main Memory Management"
source: "https://www.geeksforgeeks.org/operating-systems/partition-allocation-methods-in-memory-management/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Main Memory Management"
tags:
  - gate/cs
  - subject/operating-system
  - topic/main-memory-management
---


> [!abstract] Partition Allocation Methods in Memory Management
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Main Memory Management`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/partition-allocation-methods-in-memory-management/)

---

# Partition Allocation Methods in Memory Management

Memory management techniques are methods used by an operating system to allocate, control, and release main memory during program execution. They ensure that multiple processes can use memory efficiently without interfering with each other. Proper memory management improves system performance and prevents memory wastage.
- **Single contiguous allocation:** Simplest allocation method used by MS-DOS. All memory (except some reserved for OS) is available to a process.
- **Partitioned allocation:** Memory is divided into different blocks or partitions. Each process is allocated according to the requirement.
- **Paged memory management:** Memory is divided into fixed-sized units called page frames, used in a virtual memory environment.
- **Segmented memory management:** Memory is divided into different segments (a segment is a logical grouping of the process' data or code).In this management, allocated memory doesn't have to be contiguous.
Most of the operating systems (for example Windows and Linux) use Segmentation with Paging. A process is divided into segments and individual segments have pages. 
> In **Partition Allocation**, when there is more than one partition freely available to accommodate a process's request, a partition must be selected. To choose a particular partition, a partition allocation method is needed. A partition allocation method is considered better if it avoids internal fragmentation. 
### There are different Placement Algorithm:
1. First Fit
2. Best Fit
3. Worst Fit
4. Next Fit
**1. First Fit**: In the first fit, the partition is allocated which is the first sufficient block from the top of Main Memory. It scans memory from the beginning and chooses the first available block that is large enough. Thus it allocates the first hole that is large enough. 
![1](assets/1-2082b9c900.webp)
**2. Best Fit** Allocate the process to the partition which is the first smallest sufficient partition among the free available partition. It searches the entire list of holes to find the smallest hole whose size is greater than or equal to the size of the process. 
![2-](assets/2--f0238dec33.webp)
**3. Worst Fit** Allocate the process to the partition which is the largest sufficient among the freely available partitions available in the main memory. It is opposite to the best-fit algorithm. It searches the entire list of holes to find the largest hole and allocate it to process.  
![3](assets/3-7f7505ae3e.webp)
**4. Next Fit:** Next fit is similar to the first fit but it will search for the first sufficient partition from the last allocation point. 
**Is Best-Fit really best?** 
Although best fit minimizes the wastage space, it consumes a lot of processor time for searching the block which is close to the required size. Also, Best-fit may perform poorer than other algorithms in some cases. For example, see the below exercise. 
**Comparison of Partition Allocation Methods:**
| Sl.No. | Partition Allocation Method | Advantages | Disadvantages |
| --- | --- | --- | --- |
| 1. | Fixed Partition | Simple, easy to use, no complex algorithms needed | Memory waste, inefficient use of memory resources |
| 2. | Dynamic Partition | Flexible, more efficient, partitions allocated as required | Requires complex algorithms for memory allocation |
| 3. | Best-fit Allocation | Minimizes memory waste, allocates smallest suitable partition | More computational overhead to find smallest split |
| 4. | Worst-fit Allocation | Ensures larger processes have sufficient memory | May result in substantial memory waste |
| 5. | First-fit Allocation | Quick, efficient, less computational work | Risk of memory fragmentation |
**Exercise:**
Consider the memory requests from processes in the following order:
**300K, 25K, 125K, 50K**.
The available memory blocks are:
**150K, 150K, 350K**.
Which of the following partition allocation schemes can satisfy the above requests?
A) Best fit but not first fit
 B) First fit but not best fit
 C) Both first fit & best fit
 D) Neither first fit nor best fit
**Solution:**
**Best Fit:**
1. 300K → allocated from 350K block, leaving 50K.
2. 25K → allocated from the remaining 50K block, leaving 25K.
3. 125K → allocated from 150K block, leaving 25K.
4. 50K → cannot be allocated (remaining free spaces are 25K + 25K, which is insufficient).
**Best fit cannot satisfy all requests.**
**First Fit:**
1. 300K → allocated from 350K block, leaving 50K.
2. 25K → allocated from 150K block, leaving 125K.
3. 125K → allocated from the remaining 125K block.
4. 50K → allocated from the remaining 50K block.
First fit can satisfy all requests.
Answer:
B) First fit but not best fit
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/partition-allocation-methods-in-memory-management/)

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
> - [[Multilevel Paging]]
