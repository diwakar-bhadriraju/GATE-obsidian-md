---
title: "Spooling vs Buffering"
subject: "Operating System"
topic: "Virtual Memory"
source: "https://www.geeksforgeeks.org/operating-systems/difference-between-spooling-and-buffering/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Virtual Memory"
tags:
  - gate/cs
  - subject/operating-system
  - topic/virtual-memory
---


> [!abstract] Spooling vs Buffering
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Virtual Memory`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/difference-between-spooling-and-buffering/)

---

# Spooling vs Buffering

Input/output (I/O) operations can be slow because different devices work at different speeds. To improve I/O efficiency and reduce waiting time, operating systems use techniques such as spooling and buffering. Although both improve I/O performance, they are used for different purposes.
- [**Spooling**](https://www.geeksforgeeks.org/operating-systems/what-exactly-spooling-is-all-about/)**:** Stores multiple I/O jobs in a disk-based queue so that a shared device can process them one at a time while other programs continue executing.
- [**Buffering**](https://www.geeksforgeeks.org/operating-systems/buffering-in-os/)**:** Temporarily stores data in memory to make data transfer smoother between devices or programs, reducing waiting time and improving communication speed and reliability.
![spooling_vs_buffering](assets/spooling_vs_buffering-2e80ef2da7.jpg)
## Spooling vs Buffering
| **Spooling** | **Buffering** |
| --- | --- |
| Overlaps the I/O of one job with the execution of another job. | Overlaps the I/O with the execution of the same job. |
| Stands for Simultaneous Peripheral Operation On-Line. | Has no full form. |
| Uses secondary storage (usually disk) as a queue for pending I/O jobs. | Uses a small area of RAM as a temporary buffer. |
| Suitable for managing multiple queued I/O requests for shared devices. | Limited by available memory and intended for temporary data storage. |
| **Example:** Print jobs are queued on disk and sent to the printer one by one. | **Example:** Video streaming buffers data in memory for smooth playback. |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/difference-between-spooling-and-buffering/)

## GATE CS

- Subject: Operating System
- Topic: Virtual Memory

> [!note] Related notes
>
> - [[Belady’s Anomaly]]
> - [[Overlays in Memory Management]]
> - [[Page Fault Handling]]
> - [[Page Replacement Algorithms]]
> - [[Program for Optimal Page Replacement Algorithm]]
> - [[Secondary memory – Hard disk drive]]
> - [[Swap Space]]
> - [[Techniques to handle Thrashing]]
> - [[Virtual Memory]]
> - [[What exactly Spooling is all about]]
