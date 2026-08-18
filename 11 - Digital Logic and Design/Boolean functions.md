---
title: "Boolean Functions"
subject: "Digital Logic and Design"
topic: "Introduction of Boolean Algebra and Logic Gates"
source: "https://www.geeksforgeeks.org/digital-logic/boolean-functions/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Introduction of Boolean Algebra and Logic Gates"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/introduction-of-boolean-algebra-and-logic-gates
---


> [!abstract] Boolean Functions
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Introduction of Boolean Algebra and Logic Gates`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/boolean-functions/)

---

# Boolean Functions

Boolean Algebra was given by George Boole. It is a set of rules used to simplify a given logical expression without changing its functionality. It is mainly used when several variables present are less. The algebraic expression used in Boolean Algebra is known as Boolean Expression and it is used to describe Boolean Function. The Boolean expression generally consists of value 0 or 1, binary variables, and logical operation.
## Truth Table Formation
The truth table is a table that comprises all the possible outcomes of a Boolean function used in Boolean algebra. It is used to establish a relation between various variable that contributes to the Boolean function. 1 in the Truth table represents true value and 0 represents false value. Truth Table provides us with an easy method to test whether a given argument is valid or not for legitimate input.
> Total no. of combinations = 2n
>
> where, n = no. of variables.
### **Truth Table for 2 Variables**
Total no. of combinations = 22  = 4
| A | B | A V B | A Ʌ B | ~A | ~B |
| --- | --- | --- | --- | --- | --- |
| 0 | 0 | 0 | 0 | 1 | 1 |
| 0 | 1 | 1 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 | 0 | 0 |
## Methods to Solve Boolean Function
### 1. Karnaugh-map or K-map
karnaugh-map is used to minimize the number of logic gates that are required in a digital circuit. The cells are arranged in a way so that simplification of a given expression is simply a matter of properly grouping the cells.
**SUM OF PRODUCT (SOP)**
SOP as the name itself suggests sum of products. It is the sum of all the products where the output is 1. It is denoted by Σ which tells about the minterms 'm'. When two or more terms are multiplied via AND gate and their respective resultants are added with the help of OR gate is defined as Sum Of Products.
In case of SOP, consider the following:
A = 1
A' = 0
Let us understand it with an example.
|  | A | B | C | **Y** |
| --- | --- | --- | --- | --- |
| m0 | 0 | 0 | 0 | **1** |
| m1 | 0 | 0 | 1 | **0** |
| m2 | 0 | 1 | 0 | **1** |
| m3 | 0 | 1 | 1 | **1** |
| m4 | 1 | 0 | 0 | **0** |
| m5 | 1 | 0 | 1 | **0** |
| m6 | 1 | 1 | 0 | **1** |
| m7 | 1 | 1 | 1 | **1** |
In SOP, we consider only those expression where value of Y is 1 (high).
> SOP = Σ (m0, m2, m3, m6, m7)
>
> = A'B'C' + A'BC' + A'BC + ABC' + ABC
>
> = A'B'C' + BC'(A + A') + BC (A + A')
>
> = A'B'C' + BC' + BC
>
> = A'B'C' + B(C' + C)
>
> = A'B'C' + B
**PRODUCT OF SUM (POS)**
POS stands for product of sum and it is used when the output is 0. It is denoted by Π which tells about the maxterms 'M'.
It consists of two or more OR gates that are ANDed together.
In case of POS, consider the following:
A = 0
A' = 1
Let us understand it with an example.
|  | A | B | C | Y |
| --- | --- | --- | --- | --- |
| M0 | 0 | 0 | 0 | 0 |
| M1 | 0 | 0 | 1 | 1 |
| M2 | 0 | 1 | 0 | 1 |
| M3 | 0 | 1 | 1 | 0 |
| M4 | 1 | 0 | 0 | 0 |
| M5 | 1 | 0 | 1 | 1 |
| M6 | 1 | 1 | 0 | 1 |
| M7 | 1 | 1 | 1 | 0 |
> POS = Π (M0, M3, M4, M7)
>
> = (A + B + C) . (A + B' + C') . (A + B' + C') . (A' + B' + C')
#### Example of Karnaugh-map
F( A, B, C) = Σm ( 0, 1, 2, 4, 7)
|  | A | B | C | F |
| --- | --- | --- | --- | --- |
| m0 | 0 | 0 | 0 | 1 |
| m1 | 0 | 0 | 1 | 1 |
| m2 | 0 | 1 | 0 | 1 |
| m3 | 0 | 1 | 1 | 0 |
| m4 | 1 | 0 | 0 | 1 |
| m5 | 1 | 0 | 1 | 0 |
| m6 | 1 | 1 | 0 | 0 |
| m7 | 1 | 1 | 1 | 1 |
F( A, B, C) = ABC + A'B' + B'C' + A'C'
![K-Map](assets/22-660-01ebc444ca.png)
k-map
### 2. NAND GATES
NAND gate is Negation of the AND gate. It gives the values opposite to the AND gate. It gives the value 0 only when all the inputs are 1. Below is the Truth Table for AND and NAND gate.
| A | B | A∧B | ~A∧B |
| --- | --- | --- | --- |
| 0 | 0 | 0 | 1 |
| 0 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 0 |
Let us understand solving [Boolean functions](https://www.geeksforgeeks.org/engineering-mathematics/representation-of-boolean-functions/) with the help of NAND gate
F (A, B, C) = ABC + A'B' + B'C' + A'C'
![NAND GATE](assets/23-660-00586bbc95.png)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/boolean-functions/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Introduction of Boolean Algebra and Logic Gates

> [!note] Related notes
>
> - [[Canonical and Standard Form]]
> - [[Consensus Theorem]]
> - [[Functional Completeness]]
> - [[Implicants in K-Map]]
> - [[K-Map]]
> - [[Logic Gates]]
> - [[Logical gates in logic design]]
> - [[Minimization of Boolean Functions]]
> - [[PDNF and PCNF]]
> - [[Prime implicants and Explicit implicants]]
