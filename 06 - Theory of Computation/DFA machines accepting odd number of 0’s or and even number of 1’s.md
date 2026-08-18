---
title: "DFA machines accepting odd number of 0’s or/and even number of 1’s"
subject: "Theory of Computation"
topic: "Regular Expression, Languages,Grammar, and Finite Automata"
source: "https://www.geeksforgeeks.org/theory-of-computation/dfa-machines-accepting-odd-number-of-0s-or-and-even-number-of-1s/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Regular Expression, Languages,Grammar, and Finite Automata"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/regular-expression-languages-grammar-and-finite-automata
---


> [!abstract] DFA machines accepting odd number of 0’s or/and even number of 1’s
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Regular Expression, Languages,Grammar, and Finite Automata`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/dfa-machines-accepting-odd-number-of-0s-or-and-even-number-of-1s/)

---

# DFA machines accepting odd number of 0’s or/and even number of 1’s

Prerequisite - [Designing finite automata](https://www.geeksforgeeks.org/theory-of-computation/designing-finite-automata-from-regular-expression-set-1/)
**Problem -** Construct a DFA machine over input alphabet
$$
\sum_
$$
= {0, 1}, that accepts:
1. Odd number of 0’s or even number of 1’s
2. Odd number of 0’s and even number of 1’s
3. Either odd number of 0’s or even number of 1’s but not the both together
**Solution -** Let first design two separate machines for the two conditions:
- Accepting only odd number of 0's
- Accepting only even number of 1's
Then, merge these two and find the required final states.
![](assets/fig1-5-af7a34286b.png)
![](assets/fig2-5-ff2e6e9dc7.png)
To merge these two machines, we will take the Cartesian product of the states of these two machines:
![](assets/FIGure3-a34292ec86.png)
Initial state of these DFA will be the state which contains the initial states of those two separate machines. As, q0 and q2 are the initial states thus, q0q2 is the initial state of the final DFA.
Now start designing all the DFAs one by one:
1. **Odd number of 0’s or even number of 1’s:**
   This machine accept that languages which contains either odd no. of 0's or even no. of 1's. As we know that q1 indicates odd no. of 0's and q2 indicates even no. of 1's. So, the final states of the required DFA will contain either q1 or q2.
   .'. Final states = {(q0q2), (q1q2), (q1q3)}
   ![](assets/FIG3i-0099f63886.png)
   This is our required DFA which accept the languages containing odd no. of 0's or even no. of 1's.
2. **Odd number of 0’s and even number of 1’s:**
   This machine accept that languages which contains odd no. of 0's and even no. of 1's. As we know that q1 indicates odd no. of 0's and q2 indicates even no. of 1's. So, the final states of the required DFA will contain both q1 and q2.
   .'. Final state = {(q1q2)}
   ![](assets/FIG3i-1-dd4e7ab2dd.png)
   This is our required DFA which accept the languages containing odd no. and 0's or even no. of 1's.
3. **Either odd number of 0’s or even number of 1’s but not the both together:**
   This machine accept that languages which contains either odd no. of 0's or even no. of 1's but not that languages which contains both odd no. of 0's and even no. of 1's. As we know that q1 indicates odd no. of 0's and q2 indicates even no. of 1's. So, the final states of the required DFA will contain exactly one among q1 and q2.
   .'. Final states = {(q0q2), (q1q3)}
   ![](assets/FIG3-1-0678e26a08.png)
   This is our required DFA which accept the languages containing odd no. of 0's or even no. of 1's but not the both together.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/dfa-machines-accepting-odd-number-of-0s-or-and-even-number-of-1s/)

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
