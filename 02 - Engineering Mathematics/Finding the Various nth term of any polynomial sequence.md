---
title: "Finding nth term of any Polynomial Sequence"
subject: "Engineering Mathematics"
topic: "Calculus"
source: "https://www.geeksforgeeks.org/dsa/finding-nth-term-polynomial-sequence/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Calculus"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/calculus
---


> [!abstract] Finding nth term of any Polynomial Sequence
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Calculus`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/finding-nth-term-polynomial-sequence/)

---

# Finding nth term of any Polynomial Sequence

Given a few terms of a sequence, we are often asked to find the expression for the nth term of this sequence. While there is a multitude of ways to do this, In this article, we discuss an algorithmic approach which will give the correct answer for any polynomial expression. Note that this method fails for trigonometric, exponential or other transcendental sequences.
We will take a few examples and discuss the method as we solve these examples.
**Example 1**
Let us take the sequence
```
S = 3, 9, 15, 21, ....
```
Trivial Solution
We can easily see that this is an A.P series. The starting term is 3 and the common difference is 6. Hence the nth term of the sequence is 3 + (n-1) \* 6.
Our Solution
Since we know that an nth order polynomial has the form:
```
Polynomial = Pn = a0 + a1*x^1 + a2*x^2 + ... + an*x^n
```
Since we already know a few terms of the sequence, we can substitute these values in the above expression and obtain some equations. Then we need to solve this system of linear equations and obtain the coefficients a0, a1, ... an.
The trick is to somehow know the order of the polynomial.
This is simple enough to do if we remember that the nth order forward difference is constant for an nth order polynomial. Also all higher order forward differences are 0. Let us obtain the forward differences for the series
```
3   9   15   21   27 ...
  6   6    6     6
```
Since the first forward difference is constant, we conclude that the sequence is a first order polynomial.
```
1st order polynomial Sn  = a0 + a1*n
For n = 1, Sn = 3
3 = a0 + a1   .... (1)
For n = 2, Sn = 9
9 = a0 + 2*a1  .... (2)
Solving (1) and (2) we get
a1 = 6 and a0 = -3
Hence we obtain Sn = -3 + 6*n
```
Note that we obtain slightly different formulations of the sequence in the above two methods. But both these formulations are correct and can easily be converted from one form to another
**Example 2**
```
Lets us take the sequence S =
 9   24    47   78   117  164  219 ...
   15   23   31   39   47    55
      8    8    8    8    8
Since the 2n order forward difference is constant, the Sequence is a 2nd order
polynomial
S = a0 + a1*n + a2 *n*n
Substituting n = 1, 2, 3 and corresponding entries we get
9 = a0 + a1 + a2 ... (1)
24 = a0 + 2*a1 + 4*a2 ... (2)
47 = a0 + 3*a1 + 9*a3 ... (3)
Writing matrices for above equations
A = 1 1 1
    1 2 4
    1 3 9
B = 9 24 47
X = [a0 a1 a2] = inv(A)*B = [ 2 3 4]
Hence a0 = 2, a1 = 3, a2 = 4
Therefore S = 2 + 3*n + 4 * n * n
```
**Example 3**
```
S = 28, 168, 516, 1168, 2220 ...
Forward Differences
28   168   516   1168    2220
  140   348   652    1052
     208   304    400
         96     96
The Sequence is a third order polynomial
S = a0 + a1*n + a2*n*n + a3*n*n*n
Substituting n = 1, 2, 3, 4 and corresponding values
28 = a0 + a1 + a2 + a3
168 = a0 + 2*a1 + 4*a2*a2 + 8*a3*a3*a3
516 = a0 + 3*a1 + 9*a2*a2 + 27*a3*a3*a3
1168 = a0 + 4*a1 + 16*a2*a2 + 64*a3*a3*a3
Writing matrices for above equations
A = 1 1 1 1
    1 2 4 8
    1 3 9 27
    1 4 16 64
B = 28, 168, 516, 1168
X = [a0 a1 a2 a3] = inv(A)*B = [0, 4, 8, 16]
Therefore S = 4*n + 8*n*n + 16*n*n*n
```
**Note:** To solve an nth order Sequence we need to solve a system of n equations. These equations can either be solved by hand or by using matrix-based math calculators like MATLAB, Octave etc. A free online version of Octave is available at [Octave Online](https://octave-online.net/).
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/finding-nth-term-polynomial-sequence/)

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
> - [[Indefinite Integrals]]
> - [[Indeterminate Forms]]
> - [[Lagrange’s Mean Value Theorem]]
