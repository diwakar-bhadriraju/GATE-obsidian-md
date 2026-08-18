---
title: "Introduction to NP-Complete Complexity Classes"
subject: "Theory of Computation"
topic: "Turing Machines and Undecidability"
source: "https://www.geeksforgeeks.org/dsa/introduction-to-np-completeness/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Turing Machines and Undecidability"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/turing-machines-and-undecidability
---


> [!abstract] Introduction to NP-Complete Complexity Classes
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Turing Machines and Undecidability`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/introduction-to-np-completeness/)

---

# Introduction to NP-Complete Complexity Classes

NP-complete problems are a subset of the larger class of NP problems. NP problems are a class of computational problems that can be solved in polynomial time by a non-deterministic machine and can be verified in polynomial time by a deterministic Machine.
- A problem L in NP is NP-complete if all other problems in NP can be reduced to L in polynomial time.
- If any NP-complete problem can be solved in polynomial time, then every problem in NP can be solved in polynomial time.
- NP-complete problems are the hardest problems in the NP set.
![np-complete-complexity-classes](assets/np-complete-complexity-classes-1d9d1c31af.png)
NP-Complete Complexity Classes
A decision problem L is NP-complete if it follow the below two properties:
1. L is in NP (Any solution to NP-complete problems can be checked quickly, but no efficient solution is known).
2. Every problem in NP is reducible to L in polynomial time (Reduction is defined below).
A problem is NP-Hard if it obeys Property 2 above and need not obey Property 1. Therefore, a problem is NP-complete if it is both NP and NP-hard.
## Decision vs Optimization Problems
NP-Completeness is defined for decision problems because their difficulty is easier to compare. In many cases, solving the decision version efficiently also helps solve the corresponding optimization problem using a polynomial number of calls.
- NP-completeness is defined for decision problems.
- Decision problems are easier to compare than optimization problems.
- Polynomial-time solutions to decision problems can help solve optimization problems.
- Optimization problems can be reduced to decision problems using multiple queries.
- Hence, the complexity of decision problems reflects the complexity of optimization problems.
### What is Reduction?
Let L1 and L2 be two decision problems. Suppose algorithm A2 solves L2. That is, if y is an input for L2 then algorithm A2 will answer Yes or No depending upon whether y belongs to L2 or not.
The idea is to find a transformation from L1 to L2 so that algorithm A2 can be part of algorithm A1 to solve L1.
![](assets/NP-Completeness1-f77b50fb09.png)
- Learning reductions helps solve new problems using already solved ones.
- Reductions save time and effort by reusing existing algorithms and library functions.
- A new problem can be transformed into a known problem instead of writing new code.
- Using taking the logarithm of edge weights the problem is reduced to a shortest path problem.
- Dijkstra’s algorithm can then be used instead of developing a new solution.
## How to prove that a given problem is NP-complete?
1. From the definition of NP-Complete, it seems difficult to prove that a problem L is NP-Complete.
2. By definition, we would need to show that every problem in NP can be reduced to L in polynomial time.
3. Fortunately, there is an easier method to prove NP-Completeness.
4. We take a known NP-Complete problem and reduce it to L.
5. If this reduction can be done in polynomial time, then L is NP-Complete.
6. This works due to the transitivity property of reduction.
7. If an NP-Complete problem reduces to L, then all NP problems can also be reduced to L in polynomial time.
## **What was the first problem proved as NP-Complete?**
There must be some first NP-Complete problem proved by the definition of NP-Complete problems.  SAT (Boolean satisfiability problem) is the first NP-Complete problem proved by Cook (See CLRS book for proof). 
It is always useful to know about NP-Completeness even for engineers. Suppose you are asked to write an efficient algorithm to solve an extremely important problem for your company. After a lot of thinking, you can only come up exponential time approach which is impractical. If you don't know about NP-Completeness, you can only say that I could not come up with an efficient algorithm. If you know about NP-Completeness and prove that the problem is NP-complete, you can proudly say that the polynomial-time solution is unlikely to exist. If there is a polynomial-time solution possible, then that solution solves a big problem of computer science many scientists have been trying for years. 
### NP-Complete problems and their proof for NP-Completeness.
1. [Prove that SAT is NP Complete](https://www.geeksforgeeks.org/dsa/proof-that-sat-is-np-complete/)
2. [Prove that Sparse Graph is NP-Complete](https://www.geeksforgeeks.org/dsa/prove-that-sparse-graph-is-np-complete/)
3. [Prove that KITE is NP-Complete](https://www.geeksforgeeks.org/dsa/prove-that-kite-is-np-complete/)
4. [Prove that Hamiltonian Cycle is NP-Complete](https://www.geeksforgeeks.org/dsa/proof-that-hamiltonian-cycle-is-np-complete/)
5. [Subset Sum is NP Complete](https://www.geeksforgeeks.org/dsa/subset-sum-is-np-complete/)
6. [Prove that Collinearity Problem is NP Complete](https://www.geeksforgeeks.org/dsa/proof-that-collinearity-problem-is-np-complete/)
7. [Set partition is NP complete](https://www.geeksforgeeks.org/dsa/set-partition-is-np-complete/)
8. [Hitting Set problem is NP Complete](https://www.geeksforgeeks.org/dsa/hitting-set-problem-is-np-complete/)
9. [3-coloring is NP Complete](https://www.geeksforgeeks.org/dsa/3-coloring-is-np-complete/)
10. [Set cover is NP Complete](https://www.geeksforgeeks.org/dsa/set-cover-is-np-complete/)
11. [Optimized Longest Path is NP Complete](https://www.geeksforgeeks.org/dsa/optimized-longest-path-is-np-complete/)
12. [Double SAT is NP Complete](https://www.geeksforgeeks.org/dsa/double-sat-is-np-complete/)
13. [Prove that 4 SAT is NP complete](https://www.geeksforgeeks.org/dsa/proof-that-4-sat-is-np-complete/)
14. [Prove that Dense Subgraph is NP Complete by Generalisation](https://www.geeksforgeeks.org/dsa/prove-that-dense-subgraph-is-np-complete-by-generalisation/)
15. [Prove that a problem consisting of Clique and Independent Set is NP Complete](https://www.geeksforgeeks.org/dsa/prove-that-a-problem-consisting-of-clique-and-independent-set-is-np-complete/)
16. [Prove that Almost-SAT is NP Complete](https://www.geeksforgeeks.org/dsa/proof-that-almost-sat-is-np-complete/)
17. [Prove that MAX-SAT is NP Complete](https://www.geeksforgeeks.org/dsa/proof-that-max-sat-is-np-complete/)
18. [Prove Max2SAT is NP-Complete by Generalisation](https://www.geeksforgeeks.org/dsa/prove-max2sat-is-np-complete-by-generalisation/)
19. [Subset Equality is NP Complete](https://www.geeksforgeeks.org/dsa/subset-equality-is-np-complete/)
20. [Hitting Set problem is NP Complete](https://www.geeksforgeeks.org/dsa/hitting-set-problem-is-np-complete/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/introduction-to-np-completeness/)

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
> - [[Introduction to Recursive and Recursive Enumerable Languages]]
> - [[Introduction to Turing Machine]]
