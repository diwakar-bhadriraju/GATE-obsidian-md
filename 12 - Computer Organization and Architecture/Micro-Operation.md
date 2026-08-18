---
title: "Micro-Operation"
subject: "Computer Organization and Architecture"
topic: "Instruction Pipelining"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-micro-operation/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Instruction Pipelining"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/instruction-pipelining
---


> [!abstract] Micro-Operation
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Instruction Pipelining`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-micro-operation/)

---

# Micro-Operation

**Micro-operations** (also known as micro-ops) are the functional, or atomic, operations of a processor. These are low-level instructions used in some designs to implement complex machine instructions. They generally perform operations on data stored in one or more registers.
- They transfer data between registers or between external buses of the CPU and also perform arithmetic and logical operations on registers.
- Modern CPUs execute multiple instructions in parallel using pipelining and superscalar architectures.
- Each instruction cycle is made up of several smaller units—Fetch,Indirect, Execute**,** and [Interrupt](https://www.geeksforgeeks.org/operating-systems/interrupts/)cycles.
- Each of these cycles involves a series of steps that operate on processor [registers](https://www.geeksforgeeks.org/digital-logic/shift-registers-in-digital-logic/). These steps are called **micro-operations**.
The prefix 'micro' refers to the fact that each of the steps is very simple.
![1](assets/1-199d08a66a.webp)
Micro-operations are small tasks performed inside the CPU. These tasks use data stored in the CPU’s registers to do basic operations like math or logic tasks. They also help move data between registers or between memory and registers.
## How Micro-Operations Work?
Micro-operations are combined to perform more complex instructions. For example, an addition instruction might involve several micro-operations:
- First, a **load** operation to move values into registers.
- Then, an **add** operation to perform the calculation.
- Finally, a **store** operation to save the result in memory.
## Types of Micro-Operations
Micro-operations generally fall into four major types:
- **Register Transfer Micro-Operations**: Moving data between registers or between registers and memory/I/O (e.g., loading data from memory into a register).
- **Arithmetic Micro-Operations**: Performing arithmetic calculations on register data, such as addition, subtraction, increment, and decrement.
- **Logic Micro-Operations**: Executing logical operations (bitwise) on register contents, like AND, OR, XOR, and NOT.
- **Shift Micro-Operations**: Shifting or rotating bits in a register to the left or right (useful in multiplying/dividing by powers of two or bitwise operations).
### Examples of Micro-Operations
1. **Load**: Moves data from memory into a register.
2. **Store**: Saves data from a register back into memory.
3. **Add**: Adds two values and stores the result in a register.
4. **Subtract**: Subtracts one value from another and stores the result in a register.
5. **AND**: Performs a logical AND operation on two values and stores the result in a register.
6. **OR**: Performs a logical OR operation on two values and stores the result in a register.
7. **NOT**: Reverses the bits of a value and stores the result in a register.
8. **Shift**: Moves the bits of a value to the left or right within a register.
9. **Rotate**: Rotates the bits of a value left or right in a register.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-micro-operation/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: Instruction Pipelining

> [!note] Related notes
>
> - [[Different Instruction Cycles]]
> - [[Performance of Computer]]
> - [[Pipelining]]
> - [[Pipelining Set 2]]
> - [[Pipelining Set 3]]
> - [[RISC and CISC]]
> - [[RISC and CISC Set 2]]
> - [[2D and 2.5D Memory organization]]
> - [[A simple understanding of Computer]]
> - [[Addressing Modes]]
