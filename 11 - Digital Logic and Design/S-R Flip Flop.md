---
title: "SR Flip Flop"
subject: "Digital Logic and Design"
topic: "Sequential Circuit"
source: "https://www.geeksforgeeks.org/digital-logic/sr-flip-flop/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Sequential Circuit"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/sequential-circuit
---


> [!abstract] SR Flip Flop
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Sequential Circuit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/sr-flip-flop/)

---

# SR Flip Flop

## **What is SR Flip Flop?**
It is a [Flip Flop](https://www.geeksforgeeks.org/digital-logic/flip-flop-types-their-conversion-and-applications/) with two inputs, one is S and the other is R. **S** here stands for Set and **R** here stands for Reset. Set basically indicates set the flip flop which means output 1 and reset indicates resetting the flip flop which means output 0. Here, a clock pulse is supplied to operate this flip-flop, hence it is a clocked flip-flop.
### What is Flip Flop?
Flip-Flop is a term that comes under digital electronics, and it is an [electronic component](https://www.geeksforgeeks.org/electrical-engineering/electronic-components/) that is used to store one single bit of information.
![Diagrammatic Representation of Flip Flop](assets/sr1-3b09b5812b.png)
Diagrammatic Representation of Flip Flop
Since Flip Flop is a [sequential circuit](https://www.geeksforgeeks.org/digital-logic/introduction-of-sequential-circuits/) so its input is based upon two parameters, one is the **current input** and other is the **output from previous state**. It has two outputs, both are **complement** of each other. It may be in one of two stable states, either 0 or 1.
**Prerequisite**: [Introduction of Sequential Circuits](https://www.geeksforgeeks.org/digital-logic/introduction-of-sequential-circuits/)
## **Construction of SR Flip Flop**
We can construct SR flip flop with two ways, one is with **2** [**NOR Gates**](https://www.geeksforgeeks.org/digital-logic/nor-gate/) + **2** [**AND Gates**](https://www.geeksforgeeks.org/digital-logic/and-gate/) and other is with **4** [**NAND Gates**](https://www.geeksforgeeks.org/digital-logic/what-is-nand-gate/).
![Construction of SR Flip Flop](assets/sr2-8ba3cb3944.png)
Ways to Construct SR Flip Flop
SR Flip Flop Construction using **2 NOR + 2 AND Gates**:
![SR Filp Flop ](assets/sr3-f43d5d8ae6.png)
SR Flip Fop using two NOR and two AND Gates
SR Flip Flop Construction using **4 NAND Gates**
![SR Flip Flop using NAND gate](assets/Untitled-Diagram---2024-05-13T153118202-e13c8116a3.webp)
SR Flip Flop using NAND Gate
## **Basic Block Diagram of SR Flip Flop**
The basic block diagram contains **S** and **R** inputs, and between them is clock pulse, **Q** and **Q'** is the complemented outputs.
![SR Flip Flop basic Block diagram](assets/sr5-3bceb95201.png)
SR Flip Flop basic Block diagram
## Working of SR Flip Flop
- **Case 1**  : Let's say,  **S=0**  and  **R=0**  , then output of both AND gates will be 0 and the value of Q and Q' will be same as their previous value, i.e, Hold state.
- **Case 2**  : Let's say,  **S=0 and R=1**  , then output of both AND gates will be 1 and 0, correspondingly the value of Q will be 0 as one of input is 1 and it is a NOR gate so it will ultimately gives 0, hence Q gets 0 value, similarly Q' will be 1.
- **Case 3**  : Let's say,  **S=1 and R=0**  , then output of both AND gates will be 0 and 1, correspondingly the value of Q' will be 0 as one of input to NOR gate is 1, so output will be 0 ultimately and this 0 value will go as input to upper NOR gate, and hence Q will become 1.
- **Case 4**  : Let's say,  **S=1 and R=1**  , then output of both AND gates will be 1 and 1 which is invalid, as the outputs should be complement of each other.
## Truth Table of SR Flip Flop
Given Below is the [Truth Table](https://www.geeksforgeeks.org/electronics-engineering/truth-table/) of SR Flip Flop
![Truth Table of SR Flip Flop](assets/sr6-36a2bafa6f.png)
Here, **S** is the Set input, **R** is the reset input,**Qn+1** is the next state and **State** tells in which state it enters
## **Function**Table of SR Flip Flop
Given Below is the Function Table of SR Flip Flop
![Function Table of SR Flip Flop](assets/sr8-4b1e065cad.png)
Here, **S** is the Set input, **R** is the reset input, **Qn** is the current state input and **Qn+1** is the next state outputs.
## **Characteristic Equation**
- The characteristic equation tells us about what will be the next state of flip flop in terms of present state.
- In order to get the characteristic equation, [K-Map](https://www.geeksforgeeks.org/digital-logic/introduction-of-k-map-karnaugh-map/) is constructed which will be shown as below:
![Characteristic Equation](assets/sr10-eeb1a778c8.png)
- If we solve the above K-Map then the characteristic equation will be  **Qn+1 = S + QnR’**
### Excitation Table
- Excitation Table basically tells about the excitation which is required by flip flop to go from current state to next state.
![Excitation Table](assets/sr7-592818b555.png)
- Here,  **Qn**  is the current state,  **Qn+1**  is the next state outputs and  **S**  ,  **R**  are the set and reset inputs respectively.
## Applications of SR Flip Flop
There are numerous applications of SR Flip Flop in Digital System, which are listed below:
- **Register**  : SR Flip Flop used to create register. Designer can create any size of register by combining SR Flip Flops.
- **Counters**  : SR Flip Flops used in [counters](https://www.geeksforgeeks.org/digital-logic/counters-in-digital-logic/) . Counters counts the number of events that occurs in a digital system.
- **Memory**  : SR Flip Flops used to create [memory](https://www.geeksforgeeks.org/computer-organization-architecture/introduction-to-memory-and-memory-units/) which are used to store data, when the power is turned off.
- **Synchronous System**  : SR Flip Flop are used in synchronous system which are used to synchronize the operation of different component.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/sr-flip-flop/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Sequential Circuit

> [!note] Related notes
>
> - [[Amortized analysis for increment in counter]]
> - [[Asynchronous Sequential Circuits]]
> - [[Counters]]
> - [[D Flipflop]]
> - [[Design 101 sequence detector]]
> - [[Design counter for given sequence]]
> - [[Flip-flop types and their Conversion]]
> - [[Introduction of Sequential Circuits]]
> - [[Master Slave JK Flip Flop]]
> - [[n-bit Johnson Counter]]
