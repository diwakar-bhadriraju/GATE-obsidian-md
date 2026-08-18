---
title: "Process vs Thread"
subject: "Operating System"
topic: "Processes, Threads, CPU Scheduling"
source: "https://www.geeksforgeeks.org/operating-systems/difference-between-process-and-thread/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Processes, Threads, CPU Scheduling"
tags:
  - gate/cs
  - subject/operating-system
  - topic/processes-threads-cpu-scheduling
---


> [!abstract] Process vs Thread
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Processes, Threads, CPU Scheduling`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/difference-between-process-and-thread/)

---

# Process vs Thread

Modern operating systems are designed to handle multiple tasks efficiently while maintaining good performance and responsiveness. These are mainly achieved through processes and threads.
- Process is the Independent program with its own memory
- Thread is small unit of a process sharing same memory
## Process
[Process](https://www.geeksforgeeks.org/operating-systems/process-in-operating-system/) is a program that is currently in execution within an operating system. It operates in an independent environment and is managed by the OS for proper scheduling and execution. Processes form the basis of program execution in a multitasking system. Its Properties are:
- Each process has a unique Process ID (PID) for identification.
- Every process moves through different states such as new, ready, running, waiting, and terminated.
- Processes communicate with each other using [Inter-Process Communication (IPC) methods](https://www.geeksforgeeks.org/operating-systems/methods-in-interprocess-communication/).
![12](assets/12-3e90cb0ae1.webp)
Process
## Thread
[Thread](https://www.geeksforgeeks.org/operating-systems/thread-in-operating-system/) is a smallest unit of execution within a process. It enables a program to perform multiple tasks concurrently while sharing the same memory and resources. Threads improve application performance and responsiveness in multitasking environments. Its properties are:
- Each thread has its own Thread ID (TID) for identification.
- A thread also moves through states such as new, runnable, running, waiting, and terminated.
- Threads within the same process share memory and resources, enabling faster communication.
- Context switching can occur between threads to allow multiple tasks to execute efficiently.
![thread](assets/thread-f42d7d935d.webp)
Thread
## Similarities Between Threads and Processes
- **Units of Execution:** Both are execution units within an operating system and are part of process management.
- **OS Scheduling & Preemption:** Both are scheduled by the operating system for fair CPU allocation, and can be preempted for multitasking.
- **Own Execution Context:** Each has its own execution context, including program counter, CPU registers, and stack space.
- **Creation During Runtime:** Both can create child entities during their execution lifecycle.
- **Communication & Resource Release:** Both can communicate using IPC mechanisms, and upon termination, their allocated resources are released back to the operating system
## Process vs Thread
| Process | Thread |
| --- | --- |
| Program in execution | Part of a process |
| Takes more time to create & terminate | Takes less time to create & terminate |
| Context switching is slow | Context switching is fast |
| Heavyweight | Lightweight |
| Less efficient communication | More efficient communication |
| Blocking one process doesn’t affect others | Blocking a user-level thread may block all |
| Uses system calls | Created using APIs (may not need OS call) |
| Has its own PCB, stack, address space | Shares PCB & address space, has own TCB & stack |
| Does not share data | Shares data with other threads |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/difference-between-process-and-thread/)

## GATE CS

- Subject: Operating System
- Topic: Processes, Threads, CPU Scheduling

> [!note] Related notes
>
> - [[Benefits of Multithreading]]
> - [[Context Switching in OS]]
> - [[Difference between multitasking, multithreading and multiprocessing]]
> - [[Fork function call]]
> - [[fork() in C]]
> - [[Introduction of System Call]]
> - [[Microkernel]]
> - [[Monolithic Kernel and key differences from Microkernel]]
> - [[Multi threading models]]
> - [[Multithreading]]
