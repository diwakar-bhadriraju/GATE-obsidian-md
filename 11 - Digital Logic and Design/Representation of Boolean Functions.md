---
title: "Representation of Boolean Functions"
subject: "Digital Logic and Design"
topic: "Introduction of Boolean Algebra and Logic Gates"
source: "https://www.geeksforgeeks.org/engineering-mathematics/representation-of-boolean-functions/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Introduction of Boolean Algebra and Logic Gates"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/introduction-of-boolean-algebra-and-logic-gates
---


> [!abstract] Representation of Boolean Functions
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Introduction of Boolean Algebra and Logic Gates`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/representation-of-boolean-functions/)

---

# Representation of Boolean Functions

A Boolean function is a function that takes one or more Boolean inputs and produces a Boolean output. It can be represented using Boolean algebra, which involves operations such as AND, OR, NOT, NAND, NOR, XOR, and XNOR.
The most common representations of Boolean functions are:
### 1. Boolean Expression
A Boolean expression represents a Boolean function using Boolean variables, constants (0 and 1), and logical operators such as AND (·), OR (+), and NOT (').
> **Example:** F(A, B, C) = A′B + BC′
Here, the function evaluates to 1 whenever either A′B or BC′ is true.
### 2. Truth Table
A truth table lists every possible combination of input variables along with the corresponding output of the Boolean function. For a function with n variables, the truth table contains 2n rows.
> **Example:** For F(A,B) = A + B
| A | B | F |
| --- | --- | --- |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |
### 3. Logic Circuit Representation
A Boolean function can also be represented as a logic circuit using logic gates such as AND, OR, NOT, NAND, NOR, XOR, and XNOR.
> **For example**, the Boolean function F = A + BC can be implemented by first passing B and C through an AND gate and then OR-ing the result with A.
### 4. Canonical Representation
A Boolean function can be written in canonical form, where every term contains all the variables exactly once.
There are two canonical representations:
- **Canonical Sum of Products (SOP):** Formed by OR-ing all the minterms for which the function is 1.
- **Canonical Product of Sums (POS):** Formed by AND-ing all the maxterms for which the function is 0.
> **Example:** F(A,B,C) = Σm(1,3,6) or F(A,B,C) = ΠM(0,2,4,5,7)
Both expressions represent the same Boolean function.
### 5. Karnaugh Map (K-Map)
A Karnaugh Map is a graphical representation of a Boolean function. It arranges minterms in Gray code order, allowing adjacent cells to be grouped for simplifying Boolean expressions.
> **Example:** For F(A, B, C) = Σm(1, 3, 5, 7)
the corresponding K-map groups all four adjacent 1's, simplifying the function to F = C
### 6. Binary Decision Diagram (BDD)
A Binary Decision Diagram (BDD) is a graph-based representation in which each internal node represents a Boolean variable, and each path from the root to a terminal node corresponds to a sequence of variable assignments. The terminal nodes represent the Boolean values 0 and 1.
**Example:** For F(A,B) = A + B
- If A = 1, the output is 1.
- If A = 0, the output depends on the value of B.
This decision process is represented as a directed graph.
## Applications
1. **Digital Circuit Design:** Boolean functions are used to design and simplify digital circuits, including logic gates, multiplexers, adders, and more. Simplifying Boolean expressions reduces the number of gates required, optimizing circuit design. Example: Designing a digital circuit to perform arithmetic operations involves using Boolean functions to define the behavior of adders and subtractors.
2. **Computer Algorithms:** Boolean functions are integral to algorithms that involve decision-making, such as search algorithms, sorting algorithms, and error detection and correction algorithms.Example: In search algorithms, Boolean functions help determine whether a condition is met, guiding the search process.
3. **Fault Detection:** Boolean functions are used in fault detection and diagnosis in digital systems. By comparing the expected and actual outputs of a digital circuit, faults can be identified and corrected. Example: Built-in self-test (BIST) techniques use Boolean functions to generate test patterns and compare the results to detect faults in integrated circuits.
4. **Control Systems:** Boolean functions are used in control systems to define the logic for system operation, such as switching on or off, opening or closing valves, and more.Example: In an automated manufacturing process, Boolean functions control the operation of machinery based on sensor inputs.
**➣Practice:** [Solved Examples](https://www.geeksforgeeks.org/maths/boolean-functions-practice-questions/)
### Related Articles
> - [Boolean Algebra - Expression, Rules, Theorems](https://www.geeksforgeeks.org/digital-logic/boolean-algebra/)
> - [Boolean Functions](https://www.geeksforgeeks.org/digital-logic/boolean-functions/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/representation-of-boolean-functions/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Introduction of Boolean Algebra and Logic Gates

> [!note] Related notes
>
> - [[Boolean functions]]
> - [[Canonical and Standard Form]]
> - [[Consensus Theorem]]
> - [[Functional Completeness]]
> - [[Implicants in K-Map]]
> - [[K-Map]]
> - [[Logic Gates]]
> - [[Logical gates in logic design]]
> - [[Minimization of Boolean Functions]]
> - [[PDNF and PCNF]]
