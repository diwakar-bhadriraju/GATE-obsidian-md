---
title: "Context Switching in Operating System"
subject: "Operating System"
topic: "Processes, Threads, CPU Scheduling"
source: "https://www.geeksforgeeks.org/operating-systems/context-switch-in-operating-system/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Processes, Threads, CPU Scheduling"
tags:
  - gate/cs
  - subject/operating-system
  - topic/processes-threads-cpu-scheduling
---


> [!abstract] Context Switching in Operating System
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Processes, Threads, CPU Scheduling`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/context-switch-in-operating-system/)

---

# Context Switching in Operating System

Context switching is the process where the CPU stops running one process, saves its current state, and loads the saved state of another process so that multiple processes can share the CPU effectively.
## Need in Multitasking
It is essential in multitasking systems where many processes need CPU time.
- In multitasking, the CPU keeps switching between processes.
- This makes it seem like processes are running at the same time, even though the CPU works on one process at a time.
- Without context switching, one process could monopolize the CPU, and others would have to wait indefinitely
## Role in Scheduling
- The scheduler decides which process should run next based on a scheduling algorithm (like Round Robin, Priority Scheduling, etc.).
- Context switching executes that decision by stopping the current process and starting the chosen one.
- The [dispatcher](https://www.geeksforgeeks.org/operating-systems/difference-between-dispatcher-and-scheduler/) is the component that actually performs the switch.
## Context Switching Triggers
Context Switching Happen:
- When a high-priority process comes to a ready state (i.e. with higher priority than the running process).
- An Interrupt occurs.
- User and kernel-mode switch (It is not necessary though)
- Preemptive CPU scheduling is used.
When switching between user mode and kernel/user mode is necessary, operating systems use the kernel/user switch.
## Working Process of Context Switching
Let us take examples of two processes **po** and **p1** that execute in interleaved manner
![1223](assets/1223-35546bed8e.webp)
State Diagram of Context Switching
**Explanation of the Above Diagram**
The diagram illustrates how the CPU alternates execution between two processes — p0 and p1 — through context switching.
1. Execution Phase (Process p0)
- Process p0 is running while p1 remains idle.
- At some point, an interrupt or system call occurs (e.g., a timer interrupt or I/O completion).
2. Saving Current State (p0 → PCB0)
- The operating system pauses p0.
- The current state of p0 (register values, program counter, etc.) is saved into its Process Control Block (PCB0).
- This ensures that p0 can later resume exactly where it left off.
3. Loading New Process State (PCB1 → p1)
- The OS retrieves the saved state of p1 from PCB1.
- This step restores p1’s CPU context so it can continue execution from its last saved point.
4. Execution Phase (Process p1)
- Now, p1 is running while p0 is idle.
- Another interrupt or system call occurs, triggering another switch.
5. Saving State of p1 (p1 → PCB1): The OS saves the current state of p1 into PCB1.
6. Reloading State of p0 (PCB0 → p0)
- The saved state of p0 from PCB0 is loaded back into the CPU registers.
- p0 resumes execution right where it left off.
## Overhead
- Time spent switching is called context switch overhead.
- During this time, the CPU is not performing actual process work it’s just preparing to run the next process.
- If context switching happens too often, CPU efficiency drops.
## Factors Affecting Switch Time
Context-switch times are highly dependent on hardware support. For example, some processors (such as the Sun UltraSPARC) provide multiple sets of registers. In this case, a context switch simply requires changing the pointer to the current register set. However, if there are more active processes than available register sets, the system resorts to copying register data to and from memory, as before. Additionally, the more complex the operating system, the greater the amount of work that must be done during a context switch.
- Hardware support for fast register saving/loading.
- Number of registers (more registers = more time to save/load).
- Memory speed for PCB storage.
- Efficiency of OS kernel code.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/context-switch-in-operating-system/)

## GATE CS

- Subject: Operating System
- Topic: Processes, Threads, CPU Scheduling

> [!note] Related notes
>
> - [[Benefits of Multithreading]]
> - [[Difference between multitasking, multithreading and multiprocessing]]
> - [[Difference between thread and process]]
> - [[Fork function call]]
> - [[fork() in C]]
> - [[Introduction of System Call]]
> - [[Microkernel]]
> - [[Monolithic Kernel and key differences from Microkernel]]
> - [[Multi threading models]]
> - [[Multithreading]]
