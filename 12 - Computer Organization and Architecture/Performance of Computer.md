---
title: "Performance of Computer in Computer Organization"
subject: "Computer Organization and Architecture"
topic: "Instruction Pipelining"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-performance-of-computer/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Instruction Pipelining"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/instruction-pipelining
---


> [!abstract] Performance of Computer in Computer Organization
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Instruction Pipelining`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-performance-of-computer/)

---

# Performance of Computer in Computer Organization

In computer organization, performance refers to the speed and efficiency at which a computer system can execute tasks and process data. A high-performing computer system is one that can perform tasks quickly and efficiently while minimizing the amount of time and resources required to complete these tasks.
Here are several factors that can impact the performance of a computer system, including:
- **Processor speed:**  The speed of the processor, measured in GHz (gigahertz), determines how quickly the computer can execute instructions and process data.
- **Memory:**  The amount and speed of the memory, including RAM (random access memory) and cache memory, can impact how quickly data can be accessed and processed by the computer.
- **Storage:**  The speed and capacity of the storage devices, including hard drives and solid-state drives (SSDs), can impact the speed at which data can be stored and retrieved.
- **I/O devices:**  The speed and efficiency of input/output devices, such as [keyboards](https://www.geeksforgeeks.org/python/keyboard-module-in-python/) , mice, and displays, can impact the overall performance of the system.
- **Software optimization:**  The efficiency of the software running on the system, including operating systems and applications, can impact how quickly tasks can be completed.
Improving the performance of a computer system typically involves optimizing one or more of these factors to reduce the time and resources required to complete tasks. This can involve upgrading hardware components, optimizing software, and using specialized performance-tuning tools to identify and address bottlenecks in the system.
**Computer performance** is the amount of work accomplished by a computer system. The word performance in computer performance means "How well is the computer doing the work it is supposed to do?". It basically depends on the response time, throughput, and execution time of a computer system. **Response time** is the time from the start to completion of a task. This also includes:
- Operating system overhead.
- Waiting for I/O and other processes
- Accessing disk and memory
- Time spent executing on the CPU or execution time.
**Throughput** is the total amount of work done in a given time. **CPU execution time** is the total time a CPU spends computing on a given task. It also excludes time for I/O or running other programs. This is also referred to as simply CPU time. Performance is determined by execution time as performance is inversely proportional to execution time.
```
Performance = (1 / Execution time)
```
And,
```
(Performance of A /  Performance of B) = (Execution Time of B / Execution Time of A)
```
If given that Processor A is faster than processor B, that means execution time of A is less than that of execution time of B. Therefore, performance of A is greater than that of performance of B. **Example -** Machine A runs a program in 100 seconds, Machine B runs the same program in 125 seconds
```
(Performance of A /  Performance of B) = (Execution Time of B / Execution Time of A) = 125 / 100 = 1.25
```
That means machine A is 1.25 times faster than Machine B. And, the time to execute a given program can be computed as:
```
Execution time  = CPU clock cycles x clock cycle time
```
Since clock cycle time and clock rate are reciprocals, so,
```
Execution time  = CPU clock cycles / clock rate
```
The number of CPU clock cycles can be determined by,
```
CPU clock cycles = (No. of instructions / Program ) x (Clock cycles / Instruction) = Instruction Count x CPI
```
Which gives,
```
Execution time = Instruction Count x CPI x clock cycle time= Instruction Count x CPI / clock rate
```
## Units for CPU Execution TimeCPU Execution Time**How to Improve Performance?**
To improve performance you can either:
- Decrease the CPI (clock cycles per instruction) by using new Hardware.
- Decrease the clock time or Increase clock rate by reducing propagation delays or by use pipelining.
- Decrease the number of required cycles or improve ISA or Compiler.
## **Execution Upgrade Procedures**
The Exhibition upgrade on computer chip execution time is worked with by the accompanying variables in a significant manner.
1.Internal Engineering of the computer chip
2.Instruction Arrangement of the central processor
3.Memory Speed and transmission capacity
4.Percentage utilization of the registers in execution (note: Registers are something like multiple times quicker than memory).
Further, the accompanying highlights of a framework likewise improve the general presentation:
### Compositional Augmentations (Register set/GPRs/Register Document)
1.Special guidelines and tending to modes
2.Status register contents
3.Program control stack
4.Pipelining
5.Multiple degrees of Store Memory
6.Use of co-processors or particular equipment for Drifting Point tasks, Vector handling, Media handling.
7.Virtual Memory and Memory the executives Unit execution.
8.System Transport execution.
9.Super Scalar Handling
## **Uses and Benefitsof Performance of Computer**
 Some of the key uses and benefits of a high-performing computer system include:
- **Increased productivity:**  A high-performing computer can help increase productivity by reducing the time required to complete tasks, allowing users to complete more work in less time.
- **Improved user experience:**  A fast and efficient computer system can provide a better user experience, with smoother operation and fewer delays or interruptions.
- **Faster data processing:**  A high-performing computer can process data more quickly, enabling faster access to critical information and insights.
- **Enhanced gaming and multimedia performance:**  High-performance computers are better suited for gaming and multimedia applications, providing smoother and more immersive experiences.
- **Better efficiency and cost savings:**  By optimizing the performance of a computer system, it is possible to reduce the time and resources required to complete tasks, leading to better efficiency and cost savings.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-performance-of-computer/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: Instruction Pipelining

> [!note] Related notes
>
> - [[Different Instruction Cycles]]
> - [[Micro-Operation]]
> - [[Pipelining]]
> - [[Pipelining Set 2]]
> - [[Pipelining Set 3]]
> - [[RISC and CISC]]
> - [[RISC and CISC Set 2]]
> - [[2D and 2.5D Memory organization]]
> - [[A simple understanding of Computer]]
> - [[Addressing Modes]]
