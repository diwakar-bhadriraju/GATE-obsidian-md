---
title: "n-bit Johnson Counter in Digital Logic"
subject: "Digital Logic and Design"
topic: "Sequential Circuit"
source: "https://www.geeksforgeeks.org/digital-logic/n-bit-johnson-counter-in-digital-logic/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Sequential Circuit"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/sequential-circuit
---


> [!abstract] n-bit Johnson Counter in Digital Logic
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Sequential Circuit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/n-bit-johnson-counter-in-digital-logic/)

---

# n-bit Johnson Counter in Digital Logic

JA Johnson counter, also known as a twisted ring or creeping counter, is a synchronous shift register counter where the complemented output of the last flip-flop is fed into the input of the first. It uses **n** flip-flops to generate **2n** unique states, offering better state efficiency than regular ring counters.
- Requires **n** flip-flops to generate **2n** distinct states, making it more efficient than a ring counter.
- Commonly used for applications needing self-decodable outputs and efficient state utilization.
> Total number of used and unused states in n-bit Johnson counter: 
> number of used states=2n 
> number of unused states=2n - 2\*n 
>  
> **Example:** 
> If n=4 
> 4-bit Johnson counter 
>
> Initially, suppose all flip-flops are reset. 
![11](assets/11-2-8fcfd239f0.jpg)
### **Truth Table**
![22](assets/22-7bcb075943.jpg)
where, CP is clock pulse and Q1, Q2, Q3, Q4 are the states. 
> Question: Determine the total number of used and unused states in 4-bit Johnson counter. 
>
> Answer: Total number of used states= 2\*n 
> = 2\*4 
> = 8 
> Total number of unused states= 2n - 2\*n 
> = 24-2\*4 
> = 8 
## **Advantages**
- The Johnson counter has same number of flip flop but it can count twice the number of states the ring counter can count.
- It can be implemented using D and JK flip flop.
- Johnson ring counter is used to count the data in a continuous loop.
- Johnson counter is a self-decoding circuit.
## **Disadvantages**
- Johnson counter doesn't count in a binary sequence.
- In Johnson counter more number of states remain unutilized than the number of states being utilized.
- The number of flip flops needed is one half the number of timing signals.
- It can be constructed for any number of timing sequence.
## **Applications**
- Johnson counter is used as a synchronous decade counter or divider circuit.
- It is used in hardware logic design to create complicated Finite states machine. ex: ASIC and FPGA design.
- The 3 stage Johnson counter is used as a 3 phase square wave generator which produces 1200 phase shift.
- It is used to divide the frequency of the clock signal by varying their feedback.
## Ring Counter vs Johnson Counter
| Parameters | Ring Counter | Johnson Counter |
| --- | --- | --- |
| Configuration | A ring counter employs the carry-in of the last flip-flop into the input of the first flip-flop without any manipulation. | In Johnson counter, the complement of output of the last flip-flop is applied to the input of the first flip-flop. |
| Number of Flip- Flops | 'n' flip-flops are required to count 'n' states. | 'n' flip-flops are required to count '2n' states. |
| Counting Sequence | It counts in a simple binary sequence often having one '1' and the rest '0's in each state. | It counts in a twisted sequence, where the output is a mixture of binary 1s and 0s. |
| Number of States | It can Generate 'n' unique states | It can Generate '2n' unique states |
| Unused states | None, because all the states are utilized | '2n-2n' states are unused |
| Self-Decoding Capability | Its not self-decoding since additional circuitry is needed | Its self-decoding makes it simpler for certain applications |
| Circuit Complexity | Since it does not require inversion feedback, thus the circuit is simple | Due to inversion, the circuit is slightly more complex |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/n-bit-johnson-counter-in-digital-logic/)

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
> - [[Ring Counter]]
