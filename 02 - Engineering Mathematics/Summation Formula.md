---
title: "Summation Formulas"
subject: "Engineering Mathematics"
topic: "Calculus"
source: "https://www.geeksforgeeks.org/maths/summation-formula/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Calculus"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/calculus
---


> [!abstract] Summation Formulas
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Calculus`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/summation-formula/)

---

# Summation Formulas

In mathematics, the summation is the basic addition of a sequence of numbers, called addends or summands; the result is their sum or total. The summation of an explicit sequence is denoted as a succession of additions.
> For example, the summation of (1, 3, 4, 7) can be written as 1 + 3 + 4 + 7, and the result of this expression is 15, i.e., 1 + 3 + 4 + 7 = 15. Since the addition operation is both associative and commutative, parentheses are not necessary when listing the sequence, and the result will remain the same regardless of the order in which the summands are added.
Building on the concept of summation, a more compact and systematic way to represent a sum is through summation notation, also known as sigma (∑) notation. This notation allows us to express long sums concisely and can be applied to any formula or function.
The general form of summation notation is:
>
$$
\sum_{i=1}^{n} x_i = x_1 + x_2 + \cdots + x_n
$$
Where:
- **ⅈ**  is an index that takes values from the lower limit to the upper limit.
- n denotes the last element up to which the summation extends.
- xi​ represents the i-th term of the sequence.
> **For example**,
>
>
$$
\sum_{i=1}^{10}
$$
>
>  is a sigma notation representing the sum of the finite sequence 1 + 2 + 3 + 4 + ⋯ + 10, where the first element corresponds to i = 1 and the last element is n = 10.
## **Uses of the Summation Formula**
Summation notation can be used in various fields of mathematics:
- [Sequence and Series](https://www.geeksforgeeks.org/dsa/sequences-and-series/)
- [Integration](https://www.geeksforgeeks.org/maths/integration/)
- [Probability](https://www.geeksforgeeks.org/maths/probability-in-maths/)
- [Permutation and Combination](https://www.geeksforgeeks.org/maths/permutations-and-combinations/)
- [Statistics](https://www.geeksforgeeks.org/maths/statistics/)
**Note:** A summation is a short form of repetitive addition. We can also replace summation with a loop of addition.
## **Properties of Summation**
**Property 1**
> i=1**∑**n c = c + c + c + .... + c (n) times = nc 
**For example:** Find the value of  i=1**∑**4 c.
By using property 1 we can directly calculate the value of i=1**∑**4 c as 4×c = 4c.
**Property 2**
> c=1**∑**n kc = (k×1) + (k×2) +  (k×3)  + .... + (k×n) .... (n) times = k × (1 + ... + n)  = k  c=1**∑**n c
**For example:** Find the value of i=1**∑**4 5i.
By using property 2 and 1 we can directly calculate value of i=**1**∑**4 5i as 5 × i=1**∑**4 i = 5 × ( 1 + 2 + 3 + 4) = 50.
**Property 3**
> c=1**∑**n (k+c) = (k+1) + (k+2) +  (k+3)  + .... + (k+n) .... (n) times = (n × k) +  (1 + ... + n)  = nk + c=1**∑**n c
**For example**: Find the value of  i=1∑4 (5+i).
By using property 2 and 3 we can directly calculate value of i=1**∑**4 (5+i) as 5×4 +  i=1**∑**4 i = 20 + ( 1 + 2 + 3 + 4) = 30.
**Property 4**
> k=1**∑**n (f(k) + g(k)) = k=1**∑**n f(k) + k=1**∑**n g(k)
**For example:** Find value of  i=1∑4 (i + i2).
By using property 4  we can directly calculate value of i=1**∑**4 (i + i2) as i=1**∑**4 i  + i=1**∑**4 i2  = ( 1 + 2 + 3 + 4) + (1 + 4 + 9 + 16) = 40.
## **Standard Summation Formulas**
Here is a structured table summarizing all the given formula:
| Type of Sum | Expression | Summation Notation |
| --- | --- | --- |
| Sum of First n Natural Numbers | (1+2+3+...+n) |
$$
\dfrac{n(n+1)}{2}
$$
 |
| Sum of Square of First n Natural Numbers | (12+22+32+...+n2) | i =
$$
1∑n (i^2) = \frac{[n ×(n +1)× (2n+1)]}{6}
$$
 |
| Sum of Cube of First n Natural Numbers | (13+23+33+...+n3) | i=
$$
1∑n (i^2) = \frac{[n ×(n +1)× (2n+1)]}{6}
$$
 |
| Sum of First n Even Natural Numbers | (2+4+...+2n) | i=1**∑**n (2i) = [n ×(n +1)] |
| Sum of first n odd natural numbers | (1+3+...+2n-1) | i=1**∑**n (2i-1) = n2 |
| Sum of Square of First n Even Natural Numbers | (22+42+...+(2n)2) | i=
$$
1∑n (2i)^2 = \frac{[2n(n + 1)(2n + 1)]}{3}
$$
 |
| Sum of Square of First n Odd Natural Numbers | (12+32+...+(2n-1)2) | i=1**∑**n (2i)2 =
$$
\frac{[2n(n + 1)(2n + 1)]}{3}
$$
 |
| Sum of Cube of First n Even Natural Numbers | (23+43+...+(2n)3) | =1**∑**n (2i)3 = 2[n(n+1)]2 |
| Sum of Cube of First n Odd Natural Numbers | (13+33+...+(2n-1)3) | (13+33+...+(2n-1)3) |
### **Related Articles**
> - [Sum of N Terms of AP Formula](https://www.geeksforgeeks.org/maths/sum-of-n-terms-of-an-ap/)
> - [Sum of Natural Numbers](https://www.geeksforgeeks.org/maths/sum-of-natural-numbers/)
> - [Arithmetic Progression and Geometric Progression](https://www.geeksforgeeks.org/maths/arithmetic-progression-and-geometric-progression/)
## Example on Summation Formula
**Example 1:** Find the sum of first 10 natural numbers, using the summation formula.
**Solution:**
> Using the summation formula for sum of n natural number i=1∑n (i) = [n ×(n +1)]/2
> We have sum of first 10 natural numbers =  i=1∑10 (i) = [10 ×(10 +1)]/2 = **55**
**Example 2:** Find the sum of 10 first natural numbers greater than 5, using the summation formula.
**Solution:**
> According to the question:
>
> Sum of 10 first natural numbers greater than 5 =  i=6∑15 (i) 
>
> =  i=1∑15 (i) -  i=1∑5 (i) 
> = [15 × 16 ] / 2 - [5 × 6]/2
> = 120 - 15
> = **105**
**Example 3:** Find the sum of given finite sequence 12 + 22 + 32 + ... 82.
**Solution:**
> Given sequence is 12 + 22 + 32 + ... 82 , it can be written as  i=1∑8 i2 using the property/ formula of summation
>
> i=1∑8 i2 = [8 ×(8 +1)× (2×8 +1)]/6 = [8 × 9 × 17] / 6 
> = 204
**Example 4:** Simplify c=1∑n kc.
**Solution:**
> Given summation formula = c=1∑n kc
> = (k×1) + (k×2) + ...... + (k×n) (n terms)
> = k (1 + 2 + 3 +..... + n)
> c=1∑n kc = **k** **c=1**∑**n** **c**
**Example 5:** Simplify and evaluate x=1∑n (4+x).
**Solution:**
> Given summation is  x=1∑n (4+x)
>
> As we know that c=1∑n (k+c) = nk + c=1∑n c
> Given summation can be simplified as,
> **4n +** **x=1**∑**n** **(x)**
**Example 6:** Simplify x = 1∑n (2x + x2).
**Solution:**
> Given summation is  x=1∑n (2x+x2).
>
> as we know that k=1∑n (f(k) + g(k)) = k=1∑n f(k) + k=1∑n g(k)
> given summation can be simplified as**x=1**∑**n** **(2x) +** **x=1**∑**n** **(x**2**).**
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/summation-formula/)

## GATE CS

- Subject: Engineering Mathematics
- Topic: Calculus

> [!note] Related notes
>
> - [[Absolute Minima and Maxima]]
> - [[Application of Derivative]]
> - [[Cauchy’s mean value theorem]]
> - [[Chain Rule Derivative]]
> - [[Continuity]]
> - [[Differentiability]]
> - [[Euler's Formula]]
> - [[Finding the Various nth term of any polynomial sequence]]
> - [[Indefinite Integrals]]
> - [[Indeterminate Forms]]
