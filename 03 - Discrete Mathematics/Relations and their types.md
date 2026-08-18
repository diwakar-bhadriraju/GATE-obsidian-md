---
title: "Relations in Mathematics"
subject: "Discrete Mathematics"
topic: "Algebraic and Set-Theoretic Structures"
source: "https://www.geeksforgeeks.org/maths/relation-in-maths/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Algebraic and Set-Theoretic Structures"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/algebraic-and-set-theoretic-structures
---


> [!abstract] Relations in Mathematics
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Algebraic and Set-Theoretic Structures`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/relation-in-maths/)

---

# Relations in Mathematics

A relation in mathematics is defined as the relationship between two sets.
- If we are given two sets, set A and set B, and set A has a relation with set B, then each value of set A is related to a value of set B through some unique relation.
- Here, set A is called the domain of the relation, and set B is called the range of the relation.
**Example:** Suppose there are two sets X = {4, 36, 49, 50} and Y = {1, -2, -6, -7, 7, 6, 2}.
A relation R states that "(x, y) is in the relation R if x is a square of y" can be represented using ordered pairs,
- R = {(4, -2), (4, 2), (36, -6), (36, 6), (49, -7), (49, 7)}
Also, the image added below shows two sets, A and B, and the relation between them.
- Set A = {x, y, z}
- Set B = {1, 2, 3}
![Relation Example](assets/Relation-036db116b5.jpg)
## Representation of Relations
In mathematics or [set theory](https://www.geeksforgeeks.org/maths/set-theory/) we can represent the relation using different techniques, and the two important ways to represent the set are,
### **1. Set Builder Notation**
If a relation between two sets is represented using the logical formula, then this type of representation is called the set builder notation.
For example, if we are given two sets, set X = {2, 4, 6} and set Y = {4, 8, 12}. Then, on observing clearly, we can see that each element of set Y is twice each element of set X the relation between them is,
> R {(a, b): b is twice of a, a ∈ X, b ∈ Y}
### **2. Roaster Form**
Roaster form is another way of representing a relation. In roaster form, we use ordered pairs to represent the relation.
For example, if we are given two sets, set X = {2, 4, 6} and set Y = {4, 8, 12}. Then the relation between set X and set Y is represented using the relation R such that,
> R = {(2, 4), (4, 8), (6, 12)}
## Graphing Relations
Relations can be easily represented on the graphs, and representing them on graphs is an easy way of explaining them. The ordered pair in a relation represents a coordinate that can be plotted on the [Cartesian coordinate system](https://www.geeksforgeeks.org/maths/cartesian-coordinate-system/).
- Substitute x with random numerical values in the relation.
- Find the corresponding y value of the respective x value.
- Write the ordered pair such that, {(x, y)}
- Plot these points and join them to find the required curve.
The graph of the relation y = x2 is added below,
![parabolic-function](assets/parabolic-function-78a9410e78.png)
## Importance in Computer Science
Relations are widely used in computer science, often without explicitly calling them “relations.” Some key applications include:
**1. Databases (Relational Model)**
- The term relational database comes directly from the mathematical concept of a relation.
- A database table is a set of tuples — exactly what a relation is in set theory.
**2. Graphs and Networks**
- A graph can be seen as a relation between vertices.
- In an undirected graph, the relation is symmetric.
- In a directed graph, the relation is not necessarily symmetric.
**3. State Machines**
- In automata theory, the **transition function** is a relation between states and inputs to next states.
**4. Other Applications**
- **Data Structures:** Adjacency matrices and adjacency lists in graphs are ways to store relations between nodes.
- **Information Retrieval:** Search engines model the relation between **documents** and **keywords**.
**➢Practice:**[Solved Examples](https://www.geeksforgeeks.org/maths/relations-in-mathematics-practice-questions/)
### Related Articles
> - [Types of Relations](https://www.geeksforgeeks.org/maths/types-of-relation-in-maths/)
> - [Equivalence Relations](https://www.geeksforgeeks.org/maths/equivalence-relations/)
> - [Functions](https://www.geeksforgeeks.org/maths/what-is-a-function/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/relation-in-maths/)

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
