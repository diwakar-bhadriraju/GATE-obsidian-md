---
title: "Difference between Hardwired and Micro-programmed Control Unit | Set 2"
subject: "Computer Organization and Architecture"
topic: "ALU, Data‐Path and Control Unit"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/difference-between-hardwired-and-micro-programmed-control-unit-set-2/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/ALU, Data‐Path and Control Unit"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/alu-data-path-and-control-unit
---


> [!abstract] Difference between Hardwired and Micro-programmed Control Unit | Set 2
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `ALU, Data‐Path and Control Unit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/difference-between-hardwired-and-micro-programmed-control-unit-set-2/)

---

# Difference between Hardwired and Micro-programmed Control Unit | Set 2

Prerequisite - [Hardwired v/s Micro-programmed Control Unit](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-hardwired-vs-micro-programmed-control-unit/) To execute an instruction, there are two types of control units Hardwired Control unit and Micro-programmed control unit.
1. Hardwired control units are generally faster than microprogrammed designs. In hardwired control, we saw how all the control signals required inside the CPU can be generated using a state counter and a PLA circuit.
2. A microprogrammed control unit is a relatively simple logic circuit that is capable of (1) sequencing through microinstructions and (2) generating control signals to execute each microinstruction.
The control unit’s implementation, whether hardwired or micro-programmed, affects the performance and flexibility of the CPU.
| Hardwired Control Unit | Microprogrammed Control Unit |
| --- | --- |
| Hardwired control unit generates the control signals needed for the processor using logic circuits | Microprogrammed control unit generates the control signals with the help of micro instructions stored in control memory |
| Hardwired control unit is faster when compared to microprogrammed control unit as the required control signals are generated with the help of hardwares | This is slower than the other as micro instructions are used for generating signals here |
| Difficult to modify as the control signals that need to be generated are hard wired | Easy to modify as the modification need to be done only at the instruction level |
| More costlier as everything has to be realized in terms of logic gates | Less costlier than hardwired control as only micro instructions are used for generating control signals |
| It cannot handle complex instructions as the circuit design for it becomes complex | It can handle complex instructions |
| Only limited number of instructions are used due to the hardware implementation | Control signals for many instructions can be generated |
| Used in computer that makes use of Reduced Instruction Set Computers(RISC) | Used in computer that makes use of Complex Instruction Set Computers(CISC) |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/difference-between-hardwired-and-micro-programmed-control-unit-set-2/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: ALU, Data‐Path and Control Unit

> [!note] Related notes
>
> - [[Asynchronous Data Transfer]]
> - [[Control Unit and design]]
> - [[Hardwired v s Micro-programmed Control Unit]]
> - [[Horizontal micro-programmed Vs Vertical micro-programmed control unit]]
> - [[Synchronous Data Transfer]]
> - [[2D and 2.5D Memory organization]]
> - [[A simple understanding of Computer]]
> - [[Addressing Modes]]
> - [[AI, ML & Data Science]]
> - [[Amdahl’s law and its proof]]
