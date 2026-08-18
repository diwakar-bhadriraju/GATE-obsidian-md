---
title: "Propositional Equivalences"
subject: "Discrete Mathematics"
topic: "Propositional and First-Order Logic"
source: "https://www.geeksforgeeks.org/engineering-mathematics/mathematical-logic-propositional-equivalences/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Propositional and First-Order Logic"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/propositional-and-first-order-logic
---


> [!abstract] Propositional Equivalences
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Propositional and First-Order Logic`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/mathematical-logic-propositional-equivalences/)

---

# Propositional Equivalences

Propositional equivalences are logical relationships in which two or more propositions have the same truth value in every possible case.
- Two propositions P and Q are said to be logically equivalent if they have identical truth tables.
- This relationship is denoted as P ≡ Q.
- It helps in simplifying and solving logical expressions.
![propositional_equivalence](assets/propositional_equivalence-ca74595064.webp)
Some of the key propositional equivalences are given below:
##### 1. **Identity Laws**
> - P∧ true ≡ P
> - P∨ false ≡ P
##### 2**. Domination Laws**
> - P∨ true ≡ true
> - P∧ false ≡ false
##### 3**. Idempotent Laws**
> - P∨ P ≡ P
> - P∧ P ≡ P
##### 4**. Double Negation Law**
> - ¬(¬P) ≡ P
##### 5**. Commutative Laws**
> - P∨ Q ≡ Q∨ P
> - P∧ Q ≡ Q∧ P
##### 6**. Associative Laws**
> - (P ∨ Q) ∨ R ≡ P ∨ (Q ∨ R )
> - (P ∧ Q) ∧ R ≡ P ∧ (Q ∧ R)
##### 7. **Distributive Laws**
> - P ∨ (Q ∧ R) ≡ (P ∨ Q) ∧ (P ∨ R)
> - P ∧ (Q∨ R) ≡ (P ∧ Q) ∨ (P ∧ R)
##### 8. **De Morgan's Laws**
> - ¬(P ∧ Q) ≡ ¬P ∨ ¬Q
> - ¬(P ∨ Q) ≡ ¬P ∧ ¬Q
##### 9**. Absorption Laws**
> - P∨ (P ∧ Q) ≡P
> - P∧ (P ∨ Q) ≡P
##### 10**. Negation Laws**
> - P ∨ ¬P ≡true
> - P ∧ ¬P ≡ false
### Applications
**1. Digital Logic Design**: Propositional equivalences are used to simplify Boolean expressions, which helps in designing simpler, faster, and more efficient digital circuits.
**2. Software Engineering**: They help simplify conditional statements and logical expressions in programs, making the code easier to read, understand, and optimize.
**3. Theoretical Computer Science**: Propositional equivalences are used to analyze algorithms, prove logical correctness, and improve computational efficiency.
**4. Control Systems**: They are used to simplify logical conditions in control systems, helping systems work more accurately, efficiently, and reliably.
**➢Practice:**[Solved Examples](https://www.geeksforgeeks.org/maths/propositional-equivalences-practice-questions/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/mathematical-logic-propositional-equivalences/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Propositional and First-Order Logic

> [!note] Related notes
>
> - [[Consensus Theorem]]
> - [[Introduction to Propositional Logic]]
> - [[Predicates and Quantifiers Set 1]]
> - [[Predicates and Quantifiers Set 2]]
> - [[Proposition Laws and Algebra]]
> - [[Rules of Inference]]
> - [[Some theorems on Nested Quantifiers]]
> - [[Binomial Coefficients]]
> - [[Cartesian Product of Two Sets]]
> - [[Classes of Functions]]
