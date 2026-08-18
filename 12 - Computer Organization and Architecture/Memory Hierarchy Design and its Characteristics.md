---
title: "Memory Hierarchy Design and its Characteristics"
subject: "Computer Organization and Architecture"
topic: "Cache Memory"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/memory-hierarchy-design-and-its-characteristics/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Cache Memory"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/cache-memory
---


> [!abstract] Memory Hierarchy Design and its Characteristics
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Cache Memory`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/memory-hierarchy-design-and-its-characteristics/)

---

# Memory Hierarchy Design and its Characteristics

In the Computer System Design, Memory Hierarchy is an enhancement to organize the memory such that it can minimize the access time. The Memory Hierarchy was developed based on a program behavior known as [locality of references](https://www.geeksforgeeks.org/computer-organization-architecture/locality-of-reference-and-cache-operation-in-cache-memory/) (same data or nearby data is likely to be accessed again and again). The figure below clearly demonstrates the different levels of the memory hierarchy.
## Why Memory Hierarchy is Required in the System?
Memory Hierarchy helps in optimizing the memory available in the computer. There are multiple levels present in the memory, each one having a different size, different cost, etc. Some types of memory like cache, and main memory are faster as compared to other types of memory but they are having a little less size and are also costly whereas some memory has a little higher storage value, but they are a little slower. Accessing of data is not similar in all types of memory, some have faster access whereas some have slower access.
## Types of Memory Hierarchy
This Memory Hierarchy Design is divided into 2 main types:
- **External Memory or Secondary Memory:** Comprising of Magnetic Disk, Optical Disk, and Magnetic Tape i.e. peripheral storage devices which are accessible by the processor via an I/O Module.
- **Internal Memory or Primary Memory:** Comprising of Main Memory, Cache Memory &  [CPU registers](https://www.geeksforgeeks.org/computer-organization-architecture/different-classes-of-cpu-registers/). This is directly accessible by the processor.
![Memory-Hierarchy-Design](assets/Memory-Hierarchy-Design-2ecc4db957.webp)
## Memory Hierarchy Design
### 1. Registers
Registers are small, high-speed memory units located in the CPU. They are used to store the most frequently used data and instructions. [Registers](https://www.geeksforgeeks.org/computer-organization-architecture/different-classes-of-cpu-registers/) have the fastest access time and the smallest storage capacity, typically ranging from 16 to 64 bits.
### 2. Cache Memory
Cache memory is a small, fast memory unit located close to the CPU. It stores frequently used data and instructions that have been recently accessed from the main memory. [Cache memory](https://www.geeksforgeeks.org/computer-organization-architecture/cache-memory-in-computer-organization/) is designed to minimize the time it takes to access data by providing the CPU with quick access to frequently used data.
### **3. Main Memory**
Main memory, also known as [RAM](https://www.geeksforgeeks.org/computer-science-fundamentals/random-access-memory-ram/) (Random Access Memory), is the primary memory of a computer system. It has a larger storage capacity than cache memory, but it is slower. [Main memory](https://www.geeksforgeeks.org/operating-systems/memory-management-in-operating-system/) is used to store data and instructions that are currently in use by the CPU.
#### Types of Main Memory
- **Static RAM:** Static RAM stores the binary information in flip flops and information remains valid until power is supplied. [Static RAM](https://www.geeksforgeeks.org/computer-organization-architecture/difference-between-sram-and-dram/) has a faster access time and is used in implementing cache memory.
- **Dynamic RAM:** It stores the binary information as a charge on the capacitor. It requires refreshing circuitry to maintain the charge on the capacitors after a few milliseconds. It contains more memory cells per unit area as compared to SRAM.
read more about - [Different Types of RAM (Random Access Memory)](https://www.geeksforgeeks.org/computer-organization-architecture/different-types-ram-random-access-memory/)
### 4. Secondary Storage
Secondary storage, such as  [hard disk drives (HDD) and solid-state drives (SSD)](https://www.geeksforgeeks.org/computer-organization-architecture/difference-between-hard-disk-drive-hdd-and-solid-state-drive-ssd/)  , is a non-volatile memory unit that has a larger storage capacity than main memory. It is used to store data and instructions that are not currently in use by the CPU. Secondary storage has the slowest access time and is typically the least expensive type of memory in the memory hierarchy.
### 5. Magnetic Disk
Magnetic Disks are simply circular plates that are fabricated with either a metal or a plastic or a magnetized material. The [Magnetic disks](https://www.geeksforgeeks.org/operating-systems/magnetic-disk-memory/) work at a high speed inside the computer and these are frequently used.
### 6. Magnetic Tape
Magnetic Tape is simply a magnetic recording device that is covered with a plastic film. [Magnetic Tape](https://www.geeksforgeeks.org/computer-organization-architecture/magnetic-tape-memory/) is generally used for the backup of data. In the case of a magnetic tape, the access time for a computer is a little slower and therefore, it requires some amount of time for accessing the strip.
## Characteristics of Memory Hierarchy
- **Capacity:** It is the global volume of information the memory can store. As we move from top to bottom in the Hierarchy, the capacity increases.
- **Access Time:** It is the time interval between the read/write request and the availability of the data. As we move from top to bottom in the Hierarchy, the access time increases.
- **Performance:** The Memory Hierarch design ensures that frequently accessed data is stored in faster memory to improve system performance.
- **Cost Per Bit:** As we move from bottom to top in the Hierarchy, the cost per bit increases i.e. Internal Memory is costlier than External Memory.
## System-Supported Memory Standards
According to the memory Hierarchy, the system-supported memory standards are defined below:
![memory_table](assets/memory_table-51fe42f79b.webp)
## Advantages of Memory Hierarchy
- **Performance:** Frequently used data is stored in faster memory (like cache), reducing access time and improving overall system performance.
- **Cost Efficiency:** By combining small, fast memory (like registers and cache) with larger, slower memory (like RAM and HDD), the system achieves a balance between cost and performance. It saves the consumer's price and time.
- **Optimized Resource Utilization:** Combines the benefits of small, fast memory and large, cost-effective storage to maximize system performance.
- **Efficient Data Management:** Frequently accessed data is kept closer to the CPU, while less frequently used data is stored in larger, slower memory, ensuring efficient data handling.
## Disadvantages of Memory Hierarchy
- **Complex Design:** Managing and coordinating data across different levels of the hierarchy adds complexity to the system's design and operation.
- **Cost:** Faster memory components like registers and cache are expensive, limiting their size and increasing the overall cost of the system.
- **Latency:** Accessing data stored in slower memory (like secondary or tertiary storage) increases the latency and reduces system performance.
- **Maintenance Overhead:** Managing and maintaining different types of memory adds overhead in terms of hardware and software.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/memory-hierarchy-design-and-its-characteristics/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: Cache Memory

> [!note] Related notes
>
> - [[2D and 2.5D Memory organization]]
> - [[Cache Memory]]
> - [[Cache Organization Introduction]]
> - [[Different Types of RAM]]
> - [[Introduction to memory and memory units]]
> - [[Locality and Cache friendly code]]
> - [[Memory Interleaving]]
> - [[RAM vs ROM]]
> - [[Read and Write operations in memory]]
> - [[Types of computer memory]]
