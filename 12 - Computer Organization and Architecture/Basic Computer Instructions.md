---
title: "Computer Organization - Basic Computer Instructions"
subject: "Computer Organization and Architecture"
topic: "Machine Instructions and Addressing Modes"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-basic-computer-instructions/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Machine Instructions and Addressing Modes"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/machine-instructions-and-addressing-modes
---


> [!abstract] Computer Organization - Basic Computer Instructions
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Machine Instructions and Addressing Modes`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-basic-computer-instructions/)

---

# Computer Organization - Basic Computer Instructions

Computer organization describes how different parts of a computer system are arranged and connected to work together.
- Focuses on how hardware components interact to perform tasks.
- Includes the basic set of instructions that the computer can execute.
- Helps understand how programs are processed at a low level.
- Forms the foundation for efficient system operation.
## Basic Computer Instructions
Basic computer instructions are commands that tell a computer how to perform specific tasks. These instructions are typically divided into three categories:
- Data Transfer Instructions
- Arithmetic and Logic Instructions
- Control Instructions
## Data Transfer Instructions
Data transfer instructions are used to move data from one location to another within a computer system. This includes transferring information between memory, CPU registers, and other storage locations.
### Common Data Transfer Instructions
- **Load:** Copies data from memory into a CPU register for processing.
- **Store:** Transfers data from a CPU register back to memory.
- **Move:** Transfers data from one register to another within the CPU.
## Arithmetic and Logic Instructions
These instructions are used to perform mathematical and logical operations. They enable computers to handle calculations and make decisions based on certain conditions.
### Arithmetic Instructions
- **Add**: Adds two numbers.
- **Subtract**: Subtracts one number from another.
- **Multiply**: Multiplies two numbers.
- **Divide**: Divides one number by another.
### Logic Instructions
- **AND**: Performs a bitwise operation on binary operands. The result is 1 only if all corresponding bits are 1, otherwise, the result is 0.
- **OR**: Performs a bitwise operation on binary operands. The result is 1 if at least one of the corresponding bits is 1, otherwise, the result is 0.
- **NOT**: A unary bitwise operation that inverts each bit of the operand (1 becomes 0 and 0 becomes 1).
- **XOR (Exclusive OR)**: Performs a bitwise operation that returns 1 if the corresponding bits are different and 0 if they are the same. For multiple operands, it returns 1 when the number of 1s is odd and 0 when even.
## Control Instructions
Control instructions determine the flow of execution in a program. They guide the computer in deciding which instruction should be executed next, enabling decision-making, looping, and function execution.
### Common Control Instructions
- **Jump (JMP):** Transfers program execution directly to a specific instruction elsewhere in the code.
- **Conditional Branch:** Transfers execution to another instruction only when a specified condition is satisfied, such as Branch if Zero (BZ) or Branch if Not Zero (BNZ).
- **Call:** Transfers control to a subroutine, which is a group of instructions designed to perform a specific task.
- **Return:** Returns control back to the main program after the subroutine finishes execution.
## Instruction Set of a Basic Computer
A basic computer uses a 16-bit Instruction Register (IR). An instruction can be classified as a memory reference, register reference, or input/output instruction based on specific bits in the instruction format.
### 1. Memory Reference Instructions
These instructions use a **memory address as an operand**, while the other operand is always the **accumulator**.
- The instruction consists of a 12-bit address, a 3-bit opcode (not equal to 111), and a 1-bit addressing mode for direct or indirect addressing.
- These instructions operate on data stored in memory.
![1](assets/1-47898edf5d.webp)
Memory Reference Instruction Format
### 2. Register Reference Instructions
Register reference instructions perform operations directly on CPU registers rather than memory locations.
- IR(14–12) is equal to 111 and this value distinguishes register reference instructions from memory reference instructions.
   IR(15) is equal to 0 and this value differentiates them from input/output instructions.
- The remaining 12 bits are used to specify the register operation to be performed.
![2](assets/2-9843ef19dc.webp)
Register Reference Instruction Format
### 3. Input/Output Instructions
Input/output instructions are used for communication between the computer and external devices.
- IR(14–12) is equal to 111 and this distinguishes input output instructions from memory reference instructions.
- IR(15) is equal to 1 and this distinguishes them from register reference instructions.
- The remaining 12 bits are used to specify the input output operation.
![3](assets/3-de7592c6cb.webp)
Input/Output Instruction Format
## Essential Instructions in a Basic Computer
The [**Program Counter (PC)**](https://www.geeksforgeeks.org/operating-systems/what-is-program-counter/) is a key component of a computer system that holds the address of the next instruction to be executed. These instructions are processed by the Central Processing Unit (CPU) and form the foundation for all program operations.
### Basic PC instructions
| Symbol | Hexadecimal Code | Description |
| --- | --- | --- |
| AND | 0xxx, 8xxx | AND memory word to AC |
| ADD | 1xxx, 9xxx | Add memory word to AC |
| LDA | 2xxx, Axxx | Load memory word to AC |
| STA | 3xxx, Bxxx | Store AC content in memory |
| BUN | 4xxx, Cxxx | Branch Unconditionally |
| BSA | 5xxx, Dxxx | Branch and Save Return Address |
| ISZ | 6xxx, Exxx | Increment and skip if 0 |
| CLA | 7800 | Clear AC |
| CLE | 7400 | Clear E(overflow bit) |
| CMA | 7200 | Complement AC |
| CME | 7100 | Complement E |
| CIR | 7080 | Circulate right AC and E |
| CIL | 7040 | Circulate left AC and E |
| INC | 7020 | Increment AC |
| SPA | 7010 | Skip next instruction if AC > 0 |
| SNA | 7008 | Skip next instruction if AC < 0 |
| SZA | 7004 | Skip next instruction if AC = 0 |
| SZE | 7002 | Skip next instruction if E = 0 |
| HLT | 7001 | Halt computer |
| INP | F800 | Input character to AC |
| OUT | F400 | Output character from AC |
| SKI | F200 | Skip on input flag |
| SKO | F100 | Skip on output flag |
| ION | F080 | Interrupt On |
| IOF | F040 | Interrupt Off |
**In the table:**
- **AC (Accumulator)**: A register that temporarily stores data during arithmetic or logic operations.
- **E (Carry/Overflow Bit)**: A single-bit register used for carry operations or overflow detection in arithmetic calculations.
### **Example of ADD Instruction Execution**
Assume that memory address **0001** contains the value **5** and the **Accumulator (AC)** currently holds the value **10**. When the **ADD** instruction is executed, the CPU fetches the value from memory, adds it to the contents of the accumulator, and stores the result back in the accumulator.
> AC ← AC + M[0001]
> Result: AC = 10 + 5 = 15
## **Uses of Basic Computer Instructions**
- **Data Manipulation:** Basic computer instructions are used to move and process data within the computer system, including transferring data between memory and the CPU and performing arithmetic and logical operations.
- **Control Flow:** These instructions control the sequence of program execution by enabling conditional branching, looping, and function calls.
- **Input and Output Operations:** Basic instructions allow data to be transferred between the computer system and external devices such as keyboards, displays, printers, and storage devices.
- **Program Execution:** They support program execution by fetching, decoding, and executing instructions and managing the movement of data required by programs.
- **Operating System Support:** Basic computer instructions provide low-level functionality that the operating system uses to implement tasks such as process control, interrupt handling, and resource management.
## **Issues of Basic Computer Instructions**
- **Complexity:** Basic computer instructions can be difficult to understand, especially for beginners, which makes programming more challenging.
- **Limited Functionality:** These instructions support only simple operations. Complex tasks often require writing additional instructions, increasing program length and effort.
- **Compatibility:** Instruction sets may vary across different computer systems. This variation can require programmers to write system-specific code, which is time-consuming and inefficient.
- **Security:** Basic computer instructions can be vulnerable to security issues such as buffer overflows and code injection attacks.
- **Maintenance:** Programs written using basic instructions can be difficult to maintain as systems grow more complex and codebases become larger, requiring significant time and resources.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-basic-computer-instructions/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: Machine Instructions and Addressing Modes

> [!note] Related notes
>
> - [[A simple understanding of Computer]]
> - [[Addressing Modes]]
> - [[Amdahl’s law and its proof]]
> - [[Computer Architecture and Computer Organization]]
> - [[Computer System Level Hierarchy]]
> - [[Difference between CALL and JUMP instructions]]
> - [[Flynn’s taxonomy]]
> - [[General Register based CPU Organization]]
> - [[Generations of computer]]
> - [[Hardware architecture]]
