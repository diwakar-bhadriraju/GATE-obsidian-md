---
title: "Half Subtractor in Digital Logic"
subject: "Digital Logic and Design"
topic: "Combinational Circuit"
source: "https://www.geeksforgeeks.org/digital-logic/half-subtractor-in-digital-logic/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Combinational Circuit"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/combinational-circuit
---


> [!abstract] Half Subtractor in Digital Logic
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Combinational Circuit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/half-subtractor-in-digital-logic/)

---

# Half Subtractor in Digital Logic

A Half Subtractor is a combinational logic circuit that performs the subtraction of two single-bit binary numbers. It has two inputs (A and B) and produces two outputs: Difference and Borrow.
- Can be implemented using a combination of XOR, AND, and NOT logic gates.
- Acts as the basic building block for designing full subtractors and multi-bit subtraction circuits.
![](assets/Half-Subtractor-in-Digital-Logic-b3c7c1488a.png)
## **Truth Table of Half Subtractor**
| A | B | Diff | Borrow |
| --- | --- | --- | --- |
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 1 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 0 |
## Logical Expression of Half Subtractor
The Difference and Borrow outputs are obtained using separate K-maps.
### **For Difference**
![1](assets/1-f3fe78e76e.webp)
K-Map Diff
Difference = A'B + AB' = A ⊕ B
### **For Borrow**
![2](assets/2-f9a7716dbd.webp)
K-Map for Borrow
Borrow = A'B
## Advantages
- **Simple Design:** Half subtractors use only a few logic gates, making them easy to design and implement.
- **Low Hardware Cost:** Fewer logic gates reduce circuit complexity, cost, and power consumption.
- **Foundation for Larger Circuits:** They serve as the basic building block for full subtractors and multi-bit subtraction circuits.
## Disadvantages
- **Limited Functionality:** It can subtract only two single-bit binary numbers.
- **Not Suitable for Multi-bit Subtraction:** Multi-bit subtraction requires full subtractors or additional circuitry.
- **Higher Delay in Large Circuits:** Cascading multiple half subtractors increases propagation delay and reduces efficiency.
## **Application**
- **Arithmetic Circuits:** Forms the basic building block of full subtractors and multi-bit subtraction circuits.
- **Digital Computers:** Performs binary subtraction operations in arithmetic logic units (ALUs).
- **Calculators and Digital Systems:** Helps carry out subtraction operations in calculators, processors, and other digital devices.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/half-subtractor-in-digital-logic/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Combinational Circuit

> [!note] Related notes
>
> - [[BCD Adder]]
> - [[BCD to 7 Segment Decoder]]
> - [[Binary Decoder]]
> - [[Carry Look-Ahead Adder]]
> - [[Combinational circuits using Decoder]]
> - [[De-MUX]]
> - [[Encoder]]
> - [[Encoders and Decoders]]
> - [[Full Adder]]
> - [[Full Subtractor]]
