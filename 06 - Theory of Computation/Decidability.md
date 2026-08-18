---
title: "Decidability and Undecidability in TOC"
subject: "Theory of Computation"
topic: "Turing Machines and Undecidability"
source: "https://www.geeksforgeeks.org/theory-of-computation/decidability-and-undecidability-in-toc/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Turing Machines and Undecidability"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/turing-machines-and-undecidability
---


> [!abstract] Decidability and Undecidability in TOC
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Turing Machines and Undecidability`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/decidability-and-undecidability-in-toc/)

---

# Decidability and Undecidability in TOC

Whenever we asked to identify whether a language (or problem\*) is solvable or not appear very often in the GATE exam. Once the basic ideas are clear and you have practiced enough, these questions become much easier. Depending on how they can be solved, languages are divided into the following types:
- Decidable Languages
- Partially Decidable Languages
- Undecidable Languages
### Decidable Language
A decision problem PPP is said to be **decidable** if there exists an algorithm (or Turing Machine) that always halts and correctly determines the answer for every input. In other words, the language LLL, consisting of all inputs for which the answer is “yes,” is decidable.
**Examples:**
1. **Acceptance problem for DFA** – Given a DFA and an input string, determine whether the DFA accepts the string.
2. **Emptiness problem for DFA** – Given a DFA, determine whether it accepts at least one string.
3. **Equivalence problem for DFA** – Given two DFAs, determine whether both accept the same language.
### Undecidable Language
A decision problem PPP is said to be undecidable if there is no algorithm or computational procedure that can correctly determine the answer for every possible input. Such problems cannot be solved completely using a mechanical, step-by-step procedure.
- An undecidable language may be partially decidable, meaning a Turing Machine can accept “yes” instances but may not halt for “no” instances.
- If a language is not even partially decidable, then no Turing Machine exists that can recognize it.
**Example:**
The **Halting Problem** – Given a program and an input, determine whether the program will halt or run forever. This problem is undecidable.
### Partially Decidable (or Semi-Decidable) Language
A decision problem PPP is said to be **partially decidable** or **semi-decidable** if there exists a semi-algorithm for it. This means that the language LLL consisting of all “yes” instances of PPP is recursively enumerable (RE).
- A language LLL is called partially decidable if it is RE but not recursive (REC).
- Turing Machine will halt and accept all strings in LLL, but for strings not in LLL, the machine may run forever.
### Recursive Language (REC)
A language LLL is called recursive if there exists a Turing Machine that accepts every string belonging to LLL and rejects every string not belonging to LLL. The Turing Machine always halts for every input string and produces a definite result, either accept or reject.
A language LLL is said to be decidable if it is recursive. Hence, all decidable languages are recursive languages, and all recursive languages are decidable.
### Recursively Enumerable Language (RE)
A language LLL is said to be recursively enumerable if there exists a Turing Machine that accepts and halts for every input string belonging to LLL. For input strings that are not in LLL, the Turing Machine may either reject or run forever without halting.
By definition, every recursive (REC) language is also a recursively enumerable (RE) language, but not every RE language is recursive. 
> A common way to solve decidability problems is by using **reduction**, where a problem with known decidability is transformed into another problem. If an undecidable problem P1P\_1P1​ can be reduced to a problem P2P\_2P2​, then P2P\_2P2​ must also be undecidable. Otherwise, if P2P\_2P2​ were decidable, P1P\_1P1​ would also be decidable, which contradicts the fact that P1P\_1P1​ is undecidable.
### E**xamples:**
**1: State Entry Problem**
**Problem:**
Given a Turing Machine M and an input string 𝑤 , determine whether a specific state 𝑄 is ever reached during the computation of M on 𝑤. This is called the State Entry Problem.
**Reduction from the Halting Problem:**
A Turing Machine halts when a transition δ(q i ​ ,a) is undefined. Modify the machine by replacing every undefined transition with
#### δ(q**i**​ ,a) = (Q, a, L or R)
Thus, the machine reaches state 𝑄 Q if and only if it would have halted.
If an algorithm existed that always halts and decides whether state Q is reached, it would also decide the Halting Problem. Since the Halting Problem is undecidable, this leads to a contradiction.
**Conclusion:**
The State Entry Problem is undecidable.
**2. Given two regular languages L1 and L2, is the problem of finding whether a string 'w' exists in both L1 and L2, a decidable problem or not.**
First we make two Turing machines TM1 and TM2 which simulate the DFAs of languages L1 and L2 respectively. We know that a DFA always halts, so a Turing machine simulating a DFA will also always halt. We enter the string 'w' in TM1 and TM2. Both Turing machines will halt and give us an answer. We can connect the outputs of the Turing machines to a modified 'AND' gate which will output 'yes' only when both the Turing machines answer 'yes'. Otherwise it will output 'no'. Since this system of two Turing machines and a modified AND gate will always stop, this problem is a decidable problem.  
There are a lot of questions on this topic. There is no universal algorithm to solve them. Most of the questions require unique and ingenious proofs. Here is where experience is needed. By solving a lot of these problems, one can become very quick in coming up with proofs for these problems on the spot. So, keep practicing.   \*The words 'language' and 'problem' can be used synonymously in Theory of computation. For e.g. The 'Halting problem' can also be written as 'L = {<M, w> | Turing machine 'M' halts on input 'w'}'. Here 'L' is a language.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/decidability-and-undecidability-in-toc/)

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
> - [[Decidable and undecidable problems]]
> - [[Halting Problem]]
> - [[Introduction to NP-Completeness]]
> - [[Introduction to Recursive and Recursive Enumerable Languages]]
> - [[Introduction to Turing Machine]]
