---
title: "Closure of Relations"
subject: "Discrete Mathematics"
topic: "Algebraic and Set-Theoretic Structures"
source: "https://www.geeksforgeeks.org/engineering-mathematics/closure-relations/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Algebraic and Set-Theoretic Structures"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/algebraic-and-set-theoretic-structures
---


> [!abstract] Closure of Relations
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Algebraic and Set-Theoretic Structures`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/closure-relations/)

---

# Closure of Relations

Closure of a relation means adding the minimum required ordered pairs to a relation so that it satisfies a desired property (reflexive, symmetric, or transitive) without removing any existing pairs. The original relation remains unchanged, and only the necessary pairs are added.
## Types of Closure
![reflexive_closure](assets/reflexive_closure-4999647d4e.webp)
### 1. Reflexive Closure
The reflexive closure of a relation R on a set A is the smallest relation R′ that contains R and is reflexive. This means that every element in A is related to itself.
**Formula:** R′ = R ∪ {(a,a) ∣ a ∈ A}
**Example:** Let A = {1,2} and R={(1,2)}. The reflexive closure of R is: R′ = {(1,2),(1,1),(2,2)}.
### 2. Symmetric Closure
The symmetric closure of a relation R on a set A is the smallest relation R′ that contains R and is symmetric. This means that if (a,b) ∈ R′, then (b,a) ∈ R′
**Formula:** R′ = R ∪ {(b,a) ∣ (a,b) ∈ R}
**Example:** Let A = {1,2} and R = {(1,2)}. The symmetric closure of R is: R′ = {(1,2),(2,1)}.
### 3. Transitive Closure
The transitive closure of a relation R on a set A is the smallest relation R′ that contains R and is transitive. If you can reach from a → b and b → c, then R′ must include a → c directly.
> **Note:** If (a,b) ∈ R′ and (b,c) ∈ R′, then (a,c) ∈ R′.
## **Algorithm (Warshall's Algorithm)**
Warshall’s Algorithm is used to find the transitive closure of a relation. It checks whether a path exists between two elements through intermediate elements and adds the necessary ordered pairs to make the relation transitive.
**Steps of the Algorithm:**
**1.** Represent the relation R as a 0/1 matrix M, where:
- M[i][j] = 1 if (i, j) ∈ R
- M[i][j] = 0 otherwise
**2.** Select each element k as an intermediate element one by one.
**3.** If M[i][k] = 1 and M[k][j] = 1, then set M[i][j] = 1.
**4.** Repeat this process for all elements in the set.
**5.** The final matrix represents the transitive closure R′.
**Example:** Let A = {1,2,3} and R = {(1,2),(2,3)}.
> Since there is a path from 1 to 2 and from 2 to 3, an indirect relation from 1 to 3 exists. Therefore, add (1,3) to the relation.
>
> Thus, the transitive closure is:
>  R′ = {(1,2),(2,3),(1,3)}.
## Applications in Engineering
1. **Database Theory**: In database theory, the closure of relations is used in query optimization and integrity constraints.
**Example:** Ensuring that a database relation maintains transitive dependencies helps in normalizing the database and reducing redundancy.
**2. Computer Networks**: Closure of relations helps in network routing algorithms to ensure that connections are efficiently managed.
**Example:** Using the transitive closure to find the shortest path in a network by considering all possible routes.
**3. Formal Verification**: In formal methods, closure properties are used to verify the correctness of systems and protocols.
**Example:** Verifying that a system maintains certain properties under all possible transitions can be achieved by computing the transitive closure of the state transition relation.
**4. Compiler Design**: Closure properties are used in data flow analysis to optimize and validate code.
**Example:** Using the transitive closure in reaching definitions analysis to determine all definitions that can reach a particular point in the code.
**5. Social Network Analysis**: In social network analysis, closure properties help understand the reachability and influence within a network.
**Example:** Computing the transitive closure to find all indirect connections between individuals in a social network.
**➢Practice:**[Solved Examples](https://www.geeksforgeeks.org/maths/closure-of-relations-practice-questions/)
### Related Articles
> - [Functional Dependency and Attribute Closure](https://www.geeksforgeeks.org/dbms/functional-dependency-and-attribute-closure/)
> - [Closure of Relations](https://www.geeksforgeeks.org/engineering-mathematics/closure-relations/)
> - [Relations in Mathematics](https://www.geeksforgeeks.org/maths/relation-in-maths/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/closure-relations/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Algebraic and Set-Theoretic Structures

> [!note] Related notes
>
> - [[Cartesian Product of Two Sets]]
> - [[Classes of Functions]]
> - [[Composition of Functions]]
> - [[Equivalence Relations]]
> - [[Groups]]
> - [[Hasse Diagrams]]
> - [[Introduction to Set Theory]]
> - [[Inverse Functions]]
> - [[Modular Addition]]
> - [[Multiplication Modulo]]
