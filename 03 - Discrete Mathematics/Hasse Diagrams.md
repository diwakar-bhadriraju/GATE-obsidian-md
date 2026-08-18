---
title: "Hasse Diagrams"
subject: "Discrete Mathematics"
topic: "Algebraic and Set-Theoretic Structures"
source: "https://www.geeksforgeeks.org/engineering-mathematics/discrete-mathematics-hasse-diagrams/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Algebraic and Set-Theoretic Structures"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/algebraic-and-set-theoretic-structures
---


> [!abstract] Hasse Diagrams
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Algebraic and Set-Theoretic Structures`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/discrete-mathematics-hasse-diagrams/)

---

# Hasse Diagrams

A Hasse diagram is a graphical representation of the relation of elements of a partially ordered set ([poset](https://www.geeksforgeeks.org/engineering-mathematics/partial-orders-lattices/)). It represents the order of elements without showing every relation explicitly. Instead, only the covering relations are drawn, making the diagram easier to understand.
- Each element of the poset is shown as a point (or node)
- If **p** < **q** and there is no element **r** such that **p** < **r**, then **p** and **q** are joined by a line, with **p** placed below **q**.
- Redundant connections are omitted (e.g., if **A** < **B** and **B** < **C**, the direct link **A** < **C** is skipped).
- Larger elements are placed above smaller elements, so arrows are not required because the upward direction indicates the order.
> **Note:** To draw a Hasse diagram, the provided set must be a poset. 
A poset A is a pair (B, ≤), where B is a set and ≤ is a partial order on B that satisfies the following:
> - Reflexivity → p ≤ p ∀ p 𝜖 B
> - Anti-symmetric → p ≤ q and q ≤ p if p = q
> - Transitivity → if p ≤ q and q ≤ r, then p ≤ r
### Steps to Draw a Hasse Diagram
Follow these steps to draw a Hasse diagram:
> **Step 1:** List all the elements of the set.
>
> **Step 2:** Determine the ordering relation between the elements (such as divisibility, subset, or less than).
>
> **Step 3:** Identify the covering relations by removing all transitive relations.
>
> **Step 4:** Draw each element as a point, placing smaller elements at the bottom and larger elements at the top.
>
> **Step 5:** Connect only the covering pairs with straight line segments.
### **Properties**
- Maximal element is an element of a POSET that is not less than any other element of the POSET. Or we can say that it is an element that is not related to any other element. Top elements of the Hasse Diagram.
- A minimal element is an element of a POSET that is not greater than any other element of the POSET. Or we can say that no other element is related to this element. Bottom elements of the Hasse Diagram.
- The greatest element (if it exists) is the element succeeding all other elements. If it exists, it is unique.
- The least element is the element that precedes all other elements. If it exists, it is unique.
**➢Practice:**[Solved Examples](https://www.geeksforgeeks.org/maths/hasse-diagrams-practice-questions/)
### Related Articles
> - [Partial Orders and Lattices](https://www.geeksforgeeks.org/engineering-mathematics/partial-orders-lattices/)
> - [Discrete Mathematics](https://www.geeksforgeeks.org/engineering-mathematics/discrete-mathematics-tutorial/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/discrete-mathematics-hasse-diagrams/)

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
> - [[Introduction to Set Theory]]
> - [[Inverse Functions]]
> - [[Modular Addition]]
> - [[Multiplication Modulo]]
