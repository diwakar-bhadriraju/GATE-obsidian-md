---
title: "Execution and Throughput"
subject: "Computer Organization and Architecture"
topic: "Instruction Pipelining"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-and-architecture-pipelining-set-1-execution-stages-and-throughput/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Instruction Pipelining"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/instruction-pipelining
---


> [!abstract] Execution and Throughput
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Instruction Pipelining`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-and-architecture-pipelining-set-1-execution-stages-and-throughput/)

---

# Execution and Throughput

Pipelining is an arrangement of the CPU's hardware components to raise the CPU's general performance. In a pipelined processor, procedures called 'stages’ are accomplished in parallel, and the execution of more than one line of instruction occurs.
- Each stage works on a different part of an instruction.
- The goal is to complete one instruction per clock cycle after filling.
![pipelined](assets/pipelined-7d7d3521d2.webp)
## **Execution in a Pipelined Processor**
Execution sequence of instructions in a pipelined processor can be visualised using a space-time diagram. For example, consider a processor having 4 stages and let there be 2 instructions to be executed. We can visualize the execution sequence through the following space-time diagrams: 
### **Non-Overlapped Execution**
| Stage / Cycle | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| S1 | I1 |  |  |  | I2 |  |  |  |
| S2 |  | I1 |  |  |  | I2 |  |  |
| S3 |  |  | I1 |  |  |  | I2 |  |
| S4 |  |  |  | I1 |  |  |  | I2 |
Total time = 8 Cycle 
### **Overlapped Execution**
| Stage / Cycle | 1 | 2 | 3 | 4 | 5 |
| --- | --- | --- | --- | --- | --- |
| S1 | I1 | I2 |  |  |  |
| S2 |  | I1 | I2 |  |  |
| S3 |  |  | I1 | I2 |  |
| S4 |  |  |  | I1 | I2 |
Total time = 5 Cycle **Pipeline Stages** [RISC](https://www.geeksforgeeks.org/computer-organization-architecture/advanced-risc-machine-arm-processor/) processor has 5 stage instruction pipeline to execute all the instructions in the RISC instruction set. Following are the 5 stages of the RISC pipeline with their respective operations:
- **Stage 1 (Instruction Fetch):** In this stage the [CPU](https://www.geeksforgeeks.org/computer-organization-architecture/what-are-the-functions-of-a-cpu/) fetches the instructions from the address present in the memory location whose value is stored in the program counter.
- **Stage 2 (Instruction Decode):** In this stage, the instruction is decoded and register file is accessed to obtain the values of registers used in the instruction.
- **Stage 3 (Instruction Execute):** In this stage some of activities are done such as [ALU](https://www.geeksforgeeks.org/computer-science-fundamentals/difference-between-alu-and-cu/) operations.
- **Stage 4 (Memory Access):** In this stage, memory operands are read and written from/to the memory that is present in the instruction.
- **Stage 5 (Write Back):** In this stage, computed/fetched value is written back to the register present in the instructions.
**Performance of a pipelined processor** Consider a 'k' segment pipeline with clock cycle time as 'Tp'. Let there be 'n' tasks to be completed in the pipelined processor. Now, the first instruction is going to take 'k' cycles to come out of the pipeline but the other 'n – 1' instructions will take only '1' cycle each, i.e, a total of 'n – 1' cycles. So, time taken to execute 'n' instructions in a pipelined processor:
```
                     ETpipeline = k + n – 1 cycles                              = (k + n – 1) Tp
```
In the same case, for a non-pipelined processor, the execution time of 'n' instructions will be:
```
                    ETnon-pipeline = n * k * Tp
```
So, speedup (S) of the pipelined processor over the non-pipelined processor, when 'n' tasks are executed on the same processor is:
```
    S = Performance of non-pipelined processor /        Performance of pipelined processor
```
As the performance of a processor is inversely proportional to the execution time, we have,
```
   S = ETnon-pipeline / ETpipeline    => S =  [n * k * Tp] / [(k + n – 1) * Tp]       S = [n * k] / [k + n – 1]
```
When the number of tasks 'n' is significantly larger than k, that is, n >> k
```
    S = n * k / n    S = k
```
where 'k' are the number of stages in the pipeline. Also, **Efficiency** = Given speed up / Max speed up = S / Smax We know that Smax = k So, **Efficiency** = S / k **Throughput** = Number of instructions / Total time to complete the instructions So,
## Throughout
Performance of pipeline is measured using two main metrices as Throughput and latency. **Throughout** = n / (k + n – 1) \* Tp Note: The cycles per instruction (CPI) value of an ideal pipelined processor is 1/tp, when n is not given or ideal case case and n is very large.
- It measure number of instruction completed per unit time.
- It represents overall processing speed of pipeline.
- Higher throughput indicate processing speed of pipeline.
- Calculated as, throughput= number of instruction executed/ execution time.
- It can be affected by pipeline length, clock frequency. efficiency of instruction execution and presence of pipeline hazards or stalls.
## Latency
- It measure time taken for a single instruction to complete its execution.
- It represents delay or time it takes for an instruction to pass through pipeline stages.
- Lower latency indicates better performance .
- It is calculated as, Latency= k × Tp ( where k = number of pipeline stages & Tp = clock cycle time ).
- It in influenced by pipeline length, depth, clock cycle time, instruction dependencies and pipeline hazards.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-and-architecture-pipelining-set-1-execution-stages-and-throughput/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: Instruction Pipelining

> [!note] Related notes
>
> - [[Different Instruction Cycles]]
> - [[Micro-Operation]]
> - [[Performance of Computer]]
> - [[Pipelining Set 2]]
> - [[Pipelining Set 3]]
> - [[RISC and CISC]]
> - [[RISC and CISC Set 2]]
> - [[2D and 2.5D Memory organization]]
> - [[A simple understanding of Computer]]
> - [[Addressing Modes]]
