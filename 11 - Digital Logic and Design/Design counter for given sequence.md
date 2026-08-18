---
title: "Design counter for given sequence"
subject: "Digital Logic and Design"
topic: "Sequential Circuit"
source: "https://www.geeksforgeeks.org/digital-logic/design-counter-given-sequence/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Sequential Circuit"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/sequential-circuit
---


> [!abstract] Design counter for given sequence
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Sequential Circuit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/design-counter-given-sequence/)

---

# Design counter for given sequence

Counter is a sequential circuit implemented via flip flops. They are used to count the number of clock signals or pulse. A mod n counter will count from 0 to n-1.
Counters can be [synchronous or asynchronous](https://www.geeksforgeeks.org/digital-logic/differences-between-synchronous-and-asynchronous-counter/). In synchronous counter, a single common clock is used for all the [flip flops.](https://www.geeksforgeeks.org/digital-logic/flip-flop-types-their-conversion-and-applications/) Whereas in [asynchronous counter](https://www.geeksforgeeks.org/digital-logic/asynchronous-down-counter/), only a clock is given as input for first flip flop. For an intermediate or final flip flops, its clock pulse will be the output of previous flip flop.
**Problem -** Design synchronous counter for sequence: 0 → 1 → 3 → 4 → 5 → 7 → 0, using T flip-flop. **Explanation -** For given sequence, state transition diagram as following below:
![cs](assets/cs-c91fac400c.webp)
**State Transition Table Logic**
| Present State | Next State |
| --- | --- |
| 0 | 1 |
| 1 | 3 |
| 3 | 4 |
| 4 | 5 |
| 5 | 7 |
| 7 | 0 |
State transition table for given sequence
| Present State | | | Next State | | |
| --- | --- | --- | --- | --- | --- |
| Q3 | Q2 | Q1 | Q3(t+1) | Q2(t+1) | Q1(t+1) |
| 0 | 0 | 0 | 0 | 0 | 1 |
| 0 | 0 | 1 | 0 | 1 | 1 |
| 0 | 1 | 1 | 1 | 0 | 0 |
| 1 | 0 | 0 | 1 | 0 | 1 |
| 1 | 0 | 1 | 1 | 1 | 1 |
| 1 | 1 | 1 | 0 | 0 | 0 |
**T flip-flop -** If value of Q changes either from 0 to 1 or from 1 to 0 then input for T flip-flop is 1 else input value is 0.
| Qt | Qt+1 | **T** |
| --- | --- | --- |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |
Draw input table of all T flip-flops by using the excitation table of T flip-flop. As nature of T flip-flop is toggle in nature. Here, Q3 as Most significant bit and Q1 as least significant bit.
| Input table of Flip-Flops | | | |
| --- | --- | --- | --- |
| T3 | T2 | T1 |  |
| 0 | 0 | 1 |  |
| 0 | 1 | 0 |  |
| 1 | 1 | 1 |  |
| 0 | 0 | 1 |  |
| 0 | 1 | 0 |  |
| 1 | 1 | 1 |  |
Find value of T3, T2, T1 in terms of Q3, Q2, Q1 using K-Map (Karnaugh Map): ![](assets/DLD1-5ef5478408.png) Therefore,
```
T3 = Q2
```
![](assets/DLD2-7c95ef4c5d.png) Therefore,
```
T2 = Q1
```
![Untitled-Diagram-(1)](assets/Untitled-Diagram--1--52287880a1.webp)
K map
Therefore,
```
T1 = Q2+Q1'
```
Now, you can design required circuit using expressions of K-maps: ![66666](assets/img39-a37374b415.png)
## Advantages of Counters
- Counters can be use for measuring time. E.g. Elapsed time, Response time, etc.
- They can be used in real time system
- They are easy to implement and cost effective
## Disadvantages of Counters
1. The hazards and delay in flip-flop can create error
2. Different digital circuit are to be realized for different value of n and type of flip flop used in n-mod counter
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/design-counter-given-sequence/)

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
> - [[Flip-flop types and their Conversion]]
> - [[Introduction of Sequential Circuits]]
> - [[Master Slave JK Flip Flop]]
> - [[n-bit Johnson Counter]]
> - [[Ring Counter]]
