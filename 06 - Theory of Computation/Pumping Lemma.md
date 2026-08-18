---
title: "Pumping Lemma in Theory of Computation"
subject: "Theory of Computation"
topic: "Regular Expression, Languages,Grammar, and Finite Automata"
source: "https://www.geeksforgeeks.org/theory-of-computation/pumping-lemma-in-theory-of-computation/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Regular Expression, Languages,Grammar, and Finite Automata"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/regular-expression-languages-grammar-and-finite-automata
---


> [!abstract] Pumping Lemma in Theory of Computation
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Regular Expression, Languages,Grammar, and Finite Automata`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/pumping-lemma-in-theory-of-computation/)

---

# Pumping Lemma in Theory of Computation

There are two Pumping Lemmas, which are Regular Languages and Context-Free Languages. The Pumping Lemma for Regular Languages states that for any regular language L, there exists an integer n such that any string x ∈ L with length |x| ≥ n can be divided into x = uvw, where u, v, w ∈ Σ\*, satisfying the following conditions:
**|uv| ≤ n**
**|v| ≥ 1**
**For all i ≥ 0, u vⁱ w ∈ L**
- The substring v can be repeated (pumped) any number of times and the string will still belong to L.
- The Pumping Lemma is mainly used to prove that a language is not regular.
- If any pumped string does not belong to L, then L is not regular.
- However, satisfying the Pumping Lemma does not guarantee that a language is regular.
![p1](assets/p1-204f2bc6a8.png)For example, let us prove L01 = {0n1n | n ? 0} is irregular. Let us assume that L is regular, then by Pumping Lemma the above given rules follow. Now, let x ? L and |x| ? n. So, by Pumping Lemma, there exists u, v, w such that (1) – (3) hold.   We show that for all u, v, w, (1) - (3) does not hold. If (1) and (2) hold then x = 0n1n = uvw with |uv| ? n and |v| ? 1. So, u = 0a, v = 0b, w = 0c1n where : a + b ? n, b ? 1, c ? 0, a + b + c = n But, then (3) fails for i = 0 uv0w = uw = 0a0c1n = 0a + c1n ? L, since a + c ? n.
![p2](assets/p2-c6533250a7.png)
### **Pumping Lemma for Context-free Languages (CFL)**
Pumping Lemma for CFL states that for any Context Free Language L, it is possible to find two substrings that can be 'pumped' any number of times and still be in the same language.
- For any language L, we break its strings into five parts and pump second and fourth substring.
- It is used as a tool to prove that a language is not CFL.
- Because, if any one string does not satisfy its conditions, then the language is not CFL.
Thus, if L is a CFL, there exists an integer n, such that for all x ? L with |x| ? n, there exists u, v, w, x, y ? ?\*, such that x = uvwxy, and (1) |vwx| ? n (2) |vx| ? 1 (3) for all i ? 0: uviwxiy ? L 
### p3Prove that: **L**012**​ = { 0**n**1**n**2**n** **∣ n ≥ 0 }** is not context-free.
**Proof:** Assume L012 = {0n1n2n | n ? 0} is context-free.
By the CFL Pumping Lemma, there exists p such that any string s ∈ L with ∣s∣ ≥ p can be written as s=uvwxy satisfying:
∣vwx∣≤p , ∣vx∣≥1 and uviwxiy ∈ L for all i ≥ 0.
Take s=0p1p2p .
Since ∣vwx∣≤p, vwx cannot include both 0’s and 2’s. Thus it lies within one block or at most spans two adjacent blocks.
Pumping i=0 or i=2 changes the number of symbols in only one or two blocks, while the third block remains unchanged. Hence the numbers of 0’s, 1’s, and 2’s are no longer equal, so the pumped string is not in L.
This contradicts the Pumping Lemma.
Therefore, L012 = {0n1n2n | n ? 0} is **not** context-free.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/pumping-lemma-in-theory-of-computation/)

## GATE CS

- Subject: Theory of Computation
- Topic: Regular Expression, Languages,Grammar, and Finite Automata

> [!note] Related notes
>
> - [[Chomsky Hierarchy]]
> - [[Closure properties of Regular languages]]
> - [[Concatenation process in DFA]]
> - [[Conversion from NFA to DFA]]
> - [[Designing Deterministic Finite Automata]]
> - [[Designing Deterministic Finite Automata Set 1]]
> - [[Designing Deterministic Finite Automata Set 2]]
> - [[Designing Finite Automata from Regular Expression]]
> - [[Designing Non-Deterministic Finite Automata]]
> - [[Designing Non-Deterministic Finite Automata (2)]]
