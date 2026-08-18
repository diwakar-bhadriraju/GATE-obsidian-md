---
title: "Fixed (or static) Partitioning in Operating System"
subject: "Operating System"
topic: "Main Memory Management"
source: "https://www.geeksforgeeks.org/operating-systems/fixed-or-static-partitioning-in-operating-system/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Main Memory Management"
tags:
  - gate/cs
  - subject/operating-system
  - topic/main-memory-management
---


> [!abstract] Fixed (or static) Partitioning in Operating System
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Main Memory Management`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/fixed-or-static-partitioning-in-operating-system/)

---

# Fixed (or static) Partitioning in Operating System

Fixed partitioning, also known as static partitioning, is one of the earliest memory management techniques used in operating systems. In this method, the main memory is divided into a fixed number of partitions at system startup, and each partition is allocated to a process. These partitions remain unchanged throughout system operation, ensuring a simple, predictable memory allocation process. Despite its simplicity, fixed partitioning has several limitations, such as internal fragmentation and inflexible handling of varying process sizes. This article delves into the advantages, disadvantages, and applications of fixed partitioning in modern operating systems.
## What is Fixed (or static) Partitioning in the Operating System?
Fixed (or static) partitioning is one of the earliest and simplest memory management techniques used in operating systems. It involves dividing the main memory into a fixed number of partitions at system startup, with each partition being assigned to a process. These partitions remain unchanged throughout the system’s operation, providing each process with a designated memory space. This method was widely used in early operating systems and remains relevant in specific contexts like embedded systems and real-time applications. However, while fixed partitioning is simple to implement, it has significant limitations, including inefficiencies caused by internal fragmentation.
1. In fixed partitioning, the memory is divided into fixed-size chunks, with each chunk being reserved for a specific process. When a process requests memory, the operating system assigns it to the appropriate partition. Each partition is of the same size, and the memory allocation is done at system boot time.
2. Fixed partitioning has several advantages over other memory allocation techniques. First, it is simple and easy to implement. Second, it is predictable, meaning the operating system can ensure a minimum amount of memory for each process. Third, it can prevent processes from interfering with each other's memory space, improving the security and stability of the system.
3. However, fixed partitioning also has some disadvantages. It can lead to internal fragmentation, where memory in a partition remains unused. This can happen when the process's memory requirements are smaller than the partition size, leaving some memory unused. Additionally, fixed partitioning limits the number of processes that can run concurrently, as each process requires a dedicated partition.
Overall, fixed partitioning is a useful memory allocation technique in situations where the number of processes is fixed, and the memory requirements for each process are known in advance. It is commonly used in [embedded systems](https://www.geeksforgeeks.org/computer-organization-architecture/introduction-of-embedded-systems-set-1/), [real-time systems,](https://www.geeksforgeeks.org/computer-science-fundamentals/real-time-systems/) and systems with limited memory resources.
In operating systems, Memory Management is the function responsible for allocating and managing a computer's main memory. [Memory Management](https://www.geeksforgeeks.org/operating-systems/memory-management-in-operating-system/) function keeps track of the status of each memory location, either allocated or free to ensure effective and efficient use of Primary Memory. 
**There are two Memory Management Techniques:**
1. **Contiguous**
2. **Non-Contiguous**
### Contiguous Memory Allocation:
In contiguous memory allocation, each process is assigned a single continuous block of memory in the main memory. The entire process is loaded into one contiguous memory region.
In Contiguous Technique, executing process must be loaded entirely in the main memory.
**Contiguous Technique can be divided into:**
- Fixed (or static) partitioning
- Variable (or dynamic) partitioning
**Fixed Partitioning:** 
This is the oldest and simplest technique used to put more than one process in the main memory. In this partitioning, the number of partitions (non-overlapping) in [RAM](https://www.geeksforgeeks.org/computer-science-fundamentals/random-access-memory-ram/) is **fixed but the size** of each partition may or **may not be the same**. As it is a **contiguous** allocation, hence no spanning is allowed. Here partitions are made before execution or during system configure. 
![Fixed Partitioning](assets/444-4-f72ff83c9d.png)
As illustrated in above figure, first process is only consuming 1MB out of 4MB in the main memory. 
Hence, Internal Fragmentation in first block is (4-1) = 3MB. 
Sum of Internal Fragmentation in every block = (4-1)+(8-7)+(8-7)+(16-14)= 3+1+1+2 = 7MB. 
Suppose process P5 of size 7MB comes. But this process cannot be accommodated in spite of available free space because of contiguous allocation (as spanning is not allowed). Hence, 7MB becomes part of External Fragmentation. 
### **Advantages of Fixed Partitioning**
- **Easy to implement:** The algorithms required are simple and straightforward.
- **Low overhead:** Requires minimal system resources to manage, ideal for resource-constrained systems.
- **Predictable**: Memory allocation is predictable, with each process receiving a fixed partition.
- **No external fragmentation:** Since the memory is divided into fixed partitions and no spanning is allowed, external fragmentation is avoided.
- **Suitable for systems with a fixed number of processes:** Ideal for systems where the number of processes and their memory requirements are known in advance.
- **Prevents process interference:** Ensures that processes do not interfere with each other's memory, improving system stability.
- **Efficient memory use:** Particularly in systems with fixed, known processes and [batch processing](https://www.geeksforgeeks.org/operating-systems/batch-processing-operating-system/) scenarios.
- **Good for batch processing:** Works well in environments where the number of processes remains constant over time.
- **Better control over memory allocation:** The operating system has clear control over how memory is allocated and managed.
- **Easy to debug:** Fixed Partitioning is easy to debug since the size and location of each process are predetermined.
### **Disadvantages of Fixed Partitioning**
1. **Internal Fragmentation:** Main memory use is inefficient. Any program, no matter how small, occupies an entire partition. This can cause internal fragmentation.
2. **Limit process size:** Process of size greater than the size of the partition in Main Memory cannot be accommodated. The partition size cannot be varied according to the size of the incoming process size. Hence, the process size of 32MB in the above-stated example is invalid.
3. **Limitation on Degree of Multiprogramming:**  Partitions in Main Memory are made before execution or during system configure. Main Memory is divided into a fixed number of partitions. Suppose if there are partitions in RAM and are the number of processes, then 
$$
n2 <= n1
$$
   condition must be fulfilled. Number of processes greater than the number of partitions in RAM is invalid in Fixed Partitioning.
### **Clarification:**
Internal fragmentation is a notable disadvantage in fixed partitioning, whereas external fragmentation is not applicable because processes cannot span across multiple partitions, and memory is allocated in fixed blocks.
### Non-Contiguous Memory Allocation:
In non-contiguous memory allocation, a process is divided into multiple blocks or segments that can be loaded into different parts of the memory, rather than requiring a single continuous block.
**Key Features:**
**Divided memory blocks:** A process is divided into smaller chunks (pages, segments) and placed in available memory blocks, which can be located anywhere in the memory.
**Paging and Segmentation:**
- **Paging**: Divides memory into fixed-size blocks called pages. Pages of a process can be placed in any available memory frames.
- **Segmentation:** Divides memory into variable-sized segments based on logical sections of a program, like code, data, and stack.
## Conclusion
Fixed partitioning, though straightforward and easy to manage, presents several challenges, particularly in the form of internal fragmentation and limited flexibility in handling varying process sizes. This memory allocation technique works well in environments where memory requirements are predictable and stable. However, for modern systems with dynamic workloads and varying memory demands, more flexible techniques like dynamic partitioning or non-contiguous allocation methods have become preferable. Nonetheless, understanding fixed partitioning is crucial for grasping the evolution of memory management in operating systems and its applications in specialized environments.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/fixed-or-static-partitioning-in-operating-system/)

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
> - [[Inverted Page Table]]
> - [[Logical vs Physical Address in Operating System]]
> - [[Mapping virtual address to physical addresses]]
> - [[Memory Management Partition Allocation Method]]
> - [[Multilevel Paging]]
