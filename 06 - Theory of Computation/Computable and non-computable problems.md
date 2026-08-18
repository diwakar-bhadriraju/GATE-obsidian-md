---
title: "Computable and Non-Computable Problems"
subject: "Theory of Computation"
topic: "Turing Machines and Undecidability"
source: "https://www.geeksforgeeks.org/theory-of-computation/computable-and-non-computable-problems-in-toc/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Turing Machines and Undecidability"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/turing-machines-and-undecidability
---


> [!abstract] Computable and Non-Computable Problems
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Turing Machines and Undecidability`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/computable-and-non-computable-problems-in-toc/)

---

# Computable and Non-Computable Problems

Problems are classified as computable or non-computable based on whether they can be solved by an algorithm. Computable problems have a clear, step-by-step procedure that always lead to a correct solution while non-computable problems cannot be solved by any algorithm, no matter how much time or resources are given.
## **Computable Problems**
A computable problem is a problem for which an algorithm can always give a correct solution for every input. These problems can be solved using a finite sequence of steps, and the algorithm always stops after producing the correct output. Examples include arithmetic calculations, searching, sorting, and many standard computational tasks.
- A computable problem can be solved by an algorithm.
- The algorithm always produces the correct result for every valid input.
- The algorithm halts (stops) after a finite number of steps.
- Examples of computable problems include addition of numbers, finding the greatest common divisor (GCD), sorting a list, and searching for an element in a dataset.
- The term algorithm can also be represented using a computer program or a Turing Machine
### Examples of Computable Problems
These are four simple examples of the computable problem:
- Computing the [greatest common divisor](https://www.geeksforgeeks.org/maths/greatest-common-divisor-gcd/) of a pair of integers.
- Computing the least common multiple of a pair of integers.
- Finding the shortest path between a pair of nodes in a finite graph.
- Determining whether a propositional formula is a tautology.
![computable_problem_diagram](assets/computable_problem_diagram-a2965de671.webp)
| **Advantages** | **Disadvantages** |
| --- | --- |
| Efficient algorithms exist for many computable problems | Some computable problems require very high computation time |
| Provide practical and reliable solutions | Large memory or resources may be required |
| Well-defined inputs and outputs make behavior predictable | Performance degrades for very large inputs |
| Easy to analyze and verify correctness | Not all computable problems are practically feasible |
## Non-Computable Problems
A non-computable problem is one for which no algorithm can always give a correct solution. The most famous example is the Halting Problem, which asks whether a program (or Turing machine) will stop or run forever for a given input. Since some programs may loop infinitely, no general algorithm can solve this problem for all cases.
- A non-computable problem cannot be solved by any algorithm.
- The Halting Problem is the most famous example of a non-computable problem.
- It determines whether a program halts or runs forever for a given input.
- Programs that loop infinitely make this problem undecidable.
- The term “computer program” can be replaced by “Turing machine” or “algorithm”.
### Examples of Non-Computable Problems
**Halting Problem:** The problem of determining whether a program (or Turing machine) will halt or run forever for a given input is non-computable. No algorithm can solve this problem for all possible programs and inputs.
![non_computable_problem_diagram](assets/non_computable_problem_diagram-7d96ad03cc.webp)
| **Advantages** | **Disadvantages** |
| --- | --- |
| Cover deep questions beyond algorithmic solutions | No algorithm exists to solve them |
| Encourage research in math, logic, and computation | Cannot be applied directly to real-world tasks |
| Help define the limits of machine computation | Often involve infinite or undefined computations |
| Lead to new theories and computational models | Difficult to analyze or verify conclusively |
## **Proving Computability or Non-Computability**
We can show that a problem is computable by describing a procedure and proving that the procedure always terminates and always produces the correct answer. It is enough to provide a convincing argument that such a procedure exists. Finding the actual procedure is not necessary (but often helps to make the argument more convincing).
- To show that a problem is not computable, we need to show that no algorithm exists that solves the problem.
- Since there are an infinite number of possible procedures, we cannot just list all possible procedures and show why each one does not solve the problem.
- Instead, we need to construct an argument showing that if there were such an algorithm, it would lead to a contradiction.
- The core of our argument is based on knowing the Halting Problem is non-computable.
- If a solution to some new problem P could be used to solve the Halting Problem, then we know that P is also non-computable.
- That is, no algorithm exists that can solve P since if such an algorithm exists, it could be used to also solve the Halting Problem, which we already know is impossible.
- The proof technique where we show that a solution for some problem P can be used to solve a different problem Q is known as a reduction.
- A problem Q is reducible to a problem P if a solution to P could be used to solve Q.
- This means that problem Q is no harder than problem P since a solution to problem Q leads to a solution to problem P.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/computable-and-non-computable-problems-in-toc/)

## GATE CS

- Subject: Theory of Computation
- Topic: Turing Machines and Undecidability

> [!note] Related notes
>
> - [[Construct a Turing machine for L = {aibjck i j = k; i, j, k ≥ 1}]]
> - [[Construct a Turing Machine for language L = {0n1n2n n≥1}]]
> - [[Construct a Turing Machine for language L = {ww w ∈ {0,1}}]]
> - [[Construct a Turing Machine for language L = {wwr w ∈ {0, 1}}]]
> - [[Decidability]]
> - [[Decidable and undecidable problems]]
> - [[Halting Problem]]
> - [[Introduction to NP-Completeness]]
> - [[Introduction to Recursive and Recursive Enumerable Languages]]
> - [[Introduction to Turing Machine]]
