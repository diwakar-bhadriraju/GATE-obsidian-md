---
title: "Pipelining Types and Stalling"
subject: "Computer Organization and Architecture"
topic: "Instruction Pipelining"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-and-architecture-pipelining-set-3-types-and-stalling/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Instruction Pipelining"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/instruction-pipelining
---


> [!abstract] Pipelining Types and Stalling
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Instruction Pipelining`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-and-architecture-pipelining-set-3-types-and-stalling/)

---

# Pipelining Types and Stalling

Pipelining is a fundamental technique used in computer architecture to improve the throughput of instruction execution by overlapping the execution phases of multiple instructions. The effectiveness of a pipeline depends significantly on how the pipeline stages are organized and timed. There are two primary types of pipelines based on stage timing: 
### Uniform Delay Pipeline
In this type of pipeline, all the stages will take the same time to complete an operation. In a uniform delay pipeline, Cycle Time (Tp) = Stage Delay If buffers are included between the stages, then Cycle Time (Tp) = Stage Delay + Buffer Delay.
### Non-Uniform Delay Pipeline
In this type of pipeline, different stages take different times to complete an operation. In this type of pipeline, Cycle Time (Tp) = Maximum(Stage Delay) For example, if there are 4 stages with delays of 1 ns, 2 ns, 3 ns, and 4 ns, then Tp = Maximum(1 ns, 2 ns, 3 ns, 4 ns) = 4 ns If buffers are included between the stages, Tp = Maximum(Stage delay + Buffer delay)
**Example:** Consider a 4-segment pipeline with stage delays (2 ns, 8 ns, 3 ns, 10 ns). Find the time taken to execute 100 tasks in the above pipeline. **Solution:** As the above pipeline is a non-linear pipeline, Tp = max(2, 8, 3, 10) = 10 ns. We know that ETpipeline = (k + n – 1) Tp = (4 + 100 – 1) 10 ns = 1030 ns. NOTE: MIPS = Million instructions per second
### **Performance of Pipeline with Stalls**
![performance](assets/performance-20b603ab96.webp)
- => S = Average Execution Timenon-pipeline / Average Execution Timepipeline
- => S = CPInon-pipeline \* Cycle Timenon-pipeline / CPIpipeline \* Cycle Timepipeline
- => S = CPInon-pipeline \* Clock frequency pipeline / CPIpipeline \* Clock frequencynon-pipeline
Ideal CPI of the pipelined processor is '1'. But due to stalls, it becomes greater than '1'. =>
- S = CPInon-pipeline \* Cycle Timenon-pipeline / (1 + Number of stalls per Instruction) \* Cycle Timepipeline
- As Cycle Timenon-pipeline = Cycle Timepipeline,
![cpi](assets/cpi-3da4ed5731.webp)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-and-architecture-pipelining-set-3-types-and-stalling/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: Instruction Pipelining

> [!note] Related notes
>
> - [[Different Instruction Cycles]]
> - [[Micro-Operation]]
> - [[Performance of Computer]]
> - [[Pipelining]]
> - [[Pipelining Set 2]]
> - [[RISC and CISC]]
> - [[RISC and CISC Set 2]]
> - [[2D and 2.5D Memory organization]]
> - [[A simple understanding of Computer]]
> - [[Addressing Modes]]
