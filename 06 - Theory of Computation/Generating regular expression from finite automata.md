---
title: "Generating Regular Expression from Finite Automata"
subject: "Theory of Computation"
topic: "Regular Expression, Languages,Grammar, and Finite Automata"
source: "https://www.geeksforgeeks.org/theory-of-computation/generating-regular-expression-from-finite-automata/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Regular Expression, Languages,Grammar, and Finite Automata"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/regular-expression-languages-grammar-and-finite-automata
---


> [!abstract] Generating Regular Expression from Finite Automata
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Regular Expression, Languages,Grammar, and Finite Automata`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/generating-regular-expression-from-finite-automata/)

---

# Generating Regular Expression from Finite Automata

Finite Automata and Regular Expressions are two ways to represent patterns in strings within formal language theory. While Finite Automata use states and transitions, Regular Expressions provide a compact symbolic notation.
Converting a Finite Automaton into a Regular Expression helps to understand their equivalence and is useful in fields like compiler design and text processing.
### **1. State Elimination Method**
**Step 1:** If the initial state is either an accepting state or has incoming transitions, introduce a new non-accepting start state. Then, add an
$$
\epsilon
$$
-transition (epsilon transition) from the new start state to the original start state.
**Step 2:** If there are multiple accepting states, or if the single accepting state has outgoing transitions, create a new accepting state. Change all other accepting states to non-accepting states. Add
$$
\epsilon
$$
-transitions from each former accepting state to this new accepting state.
**Step 3:** For each state that is neither a start nor an accepting state, eliminate the state and update the transitions accordingly to maintain the functionality of the automaton.
**Example**:
![](assets/Regular_Expression_from_automata_1-24e0aab458.jpg)
**Solution:**
### **2. Arden’s Theorem**
Let P and Q be 2 regular expressions. If P does not contain null string, then the following equation in R, viz R = Q + RP, Has a unique solution by R = QP\*
**Assumptions -**
- The transition diagram should not have
$$
\epsilon
$$
  -moves.
- It must have only one initial state.
**Using Arden’s Theorem to find Regular Expression of Deterministic Finite automata -**
1. For getting the regular expression for the automata we first create equations of the given form for all the states **q**1** **= q**1**w**11** **+q**2**w**21** **+…+q**n**w**n1** **+**
$$
\epsilon
$$
    **(q**1** **is the initial state) q**2** **= q**1**w**12** **+q**2**w**22** **+…+q**n**w**n2** **. . . q**n** **= q**1**w**1n** **+q**2**w**2n** **+…+q**n**w**nn**wij is the regular expression representing the set of labels of edges from qi to qj
   **Note -** For parallel edges there will be that many expressions for that state in the expression.
2. Then we solve these equations to get the equation for qi in terms of wij and that expression is the required solution, where qi is a final state.
**Example:** ![](assets/Regular_Expression_from_automata_8-1-1719e8d0c9.jpg)**Solution:** Here the initial state is q1 and the final state is q1. The equations for the three states q1, q2, and q3 are as follows:
We are given the following equations for three states: q1, q2, and q3:
- q1 = q1a + q3a +
$$
\epsilon
$$
   (since q1 is the initial state, we have an epsilon transition)
- q2 = q1b + q2b + q3b
- q3 = q2a
Solving the Equations:
**Step 1: Solve for q2**
- Start by substituting the value of q3 into the equation for q2: q2 = q1b + q2b + q3b
- Substituting q3 = q2a: q2 = q1b + q2b + (q2a)b
- Simplify the expression: q2 = q1b + q2(b + ab)
Now, apply Arden's Theorem to simplify further: q2 = q1b (b + ab)\*
**Step 2: Solve for q1**
- Now substitute the value of q2 into the equation for q1: q1 = q1a + q3a +
$$
\epsilon
$$
- Substitute q3 = q2a: q1 = q1a + q2aa +
$$
\epsilon
$$
- Substitute the value of q2 = q1b(b + ab)\*: q1 = q1a + q1b(b + ab)\*aa +
$$
\epsilon
$$
- Simplify the expression: q1 = q1(a + b(b + ab)\*aa) +
$$
\epsilon
$$
- Finally, apply Arden's Theorem: q1 = (a + b(b + ab)\*aa)\*
Hence, the regular expression is **(a + b(b + ab)\*aa)\*.**
**GATE CS Corner Questions** Practicing the following questions will help you test your knowledge. All questions have been asked in GATE in previous years or in GATE Mock Tests. It is highly recommended that you practice them.
1. [GATE CS 2008, Question 52](https://www.geeksforgeeks.org/questions/match-the-following-nfas-with-the-regular-expressions-they/)
2. [GATE CS 2007, Question 74](https://www.geeksforgeeks.org/questions/consider-the-following-finite-state-automaton-the-language-accepted/)
3. [GATE CS 2014 (Set-1), Question 25](https://www.geeksforgeeks.org/questions/gate-gate-cs-2014-set-1-question-25/)
4. [GATE CS 2014 (Set-1), Question 65](https://www.geeksforgeeks.org/questions/which-of-the-regular-expressions-given-below-represent-the/)
5. [GATE IT 2006, Question 5](https://www.geeksforgeeks.org/questions/which-regular-expression-best-describes-the-language-accepted-by/)
6. [GATE CS 2013, Question 33](https://www.geeksforgeeks.org/questions/consider-the-dfa-given-which-of-the-following-are/)
7. [GATE CS 2012, Question 12](https://www.geeksforgeeks.org/theory-of-computation/gate-gate-cs-2012-question-16/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/generating-regular-expression-from-finite-automata/)

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
