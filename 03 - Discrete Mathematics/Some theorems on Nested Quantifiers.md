---
title: "Nested Quantifiers"
subject: "Discrete Mathematics"
topic: "Propositional and First-Order Logic"
source: "https://www.geeksforgeeks.org/engineering-mathematics/mathematics-theorems-nested-quantifiers/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Propositional and First-Order Logic"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/propositional-and-first-order-logic
---


> [!abstract] Nested Quantifiers
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Propositional and First-Order Logic`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/mathematics-theorems-nested-quantifiers/)

---

# Nested Quantifiers

Nested quantifiers are quantifiers that are used together in a statement, where one quantifier is within the scope of another quantifier. They help describe relationships between different variables.
**Types of Quantification or Scopes**
1. **Universal (∀) -** The predicate is true for all values of x in the domain.
2. **Existential (∃) -** The predicate is true for at least one x in the domain.
**Examples**
**1.** For every natural number, there exists a larger natural number.
> ∀x ∈ N, ∃y ∈ N(y > x), which means for each natural number x, there exists a natural number y that is greater than x.
**2.** For every integer x, there exists an integer y such that x + y = 0.
![2056958126](assets/2056958126-300-0539abd9d3.webp)
> For example:
>
> - If x = 5, then y = −5.
> - If x = −3, then y = 3.
> - If x = 0, then y = 0.
>
> Hence, the statement is true over the set of integers.
### Understanding the Scope of Nested Quantifiers
Two quantifiers are nested if one is within the scope of the other.
**Example 1:** ∀x ∃y (x + y = 5) Here '∃' (read as-there exists) and '∀' (read as-for all) are quantifiers for variables x and y.
> The statement can be represented as ∀x Q(x) is ∃y P(x, y)  Q(x)-the predicate is a function of only x because the quantifier applies only to variable x. P(x, y) is (x + y = 5) .
**Example 2:** ∀x ∀y ((x> 0)∧(y< 0) → (xy< 0)) (in English) For every real number x and y, if x is positive and y is negative, then xy is negative, again, ∀x Q(x) where Q(x) is ∀y P(x, y).
## Converting Statements into Nested Quantifier
A statement in predicate logic is written using quantifiers and predicates.
- **Quantifiers:** ∀ (for all), ∃ (there exists).
- **Predicate:** a property or relation involving variables.
To convert a statement into a nested quantifier formula:
1. Identify the variables
2. Identify the predicate
3. Attach suitable quantifiers
**Example:** “There is a student in this lecture who has taken at least one course in Discrete Mathematics.”
> Let:
>
> - x = Student
> - y = Discrete Mathematics course
> - P(x, y) = “x has taken y”
>
> The statement becomes: “There exists a student x and there exists a course y such that x has taken y.”
>
> Symbolically: **∃x ∃y P(x, y)**
## Theorems
**Theorem 1:** The order of nested existential quantifiers can be changed without changing the meaning of the statement.
> ∃x ∃y P(x, y) ≡ ∃y ∃x P(x, y)
**Example:** Statement: P(x, y): xy = 8
 Domain: Integers
> The statement means: “There exist integers x and y such that xy = 8.”
>
> Changing the order of quantifiers gives the same meaning.
>
> Hence, ∃x ∃y P(x, y) ≡ ∃y ∃x P(x, y).
**Theorem 2:** The order of nested universal quantifiers can also be changed without changing the meaning of the statement.
> ∀x ∀y P(x, y) ≡ ∀y ∀x P(x, y)
**Example:** Statement: ∀x ∀y (xy = yx)
 Domain: Real Numbers
> The statement means: “For all real numbers x and y, xy = yx.”
>
> Changing the order of quantifiers gives the same meaning.
>
> Hence, ∀x ∀y P(x, y) ≡ ∀y ∀x P(x, y).
**Theorem 3:** To negate nested quantifiers, replace each quantifier with its opposite type (∀ becomes ∃ and ∃ becomes ∀) and negate the predicate. Thus, the negation of ∀x ∃y P(x, y) is ∃x ∀y ~P(x, y).
**Example:** Statement: ∀x ∃y (x + y = 0)
 Domain: Integers
> The statement means: “For every integer x, there exists an integer y such that x + y = 0.”
>
> Its negation is: ∃x ∀y (x + y ≠ 0)
>
> which means: “There exists an integer x such that for every integer y, x + y ≠ 0.”
**➢Practice:**[Solved Examples](https://www.geeksforgeeks.org/maths/nested-quantifiers-practice-questions/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/mathematics-theorems-nested-quantifiers/)

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
> - [[Rules of Inference]]
> - [[Binomial Coefficients]]
> - [[Cartesian Product of Two Sets]]
> - [[Classes of Functions]]
