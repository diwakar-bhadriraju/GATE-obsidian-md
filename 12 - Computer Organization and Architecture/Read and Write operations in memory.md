---
title: "Read and Write operations in Memory"
subject: "Computer Organization and Architecture"
topic: "Cache Memory"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/read-and-write-operations-in-memory/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Cache Memory"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/cache-memory
---


> [!abstract] Read and Write operations in Memory
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Cache Memory`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/read-and-write-operations-in-memory/)

---

# Read and Write operations in Memory

A memory unit stores binary information in groups of bits called words. Data input lines provide the information to be stored into the memory, Data output lines carry the information out from the memory. The control lines Read and write specifies the direction of transfer of data. Basically, in the memory organization, there are 
$$
2^{l}
$$
memory locations indexing from 0 to 
$$
2^{l}-1
$$
where l is the address buses. We can describe the memory in terms of the bytes using the following formula: 
$$
N = 2^{l} Bytes
$$
Where, l is the total address buses N is the memory in bytes For example, some storage can be described below in terms of bytes using the above formula:
```
 1kB= 210 Bytes 64 kB = 26 x 210 Bytes       = 216 Bytes 4 GB = 22 x 210(kB) x 210(MB) x 210 (GB)      = 232 Bytes
```
**Memory Address Register (MAR)** is the address register which is used to store the address of the memory location where the operation is being performed. **Memory Data Register (MDR)** is the data register which is used to store the data on which the operation is being performed.
1. **Memory Read Operation:**  Memory read operation transfers the desired word to address lines and activates the read control line.Description of memory read operation is given below: ![](assets/1-343-8389cdd0f8.png) In the above diagram initially, MDR can contain any garbage value and MAR is containing 2003 memory address. After the execution of read instruction, the data of memory location 2003 will be read and the MDR will get updated by the value of the 2003 memory location (3D).
2. **Memory Write Operation:**  Memory write operation transfers the address of the desired word to the address lines, transfers the data bits to be stored in memory to the data input lines. Then it activates the write control line. Description of the write operation is given below: ![](assets/2-253-558fc3b5ca.png) In the above diagram, the MAR contains 2003 and MDR contains 3D. After the execution of write instruction 3D will be written at 2003 memory location.
### Advantages of Read Operations:
**Speed:** Read operations are generally faster than write operations since the data is already stored in the memory.
**Efficiency:** Read operations are more efficient since they do not require modifying the data in memory.
**Non-destructive:** Read operations do not modify the data in memory, so they can be performed repeatedly without affecting the stored data.
### Disadvantages of Read Operations:
**Limited functionality:** Read operations only retrieve data from memory, so they cannot be used to modify the data.
**Security risks:** Read operations can be used to access sensitive data stored in memory, making them a potential security risk.
### Advantages of Write Operations:
**Flexibility:** Write operations allow data to be modified, making them useful for storing and updating information in memory.
**Dynamic:** Write operations allow data to be changed in real-time, making them essential for many computing applications.
**Customization:** Write operations allow users to customize and personalize their computing experience by modifying stored data.
### Disadvantages of Write Operations:
**Slower:** Write operations are generally slower than read operations since the data needs to be modified and then written back to memory.
**Overwriting risk:** Write operations can overwrite existing data in memory, leading to data loss or corruption.
**Wear and Tear:** Repeated write operations can cause wear and tear on memory cells, leading to reduced reliability and lifespan.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/read-and-write-operations-in-memory/)

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
> - [[Memory Hierarchy Design and its Characteristics]]
> - [[Memory Interleaving]]
> - [[RAM vs ROM]]
> - [[Types of computer memory]]
