---
title: "Computer Organization | Problem Solving on Instruction Format"
subject: "Computer Organization and Architecture"
topic: "Machine Instructions and Addressing Modes"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-problem-solving-instruction-format/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Machine Instructions and Addressing Modes"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/machine-instructions-and-addressing-modes
---


> [!abstract] Computer Organization | Problem Solving on Instruction Format
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Machine Instructions and Addressing Modes`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-problem-solving-instruction-format/)

---

# Computer Organization | Problem Solving on Instruction Format

Prerequisite - [Basic Computer Instructions](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-basic-computer-instructions/), [Instruction Formats](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-instruction-formats-zero-one-two-three-address-instruction/)
### Problem statement:
Consider a computer architecture where instructions are 16 bits long. The first 6 bits of the instruction are reserved for the opcode, and the remaining 10 bits are used for the operands. There are three addressing modes: immediate, direct, and register. For immediate addressing, the operand is included in the instruction itself. For direct addressing, the operand is a memory address. For register addressing, the operand is a register number.
Write the instruction format for each of the addressing modes.
### Solution:
The instruction format for each addressing mode is as follows:
1. Immediate addressing:
   | Opcode (6 bits) | Operand (10 bits) |
2. Direct addressing:
   | Opcode (6 bits) | Memory address (10 bits) |
3. Register addressing:
   | Opcode (6 bits) | Register number (5 bits) | Not used (1 bit) |
In immediate addressing, the operand is included in the instruction itself, so the 10 bits are used to represent the operand value.
In direct addressing, the 10 bits are used to represent the memory address where the operand value is stored.
In register addressing, the 5 bits are used to represent the register number where the operand value is stored. The remaining 1 bit is not used.
This instruction format can be used to implement a wide range of instructions and operations in a computer system.
An instruction format defines the different component of an instruction. The main components of an instruction are opcode (which instruction to be executed) and operands (data on which instruction to be executed). Here are the different terms related to instruction format:
- **Instruction set size -** It tells the total number of instructions defined in the processor.
- **Opcode size -** It is the number of bits occupied by the opcode which is calculated by taking log of instruction set size.
- **Operand size -** It is the number of bits occupied by the operand.
- **Instruction size -** It is calculated as sum of bits occupied by opcode and operands.
In this article, we will discuss different types of problems based on instruction format which are asked in GATE. For details about different types of instruction formats, you can refer: [Instruction Formats](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-instruction-formats-zero-one-two-three-address-instruction/) 
**Type 1:** Given instruction set size and operands size and their count, find the size of the instruction. 
In this type of questions, you will be given the size of instruction set, number of operands and their size, you have to find out the size of the instruction. 
**Que-1.** Consider a processor with 64 registers and an instruction set of size twelve. Each instruction has five distinct fields, namely, opcode, two source register identifiers, one destination register identifier, and a twelve-bit immediate value. Each instruction must be stored in memory in a byte-aligned fashion. If a program has 100 instructions, the amount of memory (in bytes) consumed by the program text is \_\_\_\_\_\_\_\_\_\_\_\_. (GATE 2016) 
(A) 100 
(B) 200 
(C) 400 
(D) 500 
**Solution:** It can be approached as: 
- The instruction consists of opcode and operands. Given the instruction set of size 12, 4 bits are required for opcode (2^4 = 16).
- As there are total 64 registers, 6 bits are required for identifying a register.
- As the instruction contains 3 registers (2 source + 1 designation), 3 \* 6 = 18 bit are required for register identifiers.
- 12 bits are required for immediate value as given.
- Total bits for an instruction = 4 + 18 + 12 = 34 bits
- The instructions are required to be stored in a byte-aligned fashion. The nearest byte boundary after 34 bits is at 40 bits (5 bytes).
- Hence, for 100 instructions, the memory required is 5 \* 100 = 500 bytes, and the correct option is (D).
**Type 2:** Given instruction size, opcode size and size of some operands, find the size and maximum value of remaining operands. 
In this type of questions, you will be given the size of instruction, size of opcode, number of operands and size of some operands, you have to find out the size or maximum value of remaining operands. 
**Que-2.** A processor has 40 distinct instructions and 24 general purpose registers. A 32-bit instruction word has an opcode, two registers operands and an immediate operand. The number of bits available for the immediate operand field is\_\_\_\_\_\_\_. (GATE CS 2016) 
**Solution:** It can be approached as: 
- As the processor has 40 instructions, number of bits for opcode = 6 (2^6 = 64)
- As the processor has 24 register, number of bits for one register = 5 (2^5 = 32)
- Total bits occupied by 2 registers and opcode = 6 + 5 + 5 =16.
- As instruction size given is 32 bits, remaining bit left for operand = 32-16 = 16 bits.
**Que-3.** A machine has a 32-bit architecture, with 1-word long instructions. It has 64 registers, each of which is 32 bits long. It needs to support 45 instructions, which have an immediate operand in addition to two register operands. Assuming that the immediate operand is an unsigned integer, the maximum value of the immediate operand is \_\_\_\_\_\_\_\_\_\_\_. (GATE CS 2014) 
**Solution:** It can be approached as: 
- As machine has 32-bit architecture, therefore, 1 word = 32 bits = instruction size
- As the processor has 64 register, number of bits for one register = 6 (2^6 = 64)
- As the processor has 45 instructions, number of bits for opcode = 6 (2^6 = 64)
- Total bits occupied by 2 registers and opcode = 6 + 6 + 6 =18.
- As instruction size given is 32 bits, remaining bit left for immediate operand = 32-18 = 14 bits.
- Maximum unsigned value using 14 bits = 2^14 – 1 = 16383 which is the answer.
**Type 3:** Instruction format with different categories of instruction 
In this type of questions, you will be given different categories of instructions. You have to find maximum possible instructions of a given type. 
**Que-4.** A processor has 16 integer registers (R0, R1, … , R15) and 64 floating point registers (F0, F1, … , F63). It uses a 2 byte instruction format. There are four categories of instructions: Type-1, Type-2, Type-3, and Type 4. Type-1 category consists of four instructions, each with 3 integer register operands (3Rs). Type-2 category consists of eight instructions, each with 2 floating point register operands (2Fs). Type-3 category consists of fourteen instructions, each with one integer register operand and one floating point register operand (1R+1F). Type-4 category consists of N instructions, each with a floating point register operand (1F). 
The maximum value of N is \_\_\_\_\_\_\_\_. (GATE-CS-2018) 
**Solution:** It can be approached as: 
- As machine has 2 byte = 16 bits instruction format, therefore, possible encodings = 2^16.
- As the processor has 16 integer register, number of bits for one integer register = 4 (2^4 = 16)
- As the processor has 64 floating point register, number of bits for one floating point register = 6 (2^6 = 64).
- For type-1 category having 4 instructions each having 3 integer register operands (4\*3 = 12 bits) will consume 4 \* 2^12 = 2^14 encodings.
- For type-2 category having 8 instructions each having 2 floating point register operands (2\*6 = 12 bits) will consume 8 \* 2^12 = 2^15 encodings.
- For type-3 category having 14 instructions each having 1 integer register and 1 floating point register operands (4 + 6 = 10 bits) will consume 14 \* 2^10 = 14336 encodings.
- For type-4 category instructions, number of encodings left = 2^16 – 2^14 – 2^15 – 14336 = 2048.
- For type-4 category having N instructions each having 1 floating point register operand (6 bits) will consume N\* 2^6 = 2048 (calculated from previous step). Therefore, N = 32.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-problem-solving-instruction-format/)

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
