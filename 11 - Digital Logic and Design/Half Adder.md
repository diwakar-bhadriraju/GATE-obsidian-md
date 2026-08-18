---
title: "Half Adder"
subject: "Digital Logic and Design"
topic: "Combinational Circuit"
source: "https://www.geeksforgeeks.org/digital-logic/half-adder-in-digital-logic/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Combinational Circuit"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/combinational-circuit
---


> [!abstract] Half Adder
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Combinational Circuit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/half-adder-in-digital-logic/)

---

# Half Adder

A half adder is a basic combinational circuit that adds two single-bit binary inputs (A and B) to produce a SUM using an XOR gate and a CARRY using an AND gate, without considering any carry-in from a previous stage.
- Performs binary addition of two single-bit inputs, generating a SUM (A ⊕ B) and CARRY (A · B).
- Cannot handle carry-in from a previous stage, making it suitable only for the first stage of multi-bit addition.
![halfadder](assets/Half_Adder-d4c0f4639a.jpg)
## Truth Table of Half Adder
| A | B | Sum | Carry |
| --- | --- | --- | --- |
| 0 | 0 | 0 | 0 |
| 0 | 1 | 1 | 0 |
| 1 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 |
## Logical Expression of Half Adder
The Half Adder performs two operations, Sum and Carry. Therefore, two K-maps are used to derive their Boolean expressions.
### Sum
![](assets/xorkmap-3590d0ed30.jpg)
Sum = A XOR B
### Carry
![](assets/Inkedandkmap1-200x155-3620b0fe47.jpg)
Carry = A AND B
## Advantages
- **Simple Design:** A half adder has a simple circuit design that uses only two logic gates (XOR and AND), making it easy to implement and understand.
- **Fast Operation:** Since it contains only a few logic gates, it produces the Sum and Carry outputs with very little delay.
- **Low Hardware Requirement:** It requires fewer hardware components, reducing circuit complexity and implementation cost.
## Disadvantages
- **No Carry Input:** A half adder cannot accept a carry input from a previous stage, limiting its use in larger arithmetic operations.
- **Limited Functionality:** It can add only two single-bit binary numbers and cannot perform multi-bit addition by itself.
- **Requires Full Adders:** For multi-bit binary addition, half adders must be combined with full adders to handle carry propagation.
## Applications
- **Binary Addition:** It is used to add two single-bit binary numbers and generate the corresponding Sum and Carry outputs.
- **Building Block for Full Adders:** Half adders are commonly used as the basic building blocks in the design of full adders.
- **Digital Arithmetic Circuits:** They are used in arithmetic units, calculators, processors, and other digital systems where simple binary addition is required.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/half-adder-in-digital-logic/)

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
