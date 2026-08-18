---
title: "RISC vs CISC"
subject: "Computer Organization and Architecture"
topic: "Instruction Pipelining"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-risc-and-cisc/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Instruction Pipelining"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/instruction-pipelining
---


> [!abstract] RISC vs CISC
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Instruction Pipelining`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-risc-and-cisc/)

---

# RISC vs CISC

RISC and CISC are two approaches to processor design with different instruction handling strategies.
- RISC uses a small set of simple, fixed-length instructions and follows a load/store approach, enabling efficient and fast execution.
- CISC uses a larger set of complex, variable-length instructions that can perform multiple operations, often requiring multiple clock cycles.
![vs](assets/vs-52febfa427.webp)
## Reduced Instruction Set Architecture (RISC)
RISC simplifies processor design by using a small, uniform set of instructions. Each instruction performs a basic operation (e.g., load, compute, store) and is designed to execute in a single clock cycle, enabling efficient pipelining and simpler hardware.
### Characteristics of RISC
- Simpler instruction, hence simple instruction decoding.
- Instruction comes in the form of one word.
- An instruction takes a single clock cycle to get executed.
- More general-purpose registers for register-to-register operations.
- Simple Addressing Modes.
- Optimized for pipelining due to uniform instruction size and simplicity.
## Complex Instruction Set Architecture (CISC)
CISC reduces the number of instructions a program needs by using a large set of complex, variable-length instructions. A single instruction can perform multiple operations (e.g., load, compute, and store), which may take multiple clock cycles.
### Characteristics of CISC
- Complex instruction, hence complex instruction decoding.
- Instructions are larger than one-word size.
- Instruction may take more than a single clock cycle to get executed.
- Less number of general-purpose registers as operations get performed in memory itself.
- Complex Addressing Modes.
## CPU Performance of RISC and CISC
Both approaches try to increase the CPU performance
$$
\text{CPU Time} = \frac{\text{Instructions}}{\text{Program}} \times \frac{\text{Cycles}}{\text{Instruction}} \times \frac{\text{Seconds}}{\text{Cycle}}
$$
- **RISC:** Reduce the cycles per instruction at the cost of the number of instructions per program.
- **CISC:** The CISC approach attempts to minimize the number of instructions per program but at the cost of an increase in the number of cycles per instruction.
Earlier when programming was done using assembly language, a need was felt to make instruction do more tasks because programming in assembly was tedious and error-prone due to which CISC architecture evolved but with the uprise of high-level language dependency on assembly reduced RISC architecture prevailed.
**Example:**
Suppose we have to add two 8-bit numbers:
- **CISC approach:** There will be a single command or instruction for this like ADD which will perform the task.
- **RISC approach:** Here programmer will write the first load command to load data in registers then it will use a suitable operator and then it will store the result in the desired location.
So, add operation is divided into parts i.e. load, operate, store due to which RISC programs are longer and require more memory to get stored but require fewer transistors due to less complex command.
## Comparison Table
RISC and CISC are two processor designs, here is a comparison table between them:
| RISC | CISC |
| --- | --- |
| Small and simple instruction set | Large and complex instruction set |
| Fixed-length instructions | Variable-length instructions |
| Usually 1 cycle per instruction | Multiple cycles per instruction |
| More general-purpose registers | Fewer registers |
| Simple and limited addressing modes | Complex and many addressing modes |
| Larger code size (more instructions) | Smaller code size (fewer instructions) |
| Simple hardware, easier pipelining | Complex hardware, harder pipelining |
| Examples: ARM, RISC-V, MIPS | Examples: x86, Intel 80386 |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-risc-and-cisc/)

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
> - [[Pipelining Set 3]]
> - [[RISC and CISC Set 2]]
> - [[2D and 2.5D Memory organization]]
> - [[A simple understanding of Computer]]
> - [[Addressing Modes]]
