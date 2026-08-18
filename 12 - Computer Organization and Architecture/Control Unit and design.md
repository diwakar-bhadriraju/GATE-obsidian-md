---
title: "Introduction to Control Unit and its Design"
subject: "Computer Organization and Architecture"
topic: "ALU, Data‐Path and Control Unit"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/introduction-of-control-unit-and-its-design/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/ALU, Data‐Path and Control Unit"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/alu-data-path-and-control-unit
---


> [!abstract] Introduction to Control Unit and its Design
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `ALU, Data‐Path and Control Unit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/introduction-of-control-unit-and-its-design/)

---

# Introduction to Control Unit and its Design

The control unit (CU) is a component of the computer’s central processing unit (CPU) that directs the operation of the processor. It fetches instructions from memory, decodes them, and generates control signals to manage the ALU, memory, and I/O devices.
Its role is to coordinate the execution of instructions by controlling the sequence of operations, and its implementation may vary depending on the CPU architecture (such as hardwired or microprogrammed control).
![what is control unit?](assets/controlunit-11b556f5f2.png)
## **Functions of the Control Unit**
- It coordinates the sequence of data movements into, out of, and between a processor's many sub-units.
- It interprets instructions.
- It controls data flow inside the processor.
- It receives external instructions or commands, which it converts to a sequence of control signals.
- It controls many execution units (i.e., [ALU](https://www.geeksforgeeks.org/computer-organization-architecture/introduction-of-alu-and-data-path/), data buffers and [registers](https://www.geeksforgeeks.org/computer-organization-architecture/different-classes-of-cpu-registers/)) contained within a CPU.
- It also handles multiple tasks, such as fetching, decoding, execution handling and storing results.
The control unit of a CPU fetches and executes instructions, playing a critical role in system performance. Its Design ensures smooth operation of various components.
## Types of Control Unit
There are two types of control units:
- Hardwired
- Micro programmable control unit.
### Hardwired Control Unit
In a Hardwired Control Unit, fixed hardware logic generates control signals based on the instruction's opcode. The opcode is decoded, and the decoder activates lines that feed a control signal generator matrix. This matrix, similar to a programmable logic array, combines decoded signals, control states, and external inputs to produce the required execution signals.
![hardwired control unit](assets/hard-3173746750.png)
- Control signals must be generated throughout the instruction execution cycle, not at a single point. Accordingly, the control unit organizes a sequence of states, with some control signals fed back to the next state generator matrix.
- The timing unit (driven by a quartz generator) provides timing signals. When a new instruction arrives, the control unit begins fetching, moves through execution states, and responds to changes in timing, flags, or interrupts by shifting states.
- External signals such as interrupts trigger dedicated states for handling them. Flags and state variables guide the choice of states during execution.
- The final states of the cycle begin fetching the next instruction, and if a stop instruction is encountered, the control unit enters an OS state, waiting for the next command.
## Micro Programmable control unit
In [microprogrammed control units](https://www.geeksforgeeks.org/computer-organization-architecture/applications-of-microprogrammed-control-unit/), subsequent instruction words are fetched into the instruction register in a normal way. However, the operation code of each instruction is not directly decoded to enable immediate control signal generation but it comprises the initial address of a microprogram contained in the control store.
### **Some Important Terms**
1. **Control Word:** A control word is a word whose individual bits represent various control signals.
2. **Micro-routine:** A sequence of control words corresponding to the control sequence of a machine instruction constitutes the micro-routine for that instruction.
3. **Micro-instruction:** Individual control words in this micro-routine are referred to as microinstructions.
4. **Micro-program:** A sequence of micro-instructions is called a micro-program, which is stored in a ROM or RAM called a Control Memory (CM).
5. **Control Store:** the micro-routines for all instructions in the instruction set of a computer are stored in a special memory called the Control Store.
### **Single-Level Control Store**
The opcode from the instruction register points to the address in the control store where the microprogram starts. The first microinstruction is loaded, containing encoded control signals and the address for the next microinstruction. Microinstruction fields are decoded, and the control field determines which [addressing mode](https://www.geeksforgeeks.org/computer-organization-architecture/addressing-modes/) or operation is used.
![With single level control store](assets/single-3bb43f32b4.png)
Conditional addressing applies processor flags to select the next microinstruction. The final microinstruction fetches the next instruction from memory.
### **Two-Level Control Store**
In a two-level control unit, microinstructions point to nano-instructions instead of directly containing control signals. The microinstruction's operation field holds the address of a nano-instruction, which includes the actual encoded control signals. The nano-instruction memory stores all needed control signal combinations for executing the full instruction set, written once and reused across microprograms. ![WIth two level control store](assets/two-2-51f13096bb.png)In this structure, microinstructions are shorter, reducing the total control memory size. Control sequencing is handled by microinstructions, while control signals are generated from nano-instructions, often in simple 1-bit/1-signal encoding without further decoding.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/introduction-of-control-unit-and-its-design/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: ALU, Data‐Path and Control Unit

> [!note] Related notes
>
> - [[Asynchronous Data Transfer]]
> - [[Hardwired v s Micro-programmed Control Unit]]
> - [[Hardwired Vs Micro-programmed Control unit Set 2]]
> - [[Horizontal micro-programmed Vs Vertical micro-programmed control unit]]
> - [[Synchronous Data Transfer]]
> - [[2D and 2.5D Memory organization]]
> - [[A simple understanding of Computer]]
> - [[Addressing Modes]]
> - [[AI, ML & Data Science]]
> - [[Amdahl’s law and its proof]]
