---
title: "Total number of Possible Functions"
subject: "Discrete Mathematics"
topic: "Algebraic and Set-Theoretic Structures"
source: "https://www.geeksforgeeks.org/maths/total-number-possible-functions/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Algebraic and Set-Theoretic Structures"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/algebraic-and-set-theoretic-structures
---


> [!abstract] Total number of Possible Functions
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Algebraic and Set-Theoretic Structures`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/total-number-possible-functions/)

---

# Total number of Possible Functions

Let A and B be two sets with m and n elements, respectively. A function from A to B assigns each element of A to exactly one element of B. Since each element of A has n possible choices in B, the total number of functions from A to B is nᵐ.
![2056958166](assets/2056958166-0167eddd47.webp)
**For example:** X = {a, b, c} and Y = {4, 5}. A function from X to Y can be represented in the figure below.
![2056958168](assets/2056958168-69e345f0e8.webp)
Considering all possibilities of mapping elements of X to elements of Y, the set of functions can be represented in Table 1. 
![2056958167](assets/2056958167-5f2cc83154.webp)
## **Number of onto functions from one set to another**
Let X and Y be two finite sets with ∣X∣ = m and ∣Y∣ = n. A function f : X → Y assigns each element of X to exactly one element of Y.
- For each element of X, there are n choices in Y.
- Since there are m elements in X, the total number of functions is:
> **Note:**
>
> - The formula works only if m ≥ n.
> - If m < n, the number of onto functions is 0 as it is not possible to use all elements of Y.
## Solved Question
**Question 1:** Let X, Y, Z be sets of sizes x, y and z respectively. Let W = X x Y. Let E be the set of all subsets of W. The number of functions from Z to E is: 
**Solution:**
> As W = X x Y is given, number of elements in W is xy. As E is the set of all subsets of W, number of elements in E is 2xy. The number of functions from Z (set of z elements) to E (set of 2xy elements) is 2xyz. So the correct option is (D) 
**Question 2:** Let S denote the set of all functions f: {0, 1}4 → {0, 1}. Denote by N the number of functions from S to the set {0,1}. The value of Log2(Log2N) is: 
**Solution:**
> As given in the question, S denotes the set of all functions f: {0, 1}4 → {0, 1}. The number of functions from {0,1}4 (16 elements) to {0, 1} (2 elements) are 216. Therefore, S has 216 elements. Also, given, N denotes the number of function from S(216 elements) to {0, 1}(2 elements). Therefore, N has 2216 elements. Calculating required value,  Log2(Log2 (2216)) =Log216 = 16.
**Question 3:**The number of onto functions (surjective functions) from set X = {1, 2, 3, 4} to set Y = {a, b, c}
**Solution:**
> Using m = 4 and n = 3, the number of onto functions is: 
> 34 - 3C1(2)4 + 3C214 = 36. 
## Practices Problems
**Question 1:** How many functions can be defined from a set with 3 elements to a set with 2 elements?
**Question 2:** If set A has 4 elements and set B has 3 elements, how many functions can be defined from A to B?
**Question 3:** How many injective (one-to-one) functions can be defined from a set with 3 elements to a set with 5 elements?
**Question 4:** How many surjective (onto) functions can be defined from a set with 4 elements to a set with 3 elements?
**Question 5:** If there are 4 elements in set A and 3 elements in set B, and each element in B must be the image of exactly 2 elements in A, how many such functions are possible?
### **Related Articles:**
> - [Mathematics | Total number of possible functions](https://www.geeksforgeeks.org/maths/total-number-possible-functions/)
> - [Number of possible Functions](https://www.geeksforgeeks.org/maths/total-number-possible-functions/)
> - [Number of Boolean functions](https://www.geeksforgeeks.org/engineering-mathematics/number-of-boolean-functions/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/total-number-possible-functions/)

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
