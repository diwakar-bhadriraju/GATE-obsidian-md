---
title: "Construct a Turing Machine for language L = {0 n 1 n 2 n | n≥1}"
subject: "Theory of Computation"
topic: "Turing Machines and Undecidability"
source: "https://www.geeksforgeeks.org/theory-of-computation/construct-turing-machine-language-l-0n1n2n-n%E2%89%A51/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Turing Machines and Undecidability"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/turing-machines-and-undecidability
---


> [!abstract] Construct a Turing Machine for language L = {0 n 1 n 2 n | n≥1}
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Turing Machines and Undecidability`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/construct-turing-machine-language-l-0n1n2n-n%E2%89%A51/)

---

# Construct a Turing Machine for language L = {0 n 1 n 2 n | n≥1}

Prerequisite - [Turing Machine](https://www.geeksforgeeks.org/theory-of-computation/turing-machine-in-toc/)
The language L = {0n1n2n | n≥1} represents a kind of language where we use only 3 character, i.e., 0, 1 and 2. In the beginning language has some number of 0's followed by equal number of 1's and then followed by equal number of 2's. Any such string which falls in this category will be accepted by this language. The beginning and end of string is marked by $ sign.
**Examples -**
```
Input  : 0 0 1 1 2 2
Output : Accepted
Input  : 0 0 0  1 1 1 2 2 2 2
Output : Not accepted
```
**Assumption:** We will replace 0 by X, 1 by Y and 2 by Z
**Approach used -**
First replace a 0 from front by X, then keep moving right till you find a 1 and replace this 1 by Y. Again, keep moving right till you find a 2, replace it by Z and move left. Now keep moving left till you find a X. When you find it, move a right, then follow the same procedure as above.
A condition comes when you find a X immediately followed by a Y. At this point we keep moving right and keep on checking that all 1's and 2's have been converted to Y and Z. If not then string is not accepted. If we reach $ then string is accepted.
- **Step-1:**
  Replace 0 by X and move right, Go to state Q1.
- **Step-2:**
  Replace 0 by 0 and move right, Remain on same state
  Replace Y by Y and move right, Remain on same state
  Replace 1 by Y and move right, go to state Q2.
- **Step-3:**
  Replace 1 by 1 and move right, Remain on same state
  Replace Z by Z and move right, Remain on same state
  Replace 2 by Z and move right, go to state Q3.
- **Step-4:**
  Replace 1 by 1 and move left, Remain on same state
  Replace 0 by 0 and move left, Remain on same state
  Replace Z by Z and move left, Remain on same state
  Replace Y by Y and move left, Remain on same state
  Replace X by X and move right, go to state Q0.
- **Step-5:**
  If symbol is Y replace it by Y and move right and Go to state Q4
  Else go to step 1
- **Step-6:**
  Replace Z by Z and move right, Remain on same state
  Replace Y by Y and move right, Remain on same state
  If symbol is $ replace it by $ and move left, STRING IS ACCEPTED, GO TO FINAL STATE Q5
![](assets/1-59-8e5b5a0fda.jpg)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/construct-turing-machine-language-l-0n1n2n-n%E2%89%A51/)

## GATE CS

- Subject: Theory of Computation
- Topic: Turing Machines and Undecidability

> [!note] Related notes
>
> - [[Computable and non-computable problems]]
> - [[Construct a Turing machine for L = {aibjck i j = k; i, j, k ≥ 1}]]
> - [[Construct a Turing Machine for language L = {ww w ∈ {0,1}}]]
> - [[Construct a Turing Machine for language L = {wwr w ∈ {0, 1}}]]
> - [[Decidability]]
> - [[Decidable and undecidable problems]]
> - [[Halting Problem]]
> - [[Introduction to NP-Completeness]]
> - [[Introduction to Recursive and Recursive Enumerable Languages]]
> - [[Introduction to Turing Machine]]
