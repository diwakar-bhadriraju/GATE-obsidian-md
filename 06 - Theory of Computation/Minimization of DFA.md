---
title: "Minimization of DFA"
subject: "Theory of Computation"
topic: "Regular Expression, Languages,Grammar, and Finite Automata"
source: "https://www.geeksforgeeks.org/theory-of-computation/minimization-of-dfa/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Regular Expression, Languages,Grammar, and Finite Automata"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/regular-expression-languages-grammar-and-finite-automata
---


> [!abstract] Minimization of DFA
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Regular Expression, Languages,Grammar, and Finite Automata`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/minimization-of-dfa/)

---

# Minimization of DFA

DFA minimization stands for converting a given DFA to its equivalent DFA with minimum number of states. DFA minimization is also called as Optimization of DFA and uses partitioning algorithm.
Suppose there is a DFA D = ( Q, Σ, δ, q0, F ) which recognizes a language L. Then the minimized DFA D = ( Q, Σ, δ, q0, F ) can be constructed for language L as: 
**Step 1:** We will divide Q (set of states) into two sets. One set will contain all final states and other set will contain non-final states. This partition is called P0. 
**Step 2:** Initialize k = 1 
**Step 3:** Find Pk by partitioning the different sets of Pk-1. In each set of Pk-1, we will take all possible pair of states. If two states of a set are distinguishable, we will split the sets into different sets in Pk. 
**Step 4:** Stop when Pk = Pk-1 (No change in partition) 
**Step 5:** All states of one set are merged into one. No. of states in minimized DFA will be equal to no. of sets in Pk. 
**How to find whether two states in partition P**k** **are distinguishable ?** 
Two states ( qi, qj ) are distinguishable in partition Pk if for any input symbol a, Δ ( qi, a ) and Δ ( qj, a ) are in different sets in partition Pk-1. 
**Example** 
Consider the following DFA shown in figure.  
![fig 1](assets/fig-11-4c93f3135f.png)
**Step 1.** P0 will have two sets of states. One set will contain q1, q2, q4 which are final states of DFA and another set will contain remaining states. So P0 = { { q1, q2, q4 }, { q0, q3, q5 } }. 
**Step 2.** To calculate P1, we will check whether sets of partition P0 can be partitioned or not: 
### **(i) For the set { q1, q2, q4 }:**
To check whether this block can be further partitioned, we compare the transitions of each state on input symbols 0 and 1.
| State | δ(0) | δ(1) |
| --- | --- | --- |
| q1 | q2 | q5 |
| q2 | q2 | q5 |
| q4 | q2 | q5 |
- On input 0, all states transition to q2, which belongs to the same block of P0.
- On input 1, all states transition to q5, which also belongs to the same block of P0.
Since all states in the set { q1, q2, q4 } have identical transition behavior for both input symbols, they are not distinguishable, hence, the block { q1, q2, q4 } cannot be partitioned further.
### **(ii) For the set { q0, q3, q5 }:**
To check whether this block can be partitioned, we compare the transitions of the states on input symbols **0** and **1**.
| State | δ(0) | δ(1) |
| --- | --- | --- |
| q0 | q3 | q1 |
| q3 | q0 | q4 |
| q5 | q5 | q5 |
For states q0 and q3:
- On input 0, the transitions go to q3 and q0, which belong to the same block of P0.
- On input 1, the transitions go to q1 and q4, which also belong to the same block of P0.
Hence, q0 and q3 are not distinguishable.
For states q0 and q5:
- On input 1, the transitions go to q1 and q5, which belong to different blocks of P0.
Hence, q0 and q5 are distinguishable. Therefore, the block {q0, q3, q5 } is partitioned into { q0, q3 } and { q5}, so, P1={{q1, q2, q4}, {q0, q3}, {q5}}
### **(iii) For the set { q1, q2, q4 } in P1:**
To compute P2, we again check whether this block can be further partitioned.
| State | δ(0) | δ(1) |
| --- | --- | --- |
| q1 | q2 | q5 |
| q2 | q2 | q5 |
| q4 | q2 | q5 |
- On input 0, all transitions go to q2, which lies in the same block of P1.
- On input 1, all transitions go to q5, which also lies in the same block of P1.
Thus, all states have identical transition behavior, Hence, the block { q1, q2, q4 } cannot be partitioned further in P2.
### **(iv) For the set { q0, q3 }:**
We compare transitions of q0 and q3 on both input symbols.
| State | δ(0) | δ(1) |
| --- | --- | --- |
| q0 | q3 | q1 |
| q3 | q0 | q4 |
- On input 0, transitions are to q3 and q0, which belong to the same block of P1.
- On input 1, transitions are to q1 and q4, which also belong to the same block of P1.
Since both transitions lead to the same blocks, q0 and q3 are not distinguishable, Hence, the block { q0, q3 } cannot be partitioned further.
### **(v) For the set { q5 }:**
This block contains only one state.
- A single-state block cannot be partitioned further.
Hence, the block { q5 } remains unchanged.
### **Final Result**
Since no further partitioning is possible, P1 = {{q1​ ,q2​, q4​}, {q0​, q3​}, {q5​}}. As P1 = P2, this is the final partition.
- States q1, q2, q4 are merged into one state.
- States q0, q3 are merged into one state.
- State q5 remains as it is.
This gives the minimized DFA. Minimized DFA corresponding to DFA of Figure 1 is shown in Figure 2 as:  
![fig 2](assets/fig-22-63a84db26d.png)**Example :**
Consider a DFA **A** over the alphabet {0, 1}. Analyze the following statements about A: 
1. The complement of L(A) is context-free.
2. L(A) = L((11**0 + 0)(0 + 1)01**)
3. A is the minimal DFA for the language it accepts.
4. A accepts all strings over {0, 1} of length at least two.
**Analysis:**
- Statement 4 claims that A accepts all strings of length ≥ 2. However, A also accepts the string `0`, which has length 1. Hence, statement 4 is **false**.
- Statement 3 claims that A is minimal. Using the minimization algorithm:
  1. Initial partition: P0 = { {q2}, {q0, q1} }
  2. After checking transitions: P1 = { {q2}, {q0, q1} }
  3. Since P0 = P1, the minimized DFA merges q0 and q1 into a single state. Therefore, statement 3 is also **false**.
![example](assets/example-d0c8c6080b.png)
**Conclusion:** Statements 3 and 4 are false.
**Correct Option:** D
### Advantages
- **Reduced Complexity**: Removes redundant states and transitions, making the DFA simpler, easier to analyze, and modify.
- **Optimal Space Utilization:** Occupies less memory and storage, which is useful for large DFAs or memory-limited environments.
- **Improved Performance**: Fewer states and transitions lead to faster execution, more efficient computation, and better handling of large inputs.
- **Language Equivalence:** Ensures the minimized DFA recognizes the same language, preserving all valid and invalid string behavior.
### Disadvantages
- **Increased Computational Complexity**: Calculating state equivalence and merging states can be time-consuming and resource-intensive, especially for large DFAs.
- **Additional Design Effor**t: Requires careful analysis of states and transitions, which can be error-prone and complex.
- **Loss of Readability:** Merged states may make the minimized DFA harder to interpret and understand.
- **Limited to DFAs**: Minimization applies only to deterministic automata; NFAs must first be converted to DFAs, which can increase size.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/minimization-of-dfa/)

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
