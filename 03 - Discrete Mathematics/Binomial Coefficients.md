---
title: "Binomial Coefficients"
subject: "Discrete Mathematics"
topic: "Combinatorics"
source: "https://www.geeksforgeeks.org/maths/coefficient-in-binomial-expansion/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Combinatorics"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/combinatorics
---


> [!abstract] Binomial Coefficients
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Combinatorics`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/coefficient-in-binomial-expansion/)

---

# Binomial Coefficients

Binomial Coefficients are positive integers represented as nCk where n >= k >= 0. The following are important properties of Binomial Coefficients.
- The value of nCk represents the number of possibilities to pick "k" items from n elements.
- The formula for nCk is **n! / {k! (n - k)!** where ! represents [factorial](https://www.geeksforgeeks.org/maths/factorial/)**.**
- These binomial coefficients of the [Binomial Theorem](https://www.geeksforgeeks.org/maths/binomial-theorem/) , which gives a formula for expanding statements such as **(a + b)**n** **=** **n**C**0** **a**n**b**0** **+** **n**C**1** **a**n-1** **b**1** **+** **n**C**2** **a**n-2** **b**2** **+ …. +** **n**C**r** **a**n-r** **b**r** **+ …. +** **n**C**n** **a**0**b**n** **.** For instance, the binomial coefficients in (x + y)3 are 1, 3, 3, and 1.
  ![Binomial-Theorem](assets/Binomial-Theorem-ffda33e1e0.webp)
- Binomial coefficients are shown in [Pascal's Triangle](https://www.geeksforgeeks.org/maths/pascals-triangle/). In (a + b)n expansion, rows correspond to coefficients. Geometry of coefficients.
![Binomial-Coefficient_](assets/Binomial-Coefficient_-755c5b1564.webp)
Binomial Coefficient
Each coefficient of any row is obtained by adding two coefficients in the preceding row, one on the immediate left and the other on the immediate right and each row is bounded by 1 on both sides.
The (r + 1)th term or general term is given by
> **T**r + 1** **=** **n**C**r** **a**n - r** **b**r**
They determine the weightage of each term in the extended-expression when raised to a [whole number](https://www.geeksforgeeks.org/maths/whole-numbers/) power.
They come in various forms, including:
- **Binomial Coefficients:** The traditional way to see (nk) as a combination, is determined by applying the following formula ( nk)= n! **/** k! × (n-k)!
- **​Pascal's Triangle**: It visually displays binomial coefficients, aiding in quick calculations and showing symmetry and patterns.
- **Multinomial Coefficients:** It extends binomial coefficients to expand polynomials with multiple terms into multinomial expressions.
Every term in the [binomial expansion](https://www.geeksforgeeks.org/maths/binomial-expansion-formula/) has a coefficient known as a binomial coefficient. The coefficient for a term like **a**n-k. They.** **b**k** **in (a + b)**n** is represented by **(**n** **k**)** which can be calculated using the Binomial Theorem Formula specified above.
### Understanding Coefficient in Binomial Expansion
**1. Notation:** representation of binomial coefficients as**n**C**k** where 'n' represents power and ' k ' means a term in expansion.
**2. Meaning:** The binomial theorem states that when expanding a binomial where the first term has an exponent of (n-k) and the second term has an exponent of k, the coefficient **(**n**C**k**) represents the multiplier.
**3. Calculation:** The formula **n**C**k** **= n! / [k! × (n - k)! ]** calculates binomial coefficients. Factorial, denoted by "!**the** " multiplies a number by all positive integers smaller than itself.
## Binomial Theorem
[Binomial theorem](https://www.geeksforgeeks.org/maths/binomial-theorem/) provides a way for the expansion of algebraic statements like (x + y)n. This expansion breaks down the terms involving x and y exponents into a sum with coefficients for each phrase in the expansion.
> Binomial theorem explains the algebraic expansion of a binomial's powers. It states that (x + y)n can be expanded into a sum of terms in the form axb × yc, with specific coefficients and exponents.
### Binomial Theorem Formula
If a and b are real numbers and n is a positive integer, then
> **(a + b)**n** **=** **n**C**0** **a**n** **+** **n**C**1** **a**n**- 1** **b**1**+** **n**C**2** **a**n - 2** **b**2** **+ . . . +** **n**C**r** **a**n - r** **b**r** **+ ... +** **n**C**n** **b**n**
where,
**n**C**r** **= n! / r! (n-r)! for 0 ≤ r ≤ n**
**For example,**
**(x + y)**4** **= x**4**+ 4x**3**y + 6x**2**y**2** **+ 4xy**3** **+ y**4**
The coefficients depend on n and the exponents are non-negative integers that add up to n.
### Important Observations About Binomial Expansion
Some important observations regarding the **The binomial**coefficient of binomial expansion are:
- The binomial expansion consists of n+1 terms, with the power of a decreasing by one in each term and the power of b increasing by one.
- The sum of the indices of a and b in each term is equal to n.
- Coefficients in the expansion follow Pascal's triangle pattern.
- The first term has a power of a equal to n and a power of b equal to 0, while the last term has a power of a equal to 0 and a power of b equal to n.
## Properties of Binomial Coefficients
Various properties of Binomial Coefficients are:
### Symmetry Property
Coefficients of the binomials show symmetry.
- **(** **n**k** **) = (** **n**n-k** **) or (n/k) = (n/(n−k))**
It can be seen from this feature that selecting k items from n elements is equivalent to selecting n−k elements to omit.
### Sum of Coefficients
It says that the sum of Coefficients in the expression (a+b)n  is:
- **⅀**n**k=0** **(** **n**k** **) = 2**n**
### Middle Term Property
Value of n determines the middle term in a binomial expansion.
- For even n, the term at **(n/2 + 1)** position is the middle term.
- For odd n, the terms at **[(n+1)/2 + 1]** and **[(n+3)/2 ]** positions are the two middle terms.
**Also Read**: [**Interesting Facts About Binomial Coefficients**](https://www.geeksforgeeks.org/maths/interesting-facts-about-binomial-coefficients/)
## How to Calculate Binomial Coefficients
Using Factorial Notation. The binomial coefficient ( **n**r** ) can be calculated using factorials:
> **(** **n**r** **)= n! / r! ( n - r)!**
- Where n! (n factorial) is the product of all positive integers up to n.
**For example:**
> **(** **5**2**) = 5! / (2×1) (3×2×1)**
>
> = (5×4×3×2×1) / (2×1×3) (2× 1)
>
> = (5× 4)/ (2×1) = 10
## Exampleson Coefficient in Binomial Expansion
**Example 1. Determine whether the expansion of (x**2** **- 2/x)**18** **will contain a term containing x**10**?**
**Solution:**
> Let Tr + 1 contain x10
>
> Tr + 1  = 18 Cr (x2)18-r - (2/x)r
>
> =18Cr x36 - 2r (-1)r. 2r x- r
>
> = (-1)r 2r 18 Crx36 - 3r
>
> Thus,
>
> 36 - 3r = 10, i.e., r =26/3
>
> Since r is a fraction, the given expansion cannot have a term containing x10
**Example 2. Find the coefficient of x**2** **in {x + (1/x)}**8**
**Solution:**
> Expanding {x + (1/x)}8 using binomial expansion formula,
>
> 8C0 x8(1/x)0 + 8C1 x7(1/x)1 + 8C2 x6(1/x)2 + 8C3 x5(1/x)3 + 8C4 x4(1/x)4 + 8C5 x3(1/x)5 + 8C6 x2(1/x)6 + 8C7 x1(1/x)7 + 8C8 x0(1/x)8
>
> From the expansion, coefficient of x2 is, 8C3 and its value is,
>
> 8C3 = 56
**Example 3. Expand (x + 2)**3**
**Solution:**
> Using Binomial Theorem:
>
> (x + 2)3 = ∑ k3=0 ( 3k )x3−k ⋅2k
>
> Calculate each term:
>
> **For k = 0:**
>
> ( 30 ) x3−0⋅20 = 1
>
> **For k = 1:**
>
> ( 31) x3−1⋅ 21 = 3⋅x2⋅2 = 6x2
>
> For k = 2:
>
> ( 32 ) x3−2 ⋅ 22 = 3 ⋅ x1 ⋅ 4 = 12x
>
> **For k = 3:**
>
> ( 33 ) x3−3 .23 = 1 ⋅ x0 ⋅ 8 = 8
>
> Combining Terms:
>
> (x + 2)3 = x3 + 6x2 + 12x + 8
**Example 4. Use the binomial expansion to approximate (1.01)**5**
**Solution:**
> We can rewrite (1.01)5 as (1 + 0.01)5
>
> Using Binomial Theorem:
>
> (1 + 0.01)5 = ∑ k5=0 (5k) (0.01) k
>
> We can approximate this by using the first few terms (for simplicity, we'll use up to k = 2):
>
> For k = 0: (50) (0.01)0 = 1
>
> For k = 1: ( 51) (0.01)1=5 × 0.01 = 0.05
>
> For k = 2: ( 52) (0.01)2 = 10 × 0.0001 = 0.001
>
> Approximate Sum:
>
> (1 + 0.01)5 ≈ 1 + 0.05 + 0.001 = 1.051
>
> Thus, (1.01)5 ≈ 1.051
**Also Read:** [**General and Middle terms in a Binomial Expansion**](https://www.geeksforgeeks.org/maths/general-and-middle-terms-binomial-theorem-class-11-maths/)
## Conclusion
Binomial coefficients are the numerical values that appear as coefficients in the expansion of a binomial expression (a+b)n using the binomial theorem. These coefficients, often written as
$$
\binom{n}{k}
$$
 or C(n,k), represent the number of ways to choose k elements from a set of nnn elements, making them crucial in combinatorics. Binomial coefficients play a crucial role in mathematical reasoning and problem-solving. Understanding and mastering their concepts can lead to new insights and improved skills.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/coefficient-in-binomial-expansion/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Combinatorics

> [!note] Related notes
>
> - [[Combinatorics Basics]]
> - [[Corollaries of Binomial Theorem]]
> - [[Generalized PnC Set 1]]
> - [[Generalized PnC Set 2]]
> - [[Generating Functions]]
> - [[Pigeonhole Principle]]
> - [[Principle of Inclusion-Exclusion]]
> - [[Cartesian Product of Two Sets]]
> - [[Classes of Functions]]
> - [[Closure of Relations]]
