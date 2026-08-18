---
title: "Set Operations"
subject: "Discrete Mathematics"
topic: "Algebraic and Set-Theoretic Structures"
source: "https://www.geeksforgeeks.org/maths/set-operations/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Algebraic and Set-Theoretic Structures"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/algebraic-and-set-theoretic-structures
---


> [!abstract] Set Operations
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Algebraic and Set-Theoretic Structures`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/set-operations/)

---

# Set Operations

A set is simply a collection of distinct objects. These objects can be numbers, letters, people, or any other identifiable items. We denote a set using curly brackets, e.g.,A = {1, 2, 3}
> Set Operations can be defined as the operations performed on two or more sets to obtain a single set containing a combination of elements from all the sets being operated upon.
![set_operations](assets/set_operations-42457ae5d3.webp)
- There are three major operations on sets: Union (∪), Intersection (∩), and Difference (-).
- Other operations include Complement, Symmetric Difference, Addition, and Subtraction.
### **Union of Sets**
The [Union of sets](https://www.geeksforgeeks.org/maths/union-of-sets/) A and B, denoted by A ∪ B, is the set of distinct elements that belong to set A or set B, or both. This operation can be represented as;
> A ∪ B = {x: x ∈ A or x ∈ B}
In simple terms, the union includes every element that appears in either of the two sets, without any repetition. Where x represents an element that belongs to A or B (or both).
The area shaded in green represents A ∪ B or the union of sets A and B.
![unit_u_495](assets/unit_u_495-5f70f622f2.webp)
Venn diagram of A ∪ B
**Example:** Find the union of A = {2, 3, 4} and B = {3, 4, 5}.
**Solution:**
> A ∪ B = {2, 3, 4, 5}.
### **Intersection**
The [intersection of the sets](https://www.geeksforgeeks.org/maths/intersection-of-sets/) A and B, denoted by **A ∩ B,** is the set of elements that belong to both A and B, i.e. set of the common elements in A and B. This operation is represented as:
> A∩B = {x: x ∈ A and x ∈ B}
In other words, the intersection contains only those elements that are present in both sets. Here, x represents the elements that are common to both sets A and B.
The area shaded in green represents A∩B or the intersection of sets A and B, which includes the elements common to both sets A and B.
![uni495](assets/uni495-2483a99e50.webp)
Venn diagram of A ∩ B
**Example:** Find the intersection of A = {2, 3, 4} and B = {3, 4, 5}
**Solution:**
> Look for elements that are common to both sets A and B.
>
> A ∩ B = {3, 4}.
The intersection of sets A and B can also be interpreted as:
> n (A ∩B) = n (A) + n (B) – n (A∪B)
Where,
- n(A) = the cardinality (or number of elements) of set A,
- n(B) = the cardinality of set B,
- n(A∪B) = the cardinality of the union of sets A and B.
### **Disjoint Set**
Two sets are said to be [disjoint](https://www.geeksforgeeks.org/maths/disjoint-sets/) if their intersection is the [empty set](https://www.geeksforgeeks.org/maths/empty-set/). i.e., sets have no common elements. In simpler terms, they don’t “overlap” at all.
 So if you try to find their intersection, you’ll get the empty set, which we denote by the symbol ϕ or {}.
The sets A and B are disjoint, meaning they have no common elements (no overlap).
![6757](assets/6757-429c9902b0.webp)
Venn Diagram of A Disjoint B
**For Example:** Let A = {1, 3, 5, 7, 9} and B = {2, 4, 6, 8}
**Solution:**
> A and B are disjoint sets since both of them have no common elements.
### **Set Difference**
The difference between sets is denoted by **'A - B'**, which is the set containing elements that are in A but not in B i.e., all elements of A except the element of B.
In the below diagram, the [set difference](https://www.geeksforgeeks.org/maths/difference-of-sets/) A−B contains all the elements that are in A but not in B.
![file](assets/file-120539c1d7.webp)
Venn diagram A-B
**Example:** If A = {1, 2, 3, 4, 5} and B = {2, 4, 6, 8}, find A - B.
**Solution:**
> A - B = {1, 3, 5}
We can also state that the difference between set A and set B is equivalent to the intersection of set A with the complement of set B. Therefore,
> A − B = A ∩ B′
>
> where B′ = the complement of set B.
### Symmetric Difference
The [symmetric difference](https://www.geeksforgeeks.org/maths/symmetric-difference-of-sets/) of A and B includes elements in A or B but not both.
- It is denoted by: A △ B or A ⊕ B.
- The symmetric difference is like saying, “Give me everything that’s not shared.
- It is defined as: A △ B = (A−B) ∪ (B−A)
The symmetric difference AΔB includes elements that are in either A or B but not in both.
![t_u_495](assets/t_u_495-fa203a71c1.webp)
Venn Diagram of A △ B
**Example**: Let set A = {1, 2, 3}, and set B = {3, 4, 5}, then Find the symmetric difference
**Solution:**
> A △ B = {1, 2, 4, 5}
### Complement of a Set
If U is a universal set and X is any subset of U, then the complement of X consists of all the elements in U that are not in X.
X' = {a : a∈ U and a ∉ X}
In the diagram below, set A' includes all elements not in A, relative to the universal set.
![76](assets/76-a3fbe9a545.webp)
Complement of a Set
**Example:** Let U = {1, 2, 3, 4, 5, 6, 7, 8} And A = {1, 2, 5, 6}
**Solution:**
> Then, the [complement](https://www.geeksforgeeks.org/maths/complement-of-a-set/) of A, denoted as A′, will be: A′ = {3, 4, 7, 8}
### Properties of Set Operations
Set operations have several important properties that govern their behavior. Here are some fundamental properties of set operations:
**Closure Property**
- Set operations are closed under their respective operations, meaning that operating on sets results in another set.
- For example, the union, intersection, and difference of sets always produce sets as their results.
**Commutative Property**
- Union: A ∪ B = B ∪ A
- Intersection: A ∩ B = B ∩ A
- Symmetric Difference: A Δ B = B Δ A
**Associative Property**
- Union: (A ∪ B) ∪ C = A ∪ (B ∪ C)
- Intersection: (A ∩ B) ∩ C = A ∩ (B ∩ C)
**Distributive Property**
- Union over Intersection: A ∪ (B ∩ C) = (A ∪ B) ∩ (A ∪ C)
- Intersection over Union: A ∩ (B ∪ C) = (A ∩ B) ∪ (A ∩ C)
**Identity Property**
- Union: A ∪ ∅ = A
- Intersection: A ∩ U = A, where U represents the universal set
- Symmetric Difference: A Δ ∅ = A
**Complement Property**
- Union: A ∪ A' = U, where U is the universal set
- Intersection: A ∩ A' = ∅ (the empty set)
**Absorption Property**
- Union over Intersection: A ∪ (A ∩ B) = A
- Intersection over Union: A ∩ (A ∪ B) = A
**➢Practice:**[Solved Examples](https://www.geeksforgeeks.org/maths/practice-questions-on-operations-on-sets/)
### **Related Articles**
> - [Set Theory](https://www.geeksforgeeks.org/maths/set-theory/)
> - [Set Symbols](https://www.geeksforgeeks.org/maths/set-theory-symbols/)
> - [Types of Sets](https://www.geeksforgeeks.org/maths/types-of-sets/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/set-operations/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Algebraic and Set-Theoretic Structures

> [!note] Related notes
>
> - [[Cartesian Product of Two Sets]]
> - [[Classes of Functions]]
> - [[Closure of Relations]]
> - [[Composition of Functions]]
> - [[Equivalence Relations]]
> - [[Groups]]
> - [[Hasse Diagrams]]
> - [[Introduction to Set Theory]]
> - [[Inverse Functions]]
> - [[Modular Addition]]
