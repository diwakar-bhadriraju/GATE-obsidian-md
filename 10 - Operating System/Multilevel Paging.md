---
title: "Multilevel Paging in Operating System"
subject: "Operating System"
topic: "Main Memory Management"
source: "https://www.geeksforgeeks.org/operating-systems/multilevel-paging-in-operating-system/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Main Memory Management"
tags:
  - gate/cs
  - subject/operating-system
  - topic/main-memory-management
---


> [!abstract] Multilevel Paging in Operating System
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Main Memory Management`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/multilevel-paging-in-operating-system/)

---

# Multilevel Paging in Operating System

Multilevel paging is a technique used in modern computer systems to efficiently handle large amounts of memory. It breaks down the virtual address space into smaller, more manageable pieces, organized into multiple levels of page tables. It consists of two or more levels of page tables in a hierarchical manner and also known as hierarchical paging.
> **Note:**  The entries of higher level of page table are pointers to lower level**,** entries of the last level page table store actual frame information. Level 1 contains a single-page table and the address of that table is stored in PTBR (Page Table Base Register).
## Why Multi-Level Paging is Required
One solution to the large memory requirements of the page tables is to use multilevel paging, only the outermost page table will reside in the main memory and other page tables will be brought to the main memory as per the requirement because, at a particular time, we do not need complete page table,
> **Note:** In this way, we can save much memory space because outermost page table can fit in exactly one frame.
**Example:** Consider a 32-bit physical address space with page size =
$$
4KB
$$
 and let there be
$$
2^{20} = 1M
$$
, the total entries in the page table, page table entry size =
$$
2^{32} /2^{12} = 2^{20}
$$
, and adding some protection bits and a dirty bit in the page table entry. Now page table size
$$
=2^{20} * 24 = 3MB
$$
which should be in the physical memory and since each process has its own page table there is so much memory wastage only for storing page tables.
![Levels in Paging](assets/virtual2-5cdd8e5325.png)
Levels in Paging
**In multilevel** [**paging**](https://www.geeksforgeeks.org/operating-systems/paging-in-operating-system/) **whatever may be levels of paging:**
- All the page tables will be stored in the main memory.
- It requires more than one memory access to get the physical address of the page frame.
- One access for each level is needed.
- Each page table entry except the last level page table entry contains the base address of the next level page table.
![3-Level_Paging_System](assets/3-Level_Paging_System-2749ea2c37.webp)
3-Level Paging System
**Reference to actual page frame:**
- Reference to PTE in level 1 Page Table = PTBR Value + Level 1 Offset present in the Virtual Address.
- Reference to PTE in level 2 Page Table = Base address (present in Level 1 PTE) + Level 2 offset (present in VA).
- Reference to PTE in level 3 Page Table= Base address (present in Level 2 PTE) + Level 3 offset (present in VA).
- Actual page frame address = PTE (present in level 3).
> **Assumption:** Byte addressable memory and n is the number of bits used to represent virtual address.
**Important formulas:** 
> - **Number of pages** =
>
>
$$
\dfrac{\text{Virtual Address Space}}{\text{Page Size}}
$$
> - **Virtual Address Space Size** =
>
>
$$
2^n
$$
>
>    bytes (if VA = nnn bits)
> - **Page Table Size** = (Number of entries) \* (Size of PTE)
## **Advantages :**
- **Reduced memory overhead:**  Multilevel paging can help to reduce the memory overhead associated with the page table. This is because each level contains fewer entries, which means that less memory is required to store the page table.
- **Faster page table lookup:**  With a smaller number of entries per level, it takes less time to perform a page table lookup. This can lead to faster system performance overall.
- **Flexibility:**  Multilevel paging provides greater flexibility in terms of how the memory space is organized. This can be especially useful in systems with varying memory requirements, as it allows the page table to be adjusted to accommodate changing needs.
## **Disadvantages :**
- **Increased complexity:**  Multilevel paging adds complexity to the memory management system, which can make it more difficult to design, implement, and debug.
- **Increased overhead:**  Although multilevel paging can reduce the memory overhead associated with the page table, it can also increase the overhead associated with page table lookups. This is because each level must be traversed to find the desired page table entry.
- **Fragmentation:**  Multilevel paging can lead to [fragmentation](https://www.geeksforgeeks.org/operating-systems/what-is-fragmentation-in-operating-system/) of the memory space, which can reduce overall system performance. This is because the page table entries may not be contiguous, which can result in additional overhead when accessing memory.
## Example Problem
Consider a virtual memory system with physical memory of 8GB, a page size of 8KB, and a 46-bit virtual address. Assume every page table exactly fits into a single page. If page table entry size is 4B then how many levels of page tables would be required? 
**Explanation:** 
> Page size = 8KB = 213 B
> Virtual address space size = 246 B
> PTE = 4B = 22 B
>
> Number of pages or number of entries in page table,
> = (virtual address space size) / (page size)
> = 246B/213 B
> = 233
**Size of Page Table:**
> = (number of entries in page table)\*(size of PTE)
> = 233\*22 B
> = 235 B
**If page table size > desired size then create 1 more level.  To create one more level:**
> **Size of Page Table > Page Size**
>
> Number of page tables in last level,
> = 235 B / 213 B
> = 222
![multilevel_paging_2](assets/multilevel_paging_2-f4901a5d82.webp)
Multilevel Paging
- Size of page table [second last level] = 222\*22B = 224B
- To create one more level, Size of page table [second last level] > page size: Number of page tables in second last level = 224B/213 B = 211
- The base address of these tables are stored in page table [third last level]: Size of page table [third last level] = 211\*22 B = 213 B = page size, 3 levels are required.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/multilevel-paging-in-operating-system/)

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
