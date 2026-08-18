---
title: "Conversion from NFA to DFA"
subject: "Theory of Computation"
topic: "Regular Expression, Languages,Grammar, and Finite Automata"
source: "https://www.geeksforgeeks.org/theory-of-computation/conversion-from-nfa-to-dfa/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Regular Expression, Languages,Grammar, and Finite Automata"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/regular-expression-languages-grammar-and-finite-automata
---


> [!abstract] Conversion from NFA to DFA
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Regular Expression, Languages,Grammar, and Finite Automata`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/conversion-from-nfa-to-dfa/)

---

# Conversion from NFA to DFA

An NFA can have zero, one or more than one move from a given state on a given input symbol. An NFA can also have NULL moves (moves without input symbol). On the other hand, DFA has one and only one move from a given state on a given input symbol. 
## Steps for converting NFA to DFA:
**Step 1: Convert the given NFA to its equivalent transition table**
To convert the NFA to its equivalent transition table, we need to list all the states, input symbols, and the transition rules. The transition rules are represented in the form of a matrix, where the rows represent the current state, the columns represent the input symbol, and the cells represent the next state. 
**Step 2: Create the DFA's start state**
The DFA's start state is the set of all possible starting states in the NFA. This set is called the "epsilon closure" of the NFA's start state. The epsilon closure is the set of all states that can be reached from the start state by following epsilon (?) transitions.
**Step 3: Create the DFA's transition table**
The DFA's transition table is similar to the NFA's transition table, but instead of individual states, the rows and columns represent sets of states. For each input symbol, the corresponding cell in the transition table contains the epsilon closure of the set of states obtained by following the transition rules in the NFA's transition table.
**Step 4: Create the DFA's final states**
The DFA's final states are the sets of states that contain at least one final state from the NFA.
**Step 5: Simplify the DFA**
The DFA obtained in the previous steps may contain unnecessary states and transitions. To simplify the DFA, we can use the following techniques:
- Remove unreachable states: States that cannot be reached from the start state can be removed from the DFA.
- Remove dead states: States that cannot lead to a final state can be removed from the DFA.
- Merge equivalent states: States that have the same transition rules for all input symbols can be merged into a single state.
**Step 6: Repeat steps 3-5 until no further simplification is possible**
After simplifying the DFA, we repeat steps 3-5 until no further simplification is possible. The final DFA obtained is the minimized DFA equivalent to the given NFA.
**Example:** Consider the following NFA shown in Figure 1. 
![](assets/nfatofdfa_Figure1-1d7a1ae169.png)
Following are the various parameters for NFA. Q = { q0, q1, q2 } Σ = ( a, b ) F = { q2 } δ (Transition Function of NFA) 
![](assets/nfatofdfa_table1-ea118da6c9.png)
Step 1: Q’ = ∅ Step 2: Q’ = {q0} Step 3: For each state in Q’, find the states for each input symbol. Currently, state in Q’ is q0, find moves from q0 on input symbol a and b using transition function of NFA and update the transition table of DFA. δ’ = Transition Function of DFA
![](assets/nfatofdfa_table2-e4e3a8c276.png)
Now { q0, q1 } will be considered as a single state. As its entry is not in Q’, add it to Q’.
So Q’ = { q0, { q0, q1 } }
Now, moves from state { q0, q1 } on different input symbols are not present in transition table of DFA, we will calculate it like:
- δ’ ( { q0, q1 }, a ) = δ ( q0, a ) ∪ δ ( q1, a ) = { q0, q1 }
- δ’ ( { q0, q1 }, b ) = δ ( q0, b ) ∪ δ ( q1, b ) = { q0, q2 }
Now we will update the transition table of DFA. δ’ (Transition Function of DFA)
![](assets/nfatofdfa_table3-4f6bcb8d9f.png)
Now { q0, q2 } will be considered as a single state. As its entry is not in Q’, add it to Q’. So Q’ = { q0, { q0, q1 }, { q0, q2 } } Now, moves from state {q0, q2} on different input symbols are not present in transition table of DFA, we will calculate it like:
- δ’ ( { q0, q2 }, a ) = δ ( q0, a ) ∪ δ ( q2, a ) = { q0, q1 }
- δ’ ( { q0, q2 }, b ) = δ ( q0, b ) ∪ δ ( q2, b ) = { q0 }
Now we will update the transition table of DFA. δ’ (Transition Function of DFA) 
![](assets/nfatofdfa_table4-e04a15ca29.png)
As there is no new state generated, we are done with the conversion. Final state of DFA will be state which has q2 as its component i.e., { q0, q2 } Following are the various parameters for DFA.
- Q’ = { q0, { q0, q1 }, { q0, q2 } }
- Σ = { a, b }
- F = { { q0, q2 } }
- δ’ as shown above
The final DFA for above NFA has been shown in Figure 2. 
![](assets/nfatofdfa_Figure2-51afd6633a.png)
**Note :** Sometimes, it is not easy to convert regular expression to DFA. First you can convert regular expression to NFA and then NFA to DFA.
**Question :** The number of states in the minimal deterministic finite automaton corresponding to the regular expression (0 + 1)\* (10) is \_\_\_\_\_\_\_\_\_\_\_\_. 
**Solution :** First, we will make an NFA for the above expression. To make an NFA for (0 + 1)\*, NFA will be in same state q0 on input symbol 0 or 1. Then for concatenation, we will add two moves (q0 to q1 for 1 and q1 to q2 for 0) as shown in Figure 3. 
![](assets/nfatofdfa_Figure3-ca012a3082.png)
![](assets/nfatofdfa_table5-48c8dd47ed.png)
![](assets/nfatofdfa_Figure4-83a9cc42d1.png)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/conversion-from-nfa-to-dfa/)

## GATE CS

- Subject: Theory of Computation
- Topic: Regular Expression, Languages,Grammar, and Finite Automata

> [!note] Related notes
>
> - [[Chomsky Hierarchy]]
> - [[Closure properties of Regular languages]]
> - [[Concatenation process in DFA]]
> - [[Designing Deterministic Finite Automata]]
> - [[Designing Deterministic Finite Automata Set 1]]
> - [[Designing Deterministic Finite Automata Set 2]]
> - [[Designing Finite Automata from Regular Expression]]
> - [[Designing Non-Deterministic Finite Automata]]
> - [[Designing Non-Deterministic Finite Automata (2)]]
> - [[DFA for accepting the language L = {anbm n+m=even}]]
