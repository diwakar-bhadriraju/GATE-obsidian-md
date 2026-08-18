---
title: "Partial Orders and Lattices (Set-2) | Mathematics"
subject: "Discrete Mathematics"
topic: "Algebraic and Set-Theoretic Structures"
source: "https://www.geeksforgeeks.org/engineering-mathematics/partial-orders-and-lattices-set-2-mathematics/#:~:text=greatest%20lower%20bound.-,Types%20of%20Lattice,-1.%20Bounded%20Lattice"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Algebraic and Set-Theoretic Structures"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/algebraic-and-set-theoretic-structures
---


> [!abstract] Partial Orders and Lattices (Set-2) | Mathematics
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Algebraic and Set-Theoretic Structures`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/partial-orders-and-lattices-set-2-mathematics/#:~:text=greatest%20lower%20bound.-,Types%20of%20Lattice,-1.%20Bounded%20Lattice)

---

# Partial Orders and Lattices (Set-2) | Mathematics

**Partial orders and lattices** are **important concepts in discrete mathematics and are widely used in computer science, especially in data structures, database theory, and the theory of computation**. Partial orders and lattices play pivotal roles in a wide array of applications within engineering, computer science, and beyond.
These structures enable the efficient organization, comparison, and optimization of data, providing essential tools for tackling complex problems in various domains.
Table of Content
- [What is Partial Order?](#what-is-partial-order)
- [Key Properties of Partial Order Sets (POSET)](#key-properties-of-partial-order-sets-poset)
- [Examples of Partial Order Sets](#examples-of-partial-order-sets)
- [Well Ordered Set](#well-ordered-set)
- [What is Lattice?](#what-is-lattice)
- [Types of Lattice](#types-of-lattice)
- [1. Bounded Lattice](#1-bounded-lattice)
- [2. Complemented Lattice](#2-complemented-lattice)
- [3.Distributive Lattice:](#3distributive-lattice)
- [4.Modular Lattice](#4modular-lattice)
- [5.Complete Lattice:-](#5complete-lattice)
## What is Partial Order?
**Partial order set, or POSET**, is a set combined with a [partial order relation](https://www.geeksforgeeks.org/dsa/partial-order-relation-on-a-set/) that defines a binary relation satisfying three properties: reflexivity, anti-symmetry, and transitivity. A partial order is a binary relation that describes a set of elements that are, in a sense, ordered, but not necessarily linear. This structure allows for the comparison of elements in a way that is not necessarily complete, meaning not all elements need to be comparable.
### Key Properties of Partial Order Sets (POSET)
1. **Reflexivity**: Every element is related to itself. For any element a in set P, a ≤ a. Reflexivity implies that an element may be compared to itself.
2. **Anti-symmetry**: If two elements are mutually related, they are equal. For any elements a and b in set P, if a ≤ b and b ≤ a, then a=b. It guarantees that two items must be the same if they are similar in both directions.
3. **Transitivity**: If an element is related to a second, which is related to a third, the first element is related to the third. For any elements a, b, and c in set P, if a ≤ b and b ≤ c , then a ≤ c.
### Examples of Partial Order Sets
- **Set of Natural Numbers with Divisibility**: Consider the set of natural numbers {1,2,3,4,…}with the relation a ≤ b if a divides b. This forms a partial ordered set.
> - Example: 3≤6 Since 3divides 6, 3≤6. This relationship is transitive (if 𝑎 a divides 𝑏 and 𝑏 divides 𝑐 , then 𝑎 divides c), reflexive (any number divides itself), and antisymmetric (if 𝑎 divides 𝑏 and 𝑏 divides 𝑎 , then 𝑎 = 𝑏 ).
- **Set of Subsets**: The power set of any set S, ordered by subset inclusion ⊆, is a partial ordered set.
> - S={{1},{1,2},{1,2,3}}, where set inclusion defines the relation ⊆. {1}⊆ {1 ,2} {1}⊆{1,2} and {1 , 2 }⊆ {1 , 2 , 3 } {1,2}⊆{1,2,3} are the examples given here.
> - Every set is a subset of itself in this relation, which is reflexive. It is also antisymmetric (if set A is a subset of B and B is a subset of A, then A=B) and transitive (if A⊆ B and A⊆ C, then A⊆ C).
## **Well Ordered Set**
Given a POSET , (X, ≤) we say that ≤ is a well-order (well-ordering) and that is well-ordered by ≤ **if** every nonempty subset of X has a least element. When X is non-empty, if we pick any two-element subset, {a, b}, of X, since the subset {a, b} must have a least element, we see that either a ≤ b or b ≤ a, i.e., every well-order is a total order. 
**E.g. -** The set of natural number (N) is a well ordered.
## Visualizing partial Orders
### Hasse Diagrams
A finite partially ordered set can be graphically represented as a Hasse diagram. Visualizing the incomplete order without precisely drawing every conceivable relationship is helpful.
Within a Hasse diagram:
1. A vertex, or point, represents each element in the set.
2. When there is no element c such that a≤c≤b, then a line (or edge) is drawn between two elements, a and b, if ≤ 𝑏≤b. This indicates that transitive relationships are not shown in the diagram; only direct links are displayed.
3. The elements are arranged so that, in the event that b≤a≤c, c is positioned below a.
## What is Lattice?
Lattice is a particular kind of partially ordered set ( POSET ) that has additional properties. In a lattice, every pair of elements has both a unique least upper bound (called the join) and a unique greatest lower bound (called the meet). These properties make lattices valuable in various fields, including mathematics, computer science, and engineering.
**Lattice:** A POSET in which every pair of element has both a least upper bound and greatest lower bound. 
## Types of Lattice
### **1. Bounded Lattice**
A lattice L is said to be bounded if it has the greatest element I and a least element 0. 
E.g. - D18= {1, 2, 3, 6, 9, 18} is a bounded lattice. 
![](assets/hasse-be8f60a866.png)
**Note:** Every Finite lattice is always bounded. 
### **2. Complemented Lattice**
A lattice L is said to be complemented if it is bounded and if every element in L has a complement. Here, each element should have at least one complement. 
E.g. - D6 {1, 2, 3, 6} is a complemented lattice. 
![](assets/hasse6-bf84b8d00d.png)
In the above diagram every element has a complement. 
Any element '**b**' will be the complement of an element '**a**' in the POSET (X, ≤) which is lattice if and only if both condition below are satisfied -:
- glb(a, b) = least element
- lub(a,b) = greatest element
or when (a ^ b = least element and a v b = greatest element) where,
greatest element (1) is element which is related by every other element in the lattice.
Mathematically, any element **a**, of POSET **(X, ≤)** which is lattice , will be greatest element **iff ∀ b ∈ X, (b,a)∈ R**. where R is the relation on which element are related. Example in above diagram for D6, greatest element is 6 as it is related by every other element in the lattice i.e. (1,6), (2,6), (3,6) ∈ R.
least element (0) is element which relates to every other element in the lattice.
Mathematically, any element **a**, of POSET **(X, ≤)** which is lattice , will be least element **iff ∀ b ∈ X, (a,b)∈ R**. where R is the relation on which element are related. Example in above diagram for D6, least element is 1 as it relates to every other element in the lattice i.e. (1,2), (1,3), (1,6) ∈ R.
Greatest and Least element in any set, if they exist will not be more than one unlike maximal and minimal elements which can be more than one.
### **3.Distributive Lattice:**
If a lattice satisfies the following two distribute properties, it is called a distributive lattice.
- x ∧ (y ∨ z) = (x ∧ y) ∨ (x ∧ z)
- x ∨ (y ∧ z) = (x ∨ y) ∧ (x ∨ z)
![](assets/dis-ab3e33ca81.png)
![](assets/diskite-5611a3080f.png)
- A complemented distributive lattice is a boolean algebra or boolean lattice.
- A lattice is distributive if and only if none of its sublattices is isomorphic to N5 or M3.
- For distributive lattice each element can have at most one complement. This can be used as a theorem to prove that a lattice is not distributive.
### **4.Modular Lattice**
If a lattice satisfies the following property, it is called a modular lattice.
a^(b∨(a^d)) = (a^b)(a^d).
Example-
![](assets/Picture1-4bbb7229d7.png)
### **5.Complete Lattice:-**
A complete lattice is a special type of lattice where every subset of elements has a lower bound and an upper bound. 
For example, Imagine a lattice based on the **ordering relation < including all natural numbers between 1 and 100.**More detailed discussion on complete lattice is given below.
**A lattice is complete if it has both a least and a greatest element. Is the statement correct?**
Before discussing the correctness of this statement we need to know few mathematical definitions. We know that a lattice is a partially ordered set(POSET ,that is, reflexive, antisymmetric and transitive) such that any pair of elements in the lattice  always has a greatest lower bound(glb) and a least upper bound(lub). Now greatest and least elements of a lattice are basically the glb and lub of all the lattice elements that is the element which is dominated by all the lattice elements and the element which dominates all the lattice elements.
As we have already explained the mathematical definitions. We now try to analyse our claim.
**First Part:  If a lattice is complete then it has both a least and a greatest element.**
**Argument:**  Consider a lattice D. Suppose, it is complete.  According to the definition of complete lattice, every subset of elements of D has a least upper bound (lub) and a greatest lower bound (glb).  It means, consider any arbitrary subset S of lattice D and S will have a lub and a glb.  Now, every set is considered as a subset to itself.
(Note that the definition clearly mentions subset and not proper subset)
So, D is a subset of itself.  It implies, subset D will have a lub (least element) and a glb (greatest element).  So, D  has  both  a  least  and  a  greatest  element.  Therefore, if a lattice is complete then it has both a least and a greatest element.
**Second Part:  If a lattice has both a least and a greatest element then it is complete.**
**Counter Example:** Consider the lattice consisting of all the rational numbers in the interval [1,2]. This set has a least element as 1 and greatest element as 2.Now we take an irrational number in this interval say square root of 2. Now we try to create a subset of this lattice consisting of rational approximation of square root of 2.As square root of 2 being irrational will not belong to this set and hence the infinite number of approximations will not have a lub. The approximations can be written as follows:-
1.4<1.41<1.414<1.4142<1.41421<1.414213<1.4142135............................and it continues without any upper bound.
Now this set of rational approximations is an infinite but is indeed a subset without a least upper bound or rather an upper bound.
Similar argument can be given in case of glb which I leave to the readers as an exercise
**Thus it is clear that a complete lattice will have both least and a greatest element but a lattice with both greatest and least element may not be complete.**
> **Also Read:**
>
> - [Partial Order Relation on a Se**t**](https://www.geeksforgeeks.org/dsa/partial-order-relation-on-a-set/)
> - [Elements of POSET](https://www.geeksforgeeks.org/engineering-mathematics/elements-of-poset/)
> - [Partial Orders and Lattices in Discrete Mathematics](https://www.geeksforgeeks.org/engineering-mathematics/partial-orders-lattices/)
## Conclusion
**Partial order sets and lattices are integral to engineering mathematics, providing powerful tools for structuring data and solving complex problems**. Their applications span optimization, network theory, control systems, and data mining, making them indispensable in modern engineering practices. By leveraging these mathematical concepts, engineers can develop more efficient algorithms and systems, driving innovation and technological advancement.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/partial-orders-and-lattices-set-2-mathematics/#:~:text=greatest%20lower%20bound.-,Types%20of%20Lattice,-1.%20Bounded%20Lattice)

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
