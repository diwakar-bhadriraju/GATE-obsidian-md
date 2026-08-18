---
title: "Minimization of Boolean Functions"
subject: "Digital Logic and Design"
topic: "Introduction of Boolean Algebra and Logic Gates"
source: "https://www.geeksforgeeks.org/digital-logic/minimization-of-boolean-functions/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Introduction of Boolean Algebra and Logic Gates"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/introduction-of-boolean-algebra-and-logic-gates
---


> [!abstract] Minimization of Boolean Functions
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Introduction of Boolean Algebra and Logic Gates`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/minimization-of-boolean-functions/)

---

# Minimization of Boolean Functions

Boolean functions are used to represent logical expressions in terms of sum of minterms or product of maxterms. Number of these literals (minterms or maxterms) increases as the complexity of the digital circuit increases. This can lead to large and inefficient circuits.
By minimizing Boolean functions, we can reduce the number of logic gates, simplify circuit design, and improve performance in terms of speed, cost, and power consumption.
For example, let the Boolean function:
> F2 = x’y’z + x’yz + xy’
This function can be further minimized by
- Grouping first two terms: **x’y’z + x’yz = x’(y’z + yz)**
- Simplify inside: **y’z + yz = z**, so it becomes **x’z**
- Add the remaining term: **x’z + xy’**
The minimized Boolean function will be:
> F2 = xy' + x’z
In the diagram below we can see the implementation of the Boolean function:
![Minimization-of-Boolean-Function](assets/Minimization-of-Boolean-Function-fb70aabee5.webp)
Minimization of Boolean Function
Instead of building a circuit with 3 big parts (one for each term), the minimized version needs only 2.
> Read more about [Representation of Boolean Functions](https://www.geeksforgeeks.org/engineering-mathematics/representation-of-boolean-functions/)
Various methods and techniques, such as Karnaugh maps, Quine-McCluskey algorithm, and the use of Boolean algebra, help achieve this simplification.
## Main Methods for Minimizing Boolean Expressions
The two main methods for minimizing Boolean expressions are:
### 1. Boolean Algebra
Boolean algebra involves using a set of rules and laws (like distributive, associative, and complement laws) to simplify Boolean expressions. This method focuses on applying algebraic manipulations to reduce the complexity of the expression by eliminating redundant terms.
| **Law/Rule** | **Expression** |
| --- | --- |
| **Identity Law** | A ⋅ 1 = A, A + 0 = A |
| **Null Law** | A ⋅ 0 = 0, A + 1 = 1 |
| **Idempotent Law** | A ⋅ A = A, A + A = A |
| **Complement Law** | A ⋅ A′ = 0, A + A' = 1 |
| **Domination Law** | A ⋅ 0 = 0, A + 1 = 1 |
| **Double Negation Law** | (A′)′ = A |
| **Distributive Law** | A ⋅ (B + C) = A ⋅ B + A ⋅ C |
| **De Morgan’s Law** | (A ⋅ B)′ = A′ + B', (A + B)′ = A′ ⋅ B′ |
| **Absorption Law** | A ⋅ (A + B) = A, A + (A ⋅ B) = A |
| **Complementation Law** | A ⋅ A′ = 0, A + A′ = 1 |
| **Consensus Theorem** | AB + A'C + BC = AB + A'C |
> Read more about [Boolean Algebraic Theorems](https://www.geeksforgeeks.org/engineering-mathematics/boolean-algebraic-theorems/)
**Example:** Simplify the Boolean function F = AB + (AC)′ + AB′C(AB + C).
**Solution:** F = AB + (AC)′ + AB′C(AB + C)
= AB + A′ + C′+ AB′C.AB + AB′C.C
= AB + A′ + C′ + 0 + AB′C (B.B′ = 0 and C.C = C)
= ABC + ABC′ + A′ + C′ + AB′C (AB = AB(C + C′) = ABC + ABC′)
= AC(B + B′) + C′(AB + 1) + A′
= AC + C′+A′ (B + B′ = 1 and AB + 1 = 1)
= AC + (AC)′ = 1
### 2. K-Map
The [Karnaugh Map](https://www.geeksforgeeks.org/digital-logic/introduction-of-k-map-karnaugh-map/) is a graphical technique used to simplify Boolean expressions by grouping adjacent cells containing 1s (minterms). This visual method makes it easier to identify patterns and minimize the expression by combining terms that can be grouped together. It is especially useful for functions with 4 or fewer variables.
## Questions Based on Minimization of Boolean Functions
**Example:** Minimize the following Boolean function using algebraic manipulation
> F = ABC'D' + ABC'D + AB'C'D + ABCD + AB'CD + ABCD' AB'CD'
**Solution:**
**1. Using Boolean Laws**
F = ABC'(D' + D) + AB'C'D + ACD(B + B') ACD'(B + B')
= ABC' + AB'C'D + ACD + ACD'
= ABC' + AB'C'D + AC(D + D')
= ABC' + AB'C'D + AC
= A(BC' + C) + AB'C'D
= A(B + C) + AB'C'D
= AB + AC + AB'C'D
= AB + AC + AC'D
= AB + AC + AD
**2. Using K-Map**
![minimizaton-boolean-Kmap](assets/minimizaton-boolean-Kmap-d54a0aba4b.jpg)
k-map
The above figure highlights the prime implicants in green, red and blue.
- The green one spans the whole third row, which gives us – AB
- The red one spans 4 squares, which gives us – AD
- The blue one spans 4 squares, which gives us – AC
So, the minimized Boolean expression is - AB + AC + AD
**GATE CS Corner Questions**:
> 1. [GATE CS 2012, Question 30](https://www.geeksforgeeks.org/questions/what-is-the-minimal-form-of-the-karnaugh-map/)
> 2. [GATE CS 2007, Question 32](https://www.geeksforgeeks.org/questions/let-fw-x-y-z-0-4-5/)
> 3. [GATE CS 2014 Set-3, Question 17](https://www.geeksforgeeks.org/questions/consider-the-following-minterm-expression-for-f-fpqrs/)
> 4. [GATE CS 2005, Question 18](https://www.geeksforgeeks.org/questions/the-switching-expression-corresponding-to-fa-b-c-d/)
> 5. [GATE CS 2004, Question 17](https://www.geeksforgeeks.org/questions/the-boolean-function-xy-xy-xy-is/)
> 6. [GATE CS 2003, Question 45](https://www.geeksforgeeks.org/questions/the-literal-count-of-a-boolean-expression-is-the/)
> 7. [GATE CS 2002, Question 12](https://www.geeksforgeeks.org/questions/minimum-sum-of-product-expression-for-fw-x-y/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/minimization-of-boolean-functions/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Introduction of Boolean Algebra and Logic Gates

> [!note] Related notes
>
> - [[Boolean functions]]
> - [[Canonical and Standard Form]]
> - [[Consensus Theorem]]
> - [[Functional Completeness]]
> - [[Implicants in K-Map]]
> - [[K-Map]]
> - [[Logic Gates]]
> - [[Logical gates in logic design]]
> - [[PDNF and PCNF]]
> - [[Prime implicants and Explicit implicants]]
