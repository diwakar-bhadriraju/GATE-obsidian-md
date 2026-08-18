---
title: "Thrashing"
subject: "Operating System"
topic: "Virtual Memory"
source: "https://www.geeksforgeeks.org/operating-systems/techniques-to-handle-thrashing/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Virtual Memory"
tags:
  - gate/cs
  - subject/operating-system
  - topic/virtual-memory
---


> [!abstract] Thrashing
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Virtual Memory`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/techniques-to-handle-thrashing/)

---

# Thrashing

Thrashing occurs when the operating system spends more time swapping pages between main memory and disk than executing processes. This causes frequent page faults, low CPU utilization, and poor system performance.
**Cycle of Thrashing:**
- **High multiprogramming:** Too many processes are loaded into memory.
- **Insufficient frames:** Each process receives fewer memory frames than required.
- **Frequent page replacement:** More page faults lead to continuous swapping between memory and disk.
![cpu_utilization](assets/cpu_utilization-f226d8c9fb.webp)
This repeated cycle of low CPU utilization -> more processes -> more page faults is called Thrashing.
### **Role of Locality in Thrashing**
The concept of locality of reference explains why thrashing occurs. A locality is a group of pages that a program frequently uses during execution.
- A locality consists of pages that are actively used together.
- For example, a function call uses its instructions, local variables, and related data pages.
- If enough memory frames are available to hold the current locality, page faults remain low.
- If the allocated frames are fewer than the locality size, page faults increase rapidly.
- Thrashing occurs when the active localities of multiple processes cannot fit into main memory at the same time.
## Techniques to Handle Thrashing
### 1. Working Set Model
The Working Set Model reduces thrashing by allocating enough frames for a process's active pages.
- Working Set (WSSᵢ): Pages used in the last Δ references.
- Total demand: D = Σ WSSᵢ
- If D > m **(available frames)** -> Thrashing occurs.
- If D ≤ m -> No thrashing.
### 2. Page Fault Frequency (PFF)
PFF controls thrashing by monitoring the page fault rate of each process.
- Set upper and lower page fault limits.
- Fault rate > upper limit: Allocate more frames.
- Fault rate < lower limit: Remove extra frames.
- No free frames: Suspend some processes and reallocate their frames.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/techniques-to-handle-thrashing/)

## GATE CS

- Subject: Operating System
- Topic: Virtual Memory

> [!note] Related notes
>
> - [[Belady’s Anomaly]]
> - [[Difference between Spooling and Buffering]]
> - [[Overlays in Memory Management]]
> - [[Page Fault Handling]]
> - [[Page Replacement Algorithms]]
> - [[Program for Optimal Page Replacement Algorithm]]
> - [[Secondary memory – Hard disk drive]]
> - [[Swap Space]]
> - [[Virtual Memory]]
> - [[What exactly Spooling is all about]]
