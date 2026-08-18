---
title: "Union Process in DFA"
subject: "Theory of Computation"
topic: "Regular Expression, Languages,Grammar, and Finite Automata"
source: "https://www.geeksforgeeks.org/theory-of-computation/union-process-in-dfa/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Regular Expression, Languages,Grammar, and Finite Automata"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/regular-expression-languages-grammar-and-finite-automata
---


> [!abstract] Union Process in DFA
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Regular Expression, Languages,Grammar, and Finite Automata`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/union-process-in-dfa/)

---

# Union Process in DFA

In theory of computation, union of two Deterministic Finite Automata (DFAs) is an operation used to construct a new DFA that recognizes union of languages accepted by the original automata. For example, two DFAs each recognizing a language L1​ and L2​ respectively, their union DFA will accept any string that belongs to either L1​ or L2​.
## **Constructing a DFA for the Union of Two DFAs**
To perform the union operation on two deterministic finite automata (DFAs), the following steps can be taken:
**Step 1:** Create a new DFA with a new set of states, consisting of all the states from both original DFAs.
**Step 2:** Define the initial state of the new DFA to be the tuple (q1, q2), where q1 and q2 are the initial states of the original DFAs.
**Step 3:** For each state in the new DFA, define the transition function by taking the union of the transition functions of the original DFAs. For example, if the transition function for the first DFA is δ1(q1, a) = q2, and the transition function for the second DFA is δ2(q3, a) = q4, then the transition function for the new DFA is δ( (q1,q3), a ) = (q2,q4). 
**Step 4:** Define the set of final states of the new DFA to be the union of the sets of final states of the original DFAs.
**Step 5:** The resulting DFA will recognize the language that is the union of the languages recognized by the original DFAs.
### Example
Let's understand the Union process in Deterministic Finite Automata (DFA) with the help of the below example. Designing a DFA for the set of string over {a, b} such that the string of the language start and end with different symbols. These two desired languages will be formed:
> L1 = {ab, aab, aabab, .......}
> L2 = {ba, bba, bbaba, .......}
L1= {starts with a and ends with b } and L2= {starts with b and ends with a}. Then L= L1 ∪ L2 or L=L1 + L2 
**State Transition Diagram for the language L**1**:** 
![](assets/TOC7-da32d80bf2.png)
State Transition Diagram
This DFA accepts all the string starting with a and ending with b. Here, State A is initial state and state C is final state. 
**State Transition Diagram for the language L**2**:** 
![](assets/TOC8-0740851694.png)
State Transition Diagram
This DFA accepts all the strings starting with b and ending with a. Here, State A is the initial state and state C is the final state. Now, Taking the union of L1 and L2 language gives the final result of the language which starts and ends with different elements. 
**State Transition Diagram of L**1** **∪ L**2**:** 
![](assets/TOC9-c37cb2f1a9.png)
State Transition Diagram
Thus as we see that L1 and L2 have been combined through the union process and this final DFA accept all the language containing strings starting and ending with different symbols. 
**Note:** From the above example, we can also infer that regular languages are closed under union(i.e. Union of two regular languages is also regular).
## Applications of Union in DFAs
- **Lexical Analysis of Compilers:** Union of DFAs allows for the creation of lexical analyzers that recognize more than one token pattern in one pass.
- **Pattern Matching in Text Processing:** Union operations permit the union of various search patterns into a single automaton to scan text efficiently.
- **Merging Several Language Acceptors:** Union makes it possible to merge individual DFAs to create automata that accept the union of several regular languages.
- **Designing Complicated Input Validators:** Union of DFAs is employed to check inputs that should conform to one out of many format rules.
- **Simplifying Automata-Based Protocols:** Union operations aid in modeling communication protocols that support different valid message formats.
- **Automated Testing Tools:** Union of DFAs helps to create test cases that cater to varied input scenarios by merging assorted input patterns.
## Limitations and Considerations
- **State Explosion Problem in Product Construction:** The intersection of two DFAs tends to cause the resulting combined automaton to have an equivalent state space size equal to the product of the original states, which causes it to grow exponentially.
- **Increased Requirements for Memory and Processing:** More computation is needed for larger DFAs, which can affect performance in real-world applications.
- **Alternative Solutions Using NFAs:** Non-deterministic Finite Automata (NFAs) provide a more space-efficient representation for union operations, which usually yields fewer states.
- **Regex Simplification Conversions:** Converting DFA to regular expression and then reversing could sometimes yield simpler automata for union but can complicate the conversion.
- **Trade-offs Between Determinism and Efficiency:** While DFAs guarantee deterministic processing, NFAs and regex-based techniques can provide more efficient union constructions but at the expense of non-determinism.
- **Minimization Techniques as Mitigation:** DFA minimization algorithms can be applied after union to minimize the number of states and increase efficiency.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/union-process-in-dfa/)

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
