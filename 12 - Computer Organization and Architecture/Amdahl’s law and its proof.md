---
title: "Amdahl's law in Computer Organization"
subject: "Computer Organization and Architecture"
topic: "Machine Instructions and Addressing Modes"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-amdahls-law-and-its-proof/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Machine Instructions and Addressing Modes"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/machine-instructions-and-addressing-modes
---


> [!abstract] Amdahl's law in Computer Organization
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Machine Instructions and Addressing Modes`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-amdahls-law-and-its-proof/)

---

# Amdahl's law in Computer Organization

Amdahl’s Law, proposed by Gene Amdahl in 1967, explains the theoretical speedup of a program when part of it is improved or parallelized. It is widely used in parallel computing to predict the benefits of using multiple processors.
The main idea is that the speedup of a system is limited by the portion of the program that cannot be parallelized (the sequential part).
### Key Terms
- **Speedup (S):**
  Performance improvement gained by enhancement.
$$
S = \frac{\text{Old Execution Time}}{\text{New Execution Time}}
$$
- **Fraction Enhanced (P):**
   The proportion of the program that can be parallelized (0 < P < 1).
- **Number of Processors (N):**
   The number of parallel units used for execution.
### Formula
$$
S = \frac{1}{(1 - P) + \frac{P}{N}}
$$
- **(1 - P):** sequential portion (cannot be parallelized).
- **P/N:** parallel portion divided among N processors.
### Maximum Speedup
- If processors are unlimited (N → ∞)
$$
S_{\text{max}} = \frac{1}{1 - P}
$$
- This means the **non-parallelizable fraction sets the performance limit**.
- If **P = 1** (100% parallelizable), theoretical speedup is infinite (not realistic).
### Example
Suppose a program spends **20% (P = 0.2)** of its time in parallelizable work, and we use **5 processors (N = 5):**
S=1(1−0.2)+0.25=10.8+0.04=1.19S = \frac{1}{(1 - 0.2) + \frac{0.2}{5}} = \frac{1}{0.8 + 0.04} = 1.19S=(1−0.2)+50.2​1​=0.8+0.041​=1.19
➡ The system improves by only **19%**, showing that the 80% sequential part is the bottleneck.
### Advantages
- Provides a clear upper bound on performance.
- Helps identify bottlenecks in programs.
- Useful in guiding hardware/software design decisions.
### Disadvantages
- Assumes the sequential part is fixed (in practice, it can sometimes be optimized).
- Assumes processors are identical, not always true in heterogeneous systems.
- Ignores real-world factors like communication, synchronization, and load balancing overhead.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-amdahls-law-and-its-proof/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: Machine Instructions and Addressing Modes

> [!note] Related notes
>
> - [[A simple understanding of Computer]]
> - [[Addressing Modes]]
> - [[Basic Computer Instructions]]
> - [[Computer Architecture and Computer Organization]]
> - [[Computer System Level Hierarchy]]
> - [[Difference between CALL and JUMP instructions]]
> - [[Flynn’s taxonomy]]
> - [[General Register based CPU Organization]]
> - [[Generations of computer]]
> - [[Hardware architecture]]
