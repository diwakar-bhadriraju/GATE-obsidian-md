---
title: "Consensus Theorem in Digital Logic"
subject: "Discrete Mathematics"
topic: "Propositional and First-Order Logic"
source: "https://www.geeksforgeeks.org/digital-logic/consensus-theorem-in-digital-logic/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Propositional and First-Order Logic, Digital Logic and Design/Introduction of Boolean Algebra and Logic Gates"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/propositional-and-first-order-logic
---


> [!abstract] Consensus Theorem in Digital Logic
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Propositional and First-Order Logic`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/consensus-theorem-in-digital-logic/)

---

# Consensus Theorem in Digital Logic

The Consensus Theorem is a boolean algebra simplification rule used to eliminate redundant terms without changing the output of a boolean expression.
- It simplifies logic expressions and reduces the number of logic gates.
- Helps design efficient digital circuits.
![Consesus-theroem](assets/Consesus-theroem-7edc542c8b.png)
Consensus Theorem
## Consensus Theorem in SOP and POS Forms
The Consensus Theorem can be expressed in both Sum-of-Products (SOP) and Product-of-Sums (POS) forms:
- **Sum-of-Products (SOP) Form**
> AB + A'C + BC = AB + A'C
- **Product-of-Sums (POS) Form**
> (A + B)(A' + C)(B + C) = (A + B)(A' + C)
Here, A' represents the complement of A. In both SOP and POS forms, the consensus term is redundant and can be removed without affecting the output of the Boolean expression.
## Proof of the Consensus Theorem
We prove the **SOP form** step by step:
- Start with the left-hand side:
> AB + A'C + BC
- Add consensus term:
> AB + A'C + BC = AB + A'C + BC(A + A') (since A + A' = 1)
- Expand BC(A + A'):
> AB + A'C + ABC + A'BC
- Factor out common terms (Absorption Law):
> AB + ABC + A'C + A'BC
>
> AB(1 + C) + A'C(1 + B)
>
> AB + A'C ---> (since 1 + C = 1 and 1 + B = 1)
- Final simplification:
> AB + A'C + BC = AB + A'C
Thus, the term BC is not needed.
## **Solved Examples**
**Example 1:** Simplify the following Boolean expression using the Consensus Theorem:
F = AB + BC' + AC
Here, the expression satisfies the conditions of the Consensus Theorem. Variable C appears in both complemented (C') and non-complemented (C) forms, and AB is the consensus (redundant) term.
![](assets/r1-11c45c850b.png)
According to the Consensus Theorem, the consensus term AB is redundant and can be removed without affecting the output. Therefore, the simplified expression is:
∴ F = BC' + AC
**Example 2:** Apply the Consensus Theorem to simplify:
F = (A + B) (A' + C) (B + C)
Here, the expression satisfies the conditions of the Consensus Theorem. Variable A appears in both complemented (A') and non-complemented (A) forms, and (B + C) is the consensus (redundant) term.
![](assets/r2-3af5cb239b.png)
According to the Consensus Theorem, the consensus term (B + C) is redundant and can be removed without affecting the output. Therefore, the simplified expression is:
∴ F = (A + B) (A' + C)
## Advantages
- **Simplifies Boolean Expressions:** Eliminates redundant terms without changing the output.
- **Reduces Logic Gates:** Fewer gates simplify circuit implementation.
- **Lowers Hardware Cost:** Reduced gate count decreases circuit complexity and cost.
## Disadvantages
- **Limited Applicability:** Works only when the expression satisfies the theorem's conditions.
- **Requires Pattern Recognition:** Identifying the consensus term may not be straightforward.
- **Cannot Simplify Every Expression:** Many Boolean expressions require other simplification methods.
## Applications
- **Logic Circuit Simplification:** Reduces the number of logic gates in digital circuits.
- **Boolean Function Minimization:** Simplifies Boolean expressions during digital circuit design.
- **Digital System Design:** Used in the design of CPUs, multiplexers, decoders, and other digital systems.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/consensus-theorem-in-digital-logic/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Propositional and First-Order Logic

> [!note] Related notes
>
> - [[Boolean functions]]
> - [[Canonical and Standard Form]]
> - [[Functional Completeness]]
> - [[Implicants in K-Map]]
> - [[Introduction to Propositional Logic]]
> - [[K-Map]]
> - [[Logic Gates]]
> - [[Logical gates in logic design]]
> - [[Minimization of Boolean Functions]]
> - [[PDNF and PCNF]]
