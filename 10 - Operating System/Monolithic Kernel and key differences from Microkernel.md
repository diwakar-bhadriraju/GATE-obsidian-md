---
title: "Monolithic Kernel and Key Differences From Microkernel"
subject: "Operating System"
topic: "Processes, Threads, CPU Scheduling"
source: "https://www.geeksforgeeks.org/operating-systems/monolithic-kernel-and-key-differences-from-microkernel/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Processes, Threads, CPU Scheduling"
tags:
  - gate/cs
  - subject/operating-system
  - topic/processes-threads-cpu-scheduling
---


> [!abstract] Monolithic Kernel and Key Differences From Microkernel
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Processes, Threads, CPU Scheduling`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/monolithic-kernel-and-key-differences-from-microkernel/)

---

# Monolithic Kernel and Key Differences From Microkernel

The kernel is the core component of an operating system (OS) responsible for managing system resources and enabling communication between hardware and software. Based on how these services and components are organized, kernels are broadly classified into two main types - Monolithic Kernel and Microkernel.
> **Note:** Both serve the same goal of providing system-level functionality but differ significantly in architecture, performance and security.
## Monolithic Kernel
A monolithic kernel is an operating system kernel in which all the operating system services run in kernel space, meaning they all share the same memory space. This type of kernel is characterized by its tight integration of system services and its high performance. Below is the diagrammatic representation of the Monolithic Kernel: 
![Monolithic-Architecture](assets/Monolithic-Architecture-0d21fb4bb1.png)
Monolithic Kernel
### Advantages of Monolithic Kernel
- One of the major advantages of having a monolithic kernel is that it provides [CPU scheduling](https://www.geeksforgeeks.org/operating-systems/cpu-scheduling-in-operating-systems/), [memory management](https://www.geeksforgeeks.org/operating-systems/memory-management-in-operating-system/), file management, and other operating system functions through [system calls](https://www.geeksforgeeks.org/operating-systems/introduction-of-system-call/).
- The other one is that it is a single large process running entirely in a single address space.
- It is a single static binary file. Examples of some Monolithic Kernel-based OSs are Unix, Linux, Open VMS, XTS-400, z/TPF.
- No need for complex inter-process communication (IPC), which speeds up system call execution.
### Disadvantages of Monolithic Kernel
- **Stability Issues**: One of the major disadvantages of a monolithic kernel is that if anyone service fails it leads to an entire system failure.
- **Lack of Modularity**: If the user has to add any new service. The user needs to modify the entire [operating system](https://www.geeksforgeeks.org/operating-systems/what-is-an-operating-system/).
- **Security Risks**: A bug or vulnerability in any service can affect the entire system since all services run in kernel mode.
- **Large Size**: The kernel can become very large and complex as more services are added.
## Microkernel
A [microkernel](https://www.geeksforgeeks.org/operating-systems/microkernel-in-operating-systems/) is a type of operating system kernel in which only the most basic services run in kernel space, with other services running in user space. This type of kernel is characterized by its modularity, simplicity, and ability to run multiple operating systems on the same hardware. The microkernel itself typically includes only the most fundamental services, such as:
![structure_of_a_micro_kernel](assets/structure_of_a_micro_kernel-c97b9dd5fc.webp)
Microkernel
- **Inter-process Communication (IPC)**: Mechanisms for processes to communicate and [synchronize](https://www.geeksforgeeks.org/operating-systems/introduction-of-process-synchronization/) with each other.
- **Basic Scheduling**: Managing the execution of processes.
- **Minimal Memory Management**: Essential functions for memory allocation and protection.
Other functionalities that are often part of a monolithic kernel, like [device drivers](https://www.geeksforgeeks.org/operating-systems/device-driver-and-its-purpose/), file systems, and network protocols, are implemented in user space as separate processes. This contrasts with a monolithic kernel, where all these services run in kernel space.
## Kernel Space vs User Space
Before comparing types of kernels, it's important to know whether components run in kernel space or user space, as this impacts how the system works. In an operating system, there are two main areas where code runs: user space and kernel space.
> **Note:** User space is where user applications run, while kernel space is where the operating system and other important parts run.
In kernel space, code can directly access system resources like memory and hardware, allowing it to perform special tasks that user space code can't .System calls are important for connecting user space and kernel space. They let user applications ask the kernel for specific services. When an application makes a system call, it switches from user space to kernel space, allowing the kernel to do what the application requested.
## Differences Between Monolithic Kernel and Microkernel
![MicrokernelVsMonolithicKernel](assets/MicrokernelVsMonolithicKernel-b5b30a3124.jpg)
Monolithic v/s Microkernel
| Basics | Micro Kernel | Monolithic Kernel |
| --- | --- | --- |
| Size | Smaller | Larger as OS and both user lie in the same address space. |
| Execution | Slower | Faster |
| Extendible | Easily extendible | Complex to extend |
| Security | If the service crashes then there is no effect on working on the microkernel. | If the process/service crashes, the whole system crashes as both user and OS were in the same address space. |
| Code | More code is required to write a microkernel. | Less code is required to write a monolithic kernel. |
| Examples | L4Linux, macOS | Windows, Linux BSD |
| Security | More secure because only essential services run in kernel mode | Susceptible to security vulnerabilities due to the amount of code running in kernel mode |
| Platform independence | More portable because most drivers and services run in user space | Less portable due to direct hardware access |
| Communication | Message passing between user-space servers | Direct function calls within [kernel](https://www.geeksforgeeks.org/operating-systems/kernel-in-operating-system/) |
| Performance | Lower due to message passing and more overhead | High due to direct function calls and less overhead |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/monolithic-kernel-and-key-differences-from-microkernel/)

## GATE CS

- Subject: Operating System
- Topic: Processes, Threads, CPU Scheduling

> [!note] Related notes
>
> - [[Benefits of Multithreading]]
> - [[Context Switching in OS]]
> - [[Difference between multitasking, multithreading and multiprocessing]]
> - [[Difference between thread and process]]
> - [[Fork function call]]
> - [[fork() in C]]
> - [[Introduction of System Call]]
> - [[Microkernel]]
> - [[Multi threading models]]
> - [[Multithreading]]
