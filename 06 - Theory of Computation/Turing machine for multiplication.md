---
title: "Turing machine for multiplication"
subject: "Theory of Computation"
topic: "Turing Machines and Undecidability"
source: "https://www.geeksforgeeks.org/theory-of-computation/turing-machine-for-multiplication/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Turing Machines and Undecidability"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/turing-machines-and-undecidability
---


> [!abstract] Turing machine for multiplication
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Turing Machines and Undecidability`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/turing-machine-for-multiplication/)

---

# Turing machine for multiplication

Prerequisite - [Turing Machine](https://www.geeksforgeeks.org/theory-of-computation/turing-machine-in-toc/)
**Problem:** Draw a turing machine which multiply two numbers.
**Example:**
![](assets/exmultituringmachine-6c35794d53.png)
Steps:
- **Step-1.** First ignore 0's, C and go to right & then if B found convert it into C and go to left.
- **Step-2.** Then ignore 0's and go left & then convert C into C and go right.
- **Step-3.** Then convert all X into X and go right if 0 found convert it into X and go to left otherwise if C found convert it into B and go to right and **stop the machine.**
- **Step-4.** If then X found convert it into X and go left then C into C and left then Y into Y and left.
- **Step-5.** Then if B found convert it into B and right then if Y into 0 and right or if C into C and right and go to step 3 and repeat the process otherwise if 0 found after 4th step then convert it into Y and right then Y into Y and right then C into C and right then 0 into 0 or X into X and right then C into C and right then 0 into 0 and right then B into 0 and left then 0 into 0 and left then C into C and left then 0 into 0 or X into X and left then C into C and left.
- **Step-6.** Then repeat the 5th step.
![](assets/2222-1-8adc26ece4.png)
Here, **q0** shows the initial state and **q1, q2, ....., q10, q11**are the transition states and **q12**shows the final state.
And X, Y, 0, C are the variables used for multiplication and R, L shows right and left.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/turing-machine-for-multiplication/)

## GATE CS

- Subject: Theory of Computation
- Topic: Turing Machines and Undecidability

> [!note] Related notes
>
> - [[Computable and non-computable problems]]
> - [[Construct a Turing machine for L = {aibjck i j = k; i, j, k ≥ 1}]]
> - [[Construct a Turing Machine for language L = {0n1n2n n≥1}]]
> - [[Construct a Turing Machine for language L = {ww w ∈ {0,1}}]]
> - [[Construct a Turing Machine for language L = {wwr w ∈ {0, 1}}]]
> - [[Decidability]]
> - [[Decidable and undecidable problems]]
> - [[Halting Problem]]
> - [[Introduction to NP-Completeness]]
> - [[Introduction to Recursive and Recursive Enumerable Languages]]
