---
title: "Paging"
subject: "Operating System"
topic: "Main Memory Management"
source: "https://www.geeksforgeeks.org/operating-systems/paging-in-operating-system/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Main Memory Management"
tags:
  - gate/cs
  - subject/operating-system
  - topic/main-memory-management
---


> [!abstract] Paging
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Main Memory Management`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/paging-in-operating-system/)

---

# Paging

Paging is a memory management technique in which a process is divided into fixed-size blocks called pages, and physical memory is divided into frames of the same size. Pages are loaded from secondary storage into main memory as needed.
- A process does not need to be stored in contiguous memory locations.
- The entire process does not need to be loaded into main memory at once; only required pages are loaded on demand. This allows efficient utilization of memory and supports execution of large programs.
- Memory allocation is simplified because memory is managed in fixed-size pages and frames.
![Page_tABLE](assets/Page_tABLE-cd52458e52.webp)
Paging in Operating System
To keep track of where each page is stored in memory, the operating system uses a page table. This table shows the connection between the logical page numbers and the physical page frames (actual locations in RAM).
> **Note:** The memory management unit uses the page table to convert logical addresses into physical addresses, so the program can access the correct data in memory.
## Paging in Memory Management
Paging addresses common challenges in allocating and managing memory efficiently. Why paging is needed as a Memory Management technique:
- **Memory isn’t always available in a single block:** Programs often need more memory than what is available in a single continuous block. Paging breaks memory into smaller, fixed-size pieces, making it easier to allocate scattered free spaces.
- **Processes size can increase or decrease:** programs don’t need to occupy continuous memory, so they can grow dynamically without the need to be moved.
### Terminologies Associated with Memory Control
- **Logical Address Space or Virtual Address Space:** The [Logical Address](https://www.geeksforgeeks.org/operating-systems/logical-and-physical-address-in-operating-system/) Space, refers to the set of all possible logical addresses that a process can generate during its execution.
- **Physical Address Space:** The [Physical Address](https://www.geeksforgeeks.org/operating-systems/logical-and-physical-address-in-operating-system/) Space refers to the total range of addresses available in a computer's physical memory (RAM).
### Important Features of Paging
- **Logical to physical address mapping:** Paging divides a process's logical address space into fixed-size pages. Each page maps to a frame in physical memory, enabling flexible [memory management](https://www.geeksforgeeks.org/operating-systems/memory-management-in-operating-system/).
- **Fixed page and frame size:** Pages and frames have the same fixed size. This simplifies memory management and improves system performance.
- **Page table entries:** Each logical page is represented by a page table entry (PTE). A PTE stores the corresponding frame number and control bits.
- **Number of page table entries:** The page table has one entry per logical page. Thus, its size equals the number of pages in the process's address space.
- **Page table stored in main memory:** The page table is kept in main memory. This can add overhead when processes are swapped in or out.
### Working of Paging
When a process requests memory, the operating system allocates one or more page frames to the process and maps the process's logical pages to the physical page frames. When a program runs, its pages are loaded into any available frames in the physical memory.
![paging](assets/paging-a70b36a57b.webp)
Working of Paging
Each program has a page table, which the operating system uses to keep track of where each page is stored in physical memory. When a program accesses data, the system uses this table to convert the program's address into a physical memory address.
**Steps Involved in Paging :**
- **Step 1 Divide Memory :** Logical -> Pages, Physical -> Frames .
- **Step 2 Allocate Pages :** Load pages into available frames.
- **Step 3 Page Table :** Map logical pages to physical frames.
- **Step 4 Translate Address :** Convert logical to physical address.
- **Step 5 Handle Page Fault :** Load missing pages from disk.
- **Step 6 Run Program :** CPU uses page table during execution.
> If Logical Address Space = 128 M words = 128 × 220 = 27 × 220 = 227 words
> Then Logical Address = log2(227)= **27 bits**
>
> If Physical Address Space = 16 M words = 16 × 220 = 24 × 220 = 224 words
> Then Physical Address = log2(224)= **24 bits**
The mapping from virtual to physical address is done by the [Memory Management Unit (MMU)](https://www.geeksforgeeks.org/operating-systems/memory-management-in-operating-system/) which is a hardware device and this mapping is known as the paging technique.
- The Physical Address Space is conceptually divided into a number of fixed-size blocks, called frames.
- The Logical Address Space is also split into fixed-size blocks, called pages.
- Page Size = Frame Size
### Example
- **Physical Address** = 12 bits, then Physical Address Space = 4 K words
- **Logical Address** = 13 bits, then Logical Address Space = 8 K words
- **Page size** = frame size = 1 K words (assumption)
> **Number of frames** = Physical Address Space / Frame Size = 4K / 1K = 4 = 22
> **Number of Pages** = Logical Address Space / Page Size = 8K / 1K = 23
**The address generated by the CPU is divided into:**
1. **Page number(p):** Number of bits required to represent the pages in [Logical Address Space](https://www.geeksforgeeks.org/operating-systems/logical-and-physical-address-in-operating-system/) or Page number
2. **Page offset(d):** Number of bits required to represent a particular word in a page or page size of Logical Address Space or word number of a page or page offset.
**A Physical Address is divided into two main parts:**
1. **Frame Number(f):** Number of bits required to represent the frame of Physical Address Space or Frame number frame
2. **Frame Offset(d):** Number of bits required to represent a particular word in a frame or frame size of Physical Address Space or word number of a frame or frame offset.
> **Physical Address** = (Frame Number << Number of Bits in Frame Offset) + Frame Offset
> where "<<" represents a bitwise left shift operation.
## Hardware implementation of Paging
The hardware implementation of the page table can be done by using dedicated registers. But the usage of the register for the page table is satisfactory only if the page table is small. If the page table contains a large number of entries then we can use TLB(translation Look-aside buffer), a special, small, fast look-up hardware cache.
![page_table_tlb](assets/page_table_tlb-f1d1ca2789.webp)
Page Table with TLB
- The [TLB](https://www.geeksforgeeks.org/operating-systems/translation-lookaside-buffer-tlb-in-paging/) is associative, high-speed memory.
- Each entry in TLB consists of two parts: a tag and a value.
- When this memory is used, then an item is compared with all tags simultaneously. If the item is found, then the corresponding value is returned.
> **Main memory access time** = m, If page table are kept in main memory, Effective access time = m(for page table) + m(for particular page in page table)
> Read Related Article [Page Table Entries](https://www.geeksforgeeks.org/operating-systems/page-table-entries-in-page-table/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/paging-in-operating-system/)

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
