---
title: "Canonical and Standard Form"
subject: "Digital Logic and Design"
topic: "Introduction of Boolean Algebra and Logic Gates"
source: "https://www.geeksforgeeks.org/digital-logic/canonical-and-standard-form/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Introduction of Boolean Algebra and Logic Gates"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/introduction-of-boolean-algebra-and-logic-gates
---


> [!abstract] Canonical and Standard Form
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Introduction of Boolean Algebra and Logic Gates`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/canonical-and-standard-form/)

---

# Canonical and Standard Form

Boolean algebra is the foundation of digital electronics, enabling the design and analysis of logic circuits. Canonical and standard forms are two common methods of representing Boolean functions, helping simplify logic expressions and optimize digital circuit implementation.
- Canonical forms provide a unique representation of Boolean functions using minterms or maxterms.
- These forms help reduce hardware complexity and improve circuit efficiency.
- Understanding canonical and standard forms makes Boolean function analysis and logic circuit design easier.
![lolo](assets/lolo-a2a3541705.webp)
Canonical vs Standard Form
## Canonical Forms in Boolean Algebra
Canonical forms provide a unique representation of Boolean functions using minterms or maxterms.
- **Minterms**: A minterm is a product term in which every Boolean variable appears exactly once, either in its true or complemented form. It represents a combination for which the output is 1.
- **Maxterms**: A maxterm is a sum term in which every Boolean variable appears exactly once, either in its true or complemented form. It represents a combination for which the output is 0.
The table below shows the minterms and corresponding maxterms for a three-variable Boolean function.
| **Decimal Index** | **X** | **Y** | **Z** | **Minterm (Product Term)** | **Maxterm (Sum Term)** |
| --- | --- | --- | --- | --- | --- |
| 0 | 0 | 0 | 0 | m₀ = X'·Y'·Z' | M₀ = X + Y + Z |
| 1 | 0 | 0 | 1 | m₁ = X'·Y'·Z | M₁ = X + Y + Z' |
| 2 | 0 | 1 | 0 | m₂ = X'·Y·Z' | M₂ = X + Y' + Z |
| 3 | 0 | 1 | 1 | m₃ = X'·Y·Z | M₃ = X + Y' + Z' |
| 4 | 1 | 0 | 0 | m₄ = X·Y'·Z' | M₄ = X' + Y + Z |
| 5 | 1 | 0 | 1 | m₅ = X·Y'·Z | M₅ = X' + Y + Z' |
| 6 | 1 | 1 | 0 | m₆ = X·Y·Z' | M₆ = X' + Y' + Z |
| 7 | 1 | 1 | 1 | m₇ = X·Y·Z | M₇ = X' + Y' + Z' |
## Types of canonical forms
### **Canonical Sum of Products (SOP)**
In the Canonical Sum of Products (SOP) form, the Boolean expression is written as the sum (OR) of all minterms for which the output is 1. Each minterm contains every input variable exactly once, either in its true or complemented form.
### **Canonical Product of Sums (POS)**
In the Canonical Product of Sums (POS) form, the Boolean expression is written as the product (AND) of all maxterms for which the output is 0. Each maxterm contains every input variable exactly once, either in its true or complemented form.
**Example**
Consider two Boolean variables A and B with the Boolean function:
> F(A, B) = A ⊕ B
The truth table below shows the minterms and maxterms corresponding to the XOR function.
| Decimal Index | A | B | F(A,B) | Minterm | Maxterm |
| --- | --- | --- | --- | --- | --- |
| 0 | 0 | 0 | 0 | — | M₀ = A + B |
| 1 | 0 | 1 | 1 | m₁ = A'B | — |
| 2 | 1 | 0 | 1 | m₂ = AB' | — |
| 3 | 1 | 1 | 0 | — | M₃ = A' + B' |
**Canonical SOP Form:**
> F(A, B) = m1 + m2 = A'.B + A.B'
**Canonical POS Form:**
> F(A, B) = M0 . M3 = (A + B).(A' + B')
Canonical SOP and POS provide unique representations of boolean functions and are widely used in Karnaugh maps, logic minimization, and digital circuit design.
## Standard Forms in Boolean Algebra
Standard forms provide a simplified way to represent Boolean functions for digital circuit implementation. Unlike canonical forms, every term is not required to contain all input variables.
## Types of standard forms:
### **Standard Sum of Products (SOP)**
In the Standard Sum of Products (SOP) form, the Boolean expression is written as the sum (OR) of product terms. Unlike canonical SOP, each product term may omit one or more variables, while preserving the same logical function.
Example
> F(A, B, C) = A'B'C + A'B + AB
Here, the product terms A'B and AB do not contain all three input variables.
### **Standard Product of Sums (POS)**
In the Standard Product of Sums (POS) form, the Boolean expression is written as the product (AND) of sum terms. Unlike canonical POS, each sum term may omit one or more variables, resulting in a simpler expression.
**Example**
> F = (A+C)(B+C)(A'+B'+C)
Here, the sum terms (A+C) and (B+C) do not contain all three input variables.
Standard SOP and POS forms simplify Boolean expressions, reduce circuit complexity, and are widely used in digital circuit design and optimization.
## Canonical Form vs Standard Form
| **Feature** | **Canonical Form** | **Standard Form** |
| --- | --- | --- |
| **Term Completeness** | Every term contains all variables | Terms may omit one or more variables |
| **Representation** | Unique | Multiple equivalent forms |
| **Complexity** | Usually higher due to more literals | Usually lower after simplification |
| **Usage** | Analysis and Boolean function representation | Circuit implementation and simplification |
| **Gate Requirement** | Generally requires more gates | Generally requires fewer gates |
| **Example** | F = A'B'C + A'BC + AB'C' + ABC | F = A'C + AB'C' + ABC |
## Conversion Between Canonical and Standard Forms
Boolean functions can be converted between canonical and standard forms to simplify logic expressions and optimize digital circuit implementation.
### **Converting Canonical Form into Standard Form**
1. Start with the canonical SOP or POS expression.
2. Apply Boolean algebra identities to combine common terms.
3. Eliminate redundant variables or terms.
4. Obtain the simplified standard form.
**Example:**
**Canonical SOP:**
F(A, B, C) = A'B'C + A'BC + AB'C + ABC
Simplification:
(A′B′C + A′BC) + (AB′C + ABC)
A′C(B′ + B) + AC(B′ + B)
A′C(1) + AC(1)
A′C + AC
Further simplification:
=A′C + AC = C(A′ + A) = C
**Standard SOP:**
F(A,B,C) = C
### **Converting Standard Form into Canonical Form**
1. Identify the missing variables in each term.
2. Expand the expression using Boolean identities.
3. Include every variable in each product or sum term.
4. Remove duplicate terms.
**Example:**
**Standard SOP:**
F = A + BC
Expand the missing variables:
A = A(B + B′)(C + C′)
=ABC + AB′C + ABC′ + AB′C′
Expand the second term:
BC = (A + A′)BC
=ABC + A′BC
Combine the terms:
F = A′BC + AB′C′ + AB′C + ABC′ + ABC
**Canonical SOP:**
F = A′BC + AB′C′ + AB′C + ABC′ + ABC
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/canonical-and-standard-form/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Introduction of Boolean Algebra and Logic Gates

> [!note] Related notes
>
> - [[Boolean functions]]
> - [[Consensus Theorem]]
> - [[Functional Completeness]]
> - [[Implicants in K-Map]]
> - [[K-Map]]
> - [[Logic Gates]]
> - [[Logical gates in logic design]]
> - [[Minimization of Boolean Functions]]
> - [[PDNF and PCNF]]
> - [[Prime implicants and Explicit implicants]]
