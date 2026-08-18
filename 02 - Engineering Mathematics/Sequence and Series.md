---
title: "Sequences and Series"
subject: "Engineering Mathematics"
topic: "Calculus"
source: "https://www.geeksforgeeks.org/dsa/sequences-and-series/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Calculus"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/calculus
---


> [!abstract] Sequences and Series
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Calculus`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/sequences-and-series/)

---

# Sequences and Series

A **sequence** is an ordered list of numbers following a specific rule. Each number in a sequence is called a "term." The order in which terms are arranged is crucial, as each term has a specific position, often denoted as an​, where n indicates the position in the sequence.
**For example**:
> - 2, 5, 8, 11, 14, . . . [Here, each term is 3 more than the previous term]
> - 3, 6, 12, 24, 48, . . . [Here, each term is 2 times of the preceding term]
> - 0, 1, 1, 2, 3, 5, 8, 13, 21, . . . [Here, each term is sum of two preceding terms]
A **series** is the sum of the terms of a sequence. If we have a sequence a1, a2, a3, . . . the series associated with it is:
> S = a1 + a2 + a3 + . . .
**Real-life example of a series**: Saving money with a fixed deposit
> Suppose you save ₹1,000 every month in a bank account that gives interest.
>  The total amount after a year is the sum of 12 deposits plus interest — that’s an arithmetic or geometric series, depending on how interest is applied.
### **Arithmetic Sequence**
An **arithmetic sequence** (or arithmetic progression) is a sequence of numbers in which the difference between consecutive terms is constant. This difference is called the [**common difference**](https://www.geeksforgeeks.org/maths/common-difference-of-an-arithmetic-progression/) (denoted as d).
**For example:**
> - 2, 5, 8, 11, 14, . . . (first term = 2 and common difference = 3)
> - 10, 7, 4, 1, −2, . . . (first term = 10 and common difference = -3)
> - 1, 2.5, 4, 5.5, 7, . . . (first term = 1 and common difference = 1.5)
The sequence in which each consecutive term has a common difference, and this difference could be positive, negative, or even zero, is known as an arithmetic sequence.
### **Geometric Sequence**
A **geometric sequence** (or geometric progression) is a sequence of numbers in which the ratio between consecutive terms is constant. This ratio is known as the common ratio (denoted as r).
**For example:**
> - 3, 6, 12, 24, 48, . . . (first term = 3 and common ratio = 2)
> - 1, 3, 9, 27, 81, . . . (first term = 1 and common ratio = 3)
> - 16, 8, 4, 2, 1, . . . (first term = 16 and common ratio = 1/2)
> - 5, −10, 20, −40, 80, . . . (first term = 5 and common ratio = -2)
### **Harmonic Sequence**
A **harmonic sequence** (or harmonic progression) is a sequence of numbers where the reciprocals of the terms form an arithmetic sequence. In other words, if the sequence is a1, a2, a3, . . . , then the sequence of reciprocals 1/a1, 1/a2, 1/a3, . . . is an arithmetic sequence.
**For example:**
> - 1, 1/2​, 1/3​, 1/4​, 1/5​, . . . (as 1, 2, 3, 4, 5, . . . is arithmetic sequence)
> - 3, 3/2, 1, 3/4, 3/5, . . . (1/3, 2/3, 3/3, 4/3, 5/3, . . . is arithmetic sequence)
## Formulas for Sequence and Series
For arithmetic, geometric, and harmonic sequences, there are various formulas to calculate the nth term or the sum of the sequence. These formulas are:
| **Type** | **Formula** | **Description** |
| --- | --- | --- |
| **n**th** **term of an Arithmetic Sequence** | an​ = a1​ + (n − 1)d | nth term of an arithmetic sequence |
| [**Sum of an Arithmetic Series**](https://www.geeksforgeeks.org/maths/sum-of-n-terms-of-an-ap/) | Sn​= 2n​(a1​ + an​) | Sum of the first n terms of an arithmetic series |
| **n**th** **term of Geometric Sequence** | an​= a ​⋅ rn−1 | nth term of a geometric sequence |
| **Sum of Geometric Series (Finite)** | Sn​ = a(1 − rn)/(​1 − r) | Sum of the first n terms of a geometric series |
| **Sum of Geometric Series (Infinite)** | **S**∞**= a/(1 − r)​​ (For r < 1}** | The sum of the infinite geometric series where r < 1. |
| **Harmonic Series** | **H**n**​= ∑**n**k=1**(1/k)** | Sum of the first n terms of the harmonic series |
## Sequences vs Series
Sequence and series are often used interchangeably by many, but there is a very clear [difference](https://www.geeksforgeeks.org/maths/difference-between-series-and-sequence/) between them.
| **Sequence** | **Series** |
| --- | --- |
| An ordered list of numbers, following a specific rule or pattern. | The sum of the terms of a sequence. |
| Typically denoted as an or {an}. | Typically denoted as Sn or ∑an. |
| 1, 2, 3, 4, 5, . . . (Arithmetic sequence) | 1 + 2 + 3 + 4 + 5 + . . . (Sum of the sequence) |
| Focuses on the terms themselves. | Focuses on the sum of the terms. |
| Written as a list or a formula for the nth term. | Written using summation notation (∑). |
| Used to define patterns or behaviors in data sets. | Used to calculate totals, averages, or in calculus for convergence. |
| Not applicable; it is a list of values. | It can converge to a limit (infinite series) or diverge. |
## Convergence and Divergence of Series
Given a sequence {an}, the series is written as:
$$
\sum_{n=1}^{\infty} a_n = a_1 + a_2 + a_3 + \dots
$$
- A series
$$
\sum_{n=1}^{\infty} a_n​
$$
   **converges** if the sequence of partial sums SN = a1 + a2 + ⋯ + aN​ approaches a finite limit as N → ∞:
>
$$
\lim_{N \to \infty} S_N = S
$$
Where S is a finite number. In this case, the series is said to have the sum S.
- A series
$$
\sum_{n=1}^{\infty} a_n​
$$
   **diverges** if the sequence of partial sums SN does not approach a finite limit as N→∞. In other words, if SN​ either grows without bound or oscillates as N → ∞, the series diverges.
### Special Series
Some special series are:
- **Arithmetic-Geometric Series** (AGS) is a special type of series that combines both arithmetic and geometric sequences. It can be expressed in the form:
> S = a + (a + d)x + (a + 2d)x2 + (a + 3d)x3 + . . .
- **Binomial Series** is an infinite series that provides a way to expand expressions of the form (a + b)n, where n is any real number (not just a positive integer). The series is derived from the [Binomial Theorem](https://www.geeksforgeeks.org/maths/binomial-theorem/), which states that:
>
$$
(a + b)^n = \sum_{k=0}^{\infty} \binom{n}{k} a^{n-k} b^k
$$
- [Taylor Series](https://www.geeksforgeeks.org/engineering-mathematics/taylor-series/) of a function f(x) about a point a is given by the formula:
>
$$
f(x) = f(a) + f'(a)(x - a) + \frac{f''(a)}{2!}(x - a)^2 + \frac{f'''(a)}{3!}(x - a)^3 + \ldots
$$
This can be expressed in summation notation as:
>
$$
f(x) = \sum_{n=0}^{\infty} \frac{f^{(n)}(a)}{n!}(x - a)^n
$$
- [Maclaurin Series](https://www.geeksforgeeks.org/engineering-mathematics/maclaurin-series/) is a special case of the Taylor Series, where the expansion is around the point a = 0:
>
$$
f(x) = f(0) + f'(0)x + \frac{f''(0)}{2!}x^2 + \frac{f'''(0)}{3!}x^3 + \ldots
$$
In summation form, it is:
>
$$
f(x) = \sum_{n=0}^{\infty} \frac{f^{(n)}(0)}{n!}x^n
$$
### **Also Check**
> - [Special Series in Maths](https://www.geeksforgeeks.org/maths/special-series-sequences-and-series-class-11-maths/)
> - [Laurent Series](https://www.geeksforgeeks.org/engineering-mathematics/laurent-series/)
> - [Power Series](https://www.geeksforgeeks.org/engineering-mathematics/power-series/)
> - [Fibonacci Sequence](https://www.geeksforgeeks.org/maths/fibonacci-sequence/)
> - [Convergence Tests](https://www.geeksforgeeks.org/engineering-mathematics/convergence-tests/)
## Solved Examples on Sequence and Series
**Question 1:** Find the 10th term of the sequence: 4, 8, 12, 16, 20, ...
**Solution**:
> Use the formula for the nth term of an arithmetic sequence: **a**n** **= a**1** **+ (n − 1) ⋅ d**
>
> For n = 10
>
> a10 = 4 + (10 − 1) ⋅ 4 = 4 + 36 = 40
>
> **Answer**: The 10th term is 40.
**Question 2:** Find the sum of the first 6 terms of the sequence: 2, 6, 18, 54, 162, …
**Solution**:
> Use the sum formula for the first n terms of a geometric series:
>
>
$$
S_n = a \cdot \frac{1 - r^n}{1 - r}
$$
>
> For n = 6:
>
>
$$
S_6 = 2 \cdot \dfrac{1 - 3^6}{1 - 3} = 2 \cdot \dfrac{1 - 729}{-2} = 2 \cdot \dfrac{-728}{-2}
$$
>
> **Answer**: The sum of the first 6 terms is 728.
**Question 3:** If the sequence is 1, 12, 13, …, find the sum of the first 5 terms of the harmonic series.
**Solution**:
> The harmonic sequence is
>
>
$$
\frac{1}{2} + \frac{1}{3} + \frac{1}{4} + \frac{1}{5}
$$
>
>
$$
S_5 = 1 + \frac{1}{2} + \frac{1}{3} + \frac{1}{4} + \frac{1}{5} = 2.2833
$$
>
> **Answer**: The sum of the first 5 terms is approximately 2.2833.
**Question 4:** Calculate the sum of the first 15 terms of the sequence: −5, −2, 1, 4, 7, …
**Solution**:
> Use the sum formula for an arithmetic series:
>
>
$$
S_n = \frac{n}{2} \cdot (2a_1 +(n-1) d)
$$
>
> For the first 15 terms:
>
> - n = 15,
> - a1 = −5,
> - d = 3
>
> Now, calculate the sum:
>
> - S15 ​= 15/2​⋅(2⋅( −5) + (15 − 1)⋅3)
> - S15​ = 15​/2 ⋅ ( -10 + 42)
> - S15​ = 15​/2 ⋅ (32)
> - S15​ = 15 ⋅ 16 = 240
>
> **Answer**: The sum of the first 15 terms is 240.
**Question 5:** Find the sum of the infinite geometric series:
$$
\frac{5}{3} + \frac{5}{9} + \dots
$$
**Solution**:
> Use the sum formula for an infinite geometric series (when ∣r∣<1):
>
>
$$
S_{\infty} = \frac{a}{1 - r}
$$
>
> where:
>
> - a1 is the first term,
> - r is the common ratio
>
> The first term of the series is 5/3, and the common ratio is 1/3
>
> Apply the formula for the infinite series:
>
> The series converges if the absolute value of the common ratio ∣r∣<1|, which is true here because ∣r∣=1/3.
>
> Now, applying the formula:
>
>
$$
S_\infty = \dfrac{\frac{5}{3}}{1 - \dfrac{1}{3}} = \dfrac{\frac{5}{3}}{\dfrac{2}{3}} = \dfrac{5}{3} \times \dfrac{3}{2} = \dfrac{5}{2}
$$
>
> **Answer**: The sum of the infinite series is 2.5
**Question 6:** The nth term of a sequence is given by the formula: an = a1 + (n − 1) d. If the first term a1 = 10 and the common difference d = −2, what is the 8th term of the sequence?
**Solution**:
> Use the formula for the nth term of an arithmetic sequence:
>
> an = a1 + (n − 1) ⋅ d
>
> For n = 8:
>
> a8 = 10 + (8 − 1)⋅(−2)
> a8 = 10 + 7⋅(−2)
> a8 = 10 − 14
> = −4
>
> **Answer**: The 8th term is -4.
### Practice Questions on Sequence and Series
1. Find the 12th term of the sequence: 5, 10, 15, 20, 25, ...
2. Find the sum of the first 8 terms of the sequence: 3, 9, 27, 81, 243, ...
3. If the sequence is 2, 6, 10, …, find the sum of the first 10 terms.
4. Calculate the sum of the first 20 terms of the sequence: 7, 11, 15, 19, 23, ...
5. Find the sum of the infinite geometric series: 1/4 + 1/16 + …
6. The nth term of a sequence is given by the formula: an = a1 + (n − 1)⋅d. If the first term a1 = 3 and the common difference d = 5, what is the 15th term of the sequence?
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/sequences-and-series/)

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
