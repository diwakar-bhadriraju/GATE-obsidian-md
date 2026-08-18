---
title: "Halting Problem in Theory of Computation"
subject: "Theory of Computation"
topic: "Turing Machines and Undecidability"
source: "https://www.geeksforgeeks.org/theory-of-computation/halting-problem-in-theory-of-computation/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Turing Machines and Undecidability"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/turing-machines-and-undecidability
---


> [!abstract] Halting Problem in Theory of Computation
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Turing Machines and Undecidability`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/halting-problem-in-theory-of-computation/)

---

# Halting Problem in Theory of Computation

The Halting Problem is a fundamental concept in the theory of computation. It deals with determining whether a computer program will halt (terminate) or run indefinitely when executed with a given input. A program is said to halt if it completes execution by accepting or rejecting the input, rather than entering an infinite loop.
- The Halting Problem asks whether a program will terminate or run forever.
- It considers a program and a specific input.
- Halting means the program stops execution after producing an output.
- There is no universal algorithm to determine halting for all programs.
- The problem is undecidable, as proven by Alan Turing.
- Applies to programs written in any programming language (C, C++, Java, etc.).
### **Concepts Related to the Halting Problem**
To understand better the halting problem, we must know [Decidability](https://www.geeksforgeeks.org/theory-of-computation/decidability-and-undecidability-in-toc/), [Undecidability](https://www.geeksforgeeks.org/theory-of-computation/undecidability-and-reducibility-in-toc/) and [Turing machine](https://www.geeksforgeeks.org/theory-of-computation/turing-machine-in-toc/), [decision problems](https://www.geeksforgeeks.org/theory-of-computation/decidable-and-undecidable-problems-in-theory-of-computation/) and also a theory named as Computability theory and Computational complexity theory. Some important terms:
- **Computability Theory** – It is a branch of the theory of computation that studies which problems can be solved using computational models. It focuses on determining whether a problem is solvable or not. Computational complexity refers to the amount of resources, such as time and space, required by an algorithm to solve a problem.
- **Decision Problems** – A decision problem is one that gives only two outputs: yes or no. It is framed as a question about input values, such as whether a solution exists. These problems are defined over an infinite set of inputs.
- **Turing Machine** – A Turing machine is a mathematical model of computation that represents a general-purpose computer. It performs co
## **Proof by Contradiction**
**Problem statement:** Can we design a machine which if given a program can find out if that program will always halt or not halt on a particular input?
**Solution:**
**1. Assumption:** Suppose we can design such a machine, called **HM(P, I)**, where:
- **HM** is the hypothetical machine/program.
- **P** is the program.
- **I** is the input.
When provided with these inputs, HM will determine whether program P halts or not.
**2. Constructing a Contradiction:** Using HM, we can create another program, called **CM(X)**, where **X** is any program passed as an argument as shown in figure.![](assets/halt1-1-c1990a16c4.png)
**3. Behavior of CM(X):** In CM(X), we call HM with inputs (X, X), meaning we pass program X both as the program and as its input. HM(X, X) will return either "Halt" or "Not Halt."
- If HM(X, X) predicts that X halts, CM(X) will enter an infinite loop.
- If HM(X, X) predicts that X does not halt, CM(X) will halt immediately.
**4. The Contradiction:** Now, consider what happens if we pass CM itself as an argument: **CM(CM)**.
- If HM predicts that CM(CM) halts, CM will loop indefinitely (contradicting HM's prediction).
- If HM predicts that CM(CM) does not halt, CM will halt immediately (again contradicting HM).
![](assets/halt2-d860f39c67.png)
In both scenarios, we face a contradiction. Therefore, our initial assumption that such a machine HM could exist must be false. Hence we can conclude that Halting Problem is undecidable. No general algorithm can determine whether every program will halt or not.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/halting-problem-in-theory-of-computation/)

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
> - [[Introduction to NP-Completeness]]
> - [[Introduction to Recursive and Recursive Enumerable Languages]]
> - [[Introduction to Turing Machine]]
