---
title: "Single Accumulator Based CPU Organization"
subject: "Computer Organization and Architecture"
topic: "Machine Instructions and Addressing Modes"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/introduction-of-single-accumulator-based-cpu-organization/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Machine Instructions and Addressing Modes"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/machine-instructions-and-addressing-modes
---


> [!abstract] Single Accumulator Based CPU Organization
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Machine Instructions and Addressing Modes`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/introduction-of-single-accumulator-based-cpu-organization/)

---

# Single Accumulator Based CPU Organization

In a single accumulator-based CPU, all arithmetic and logic operations use the Accumulator (AC) as the main register to hold intermediate results. This design is called a “One Address Machine” because instructions contain only one explicit address while the accumulator is used implicitly.
- The accumulator serves as the primary operand for most instructions.
- This leads to a simpler and more compact instruc**t**ion format.
![output](assets/output-be5aba1a28.webp)
Accumulator - based CPU Organization
## Instruction Format
In a single accumulator CPU, the basic instruction format is:
![SingleCPU](assets/SingleCPU-e44263922d.png)
Single Accumulator based CPU Instruction Format
- **Opcode (Operation Code)**: Specifies the operation to be performed (e.g., ADD, SUB, LOAD, STORE, MULT).
- **Address**: Specifies the memory location (or register) of the operand.
The first operand is always taken from the Accumulator, and the second operand is fetched from the memory location specified by the address field. The result of the operation is then stored back into the Accumulator.
## Basic Operations
Single accumulator-based CPUs support two main categories of instructions:
### **Data Transfer Instructions**
These instructions move data between memory and the accumulator.
- **LOAD X**: Transfers data from memory location X to the Accumulator.
> AC ← M[X]
- **STORE Y**: Transfers data from the Accumulator to memory location Y.
> M[Y] ← AC
> **Note:** The accumulator is always the default destination or source for data movement.
### ALU (Arithmetic and Logic Unit) Instructions
These instructions perform arithmetic or logical operations using the accumulator and a memory operand.
> For example:
>
> **MULT X**: Multiplies the content of the Accumulator with the operand stored at memory location X.
>
> AC ← AC \* M[X]
Similarly, other operations can include **ADD X**, **SUB X**, **AND X**, **OR X**, etc.
## Working Principle
The execution of an instruction in a single accumulator-based CPU typically involves the following steps:
#### **1. Fetch**
- Retrieve the instruction from the memory location pointed to by the Program Counter (PC).
- Increment the Program Counter to point to the next instruction.
#### **2. Decode**
- Interpret the fetched instruction to determine the operation (Opcode).
- Identify the operand’s address or location required for execution.
#### **3. Execute**
- Fetch the operand from memory (if required).
- Perform the operation using the Accumulator and the operand.
- Store the result back in the Accumulator.
#### **4. Store (if applicable)**
- Write the result to memory if the instruction requires.
Because the accumulator is used implicitly, the instruction length is shorter and execution is faster compared to architectures that must specify multiple operands explicitly.
## Example Program Execution
Suppose we want to compute:
> Z = (A + B) \* C
Using a single accumulator-based architecture:
> LOAD A ; AC ← M[A]
>
> ADD B ; AC ← AC + M[B]
>
> MULT C ; AC ← AC \* M[C]
>
> STORE Z ; M[Z] ← AC
This program uses the accumulator to hold intermediate results after each step. Notice that every operation involves AC, making the instruction sequence simple and compact.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/introduction-of-single-accumulator-based-cpu-organization/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: Machine Instructions and Addressing Modes

> [!note] Related notes
>
> - [[A simple understanding of Computer]]
> - [[Addressing Modes]]
> - [[Amdahl’s law and its proof]]
> - [[Basic Computer Instructions]]
> - [[Computer Architecture and Computer Organization]]
> - [[Computer System Level Hierarchy]]
> - [[Difference between CALL and JUMP instructions]]
> - [[Flynn’s taxonomy]]
> - [[General Register based CPU Organization]]
> - [[Generations of computer]]
