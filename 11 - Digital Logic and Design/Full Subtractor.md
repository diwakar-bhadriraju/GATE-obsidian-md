---
title: "Full Subtractor in Digital Logic"
subject: "Digital Logic and Design"
topic: "Combinational Circuit"
source: "https://www.geeksforgeeks.org/digital-logic/full-subtractor-in-digital-logic/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Combinational Circuit"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/combinational-circuit
---


> [!abstract] Full Subtractor in Digital Logic
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Combinational Circuit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/full-subtractor-in-digital-logic/)

---

# Full Subtractor in Digital Logic

A **Full Subtractor** is a combinational circuit used to perform binary subtraction. It has three inputs:
- **A** (Minuend)
- **B** (Subtrahend)
- **B-IN** (Borrow-in from the previous stage)
It produces two outputs:
- **Difference (D):** The result of the subtraction.
- **Borrow-out (B-OUT):** Indicates if a borrow is needed for the next stage.
The full subtractor is essential because a [**half-subtractor**](https://www.geeksforgeeks.org/digital-logic/half-subtractor-in-digital-logic/) can only subtract the least significant bit (LSB) of binary numbers. However, if a borrow is generated during the subtraction of the LSBs, it will affect the subtraction in the next stages. A **full subtractor** handles this situation by considering the borrow from the previous stage, ensuring accurate subtraction even when a borrow is present.
The full subtractor is used to subtract binary numbers with borrow handling, making it suitable for multi-bit subtraction in digital circuits like **Arithmetic Logic Units (ALUs)**. 
![Full-Subtractor-in-Digital-Logic](assets/Full-Subtractor-in-Digital-Logic-68ecb002b7.webp)
Full Subtractor in Digital Logic
## **Truth Table of Full Subtractor**
| Input | | | Output | |
| --- | --- | --- | --- | --- |
| **A** | **B** | **B**in** | **D** | **B**out** |
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 1 |
| 0 | 1 | 0 | 1 | 1 |
| 0 | 1 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 0 |
| 1 | 1 | 0 | 0 | 0 |
| 1 | 1 | 1 | 1 | 1 |
## K-Map for Full Subtractor
From above table we can draw the K-Map as shown for "difference" and "borrow".
![Full-Subtractor-in-Digital-Logic-1](assets/Full-Subtractor-in-Digital-Logic-1-23e4f824a0.webp)
K-Map for Difference
**Logical expression for difference**
The basic expression is:
> D = A'B'Bin + A'BBin' + AB'Bin' + ABBin
Factoring common terms:
> D = Bin(A'B' + AB) + Bin'(AB' + A'B)
Recognizing XOR and XNOR properties:
> A'B' + AB = A XNOR B
> AB' + A'B = A XOR B
Substituting these values:
> D = Bin(A XNOR B) + Bin' (A XOR B)
Using XNOR identity:
> D = Bin ⊕ (A ⊕ B)
Thus, the final simplified expression for the difference in a full subtractor is:
**D = (A ⊕ B) ⊕ Bin**
![Full-Subtractor-in-Digital-Logic-2](assets/Full-Subtractor-in-Digital-Logic-2-75b437dca8.webp)
K-Map for Borrow
**Logical expression for borrow**
The **borrow (Bout) output** is derived as follows:
The basic expression:
> Bout = A'B'Bin + A'BBin' + A'BBin + ABBin
Factoring common terms:
> Bout = A'Bin(B + B') + A'B(Bin + Bin') + BBin(A + A')
Simplifying:
> Bout = A'Bin + A'B + BBin
Alternatively, using another approach:
> Bout = A'B'Bin + A'BBin' + A'BBin + ABBin
Factoring common terms:
> Bout = Bin(AB + A'B') + A'B(Bin + Bin')
Using XOR and XNOR properties:
> AB + A'B' = A XNOR B
Substituting these values:
> Bout = Bin(A XNOR B) + A'B
Using XNOR identity:
> Bout = Bin (A XOR B)' + A'B
Thus, the final simplified expression for borrow in a full subtractor is:
## **Logic Circuit for Full Subtractor**
![Full-Subtractor-in-Digital-Logic-3](assets/Full-Subtractor-in-Digital-Logic-3-ac9808dbcb.webp)
Logic Circuit for Full Subtractor
## **Implementation** of Full Subtractor using Half Subtractors
2 Half Subtractors and an OR gate is required to implement a Full Subtractor.
![Full-Subtractor-in-Digital-Logic-4](assets/Full-Subtractor-in-Digital-Logic-4-99bb17d7d1.webp)
Implementation of Full Subtractors using Half Subtractor
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/full-subtractor-in-digital-logic/)

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
> - [[Grey Code]]
