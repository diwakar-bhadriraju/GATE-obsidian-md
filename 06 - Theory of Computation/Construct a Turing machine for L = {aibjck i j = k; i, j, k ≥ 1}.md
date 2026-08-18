---
title: "Construct a Turing machine for L = {a i b j c k | i*j = k; i, j, k ≥ 1}"
subject: "Theory of Computation"
topic: "Turing Machines and Undecidability"
source: "https://www.geeksforgeeks.org/theory-of-computation/construct-a-turing-machine-for-l-aibjck-ij-k-i-j-k-%E2%89%A5-1/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Turing Machines and Undecidability"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/turing-machines-and-undecidability
---


> [!abstract] Construct a Turing machine for L = {a i b j c k | i*j = k; i, j, k ≥ 1}
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Turing Machines and Undecidability`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/construct-a-turing-machine-for-l-aibjck-ij-k-i-j-k-%E2%89%A5-1/)

---

# Construct a Turing machine for L = {a i b j c k | i*j = k; i, j, k ≥ 1}

Prerequisite – [Turing Machine](https://www.geeksforgeeks.org/theory-of-computation/turing-machine-in-toc/) 
In a given language, L = {aibjck | i\*j = k; i, j, k ≥ 1}, where every string of 'a', 'b' and 'c' has a certain number of a's, then a certain number of b's and then a certain number of c's. The condition is that each of these 3 symbols should occur at least once. 'a' and 'b' can occur however many times, but the occurrences of 'c' must be equal to the product of occurrences of 'a' and occurrences of 'b'. Assume that string is ending with '$'. 
**Examples -** 
```
Input: a a b b b c c c c c c         Here a = 2, b = 3, c = 2 * 3 = 6  Output: NOT ACCEPTED          Input: a a b b c c c       Here a = 2, b = 2, c = 3 but c should be 4 (c=2*2 must be 4 but here c=3)Output: NOT ACCEPTED
```
**Approach used -** Scan the input from the left. 
1. First, replace an 'a' with 'X' and move 1 step right. Then skip all the a's and move right.
2. When the pointer reaches the first 'b' stop. Replace one 'b' with 'Y', then move right skipping all intermediate b's and corresponding to the replaced 'b' now replace one 'c' with 'Z' and move left.
3. Now move towards the left skipping all 'Z' and 'b' in the way.
4. When the pointer reaches the most recent 'Y' move right.
5. If the pointer is pointing at 'b' then repeat steps 2 to 4, else if the pointer is pointing at 'Z' then move towards left while replacing all 'Y' to 'b' and skipping all a's.
6. When the pointer comes to the most recent 'X' move one step right.
7. If the pointer is still pointing to 'a' then repeat all the above steps, else if the pointer is at 'y' then move towards right skipping all 'y' and 'Z'.
8. When $ is reached then move left. The string is ACCEPTED.
![automata-(1)](assets/automata--1--660-52945a110e.jpg)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/construct-a-turing-machine-for-l-aibjck-ij-k-i-j-k-%E2%89%A5-1/)

## GATE CS

- Subject: Theory of Computation
- Topic: Turing Machines and Undecidability

> [!note] Related notes
>
> - [[Computable and non-computable problems]]
> - [[Construct a Turing Machine for language L = {0n1n2n n≥1}]]
> - [[Construct a Turing Machine for language L = {ww w ∈ {0,1}}]]
> - [[Construct a Turing Machine for language L = {wwr w ∈ {0, 1}}]]
> - [[Decidability]]
> - [[Decidable and undecidable problems]]
> - [[Halting Problem]]
> - [[Introduction to NP-Completeness]]
> - [[Introduction to Recursive and Recursive Enumerable Languages]]
> - [[Introduction to Turing Machine]]
