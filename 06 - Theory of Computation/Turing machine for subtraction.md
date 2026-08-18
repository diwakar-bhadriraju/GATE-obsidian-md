---
title: "Turing machine for subtraction | Set 1"
subject: "Theory of Computation"
topic: "Turing Machines and Undecidability"
source: "https://www.geeksforgeeks.org/theory-of-computation/turing-machine-for-subtraction/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Turing Machines and Undecidability"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/turing-machines-and-undecidability
---


> [!abstract] Turing machine for subtraction | Set 1
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Turing Machines and Undecidability`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/turing-machine-for-subtraction/)

---

# Turing machine for subtraction | Set 1

Prerequisite - [Turing Machine](https://www.geeksforgeeks.org/theory-of-computation/turing-machine-in-toc/) **Problem-1:** Draw a Turing machine which subtract two numbers. **Example:** ![](assets/subtracttmex-746a43dc1a.png) Steps:
- **Step-1.** If 0 found convert 0 into X and go right then convert all 0's into 0's and go right.
- **Step-2.** Then convert C into C and go right then convert all X into X and go right.
- **Step-3.** Then convert 0 into X and go left then convert all X into X and go left.
- **Step-4.** Then convert C into C and go left then convert all 0's into 0's and go left then convert all X into X and go right and repeat the whole process.
- **Step-5.** Otherwise if C found convert C into C and go right then convert all X into B and go right then convert 0 into 0 and go left and then **stop the machine.**
![](assets/subtracttm-74852b6fea.png) Here, **q0** shows the initial state and **q1, q2, q3, q4, q5**are the transition states and **q6**shows the final state. And X, 0, C are the variables used for subtraction and R, L shows right and left. **Problem-2:** Draw a Turing machine which subtract two numbers m and n, where m is greater than n. ![](assets/subtracttmexg-ed9cf76b2d.png) Steps:
- **Step-1.** If 0 found convert all 0's into 0's and go right then convert C into C and go right
- **Step-2.** If X found then convert all X into X and go right or if 0 found then convert 0 into X and go left and go to next step otherwise go to 5th step
- **Step-3.** Then convert all X into X and go left then convert C into C and go left
- **Step-4.** Then convert all 0's into 0's and go left then convert B into B and go right then convert 0 into B and go right and repeat the whole process
- **Step-5.** Otherwise if B found convert B into B and go left then convert all X into B and go left then convert C into B and go left and then **stop the machine.**
![](assets/subtracttmg-bd672714e1.png) Here, **q0** shows the initial state and **q1, q2, q3, q4, q5**are the transition states and **q6**shows the final state. And B, X, 0, C are the variables used for subtraction(m>n) and R, L shows right and left and B variable is a input symbol. See for - [Turing Machine for subtraction | Set 2](https://www.geeksforgeeks.org/theory-of-computation/turing-machine-for-subtraction-set-2/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/turing-machine-for-subtraction/)

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
