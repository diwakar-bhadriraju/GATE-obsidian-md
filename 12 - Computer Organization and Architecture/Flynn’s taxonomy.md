---
title: "Flynn's Taxonomy"
subject: "Computer Organization and Architecture"
topic: "Machine Instructions and Addressing Modes"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/computer-architecture-flynns-taxonomy/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Machine Instructions and Addressing Modes"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/machine-instructions-and-addressing-modes
---


> [!abstract] Flynn's Taxonomy
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Machine Instructions and Addressing Modes`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-architecture-flynns-taxonomy/)

---

# Flynn's Taxonomy

Flynn's Taxonomy classifies computer architectures according to how many instruction streams (processes) and data streams they can process simultaneously, dividing them into four categories: SISD, SIMD, MISD, and MIMD.
![flynn_s_classification_of_computers](assets/flynn_s_classification_of_computers-c0d0f1a09c.webp)
Classification of Flynn's Taxonomy
### Single-Instruction, Single-Data (SISD) Systems
An SISD computing system is a uniprocessor machine which is capable of executing a single instruction, operating on a single data stream. In SISD, machine instructions are processed in a sequential manner, and computers adopting this model are popularly called sequential computers. Most conventional computers have SISD architecture. All the instructions and data to be processed have to be stored in primary memory.
![sisd](assets/sisd-1f7ba76f51.webp)
The speed of the processing element in the SISD model is limited(dependent) by the rate at which the computer can transfer information internally. Dominant representative SISD systems are IBM PCs, workstations.
### Single-Instruction, Multiple-Data (SIMD) Systems
An SIMD system is a multiprocessor machine capable of executing the same instruction on all the CPUs but operating on different data streams. Machines based on an SIMD model are well suited to scientific computing since they involve lots of vector and matrix operations.
![simd](assets/simd-3bd2e0cde0.webp)
So that the information can be passed to all the processing elements (PEs) organized data elements of vectors can be divided into multiple sets(N-sets for N PE systems) and each PE can process one data set. Dominant representative SIMD systems is Cray’s vector processing machine.
### Multiple-Instruction, Single-Data (MISD) systems
An MISD computing system is a multiprocessor machine capable of executing different instructions on different PEs but all of them operating on the same dataset.
![misd](assets/misd-64f63f7127.webp)
Example Z = sin(x)+cos(x)+tan(x) The system performs different operations on the same data set. Machines built using the MISD model are not useful in most of the application, a few machines are built, but none of them are available commercially.
### Multiple-Instruction, Multiple-Data (MIMD) Systems
An MIMD system is a multiprocessor machine which is capable of executing multiple instructions on multiple data sets. Each PE in the MIMD model has separate instruction and data streams; therefore machines built using this model are capable to any kind of application. Unlike SIMD and MISD machines, PEs in MIMD machines work asynchronously.
![mimd](assets/mimd-a46e12927c.webp)
MIMD machines are classified into **shared-memory** and **distributed-memory** models depending on how processors connect to memory. In a **shared-memory MIMD system** (tightly coupled), all processors use the same global memory, and communication happens through it. Any change made by one processor is visible to all others. Examples include Silicon Graphics and Sun/IBM’s SMP systems.
In a **distributed-memory MIMD system** (loosely coupled), each processor has its own local memory, and they communicate through an interconnection network (like tree or mesh).
Shared-memory systems are easier to program but harder to scale and more vulnerable to failures, since a fault can affect the whole system. In contrast, distributed-memory systems are more scalable and fault-tolerant, since each processor is independent. For real-world use, distributed-memory MIMD is generally considered **superior for large-scale and high-performance computing**, due to their scalability, reliability, and ability to handle complex tasks efficiently.
> **Must Read**
>
> - [Computer Organization - Von Neumann architecture](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-von-neumann-architecture/)
> - [Computer Organization and Architecture Tutorial](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-and-architecture-tutorials/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-architecture-flynns-taxonomy/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: Machine Instructions and Addressing Modes

> [!note] Related notes
>
> - [[A simple understanding of Computer]]
> - [[Addressing Modes]]
> - [[Amdahl’s law and its proof]]
> - [[Basic Computer Instructions]]
> - [[Computer Architecture and Computer Organization]]
> - [[Computer System Level Hierarchy]]
> - [[Difference between CALL and JUMP instructions]]
> - [[General Register based CPU Organization]]
> - [[Generations of computer]]
> - [[Hardware architecture]]
