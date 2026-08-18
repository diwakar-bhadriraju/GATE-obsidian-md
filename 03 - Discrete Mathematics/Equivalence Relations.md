---
title: "Equivalence Relations"
subject: "Discrete Mathematics"
topic: "Algebraic and Set-Theoretic Structures"
source: "https://www.geeksforgeeks.org/maths/equivalence-relations/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Algebraic and Set-Theoretic Structures"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/algebraic-and-set-theoretic-structures
---


> [!abstract] Equivalence Relations
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Algebraic and Set-Theoretic Structures`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/equivalence-relations/)

---

# Equivalence Relations

An equivalence relation is a type of relation that satisfies three fundamental properties: reflexivity, symmetry, and transitivity. These properties ensure that it defines a partition on a set, where elements are grouped into equivalence classes based on their similarity or equality.
- It is essential in various mathematical and theoretical contexts, including algebra, set theory, and graph theory.
- It provides a structured way to compare and classify elements within a set.
![relation](assets/relation-35212af6d0.webp)
The equivalence relation is a relationship on the set which is generally represented by the symbol **“∼”.** An equivalence relation on a set is a binary relation that satisfies three fundamental properties:
> - [Reflexivity](https://www.geeksforgeeks.org/maths/reflexive-relations/): ∀ a ∈ S: a ~ a
> - [Symmetry](https://www.geeksforgeeks.org/maths/symmetric-relations/): ∀ a, b ∈ S: a ~ b ⇒ b ~ a
> - [Transitivity](https://www.geeksforgeeks.org/maths/transitive-relations/): ∀ a, b, c ∈ S: (a ~ b) ∧ (b ~ c) ⇒ a ~ c
### Reflexive Relation
A relation R on a set A is called a reflexive relation if
> (a, a) ∈ R ∀ a ∈ A, i.e. aRa for all a ∈ A, where R is a subset of (A ✕ A), i.e. the cartesian product of set A with itself.
This means if element “a” is present in set A, then a relation “a” to “a” (aRa) should be present in relation R. If any such aRa is not present in R, then R is not a reflexive relation.
### Symmetric Relation
A relation R on a set A is called a symmetric relation if and only if
> ∀ a, b ∈ A, if (a, b) ∈ R then (b, a) ∈ R and vice versa i.e., where R is a subset of (A x A), i.e. the cartesian product of set A with itself.
This means if an ordered pair of elements “a” to “b” (aRb) is present in relation R, then an ordered pair of elements “b” to “a” (bRa) should also be present in relation R. If any such bRa is not present for any aRb in R, then R is not a symmetric relation.
### Transitive Relation
A relation R on a set A is called a transitive relation if and only if
> ∀ a, b, c ∈ A, if (a, b) ∈ R and (b, c) ∈ R then (a, c) ∈ R, where R is a subset of (A x A), i.e. the cartesian product of set A with itself.
This means if an ordered pair of elements “a” to “b” (aRb) and “b” to “c” (bRc) is present in relation R, then an ordered pair of elements “a” to “c” (aRC) should also be present in the relation R. If any such aRc is not present for any aRb & bRc in R R is not a transitive relation.
**Example:** A classic example of an equivalence relation is the relation of "equality" on the set of real numbers. Given any two real numbers "a" and "b":
- **Reflexivity:** "a = a" is always true for any real number "a."
- **Symmetry:** If "a = b," then "b = a."
- **Transitivity:** If "a = b" and "b = c," then "a = c."
**Some other examples include:**
- Congruence (in modular arithmetic)
- Congruence of Geometric Shapes
- Equivalence of Parallel Lines
### Properties
- Equivalence relations are often denoted by the symbol "≡" or by writing "∼" between related elements.
- An example of an equivalence relation is the "congruence modulo n" relation in modular arithmetic, where two integers are related if their difference is a multiple of n. This relation is reflexive, symmetric, and transitive.
- Equivalence relations are widely used in mathematics, computer science, and other fields for classifying objects, defining partitions, and simplifying complex problems.
## How to Verify an Equivalence Relation
Let us assume that R is a relation on the set of ordered pairs of positive integers such that((a, b), (c, d))∈ R if and only if ad = bc. Is R an equivalence relation?
To prove that R is an equivalence relation, we must show that R is
- Reflexive Relation
- Symmetric Relation
- Transitive Relation
Let's verify all these relations for any given relation R.
### Verify Reflexive Relation
The process of identifying if any given relation is reflexive:
- Check for the existence of every aRa tuple in the relation for all a present in the set.
- If every tuple exists, then the relation is reflexive. Otherwise, not reflexive.
**Example:** Consider set A = {a, b} and a relation R = {{a, a}, {b, b}}.
> For the element a in A: 
> ⇒ The pair {a, a} is present in R.
> ⇒ Hence aRa is satisfied.
>
> For the element b in A:
> ⇒ The pair {b, b} is present in R.
> ⇒ Hence bRb is satisfied.
As the condition for 'a', ‘b’ is satisfied, the relation is reflexive.
### Verify Symmetric Relation
To verify a symmetric relation, do the following:
- Manually check for the existence of every bRa tuple for every aRb tuple in the relation.
- If any of the tuples do not exist, then the relation is not symmetric; else, it is symmetric.
Follow the example given below for better understanding.
**Example:** Consider set A = { 1, 2, 3, 4 } and a relation R = { (1, 2), (1, 3), (2, 1), (3, 4), (3, 1),(4.3) }
> For the pair (1, 2) in R:
>
> ⇒ The reversed pair (2, 1) is present in the relation.
> ⇒ This pair satisfies the condition
>
> For the pair (1, 3) in R:
>
> ⇒ The reversed pair (3, 1) is present in the relation.
> ⇒ This pair satisfies the condition
>
> For the pair (2, 1) in R:
>
> ⇒ The reversed pair (1, 2) is present in the relation.
> ⇒ This pair satisfies the condition
>
> For the pair (3, 4) in R:
>
> ⇒ The reversed pair (4, 3) is present in the relation.
> ⇒ This pair satisfy the condition
>
> For the pair (3, 1) in R:
>
> ⇒ The reversed pair (1, 3) is present in the relation
> ⇒ This pair satisfies the condition
As the set satisfies the condition, the relation is symmetric.
### Verify Transitive Relation
To verify the transitive relation:
- Firstly, find the tuples of the form aRb & bRc in the relation.
- For every such pair, check if aRc is also present in R.
- If any of the tuples do not exist, then the relation is not transitive; else, it is transitive.
**Example:** Consider set R = {(1, 2), (2, 3), (3, 4), (1, 3), (2, 4), (1, 4)}
> For the pairs (1, 2) and (2, 3):
>  ⇒ The relation (1, 3) exists.
>  ⇒ This satisfies the condition.
>
> For the pairs (2, 3) and (3, 4):
>  ⇒ The relation (2, 4) exists.
>  ⇒ This satisfies the condition.
>
> For the pairs (1, 3) and (3, 4):
>  ⇒ The relation (1, 4) exists.
>  ⇒ This satisfies the condition.
>
> All possible pairs satisfy the condition of transitivity.
>
> So, the given relation is transitive.
>
> Hence, the transitive property is proved.
**➢Practice:**[Solved Examples](https://www.geeksforgeeks.org/maths/equivalence-relations-practice-questions/)
### Related Articles
> - [Types of Function](https://www.geeksforgeeks.org/maths/types-of-functions/)
> - [One to One Function](https://www.geeksforgeeks.org/maths/one-to-one-functions/)
> - [Injection Functions](https://www.geeksforgeeks.org/maths/injective-functions/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/equivalence-relations/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Algebraic and Set-Theoretic Structures

> [!note] Related notes
>
> - [[Cartesian Product of Two Sets]]
> - [[Classes of Functions]]
> - [[Closure of Relations]]
> - [[Composition of Functions]]
> - [[Groups]]
> - [[Hasse Diagrams]]
> - [[Introduction to Set Theory]]
> - [[Inverse Functions]]
> - [[Modular Addition]]
> - [[Multiplication Modulo]]
