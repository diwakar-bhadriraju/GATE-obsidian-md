---
title: "Belady's Anomaly in Page Replacement Algorithms"
subject: "Operating System"
topic: "Virtual Memory"
source: "https://www.geeksforgeeks.org/operating-systems/beladys-anomaly-in-page-replacement-algorithms/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Virtual Memory"
tags:
  - gate/cs
  - subject/operating-system
  - topic/virtual-memory
---


> [!abstract] Belady's Anomaly in Page Replacement Algorithms
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Virtual Memory`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/beladys-anomaly-in-page-replacement-algorithms/)

---

# Belady's Anomaly in Page Replacement Algorithms

Belady’s Anomaly is a phenomenon in operating systems where increasing the number of page frames can unexpectedly increase the number of page faults in certain page replacement algorithms. Normally, more frames should reduce page faults, but in some cases, the opposite happens, leading to inefficient memory performance.
- Occurs when more page frames result in more page faults
- Violates the expected behavior of memory improvement
- Seen in algorithms like FIFO, Second Chance, and Random
- Does not occur in optimal or stack-based algorithms (like LRU)
Generally, on increasing the number of frames to a process' virtual memory, its execution becomes faster as fewer page faults occur. Sometimes the reverse happens, i.e. more page faults occur when more frames are allocated to a process. This most unexpected result is termed Belady's Anomaly. 
### Why Some Algorithms Avoid It
Certain algorithms like Optimal and LRU never suffer from Belady’s Anomaly because they are stack-based algorithms.
- **Stack Property:** Pages in memory with N frames will always be a subset of those with N+1 frames.
- **Optimal Algorithm:** Replaces the page not needed for the longest time in the future.
- **LRU (Least Recently Used):** Keeps the most recently used pages; if frames increase, these pages still remain in memory.
- **Difference from FIFO:** FIFO may evict a useful page simply because it was loaded earlier, while stack-based algorithms maintain consistency.
**Example:** Consider the following diagram to understand the behavior of a stack-based page replacement algorithm 
![](assets/stackbased-0f6b551f45.png)
The diagram illustrates that given the set of pages i.e. {0, 1, 2} in 3 frames of memory is not a subset of the pages in memory - {0, 1, 4, 5} with 4 frames and it is a violation in the property of stack-based algorithms. This situation can be frequently seen in FIFO algorithm. 
## **Belady's Anomaly in FIFO**
In FIFO page replacement it is supposed that the number of page faults should be less when we increase the number of frames. But sometimes, when the number of page faults increases even after increasing the number of frames, "Belady's Anomaly" occurs.
Let us understand this condition using a graph:
![1graph](assets/1graph-8afa6522bc.webp)
Let us understand Belady's Anomaly in FIFO using an example:
Assuming a system that has no pages loaded in the memory and uses the FIFO Page replacement algorithm. Consider the following reference string: 
> 1, 2, 3, 4, 1, 2, 5, 1, 2, 3, 4, 5
**Case 1:** If the system has 3 frames, the given reference string the using FIFO page replacement algorithm yields a total of 9 page faults. The diagram below illustrates the pattern of the page faults occurring in the example. 
![Belady Anomaly - FIFO](assets/fifo3-0971ba754b.png)
**Case 2:** If the system has 4 frames, the given reference string using the [FIFO page replacement algorithm](https://www.geeksforgeeks.org/dsa/program-page-replacement-algorithms-set-2-fifo/) yields a total of 10 page faults. The diagram below illustrates the pattern of the page faults occurring in the example. 
![Belady Anomaly - FIFO](assets/fifo4-5046f872e9.png)
It can be seen from the above example that on increasing the number of frames while using the FIFO page replacement algorithm, the number of **page faults increased** from 9 to 10. 
> **Note -** It is not necessary that every string reference pattern cause Belady anomaly in FIFO but there is certain kind of string references that worsen the FIFO performance on increasing the number of frames. 
## **Why Stack Based Algorithms do not Suffer Anomaly?**
- **Independent of Frames:** Stack-based algorithms assign replacement priority that doesn’t depend on the number of frames.
- **Examples: Optimal, LRU, LFU:** these always avoid Belady’s Anomaly.
- **Simulation Benefit:** The hit/miss ratio can be calculated for any number of frames in a single pass through the reference string.
- **LRU Example:** Each time a page is used, it moves to the top of the stack. The top n entries are the most recently used pages. If frames increase to n+1, the new set still includes the previous n pages, so no anomaly occurs.
> 1, 2, 3, 4, 1, 2, 5, 1, 2, 3, 4, 5
**Case 1:** If the system has 3 frames, the given reference string using the [LRU page replacement algorithm](https://www.geeksforgeeks.org/dsa/program-for-least-recently-used-lru-page-replacement-algorithm/) yields a total of 10 page faults. The diagram below illustrates the pattern of the page faults occurring in the example. 
![Belady Anomaly - Case 1](assets/LRU33-5f47f8b411.png)
**Case 2:** If the system has 4 frames, the given reference string on using LRU page replacement algorithm, then total 8 page faults occur. The diagram shows the pattern of the page faults in the example. 
![Belady Anomaly - Case 2](assets/LRU44-1-753029850d.png)
> [Program to show Belady’s Anomaly](https://www.geeksforgeeks.org/operating-systems/program-to-show-beladys-anomaly/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/beladys-anomaly-in-page-replacement-algorithms/)

## GATE CS

- Subject: Operating System
- Topic: Virtual Memory

> [!note] Related notes
>
> - [[Difference between Spooling and Buffering]]
> - [[Overlays in Memory Management]]
> - [[Page Fault Handling]]
> - [[Page Replacement Algorithms]]
> - [[Program for Optimal Page Replacement Algorithm]]
> - [[Secondary memory – Hard disk drive]]
> - [[Swap Space]]
> - [[Techniques to handle Thrashing]]
> - [[Virtual Memory]]
> - [[What exactly Spooling is all about]]
