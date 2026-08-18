---
title: "Mealy Machine vs Moore Machine"
subject: "Theory of Computation"
topic: "Regular Expression, Languages,Grammar, and Finite Automata"
source: "https://www.geeksforgeeks.org/theory-of-computation/difference-between-mealy-machine-and-moore-machine/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Regular Expression, Languages,Grammar, and Finite Automata"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/regular-expression-languages-grammar-and-finite-automata
---


> [!abstract] Mealy Machine vs Moore Machine
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Regular Expression, Languages,Grammar, and Finite Automata`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/difference-between-mealy-machine-and-moore-machine/)

---

# Mealy Machine vs Moore Machine

Mealy Machines and Moore Machines are important computational models studied in the Theory of Computation and Automata. These machines help represent the behavior of computer systems and digital circuits through state diagrams. While both rely on transition functions, the method of generating output for a given input differs between them. This article covers the concepts of Mealy and Moore Machines, their diagrams, and a comparison of their characteristics.
## Mealy Machine
Mealy Machine is defined as a machine in the theory of computation whose output values are determined by both its current state and current inputs. In this machine at most one transition is possible. 
It has 6 tuples: (Q, q0, ∑, ▲, δ, λ’) 
- Q is a finite set of states
- q0 is the initial state
- ∑ is the input alphabet
- ▲ is the output alphabet
- δ is the transition function that maps Q×∑ → Q
- ‘λ’ is the output function that maps Q×∑→ ▲
The diagram is as follows:
![Mealy Machine](assets/11-23-7c86ec046b.png)
## **Moore Machine**
Moore's machine is defined as a machine in the theory of computation whose output values are determined only by its current state. It has also 6 tuples
```
(Q, q0, ∑, ▲, δ, λ) 
```
1. Q is a finite set of states
2. q0 is the initial state
3. ∑ is the input alphabet
4. ▲ is the output alphabet
5. δ is the transition function that maps Q×∑ → Q
6. λ is the output function that maps Q → ▲
**Diagram:**
![Moore Machine](assets/22-9-673eab18e5.png)
## Difference Between Mealy Machine and Moore Machine
State machines such as Mealy and Moore play a vital role in digital system design and automata theory. To better understand their differences and real-world applications, the [**GATE CS Self-Paced Course**](https://www.geeksforgeeks.org/courses/category/gate) provides in-depth lessons on finite automata and their practical use, making it an excellent resource for GATE aspirants.
The differences between the Mealy machine and Moore machine is as follows:
| **Moore Machine** | **Mealy Machine** |
| --- | --- |
| Output depends only upon the present state. | Output depends on the present state as well as present input. |
| [Moore machine](https://www.geeksforgeeks.org/theory-of-computation/mealy-and-moore-machines-in-toc/) also places its output in the state. | [Mealy Machine](https://www.geeksforgeeks.org/theory-of-computation/mealy-and-moore-machines-in-toc/) places its output on the transition. |
| More states are required. | Less number of states are required. |
| Moore machines requires more hardware requirement for circuit implementation. | Mealy Machines requires less hardware requirement for circuit implementation. |
| They react slower to inputs(One clock cycle later). | They react faster to inputs. |
| Synchronous output and state generation. | Asynchronous output generation. |
| Output is placed on states. | Output is placed on transitions. |
| Easy to design. | It is difficult to design. |
| Has more or the same states as that of the Mealy machine. | Has fewer or the same states as that of the Moore machine. |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/difference-between-mealy-machine-and-moore-machine/)

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
