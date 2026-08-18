---
title: "Difference between Multiprogramming, multitasking, multithreading and multiprocessing"
subject: "Operating System"
topic: "Processes, Threads, CPU Scheduling"
source: "https://www.geeksforgeeks.org/operating-systems/difference-between-multitasking-multithreading-and-multiprocessing/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Processes, Threads, CPU Scheduling"
tags:
  - gate/cs
  - subject/operating-system
  - topic/processes-threads-cpu-scheduling
---


> [!abstract] Difference between Multiprogramming, multitasking, multithreading and multiprocessing
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Processes, Threads, CPU Scheduling`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/difference-between-multitasking-multithreading-and-multiprocessing/)

---

# Difference between Multiprogramming, multitasking, multithreading and multiprocessing

1. **Multiprogramming -** Multiprogramming is known as keeping multiple programs in the main memory at the same time ready for execution.
2. **Multiprocessing -** A computer using more than one CPU at a time.
3. **Multitasking -** Multitasking is nothing but multiprogramming with a Round-robin scheduling algorithm.
4. **Multithreading** is an extension of multitasking.
| Feature | Multiprogramming | Multitasking | Multithreading | Multiprocessing |
| Definition | Running multiple programs on a single CPU | Running multiple tasks (applications) on a single CPU | Running multiple threads within a single task (application) | Running multiple processes on multiple CPUs (or cores) |
| Resource Sharing | Resources (CPU, memory) are shared among programs | Resources (CPU, memory) are shared among tasks | Resources (CPU, memory) are shared among threads | Each process has its own set of resources (CPU, memory) |
| Scheduling | Uses round-robin or priority-based scheduling to allocate CPU time to programs | Uses priority-based or time-slicing scheduling to allocate CPU time to tasks | Uses priority-based or time-slicing scheduling to allocate CPU time to threads | Each process can have its own scheduling algorithm |
| Memory Management | Each program has its own memory space | Each task has its own memory space | Threads share memory space within a task | Each process has its own memory space |
| Context Switching | Requires a context switch to switch between programs | Requires a context switch to switch between tasks | Requires a context switch to switch between threads | Requires a context switch to switch between processes |
| Inter-Process Communication (IPC) | Uses message passing or shared memory for IPC | Uses message passing or shared memory for IPC | Uses thread synchronization mechanisms (e.g., locks, semaphores) for IPC | Uses inter-process communication mechanisms (e.g., pipes, sockets) for IPC |
### 1. Multi programming
In a computer system, many jobs wait for CPU execution. Since memory cannot hold all jobs at once, they are kept in a job pool. In a Multiprogramming Operating System, when one job goes for an I/O operation, the operating system assigns the CPU to another job. This keeps the CPU busy and improves system efficiency.
- Multiple jobs are kept in a job pool.
- CPU switches to another job during I/O.
- Improves CPU utilization. 💻
In the image below, program A runs for some time and then goes to waiting state. In the mean time program B begins its execution. So the CPU does not waste its resources and gives program B an opportunity to run. 
![](assets/multiprogramming-d2f23c2222.jpg)
### 2. Multiprocessing
In a uni-processor system, only one process executes at a time. Multiprocessing is the use of two or more CPUs (processors) within a single Computer system. This allows multiple processes to run simultaneously, improving system speed and performance. The processors share resources such as memory, clock, and peripheral devices.
- Uses multiple CPUs in one computer system.
- Allows parallel execution of processes.
- Increases speed and performance.
- Provides higher reliability if one processor fails.
![](assets/multiPROCESSINGjpg-e470dae59b.jpg)
### 3. Multitasking
Multitasking refers to the ability of an operating system to run multiple tasks at the same time. It is an extension of Multiprogramming Operating System. In multitasking, the CPU shares its time among different tasks using time sharing and context switching. Each process is given a small time slice (quantum), and after that time the CPU switches to another process. Because this switching happens very quickly, it appears that many programs are running simultaneously, even though only one process executes at a time on a single CPU.
Key Points:
- Executes multiple tasks on one CPU.
- Uses time sharing and context switching.
- Each task gets a small time quantum.
- Creates the illusion of simultaneous execution.
In a more general sense, multitasking refers to having multiple programs, processes, tasks, threads running at the same time. This term is used in modern operating systems when multiple tasks share a common processing resource (e.g., CPU and Memory). 
![](assets/multitasking-3c5fdf60f1.jpg)
- As depicted in the above image, At any time the CPU is executing only one task while other tasks are waiting for their turn. The illusion of parallelism is achieved when the CPU is reassigned to another task. i.e all the three tasks A, B and C are appearing to occur simultaneously because of time sharing.
- So for multitasking to take place, firstly there should be multiprogramming i.e. presence of multiple programs ready for execution. And secondly the concept of time sharing.
### 4. Multi threading -
A thread is a basic unit of CPU utilization. Multithreading is an execution model that allows a single process to have multiple threads running concurrently within the same process. Each thread performs a specific task while sharing the same resources of the process. For example, in VLC media player, one thread may handle opening the player, another may play a song, and another may manage the playlist. Multithreading allows a process to handle multiple tasks or user requests efficiently without running multiple copies of the program.
- A thread is the basic unit of CPU execution.
- Multiple threads run within a single process.
- Threads share the same memory and resources.
- Improves performance and responsiveness.
![](assets/vlc-5443a0527f.jpg)
The image below completely describes the VLC player example:  
**Advantages of Multi threading -**
- Benefits of Multi threading include increased responsiveness. Since there are multiple threads in a program, so if one thread is taking too long to execute or if it gets blocked, the rest of the threads keep executing without any problem. Thus the whole program remains responsive to the user by means of remaining threads.
- Another advantage of multi threading is that it is less costly. Creating brand new processes and allocating resources is a time consuming task, but since threads share resources of the parent process, creating threads and switching between them is comparatively easy. Hence multi threading is the need of modern Operating Systems.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/difference-between-multitasking-multithreading-and-multiprocessing/)

## GATE CS

- Subject: Operating System
- Topic: Processes, Threads, CPU Scheduling

> [!note] Related notes
>
> - [[Benefits of Multithreading]]
> - [[Context Switching in OS]]
> - [[Difference between thread and process]]
> - [[Fork function call]]
> - [[fork() in C]]
> - [[Introduction of System Call]]
> - [[Microkernel]]
> - [[Monolithic Kernel and key differences from Microkernel]]
> - [[Multi threading models]]
> - [[Multithreading]]
