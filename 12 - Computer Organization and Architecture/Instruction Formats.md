---
title: "Instruction Formats"
subject: "Computer Organization and Architecture"
topic: "Machine Instructions and Addressing Modes"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-instruction-formats-zero-one-two-three-address-instruction/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Machine Instructions and Addressing Modes"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/machine-instructions-and-addressing-modes
---


> [!abstract] Instruction Formats
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Machine Instructions and Addressing Modes`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-instruction-formats-zero-one-two-three-address-instruction/)

---

# Instruction Formats

Instruction format defines how instructions are represented in a computer’s memory. There are different types of instruction formats, including zero, one, two, and three-address instructions.
![what_is_instruction_format_in_coa_](assets/what_is_instruction_format_in_coa_-6c635ca55f.webp)
Defines how the CPU decodes and executes instructions.
- **Opcode:** This field specifies the operation to be performed by the CPU, such as addition, subtraction, or data transfer.
- **Operands:** These fields contain the data or references (addresses) to data on which the operation acts.
- **Addressing Mode:** This specifies how to interpret or locate the operand, such as direct, indirect, or immediate addressing.
## Types of Instruction Formats
Instruction formats are classified into zero, one, two, and three-address types, depending on how many address fields they have. Each type works differently and is used in various ways in computer architecture.
**NOTE:** We will use the X = (A+B)\*(C+D) expression to showcase the procedure. 
### **Zero Address Instructions**
Zero-address instructions do not specify any operands or addresses explicitly. Instead, they operate on operands that are implicitly defined, typically using a stack. The required data is taken from the top of the stack, and the result is pushed back onto the stack.
For example, an addition operation in a zero-address instruction adds the top two elements of the stack without specifying their addresses.
![Zero Address Instruction](assets/Untitled-drawing4-1-72d287b5d6.jpg)
Zero Address Instruction
A stack-based computer does not use the address field in the instruction. To evaluate an expression, it is first converted to reverse Polish Notation i.e. Postfix Notation.
> **Expression:** X = (A+B)\*(C+D)
> **Postfixed :** X = AB+CD+\*
> TOP means top of stack
> M[X] is any memory location
| **Instruction** | **Stack (TOP Value After Execution)** |
| --- | --- |
| PUSH A | TOP = A |
| PUSH B | TOP = B |
| ADD | TOP = A + B |
| PUSH C | TOP = C |
| PUSH D | TOP = D |
| ADD | TOP = C + D |
| MUL | TOP = (C + D) \* (A + B) |
| POP X | M[X] = TOP |
### **One Address Instructions**
These instructions specify one operand or address, which typically refers to a memory location or register. The instruction operates on the contents of that operand, and the result may be stored in the same or a different location. For example, a one-address instruction might load the contents of a memory location into a register.
This uses an implied ACCUMULATOR register for data manipulation. One operand is in the accumulator and the other is in the register or memory location. Implied means that the CPU already knows that one operand is in the accumulator so there is no need to specify it.
![One Address Instruction](assets/Untitled-drawing2-110d33faf1.png)
One Address Instruction
> **Expression:** X = (A+B)\*(C+D)
> AC is accumulator
> M[] is any memory location
> M[T] is temporary location
| **Instruction** | **Stack / Register (AC / M[])** |
| --- | --- |
| AC = A | AC = A |
| AC = AC + B | AC = A + B |
| M[T] = AC | M[T] = A + B |
| AC = C | AC = C |
| AC = AC + D | AC = C + D |
| M[] = AC | M[] = C + D |
| AC = AC \* M[T] | AC = (A + B) \* (C + D) |
| M[X] = AC | M[X] = (A + B) \* (C + D) |
### **Two Address Instructions**
These instructions specify two operands or addresses, which may be memory locations or registers. The instruction operates on the contents of both operands, and the result is typically stored in one of the specified operands. For example, a two-address instruction might add the contents of two registers together and store the result in one of the registers.
This is common in commercial computers. Here two addresses can be specified in the instruction. Unlike earlier in one address instruction, the result was stored in the accumulator, here the result can be stored at different locations rather than just accumulators, but require more number of bit to represent the address.
![Two Address Instruction](assets/Untitled-drawing6-1-54e785b924.png)
Two Address Instruction
Here destination address can also contain an operand.
> **Expression:** X = (A+B)\*(C+D)
> R1, R2 are registers
> M[] is any memory location
| **Instruction** | **Registers / Memory (R1, R2, M[])** |
| --- | --- |
| R1 = A | R1 = A |
| R1 = R1 + B | R1 = A + B |
| R2 = C | R2 = C |
| R2 = R2 + D | R2 = C + D |
| R1 = R1 \* R2 | R1 = (A + B) \* (C + D) |
| M[X] = R1 | M[X] = (A + B) \* (C + D) |
### **Three Address Instructions**
Three address instructions are a type of instruction format that specifies three operands, which can be registers or memory locations, where two operands are used for the operation and the result is stored in the third, for example R1 ← R2 + R3; these instructions include three address fields, making programs shorter and easier to write, but they require more bits per instruction, increasing instruction size; although they simplify programming and improve readability, they do not necessarily make execution faster because the CPU still performs operations step by step through individual micro-operations.
![Three Address Instruction](assets/Untitled-drawing5-2363ab210d.png)
Three Address Instruction
> **Expression:** X = (A+B)\*(C+D)
> R1, R2 are registers
> M[] is any memory location
| Instruction | Description |
| --- | --- |
| R1 ← A | Load value A into R1 |
| R1 ← R1 + B | Add B to R1 |
| M[T1] ← R1 | Store R1 into memory at location T1 |
| R2 ← C | Load value C into R2 |
| R2 ← R2 + D | Add D to R2 |
| M[T2] ← R2 | Store R2 into memory at location T2 |
| R1 ← M[T1] | Load value from memory location T1 into R1 |
| R1 ← R1 × M[T2] | Multiply R1 with value at T2 and store in R1 |
| M[X] ← R1 | Store R1 into memory at location X |
## CPU Organization and Instruction Formats
CPU organization can be classified based on how operands are stored and accessed during instruction execution:
- **Accumulator-based Organization:**
   Uses a single special register called the accumulator to store intermediate results. Most operations are performed using this accumulator.
- **General Register Organization:**
   Uses multiple general-purpose registers to store operands and intermediate results, providing greater flexibility and faster execution.
- **Stack Organization:**
   Uses a stack structure where operations are performed on the top elements. Operands are implicitly accessed, so instructions do not need to specify addresses.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-instruction-formats-zero-one-two-three-address-instruction/)

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
