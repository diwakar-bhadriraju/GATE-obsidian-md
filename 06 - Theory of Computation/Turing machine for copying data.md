---
title: "Turing machine for copying data"
subject: "Theory of Computation"
topic: "Turing Machines and Undecidability"
source: "https://www.geeksforgeeks.org/theory-of-computation/turing-machine-for-copying-data/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Turing Machines and Undecidability"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/turing-machines-and-undecidability
---


> [!abstract] Turing machine for copying data
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Turing Machines and Undecidability`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/turing-machine-for-copying-data/)

---

# Turing machine for copying data

Prerequisite - [Turing Machine](https://www.geeksforgeeks.org/theory-of-computation/turing-machine-in-toc/) 
**Problem -** Draw a Turing machine which copy data. 
**Example -** 
![](assets/111-4-ebd6057095.png)
Steps: 
- **Step-1.** First convert all 0's, 1's into 0's, 1's and go right then B into C and go left
- **Step-2.** Then convert all 0's, 1's into 0's, 1's and go left then
- **Step-3.** If 1 convert it into X and go right convert all 0's, 1's into 0's, 1's and go right then convert C into C and go right then convert all 0's, 1's into 0's, 1's and go right then convert B into 1 and go left then convert all 0's, 1's into 0's, 1's and go left then convert C into C and go left then convert all 0's, 1's into 0's, 1's and go left then convert all X into X and go right and then repeat all the process from step-2 till end
- **Step-4.** If 0 then convert it into Y and go right then convert all 0's, 1's into 0's, 1's and go right then convert C into C and go right then convert all 0's, 1's into 0's, 1's and go right then convert B into 0 and go left then convert all 0's, 1's into 0's, 1's and go left then convert C into C and go left then convert all 0's, 1's into 0's, 1's and go left then convert all Y into Y and go right and then repeat all the process from step-2 till end
- **Step-5.** Otherwise if C found convert it into C and go left then convert all X into 1 and Y into 0 and go left then convert B into B and go right and **stop the machine.**
![](assets/a-660x372-ea9aa202c6.png)
Turing machine for copying data
Here, **q0** shows the initial state and **q1, q2, ....., q9, q11**are the transition states and **q12**shows the final state. 
And 0, 1 is the data inside a machine and X, Y, C are the variables used for copy data and R, L shows right and left.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/turing-machine-for-copying-data/)

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
