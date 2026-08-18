---
title: "Half Adder and Half Subtractor using NAND NOR gates"
subject: "Digital Logic and Design"
topic: "Combinational Circuit"
source: "https://www.geeksforgeeks.org/digital-logic/half-adder-half-subtractor-using-nand-nor-gates/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Combinational Circuit"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/combinational-circuit
---


> [!abstract] Half Adder and Half Subtractor using NAND NOR gates
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Combinational Circuit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/half-adder-half-subtractor-using-nand-nor-gates/)

---

# Half Adder and Half Subtractor using NAND NOR gates

[Half Adders](https://www.geeksforgeeks.org/digital-logic/half-adder-in-digital-logic/) and [Half Subtractors](https://www.geeksforgeeks.org/digital-logic/half-subtractor-in-digital-logic/) can be implemented using only NAND or NOR gates, as both are universal gates capable of realizing any Boolean function. This implementation is commonly used in digital circuit design when only a single type of logic gate is preferred.
- Demonstrates how universal gates can realize Sum, Carry, Difference, and Borrow outputs.
- Requires more gates than the standard implementation but uses only one gate type.
## Implementation
### **Half Adder using NAND Gates**
A Half Adder can be implemented using five NAND gates. The circuit below generates the Sum (A ⊕ B) and Carry (A · B) outputs using only NAND gates.
![](assets/1-71-cf9d043f3b.png)
### **Half Adder using NOR Gates**
A Half Adder can also be implemented using five NOR gates. The following circuit realizes the Sum and Carry outputs using only NOR gates.
![](assets/2-45-7c81b79cce.png)
### Half Subtractor using NAND Gates
A Half Subtractor can be implemented using five NAND gates to generate the Difference (A ⊕ B) and Borrow (A' · B) outputs.
![](assets/3-52-0a384037fa.png)
### **Half Subtractor using NOR Gates**
A Half Subtractor can also be realized using five NOR gates to generate the Difference and Borrow outputs.![](assets/4-29-44c5340b86.png)
## Advantages
- **Universal Gates:** NAND and NOR gates can implement any Boolean function, including Half Adders and Half Subtractors.
- **Cost-Effective:** Using a single type of gate simplifies manufacturing and reduces implementation cost.
- **Easy Standardization:** Circuits designed with only NAND or NOR gates are easier to design, test, and integrate.
## Disadvantages
- **More Gates Required:** Implementations generally require more gates than the standard XOR, AND, and NOT gate realization.
- **Higher Propagation Delay:** Additional gate levels increase the overall signal propagation delay.
- **Increased Hardware Complexity:** More gates lead to larger circuit size and may increase power consumption.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/half-adder-half-subtractor-using-nand-nor-gates/)

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
