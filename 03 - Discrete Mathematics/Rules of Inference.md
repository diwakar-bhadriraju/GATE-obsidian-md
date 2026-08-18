---
title: "Rules of Inference"
subject: "Discrete Mathematics"
topic: "Propositional and First-Order Logic"
source: "https://www.geeksforgeeks.org/engineering-mathematics/rules-of-inference/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Propositional and First-Order Logic"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/propositional-and-first-order-logic
---


> [!abstract] Rules of Inference
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Propositional and First-Order Logic`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/rules-of-inference/)

---

# Rules of Inference

Rules of inference are logical patterns used to derive valid conclusions from given premises.
- They form the foundation of formal reasoning in mathematics, logic, and artificial intelligence by ensuring each step in a proof is logically correct.
- They are mainly divided into two categories: propositional logic and predicate logic
## For Propositional Logic
These rules operate on propositions (statements that are either true or false).
> They work on whole propositions using logical connectives like AND (∧), OR (∨), NOT (¬), and implication, ensuring each reasoning step is logically valid.
### 1. Modus Ponens (Law of Detachment)
If a conditional statement is true and its condition is satisfied, the conclusion must be true.
> **Form:** If p → q and p, then q.
**Example:**
> - Premise: If it rains, the ground will be wet.
> - Premise: It is raining.
> - Conclusion: The ground is wet.
### 2. Modus Tollens (Law of Contrapositive)
If a conditional statement is true, and its consequent is false, then its antecedent must also be false.
> **Form:** If p → q and ¬q, then ¬p.
**Example:**
> - Premise: If it rains, the ground will be wet.
> - Premise: The ground is not wet.
> - Conclusion: It is not raining.
### 3. Hypothetical Syllogism
If two conditional statements are true, where the consequent of the first is the antecedent of the second, then a third conditional statement combining the antecedent of the first and the consequent of the second is also true.
> **Form:** If p → q and q → r, then p → r.
**Example:**
> - Premise: If it rains, the ground will be wet.
> - Premise: If the ground is wet, the plants will grow.
> - Conclusion: If it rains, the plants will grow.
### 4. Disjunctive Syllogism
If a disjunction (an "or" statement) is true, and one of the disjuncts (the parts of the "or" statement) is false, then the other disjunct must be true.
> **Form:** If p ∨ q and ¬p, then q.
**Example:**
> - Premise: It is either raining or sunny.
> - Premise: It is not raining.
> - Conclusion: It is sunny.
### 5. Conjunction
If two statements are true, then their conjunction (an "and" statement) is also true.
> **Form:** If p and q, then p ∧ q.
**Example:**
> - Premise: It is raining.
> - Premise: It is windy.
> - Conclusion: It is raining and windy.
### 6. Simplification
If a conjunction (an "and" statement) is true, then each of its conjuncts is also true.
> **Form:** If p ∧ q, then p
**Example:**
> - Premise: It is raining and windy.
> - Conclusion: It is raining.
### 7. Addition
If a statement is true, then the disjunction (an "or" statement) of that statement with any other statement is also true.
> **Form:** If p, then p ∨ q
**Example:**
> - Premise: It is raining.
> - Conclusion: It is raining or sunny.
### 8. Absorption(Abs)
If a conditional statement (an "if-then" statement) is true, then the antecedent implies a conjunction of itself and the consequent.
> **Form:** If P→Q, then P→(P∧Q)
**Example**:
> - Premise: If it is raining, then the ground is wet.
> - Conclusion: If it is raining, then it is raining and the ground is wet.
### 9. Resolution
If two disjunctions ("or" statements) are true, and one contains a proposition (P) while the other contains its negation (¬P), then the disjunction of the remaining parts is true.
> **Form:**If P∨Q and ¬P∨R, then Q∨R.**
>
> **Example:** It is raining or snowing and not raining or cold, so it is snowing or cold.
| Rule of Inference | Tautology | Meaning |
| --- | --- | --- |
| **Modus Ponens** | (p ∧ (p → q)) → q | If p is true and p implies q, then q is true |
| **Modus Tollens** | (¬q ∧ (p → q)) → ¬p | If q is false and p implies q, then p is false |
| **Hypothetical Syllogism** | ((p → q) ∧ (q → r)) → (p → r) | If p leads to q and q leads to r, then p leads to r |
| **Disjunctive Syllogism** | ((p ∨ q) ∧ ¬p) → q | If one option is false, the other is true |
| **Conjunction** | (p ∧ q) → (p ∧ q) | If p and q are true, they can be combined |
| **Simplification** | (p ∧ q) → p | From a pair, one part is true |
| **Addition** | p → (p ∨ q) | A true statement can be extended with OR |
| **Absorption** | (p → q) → (p → (p ∧ q)) | A rule can be strengthened by including itself |
| **Resolution** | ((p ∨ q) ∧ (¬p ∨ r)) → (q ∨ r) | Eliminates contradiction to combine results |
## For Predicate Logic
Predicate logic uses all the propositional rules above, plus additional rules for handling quantifiers.
![rules_of_inference_for_predicate_logic](assets/rules_of_inference_for_predicate_logic-7972a3a6e2.webp)
> These rules help derive valid conclusions from statements containing variables, predicates, and quantifiers.
### **1. Universal Instantiation**
If a statement is true for all objects in a domain, it is true for any specific object.
> **Form:** ∀x P(x) ⟹ P(c)
> **Example:** If all humans are mortal, then Socrates is mortal.
### **2. Universal Generalization**
If a property holds for an arbitrary object, it holds for all objects.
> **Form:** P(c) ⟹ ∀x P(x)
> **Example:** If a randomly chosen number is even, then all numbers are even (under a given proof condition).
### **3. Existential Instantiation**
If something exists in a domain, we can assign a name to it.
> **Form:** ∃x P(x) ⟹ P(c)
> **Example:** If there exists a student who passed, then we can call that student “A”.
### **4. Existential Generalization**
If a property holds for a specific object, then something exists with that property.
> **Form:** P(c) ⟹ ∃x P(x)
> **Example:** If Ram is intelligent, then there exists someone who is intelligent.
| Rule of Inference | Form | Meaning |
| --- | --- | --- |
| Universal instantiation | ∀xP(x) ⇒ P(c) | If something is true for all x, it is true for a particular case c |
| Universal generalization | P(c) ⇒ ∀x P(x) | If something is true for any arbitrary element, it’s true for all. |
| Existential instantiation | ∃xP(x) ⇒ P(c) | If something exists, we can give it a name (c). |
| Existential generalization | P(c)⇒ ∃x P(x) | If something is true for a particular c, it’s true for “some x”. |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/rules-of-inference/)

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
> - [[Propositional Equivalence]]
> - [[Some theorems on Nested Quantifiers]]
> - [[Binomial Coefficients]]
> - [[Cartesian Product of Two Sets]]
> - [[Classes of Functions]]
