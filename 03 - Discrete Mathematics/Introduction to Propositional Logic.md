---
title: "Propositional Logic"
subject: "Discrete Mathematics"
topic: "Propositional and First-Order Logic"
source: "https://www.geeksforgeeks.org/engineering-mathematics/proposition-logic/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Propositional and First-Order Logic"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/propositional-and-first-order-logic
---


> [!abstract] Propositional Logic
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Propositional and First-Order Logic`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/proposition-logic/)

---

# Propositional Logic

Propositional logic (also called sentential logic) is a branch of formal logic that deals with propositions: statements that are either true or false, and the logical relationships between them, using connectives like "and," "or," "not," and "if...then."
### **Propositions**
A proposition is a declarative statement that has a definite truth value. For example:
| Statement | Truth Value |
| --- | --- |
| The sun rises in the East and sets in the West. | **True** |
| 1 + 1 = 2 | **True** |
| ‘b’ is a vowel. | **False** |
All of the above are propositions because each has a definite truth value.
Two main types of propositions:
1. **Atomic Propositions:** A simple statement without logical connectives that cannot be broken down further.
2. **Compound Propositions:** A statement formed by combining atomic propositions using logical connectives like AND, OR, or NOT.
**Non-Propositions:** Questions, commands, and opinions are not propositions because they don’t have a definite truth value or may vary depending on context:
- “What time is it?” (Question)
- “Go out and play.” (Command)
- “x + 1 = 2” (Open sentence — depends on the value of x)
## Logical Connectives
Logical connectives combine simple propositions into compound ones using a small set of connectives:
![Propositional-logic](assets/Propositional-logic-9ba8e8bf1c.webp)
The truth value of a compound proposition depends on the truth values of its parts across every possible scenario, we consider all possible combinations of the propositions joined by a connective.
This compilation of all possible scenarios in tabular format is called a truth table.
### **1. Negation**
If **p** is a proposition, then the negation of **p** is denoted by **¬p**, which, when translated to simple English, means "It is not the case that p" or simply "not p." The truth value of -p is the opposite of the truth value of p. The truth table of -p is:
| p | ¬p |
| --- | --- |
| T | F |
| F | T |
**Example:** Negation of "It is raining today" is "It is not the case that it is raining today" or simply "It is not raining today." 
### **2. Conjunction**
For any two propositions **p** and **q**, their conjunction is denoted by p∧q, which means "**p** and **q."** The conjunction p∧q is True when both **p** and q are True, otherwise False. The truth table of p∧q is:
| p | q | p ∧ q |
| --- | --- | --- |
| T | T | T |
| T | F | F |
| F | T | F |
| F | F | F |
**Example:** Conjunction of the propositions **p**—"Today is Friday" and **q**—"It is raining today," p∧q, is "Today is Friday and it is raining today." This proposition is true only on rainy Fridays and is false on any other rainy day or on Fridays when it does not rain. 
### **3. Disjunction**
For any two propositions p and q, their disjunction is denoted by p∨q, which means "p or **q."** The disjunction p∨q is True when either **p** or **q** is True, otherwise False. The truth table of p∨q is:
| p | q | p ∨ q |
| --- | --- | --- |
| T | T | T |
| T | F | T |
| F | T | T |
| F | F | F |
**Example:** Disjunction of the propositions **p**—"Today is Friday" and q—"It is raining today," p∨q, is "Today is Friday or it is raining today." This proposition is true on any day that is a Friday or a rainy day (including rainy Fridays) and is false on any day other than Friday when it also does not rain. 
### **4. Exclusive Or**
For any two propositions **p** and **q**, their exclusive or is denoted by p⊕q, which means "either **p** or **q** but not both." The exclusive or p⊕q is True when either **p** or **q** is True, and False when both are true or both are false. The truth table of p⊕q is:
| p | q | p ⊕ q |
| --- | --- | --- |
| T | T | F |
| T | F | T |
| F | T | T |
| F | F | F |
**Example:** Exclusive or of the propositions **p**—"Today is Friday" and **q**—"It is raining today," p⊕q is "Either today is Friday or it is raining today, but not both." This proposition is true on any day that is a Friday or a rainy day (not including rainy Fridays) and is false on any day other than Friday when it does not rain or rainy Fridays. 
### **5. Implication**
For any two propositions, **p** and **q**, the statement "if **p** then **q**" is called an implication, and it is denoted by **p**→**q**. In the implication p→q, **p** is called the hypothesis or antecedent or premise, and **q** is called the conclusion or consequence. The implication is that **p**→**q** is also called a conditional statement. The implication is false when **p** is true and **q** is false; otherwise, it is true. The truth table of **p**→**q** is:
| p | q | p → q |
| --- | --- | --- |
| T | T | T |
| T | F | F |
| F | T | T |
| F | F | T |
One might wonder why p→q is true when **p** is false. This is because the implication guarantees that when **p** and q are true, then the implication is true. But the implication does not guarantee anything when the premise **p** is false.
There is no way of knowing whether or not the implication is false since **p** did not happen. This situation is similar to the "Innocent until proven Guilty" stance, which means that the implication **p**→**q** is considered true until proven false. Since we cannot call the implication **p**→**q** false when **p** is false, our only alternative is to call it true.
This follows from the Explosion Principle which says: "A False statement implies anything." Conditional statements play a very important role in mathematical reasoning; thus, a variety of terminology is used to express p → q, some of which are listed below.
> "If p, then "q"p is sufficient for q""q when p""a necessary condition for p is q""p only if q""q unless ≠p""q follows from p"
**Example:** "If it is Friday, then it is raining today" is a proposition that is of the form **p**→**q**. The above proposition is true if it is not Friday (premise is false) or if it is Friday and it is raining, and it is false when it is Friday but it is not raining. 
### 6. Biconditional or Double Implication
For any two propositions **p** and **q**, the statement "**p** if and only if (iff) q" is called a biconditional, and it is denoted by **p**↔**q**. The statement **p**↔**q** is also called a bi-implication.  **p**↔**q** has the same truth value as (**p**→**q)** ∧ (**q**→**p)**. The biconditional is true when p and q have the same truth values and is false otherwise.
The truth table of **p**↔**q** is:
| p | q | p ↔ q |
| --- | --- | --- |
| T | T | T |
| T | F | F |
| F | T | F |
| F | F | T |
Some other common ways of expressing **p**↔**q** are:
"p is necessary and sufficient for q," "if p then q, and conversely," "p only if q, and q only if p."
**Example:** "It is raining today if and only if it is Friday today" is a proposition of the form p↔q. This proposition is true if it is Friday and it is raining, or if it is not Friday and it is not raining. It is false if it is Friday but it is not raining, or if it is not Friday but it is raining.
**➢Practice:** [Solved Examples](https://www.geeksforgeeks.org/maths/propositional-logic-practie-problems/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/proposition-logic/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Propositional and First-Order Logic

> [!note] Related notes
>
> - [[Consensus Theorem]]
> - [[Predicates and Quantifiers Set 1]]
> - [[Predicates and Quantifiers Set 2]]
> - [[Proposition Laws and Algebra]]
> - [[Propositional Equivalence]]
> - [[Rules of Inference]]
> - [[Some theorems on Nested Quantifiers]]
> - [[Binomial Coefficients]]
> - [[Cartesian Product of Two Sets]]
> - [[Classes of Functions]]
