---
title: "Mathematics | Generalized PnC Set 1"
subject: "Discrete Mathematics"
topic: "Combinatorics"
source: "https://www.geeksforgeeks.org/engineering-mathematics/generalized-pnc-set-1/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Combinatorics"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/combinatorics
---


> [!abstract] Mathematics | Generalized PnC Set 1
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Combinatorics`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/generalized-pnc-set-1/)

---

# Mathematics | Generalized PnC Set 1

**Prerequisite -** [PnC and Binomial Coefficients](https://www.geeksforgeeks.org/engineering-mathematics/mathematics-pnc-binomial-coefficients/) 
So far every problem discussed in previous articles has had sets of distinct elements, but sometimes problems may involve repeated use of elements. This article covers such problems, where elements of the set are indistinguishable (or identical or not distinct).
**Permutations with repetition -**
Counting permutations when repetition of elements can be easily done using the product rule. 
Example, number of strings of length
$$
r
$$
is
$$
26^r
$$
, since for every character there are 26 possibilities.
```
The number of r-permutations of a set of n objects
with repetition is n^r.
```
**Combinations with repetition -**
Counting the number of combinations with repetition is a bit more complicated than counting permutations. Consider a set of
$$
n
$$
types of objects and we need to find out in how many ways can
$$
r
$$
elements be chosen. 
To solve the above problem we will first take a look at a similar problem that is arranging bars(|) and stars(\*). Suppose there are 5 bars and 3 stars. One possible arrangement is -
```
||*||**|
```
They can be arranged in
$$
\frac{8!}{5!3!} = C(8,3) = C(8,5)
$$
ways. 
Our original problem is similar to the above problem. The bars represent divisions between the types of elements such that each type is separated by a bar and the number of stars is
$$
r
$$
. 
If a star is before the nth bar, then that means an item of nth type is selected, except for the last type where the star can be after a bar. For example, the arrangement mentioned above, ||\*||\*\*|, represents a selection of 1 element of 3rd type and 2 elements of 5th type. 
In this way our original problem can be thought of as arranging
$$
r
$$
stars (elements) and
$$
(n-1)
$$
bars(divisions). The above result can be generalized as- 
```
There are C(r+n-1,r) = C(r+n-1,n-1)
r-combinations from a set with n
elements when repetition is allowed.
```
- **Example 1 -** In how many ways can 4 drinks can be chosen out of 6 possible types of drinks? There is no restriction on the number of drinks of a type that can be chosen and drinks of the same type are indistinguishable.
- **Solution -** The above scenario is a direct application of finding combinations with repetition. So the number of 4-combinations is -
$$
C(6-1+4,4) = C(9,4) = 126
$$
  .
- **Example 2 -** How many solutions does the equation
$$
x_1+x_2+x_3=11
$$
  have, where
$$
x_1, x_2,\:and\:x_2
$$
  are non-negative integers?
- **Solution -**
$$
x_1, x_2,\:and\:x_2
$$
  can have values ranging from 0 to 11. This situation is analogous to finding 11-combinations of 3 types of objects. 
  So number of solutions is -
$$
C(3-1+11,11) = C(13,11) = C(13,2) = 78
$$
- **Example 3 -** Consider the same question as Example 2 but with the additional constraint that
$$
x_1 \geq 1
$$
  .
- **Solution -** Since the minimum value of
$$
x_1
$$
  is 1, the effective equation becomes
$$
x_1+x_2+x_3=10
$$
  . So the number of solutions is-
$$
C(3-1+10,10) = C(12,10) = C(12,2) = 66
$$
- **Example 4 -** Consider the same question as Example 2 but with the additional constraint that
$$
x_1 < 2
$$
  .
- **Solution -** Since the constraint is not a lower limit but an upper limit, it cannot be solved in the same way as in Example 3. There is another way of solving such problems. 
  For each type of object we assign a polynomial of the form -
$$
x^{ll} + x^{ll+1} +...+ x^{ul}
$$
  , where 'll' and 'ul' are the lower and upper limits for that type of object. 
  Then all such polynomials are multiplied and the coefficient of
$$
x^r
$$
  is the number of
$$
r
$$
  -combinations. 
  In our case, there is a constraint only on
$$
x_1
$$
  . Its polynomial therefore is- 
$$
x^0 + x^1
$$
  Polynomial for
$$
x_2
$$
  and
$$
x_3
$$
  is- 
$$
x^0+x^1+x^2+x^3+x^4+x^5+x^6+x^7+x^8+x^9+x^{10}+x^{11}
$$
  Since multiplying polynomials can be tedious, we use a trick which uses the binomial theorem. 
  The above polynomial can be extended to be an infinite series since the higher order terms won't make any difference as we are only looking for the coefficient of
$$
x^{11}
$$
  . 
  So the polynomial for
$$
x_2
$$
  and
$$
x_3
$$
  is- 
$$
x^0+x^1+x^2+x^3+...+x^{11}+...
$$
  The above polynomial is also the expansion for
$$
(1-x)^{-1}
$$
  . 
  On multiplying the polynomials we get- 
$$
(1+x)*\frac{1}{(1-x)^2}
$$
$$
\frac{1}{(1-x)^2}
$$
  can be expanded through binomial theorem for negative exponents. We won't need to expand the complete polynomial, as we just need the terms
$$
x^{11}
$$
  and
$$
x^{10}
$$
  , because they will be multiplied by 1 and
$$
x
$$
  to get terms of
$$
x^{11}
$$
  . 
$$
\frac{1}{(1+x)^n} = \sum_{k=0}^{\infty} \binom{n+k-1}{k} (-1)^k x^k
$$
  . 
  For
$$
x^{10}
$$
$$
k=10
$$
  , we get- 
$$
\binom{2 + 10 - 1}{10} (-1)^{10} (-x)^{10} = 11x^{10}
$$
  For
$$
x^{11}
$$
$$
k=11
$$
  , we get- 
$$
\binom{2 + 11 - 1}{11} (-1)^{11} (-x)^{11} = 12x^{11}
$$
  On multiplying the above obtained terms with
$$
x
$$
  and 1 we get terms of
$$
x^{11}
$$
  . On adding them up we get-
$$
23x^{11}
$$
  . 
  Therefore there are 23 solutions to the given equation.
- **Example 5 -** Consider the same question as in Example-2 but with an inequality i.e.
$$
x_1+x_2+x_3 \leq 11
$$
  .
- **Solution -** We could solve this problem in 2 ways. 
  One way is to add up all
$$
r
$$
  -combinations for values of
$$
r
$$
  starting from 0 upto 11 i.e. 
$$
x_1 + x_2 + x_3 = r
$$
  for
$$
0\leq r \leq11
$$
  . We get the following values- 
  For
$$
r
$$
  = 0, ways = C(3-1+0,2) = C(2,2) = 1 
  For
$$
r
$$
  = 1, ways = C(3-1+1,2) = C(3,2) = 3 
  For
$$
r
$$
  = 2, ways = C(3-1+2,2) = C(4,2) = 6 
  For
$$
r
$$
  = 3, ways = C(3-1+3,2) = C(5,2) = 10 
  For
$$
r
$$
  = 4, ways = C(3-1+4,2) = C(6,2) = 15 
  For
$$
r
$$
  = 5, ways = C(3-1+5,2) = C(7,2) = 21 
  For
$$
r
$$
  = 6, ways = C(3-1+6,2) = C(8,2) = 28 
  For
$$
r
$$
  = 7, ways = C(3-1+7,2) = C(9,2) = 36 
  For
$$
r
$$
  = 8, ways = C(3-1+8,2) = C(10,2) = 45 
  For
$$
r
$$
  = 9, ways = C(3-1+9,2) = C(11,2) = 55 
  For
$$
r
$$
  = 10, ways = C(3-1+10,2) = C(12,2) = 66 
  For
$$
r
$$
  = 11, ways = C(3-1+11,2) = C(13,2) = 78 
  Total number of solutions = 364 
  The above problem is the same as finding the number of solutions for the equation- 
$$
x_1+x_2+x_3+x_4 = 11
$$
  The extra variable can be thought of as the difference of 11 and
$$
(x_1+x_2+x_3)
$$
  . 
  When
$$
x_1+x_2+x_3
$$
  is 0,
$$
x_4
$$
  is 11. So
$$
x_4
$$
  takes values accordingly. 
  And the number of solutions of this equation is - C(4-1+11,4-1) = C(14,3) = 364.
**References -**
[Permutations and Combinations](https://www.cs.sfu.ca/~ggbaker/zju/math/perm-comb-more.html) 
Discrete Mathematics and its Applications, by Kenneth H Rosen
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/generalized-pnc-set-1/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Combinatorics

> [!note] Related notes
>
> - [[Binomial Coefficients]]
> - [[Combinatorics Basics]]
> - [[Corollaries of Binomial Theorem]]
> - [[Generalized PnC Set 2]]
> - [[Generating Functions]]
> - [[Pigeonhole Principle]]
> - [[Principle of Inclusion-Exclusion]]
> - [[Cartesian Product of Two Sets]]
> - [[Classes of Functions]]
> - [[Closure of Relations]]
