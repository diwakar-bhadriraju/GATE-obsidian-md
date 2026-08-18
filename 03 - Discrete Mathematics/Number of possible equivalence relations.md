---
title: "Number of possible Equivalence Relations on a finite set"
subject: "Discrete Mathematics"
topic: "Algebraic and Set-Theoretic Structures"
source: "https://www.geeksforgeeks.org/engineering-mathematics/number-possible-equivalence-relations-finite-set/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Algebraic and Set-Theoretic Structures"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/algebraic-and-set-theoretic-structures
---


> [!abstract] Number of possible Equivalence Relations on a finite set
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Algebraic and Set-Theoretic Structures`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/number-possible-equivalence-relations-finite-set/)

---

# Number of possible Equivalence Relations on a finite set

An equivalence relation is defined as a relation that is **Reflexive, Symmetric, and Transitive.** Before we explore how to calculate the number of possible equivalence relations on a set ∣A∣ = n, let’s first look at an example of an equivalence relation and identify its equivalence classes.
## Example of an Equivalence Relation
Let A = { 1, 2, 3, 4} be a set and let R be an equivalence relation on A, where:
R = {(1, 1), (1, 2), (2, 1), (2, 2), (3, 3), (3, 4), (4, 3), (4, 4)}
Let's now examine the equivalence classes for the given relation.
> - The total relation T on the subset C1 = {1, 2} of A is given by T = {( 1, 1),( 1, 2),( 2, 1),( 2, 2)}, which is a subset of R. We find that there exists no total relation T′ over any superset of C1​ that is also a subset of R.
> - Thus, the equivalence class E1 = { 1, 2} represents the relation R.
Similarly, another [equivalence class](https://www.geeksforgeeks.org/maths/equivalence-class/) E2 = { 3, 4} is present under the relation R. There are no other equivalence classes in the given relation.
Observe that E1 and E2 are disjoint sets. This is a general property of equivalence relations: the equivalence classes must form a partition of the set A. In this case, the relation R corresponds to the partition {{ 1, 2},{ 3, 4}} of the set A.
## Mapping Equivalence Relations to Partitions
Each [equivalence relation](https://www.geeksforgeeks.org/maths/equivalence-relations/) on a set A is associated with one of the partitions of A. This association is even bijective, that is, every equivalence relation is associated with exactly one partition and every partition is associated with exactly one equivalence relation.
Hence, to obtain the number of equivalence relations on a finite set A, we must determine the number of partitions of A.
## The Bell Numbers
The [**Bell numbers**](https://www.geeksforgeeks.org/dsa/bell-numbers-number-of-ways-to-partition-a-set/) count the number of partitions of a set. Therefore, the number of equivalence relations on a set is the same as the corresponding Bell number for the size n of the set. The first few Bell numbers are:
$$
B_0 = 1, \, B_1 = 1, \, B_2 = 2, \, B_3 = 5, \, B_4 = 15, \, B_5 = 52, \ldots
$$
The Bell numbers are also represented by the following triangle:
> 1
> 1 2
> 2 3 5
> 5 7 10 15
> 15 20 27 37 52
The triangular structure of this is referred to as Euler's triangle and shows the recursion in the Bell numbers.
## Example: Partitions of a Set
Let’s consider the set { 1, 2, 3, 4} and find out the number of partitions for the set:
- **4**: There is but **one**manner by which all four elements can exist in a common set, demonstrating the relation of equivalence in which everything is equivalent to everything else. This maps to the entire relation.
- **3 + 1**: There are **four** different ways to partition the set into one set of size 3 and one set of size 1. In each, one element is only related to itself, and the other three are related to one another.
- **2 + 2**: There are **three** ways to partition the set into two subsets of size 2. Each subset has two elements that are associated with each other, and the remaining two elements are associated with themselves.
- **2 + 1+ 1**: There are **six** ways to partition the set into one subset of size 2 and two subsets of size 1.
- **1 + 1 + 1 + 1**: There is only **one** way to put all elements into singleton sets, which is the identity equivalence relation in which no element is related to any other.
Adding up these possibilities provides the number of partitions for { 1, 2, 3, 4}:
1+ 4+ 3+ 6+ 1 = 15
There are, therefore, **15 equivalence relations** on the set {1, 2, 3, 4}.
> Counting the number of equivalence relations on a set is the same as counting the number of partitions of the set, which is expressed by the Bell numbers. For larger sets, this may be very complex to count, but the Bell numbers give a simple method of counting the potential equivalence relations.
**Note:** Computation of Bell numbers for large sets is often complicated, and no easy closed-form formula is available for general sets. Recurrence relations and dynamic programming methods can be employed to calculate them in efficient ways.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/number-possible-equivalence-relations-finite-set/)

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
