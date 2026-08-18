---
title: "Introduction to Combinatorics"
subject: "Discrete Mathematics"
topic: "Combinatorics"
source: "https://www.geeksforgeeks.org/engineering-mathematics/mathematics-combinatorics-basics/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Combinatorics"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/combinatorics
---


> [!abstract] Introduction to Combinatorics
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Combinatorics`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/mathematics-combinatorics-basics/)

---

# Introduction to Combinatorics

Combinatorics is a branch of mathematics focused on counting, arranging, and analyzing finite sets. It deals with the study of combinations, permutations, and the structures that arise from these arrangements.
![Permutation-and-Combination-Examples](assets/Permutation-and-Combination-Examples-cop-ff48eb3a95.webp)
Combinatorics
The two fundamental concepts used to calculate the number of ways to arrange or select items:
### 1. Combination
[Combination](https://www.geeksforgeeks.org/maths/combinations/) is a selection of objects where the order does not matter. The formula for the number of combinations of 'n' objects taken 'r' at a time is
> **n**C**r** **= C(n, r) = n!/r!(n - r)!**
### 2. Permutation
[Permutation](https://www.geeksforgeeks.org/maths/permutation/) is an arrangement of objects where the order matters. The formula for the number of permutations of 'n' objects taken 'r' at a time is
> **n**P**r** **= P(n, r) = n!/(n - r)!**
**Example:** Suppose we have 3 variables named x, y, and z. Find the combination and the permutation of two variables from the given variables.
**Solution:**
![Combination-Example](assets/1-1-21d8824d7a.png)
> Combination: **xy, yz, and zx**
![Permutation-Example](assets/2-2-480efc528d.png)
> Permutation: **xy, yx, yz, zy, zx, and xz**
From the example above, we can see that in the permutation, both the xy and yx are written because the order of arrangement matters. However, in the combination, only one of them is written because both are the same things since the order of arrangement does not matter.
## Properties of Combinatorics
Here are some fundamental properties and principles of combinatorics:
### Addition Principle
If there are n ways to perform task If there are n ways to perform task A and m ways to perform task B, and these tasks cannot be done simultaneously, then there are n + m ways to choose one of these tasks.
> **Example:** If you have 3 shirts and 4 pants, there are 3+4 = 7 ways to choose either a shirt or a pant.
### Multiplication Principle
If there are n ways to perform task A and m ways to perform task B, and these tasks are independent (i.e., performing one does not affect the other), then there are n×m ways to perform both tasks.
> **Example:** If you have 3 shirts and 4 pants, there are 3×4 = 12 ways to choose a shirt and a pant.
## Uses of Combinatorics
Here are some key areas where combinatorics is used:
- **Probability Theory:** Combinatorics helps in calculating probabilities by counting the number of favorable outcomes over the total possible outcomes.
- **Graph Theory:** Used to study graphs, which are structures made up of nodes connected by edges.
- **Design and Analysis of Experiments:** Combinatorial designs help in planning experiments to ensure that the data collected is statistically valid and can be analyzed effectively.
- **Algorithms and Data Structures:** Combinatorial algorithms are used in sorting, searching, and optimization problems.
**➢Practice:**[Solved Examples](https://www.geeksforgeeks.org/maths/combinatorics-practice-questions/)
### **Related Articles**
> - [Permutation and Combination](https://www.geeksforgeeks.org/maths/permutations-and-combinations/)
> - [Binomial Theorem](https://www.geeksforgeeks.org/maths/binomial-theorem/)
> - [Pegionhole Principle](https://www.geeksforgeeks.org/engineering-mathematics/discrete-mathematics-the-pigeonhole-principle/)
> - [Fundamental Principle of Counting](https://www.geeksforgeeks.org/maths/fundamental-principle-of-counting/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/mathematics-combinatorics-basics/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Combinatorics

> [!note] Related notes
>
> - [[Binomial Coefficients]]
> - [[Corollaries of Binomial Theorem]]
> - [[Generalized PnC Set 1]]
> - [[Generalized PnC Set 2]]
> - [[Generating Functions]]
> - [[Pigeonhole Principle]]
> - [[Principle of Inclusion-Exclusion]]
> - [[Cartesian Product of Two Sets]]
> - [[Classes of Functions]]
> - [[Closure of Relations]]
