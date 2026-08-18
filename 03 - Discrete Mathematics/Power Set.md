---
title: "Power Set"
subject: "Discrete Mathematics"
topic: "Algebraic and Set-Theoretic Structures"
source: "https://www.geeksforgeeks.org/maths/power-sets/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Algebraic and Set-Theoretic Structures"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/algebraic-and-set-theoretic-structures
---


> [!abstract] Power Set
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Algebraic and Set-Theoretic Structures`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/power-sets/)

---

# Power Set

A power set is basically a set that contains all the possible [subsets](https://www.geeksforgeeks.org/maths/subsets/) of the original given set, including the null or empty set. If we have a set A, then the power set of A contains all the subsets of A, including the empty set.
![12](assets/12-a7faa04e54.webp)
**Other example:** Set A = {1, 2, 9}.
Then its power set will be {∅, {1}, {2}, {9}, {1, 2}, {1, 9}, {2, 9}, {1, 2, 9}}
Let's break down the above Power set:-
> - Here ∅ represents the [Null or Empty Set](https://www.geeksforgeeks.org/maths/empty-set/).
> - {1}, {2}, {9} this represents all the subsets with one elements.
> - {1, 2}, {1, 9}, {2, 9} this represents all the subsets with two elements.
> - Lastly, {1, 2, 9}, which represents the set itself.
Power sets are used in various fields where a list of all possibilities from some finite number of elements is required, such as computer science, data analysis, and even artificial intelligence.
Mathematically, if S is a set, then the power set P(S) is defined as:
> **P(S) = {T | T is a subset of S}**
>
> Where,
>
> - **T** represents a subset of the set S.
> - **"|"** denotes "such that."
> - The curly braces i.e., **{}** indicate a set.
Let see an example for a clear and better understanding, consider a set A = {a, e, i, o, u}, therefore power set of A is given by P(A), i.e.
> **P(A) = {∅,**
>
> **{a}, {e}, {i}, {o}, {u},**
>
> **{a, e}, {a, i}, {a, o}, {a, u}, {e, i}, {e, o}, {e, u}, {i, o}, {i, u}, {o, u},**
>
> **{a, e, i}, {a, e, o}, {a, e, u}, {a, i, o}, {a, i, u}, {a, o, u}, {e, i, o}, {e, i, u}, {e, o, u}, {i, o, u},**
>
> **{a, e, i, o}, {a, e, i, u}, {a, e, o, u}, {a, i, o, u}, {e, i, o, u},**
>
> **{a, e, i, o, u}}**
>
> Here ∅ represents a Null set or Empty set.
## How to Find Power Set?
In order to find a power set, follow these steps:
- Start with a null or empty set.
- Then add all combinations of subsets with one element.
- Then add all combinations of subsets with two elements.
- Do this till you reach the subsets with N-1 elements (where N is the total number of elements in the original set).
- Then add the original set.
## Cardinality of Power Set
**Cardinality** (cardinality of a set means the number of elements of a set) of a power set denotes the number of elements present in the power set. It is denoted by |P(A)|. Thus, number of elements in the power set is given by:
> **|P(A)| = 2**n**
>
> Where "n" is the number of elements of Set A.
**Example:** Find the cardinality of the Power Set of A, where A = {1,2,9}.
**Answer:**
> As |A| = 3, thus number of elements in Power Set of A = 2|A|
>
> Thus, |P(A)| = 23 = 8
>
> Therefore, there are 8 elements in the power set of A.
## Properties of Power Set
There are several properties of the power set, some of which are listed as follows:
- Total number of elements of a power set is 2n ( where n is the total number of elements of the original Set).
- Power Set always contains an empty set and the original set as its members.
- The elements of the power set are always greater than the elements of the original set (since it has 2n elements of the original set).
- The power set of an empty or null set is the set itself.
- An empty or null set's power set is the set itself. Following distributive rules, power sets can be utilized for set operations like [union](https://www.geeksforgeeks.org/maths/union-of-sets/), [intersection](https://www.geeksforgeeks.org/maths/intersection-of-sets/), and [complement](https://www.geeksforgeeks.org/maths/complement-of-a-set/).
- Power set size is always 2n, where n is the size of the initial set.
- Each member of the original set's subsets makes is always a member of power set too.
### **Also Check**
> - [Set Symbols](https://www.geeksforgeeks.org/maths/set-theory-symbols/)
> - [Universal Sets](https://www.geeksforgeeks.org/maths/universal-set/)
> - [Supersets](https://www.geeksforgeeks.org/maths/superset/)
## Solved Examples on Power Set
**Example 1:** Find the total no. of elements and power set for set A = {1, 2, 4, 9}
**Solution:**
> Number of elements of Set A i.e., n(A) = 4,
>
> Total number of elements of Power set = 2n(A)= 24 = 16
>
> ![Power-Set](assets/Power-Set-2cf214e2ed.webp)
**Example 2:** Find the elements of the power set for Set A, where Set A = {9, 18, 5, 6}
**Solution:**
> Since power set contains all possible subset for the given set including the null or empty set.
>
> Therefore Power set of A , P(A) = {∅, {9}, {18}, {5}, {6}, {9, 18}, {9, 5}, {9, 6}, {18, 5}, {18, 6}, {5, 6}, {9, 18, 5}, {9, 18, 6}, {9, 5, 6}, {18, 5, 6}, {9, 18, 5, 6} }
>
> So, the power set of set A = {9, 18, 5, 6} contains 2^4 = 16 elements or subsets.
**Example 3:** Find the number of elements of an empty set?
**Solution:**
> A = { }
>
> Total number of elements of power set of A , P(A) = 20 = 1
>
> P (A) = { }
>
> Power set of an empty set is the set itself.
**Example 4:** What is the size of the power set of a set A with 10 elements?
**Solution:**
> Applying the cardinality rule (|P(A)| = 2n) to calculate the elements of power set :-
>
> No. of elements of power set of Set A or P(A) = 2n , where n is no. of elements of Set A.
>
> Putting the value of n, we get :-
>
> 210 = 1024 elements for the power set.
**Example 5:** How many elements are in set A if set A has a power set with 64 subsets?
**Solution:**
> Let the number of element of Set A be 'x' .
>
> Applying the cardinality rule (|P(A)| = 2n) , we get :-
>
> ⇒ 2x  = 64
>
> ⇒ 2x = 26
>
> Comparing both sides , we get :
>
> x = 6
>
> Therefore no. of elements of set A = 6
## Practice Questions on Power Set
**Q1:** What will be the Power Set of the set A = {2x: -2 ≤ x ≤2}
**Q2:** What will be the Power Set of set P = {x: x is a prime number and x ≤ 50}
**Q3:** What will be the Cardinality of Power Set of set containing first five even natural numbers.
**Q4:** What will be the cardinality of Power Set of the set containing first 7 multiples of 3.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/power-sets/)

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
