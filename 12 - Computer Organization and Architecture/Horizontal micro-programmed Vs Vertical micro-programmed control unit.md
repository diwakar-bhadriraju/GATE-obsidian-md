---
title: "Difference between Horizontal and Vertical micro-programmed Control Unit"
subject: "Computer Organization and Architecture"
topic: "ALU, Data‐Path and Control Unit"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/difference-between-horizontal-and-vertical-micro-programmed-control-unit/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/ALU, Data‐Path and Control Unit"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/alu-data-path-and-control-unit
---


> [!abstract] Difference between Horizontal and Vertical micro-programmed Control Unit
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `ALU, Data‐Path and Control Unit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/difference-between-horizontal-and-vertical-micro-programmed-control-unit/)

---

# Difference between Horizontal and Vertical micro-programmed Control Unit

The Control Unit, in computer architecture, plays a fundamental role in the management of instruction execution by regulating the use of the processor, memory, and I/O devices. There exist mainly two methods for designing micro-programmed control units. These comprise the Horizontal and Vertical Micro programmed Control Units. The two methods are represented, encoded, and executed differently concerning control signals in attempts to control the micro-operations guiding the behavior of the CPU.
The **control unit (CU)** is the engine that runs the entire functions of a computer with the help of control signals in the proper sequence. In the **micro-programmed** control unit approach, the control signals that are associated with the operations are stored in special memory units. It is convenient to think of sets of control signals that cause specific micro-operations to occur as being "micro-instructions". The sequences of micro-instructions could be stored in an internal "**control**" memory. 
The micro-programmed control unit can be classified into two types based on the type of Control Word stored in the [Control Memory](https://www.geeksforgeeks.org/computer-organization-architecture/introduction-of-control-unit-and-its-design/), viz., Horizontal micro-programmed control unit and Vertical micro-programmed control unit. 
## What is Horizontal Micro-Programmed Control Unit?
In this design, each control signal in the control word is explicitly specified. It employs a wide control word in which every bit determines any particular [control signal](https://www.geeksforgeeks.org/computer-organization-architecture/introduction-of-control-unit-and-its-design/) or micro-operation. In the **Horizontal micro-programmed** control unit, the control signals are represented in the decoded binary format, i.e., 1 bit/CS. Here 'n' control signals require n bit encoding.
### Features of Horizontal Micro-Programmed Control Unit
- **Control Signals are Explicit:**  In horizontal control unit, every control signal is specified by a separate bit in the control word. Which means, there is direct control over all the microoperations and thus makes for a more flexible system and a faster system.
- **Wide Control Word**: In this type of micro-programming, signals are specified individually; thus, a wide control word is needed by the horizontal micro-programming. This results in longer instruction words, but it provides for control over individual operations.
- **Sequential Execution:** More than one control signal can be excited simultaneously, due to which more parallel operations can be performed in this system and hence it results in higher efficiency in executing instructions.
### Advantages of Horizontal Micro-Programmed Control Unit
- It leads to faster implementation of the instructions since the control process is more parallel.
- Control signals for every control operation are explicitly specified hence it is easier to control complex micro-operations.
### Drawbacks of Horizontal Micro-Programmed Control Unit
- High Memory Requirement: More memory is needed to store the microprograms since the size of the word is large.
- Complex Design: More lines in the control lead to complexity both while designing and while debugging.
## What is Vertical Micro-Programmed Control Unit?
Vertical Micro-programmed Control Unit uses encoded form of control signals. Instead of one bit per control signal, multiple signals are encoded into a shorter control word. [Decoders](https://www.geeksforgeeks.org/digital-logic/binary-decoder-in-digital-logic/) expand the encoded signals into real control signals. In a **Vertical micro-programmed** control unit, the control signals are represented in the encoded binary format. Here 'n' control signals require log2n bit [encoding](https://www.geeksforgeeks.org/machine-learning/feature-encoding-techniques-machine-learning/).
### Features of Vertical Micro-Programmed Control Unit
- **Encoded Control Signals:** The control signals are compressed into fewer bits, and decoders are used to produce actual control signals. This leads to control words that are shorter in length.
- **In narrow control word:** The length of control word is vertical micro-programming shorter as compared to horizontal since it uses fewer bits due to the encoding of control signals. Since only few control signals are activated at any given time, generally, vertical micro-programming results in operations as being more sequential.
### **Advantages** of Vertical Micro-Programmed Control Unit
- **Less memory is needed:** Shorter control word results in lesser memory to be used for storing of microprograms.
- **Easier designing:** Lesser number of control signals results in an easier and manageable system.
### Disadvantages of Vertical Micro-Programmed Control Unit
- **The Speed is Low.** Because of the fact that control signals have been encoded and then decoded, it takes more time than that of the horizontal micro-programming.
- **Less Flexible:** The control signals have been encoded; hence parallelism is limited and the flexibility of control over several micro-operations simultaneously gets reduced.
**Example**
Consider a hypothetical Control Unit that supports 4 k words. The Hardware contains 64 control signals and 16 Flags. What is the size of control word used in bits and control memory in a byte using: 
a) Horizontal Programming 
b) Vertical programming
**Solution:**
![](assets/hori-1-316bf5e5e9.png)
```
a)For Horizontal 64 bits for 64 signals % 16 bits for flagsControl Word Size = 64 + 16 = 80 bitsControl Memory = 4 kW = ( (4* 80) / 8 ) = 40 kByteb)For Vertical6 bits for 64 signals i.e log2644 bits for 16 flags i.e log21612 bits for 4K words i.e log2(4*1024)Control Word Size = 4 + 6 + 12 = 22 bitsControl Memory = 4 kW = ( (4* 22) / 8 ) = 11 kByte
```
### Difference Between Horizontal and Vertical Micro-Programmed Control Unit
| S. No | Horizontal µ-Programmed CU | Vertical µ-Programmed CU |
| --- | --- | --- |
| 1. | It supports longer control word. | It supports shorter control word. |
| 2. | It allows a higher degree of parallelism. If degree is n, then n Control Signals are enabled at a time. | It allows a low degree of parallelism i.e., the degree of parallelism is either 0 or 1. |
| 3. | No additional hardware is required. | Additional hardware in the form of decoders is required to generate control signals. |
| 4. | It is faster than a Vertical micro-programmed control unit. | it is slower than a Horizontal micro-programmed control unit. |
| 5. | It is more flexible than a vertical micro-programmed control unit. | It is less flexible than horizontal but more flexible than that of a hardwired control unit. |
| 6. | A horizontal micro-programmed control unit uses horizontal micro-instruction, where every bit in the control field attaches to a control line. | A vertical micro-programmed control unit uses vertical micro-instruction, where a code is used for each action to be performed and the decoder translates this code into individual control signals. |
| 7. | The horizontal micro-programmed control unit makes less use of [ROM](https://www.geeksforgeeks.org/computer-organization-architecture/read-only-memory-rom/) encoding than the vertical micro-programmed control unit. | The vertical micro-programmed control unit makes more use of ROM encoding to reduce the length of the control word. |
## Conclusion
Horizontal and vertical micro-programmed control units have their pros and cons. Flexibility in association with the speed favors horizontal micro-programming more than vertical, but this is very memory-intensive and highly complex. Actually, the opposite holds true: the control signals in vertical micro-programming are encoded, which makes them slower in relation but in actual fact requires fewer memories and is less complex.
It mainly depends on the specific system requirements being designed for selecting either of the two. If speed and flexibility are critical, then horizontal micro-programming is more suitable. If memory space and simplicity are of a premium, vertical micro-programming is the better choice.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/difference-between-horizontal-and-vertical-micro-programmed-control-unit/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: ALU, Data‐Path and Control Unit

> [!note] Related notes
>
> - [[Asynchronous Data Transfer]]
> - [[Control Unit and design]]
> - [[Hardwired v s Micro-programmed Control Unit]]
> - [[Hardwired Vs Micro-programmed Control unit Set 2]]
> - [[Synchronous Data Transfer]]
> - [[2D and 2.5D Memory organization]]
> - [[A simple understanding of Computer]]
> - [[Addressing Modes]]
> - [[AI, ML & Data Science]]
> - [[Amdahl’s law and its proof]]
