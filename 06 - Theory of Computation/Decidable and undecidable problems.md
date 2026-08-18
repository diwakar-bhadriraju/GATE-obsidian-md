---
title: "Decidable and Undecidable Problems in Theory of Computation"
subject: "Theory of Computation"
topic: "Turing Machines and Undecidability"
source: "https://www.geeksforgeeks.org/theory-of-computation/decidable-and-undecidable-problems-in-theory-of-computation/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Turing Machines and Undecidability"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/turing-machines-and-undecidability
---


> [!abstract] Decidable and Undecidable Problems in Theory of Computation
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Turing Machines and Undecidability`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/decidable-and-undecidable-problems-in-theory-of-computation/)

---

# Decidable and Undecidable Problems in Theory of Computation

In the Theory of Computation, problems can be classified into decidable and undecidable categories based on whether they can be solved using an algorithm. A **decidable problem** is one for which a solution can be found in a finite amount of time, meaning there exists an algorithm that can always provide a correct answer. While an **undecidable problem** is one where no algorithm can be constructed to solve the problem for all possible inputs. In this article, we will discuss Decidable and Undecidable problems in detail.
## What are Decidable Problems?
A problem is said to be **Decidable** if we can always construct a corresponding **algorithm** that can answer the problem correctly. We can intuitively understand Decidable issues by considering a simple example. Suppose we are asked to compute all the prime numbers in the range of 1000 to 2000. To find the **solution** to this problem, we can easily construct an algorithm that can enumerate all the prime numbers in this range.
Now talking about Decidability in terms of a Turing machine, a problem is said to be a Decidable problem if there exists a corresponding Turing machine that **halts** on every input with an answer- **yes or no**. It is also important to know that these problems are termed **Turing Decidable** since a Turing machine always halts on every input, accepting or rejecting it.
### **Semi Decidable Problems**
Semi-decidable problems are those for which a Turing machine halts on the input accepted by it but it can either halt or loop forever on the input which the Turing Machine rejects. Such problems are termed as **Turing Recognisable** problems.
### Example
We will now consider some few important **Decidable** problems:
- **Are two regular languages L and M equivalent:** We can easily check this by using Set Difference operation. L-M =Null and M-L =Null. Hence (L-M) U (M-L) = Null, then L,M are equivalent.
- **Membership of a CFL:** We can always find whether a string exists in a given CFL by using an algorithm based on dynamic programming.
- Emptiness of a CFL By checking the production rules of the CFL we can easily state whether the language generates any strings or not.
## **What are Undecidable Problems?**
The problems for which we can’t construct an algorithm that can answer the problem correctly in finite time are termed as Undecidable Problems. These problems may be partially decidable but they will never be decidable. That is there will always be a condition that will lead the Turing Machine into an infinite loop without providing an answer at all.
We can understand Undecidable Problems intuitively by considering **Fermat's Theorem**, a popular Undecidable Problem which states that no three positive integers a, b and c for any n>2 can ever satisfy the equation: a^n + b^n = c^n. If we feed this problem to a Turing machine to find such a solution which gives a contradiction then a Turing Machine might run forever, to find the suitable values of n, a, b and c. But we are always unsure whether a contradiction exists or not and hence we term this problem as an Undecidable Problem.
### **Example**
These are few important **Undecidable Problems**:
- **Whether a CFG generates all the strings or not:** As a [Context Free Grammar](https://www.geeksforgeeks.org/theory-of-computation/what-is-context-free-grammar/) (CFG) generates infinite strings, we can’t ever reach up to the last string and hence it is Undecidable.
- **Whether two CFG L and M equal:** Since we cannot determine all the strings of any CFG, we can predict that two CFG are equal or not.
- **Ambiguity of CFG:** There exist no algorithm which can check whether for the ambiguity of a Context Free Language (CFL). We can only check if any particular string of the CFL generates two different parse trees then the CFL is ambiguous.
- **Is it possible to convert a given ambiguous CFG into corresponding non-ambiguous CFL:** It is also an Undecidable Problem as there doesn’t exist any algorithm for the conversion of an ambiguous CFL to non-ambiguous CFL.
- **Is a language Learning which is a CFL, regular:** This is an Undecidable Problem as we can not find from the production rules of the CFL whether it is regular or not.
> The most well-known undecidable problem is the [**Halting Problem**](https://www.geeksforgeeks.org/theory-of-computation/halting-problem-in-theory-of-computation/), which asks whether a given program will stop running (halt) or continue running forever for a particular input. It has been proven that no algorithm can solve this problem for all programs and inputs.
Some more **Undecidable Problems** related to Turing machine:
- **Membership** problem of a Turing Machine
- **Finiteness** of a Turing Machine
- **Emptiness** of a Turing Machine
- Whether the language accepted by Turing Machine is regular or CFL
## Difference Between Decidable and Undecidable Problems
| **Aspect** | **Decidable Problems** | **Undecidable Problems** |
| --- | --- | --- |
| **Definition** | Problems that can be solved by an algorithm that always gives a correct answer in a finite time. | Problems where no algorithm can give a solution for all possible cases. |
| **Solvability** | Always solvable using a step-by-step process (algorithm). | Cannot be solved for all inputs using a single algorithm. |
| **Algorithm** | There is an algorithm that works for every input and always finishes with an answer. | No algorithm can solve the problem for every input. |
| **Halting** | The algorithm stops (halts) and gives an answer for every input. | The algorithm might never stop for some inputs, or no algorithm exists. |
| **Examples** | Problems like checking if a number is even or odd, or if a string belongs to a regular language (like finding a match in a search). | Examples include the Halting Problem, where you can’t always tell if a program will finish running or run forever. |
| **Decision Procedure** | There’s a clear method to always reach a correct conclusion. | No guaranteed method exists to solve the problem in every case. |
| **Complexity** | May be complex but can always be computed. | Too complex to compute in general, and no universal solution exists. |
| **Applications** | Useful in practical computing tasks like compiling code or searching for text patterns. | Helps understand the limits of what computers can do, showing what problems are beyond computation. |
## Conclusion
In conclusion, decidable and undecidable problems highlight the boundaries of what computers can and cannot solve. **Decidable problems** have solutions that can always be found by an algorithm, making them predictable and useful in everyday computing tasks. On the other hand, **undecidable problems** demonstrate the limits of computation, where no algorithm can provide a solution for every possible case.
Understanding the difference between these two types of problems helps us recognize which problems are solvable and which ones are beyond the reach of algorithms.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/decidable-and-undecidable-problems-in-theory-of-computation/)

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
> - [[Halting Problem]]
> - [[Introduction to NP-Completeness]]
> - [[Introduction to Recursive and Recursive Enumerable Languages]]
> - [[Introduction to Turing Machine]]
