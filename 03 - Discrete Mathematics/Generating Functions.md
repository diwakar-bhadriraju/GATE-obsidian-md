---
title: "Generating Functions"
subject: "Discrete Mathematics"
topic: "Combinatorics"
source: "https://www.geeksforgeeks.org/engineering-mathematics/discrete-maths-generating-functions-introduction-prerequisites/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Combinatorics"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/combinatorics
---


> [!abstract] Generating Functions
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Combinatorics`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/discrete-maths-generating-functions-introduction-prerequisites/)

---

# Generating Functions

A generating function is a way to represent a sequence of numbers using a power series. In this series, the coefficients of powers of x represent the terms of the sequence. Generating functions make it easier to solve problems related to sequences, counting, and recurrence relations.
The general form of a generating function is shown below.
![s_no_2](assets/s_no_2-af60158496.webp)
### Basic Prerequisites
Before learning generating functions, we need to understand some basic combinatorics concepts.
**1. Permutation:** An arrangement of objects where the order matters. It tells us how many different ways we can arrange `k` objects from `n` distinct objects.
Number of ways to arrange k objects from n objects:
$$
{}^{n}P_{k} = \frac{n!}{(n-k)!}
$$
**2. Combination:** A selection of objects where the order does not matter. It tells us how many ways we can choose `k` objects from `n` distinct objects.
Number of ways to choose k objects from n objects:
$$
{}^{n}C_{k} = \frac{n!}{k!(n-k)!}
$$
- You should also know the [Geometric Series](https://www.geeksforgeeks.org/maths/geometric-series/) formula, which is the backbone of most generating function derivations:
$$
\sum_{n=0}^{\infty} r^n = \frac{1}{1-r}, \quad |r| < 1
$$
- And the [Binomial Theorem](https://www.geeksforgeeks.org/maths/binomial-theorem/):
$$
(1+x)^n = \sum_{k=0}^{n} \binom{n}{k} x^k
$$
## Important Generating Functions
The following table shows some important generating functions and their corresponding sequences. These standard results are frequently used to solve combinatorial and recurrence relation problems.
![s_no_](assets/s_no_-2b1838fd60.webp)
## Types of Generating Functions
### 1. Ordinary Generating Function (OGF)
A generating function in which the coefficients of powers of x represent the terms of a sequence. It is mainly used in counting problems and combinatorics.
**Formula:**
$$
G(x)=\sum_{n=0}^{\infty} a_n x^n
$$
### 2. Exponential Generating Function (EGF)
A generating function where each term of the sequence is divided by n!. It is commonly used in permutation and arrangement problems where order matters.
**Formula:**
$$
G(x)=\sum_{n=0}^{\infty} a_n \frac{x^n}{n!}
$$
### 3. Dirichlet Generating Function (DGF)
A generating function used mainly in number theory, where the terms are divided by ns, with s being a complex variable.
**Formula:**
$$
G(s)=\sum_{n=1}^{\infty} \frac{a_n}{n^s}
$$
### 4. Probability Generating Function (PGF)
A generating function used in probability theory to represent the probability distribution of a discrete random variable.
**Formula:**
$$
G(x)=\sum_{n=0}^{\infty} P(X=n)x^n
$$
**➢Practice:**[Solved Examples](https://www.geeksforgeeks.org/maths/generating-functions-practice-questions/)
### Related Articles
> - [Discrete Mathematics Tutorial](https://www.geeksforgeeks.org/engineering-mathematics/discrete-mathematics-tutorial/)
> - [Functions in Discrete Mathematics](https://www.geeksforgeeks.org/engineering-mathematics/functions-in-discrete-mathematics/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/discrete-maths-generating-functions-introduction-prerequisites/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Combinatorics

> [!note] Related notes
>
> - [[Binomial Coefficients]]
> - [[Combinatorics Basics]]
> - [[Corollaries of Binomial Theorem]]
> - [[Generalized PnC Set 1]]
> - [[Generalized PnC Set 2]]
> - [[Pigeonhole Principle]]
> - [[Principle of Inclusion-Exclusion]]
> - [[Cartesian Product of Two Sets]]
> - [[Classes of Functions]]
> - [[Closure of Relations]]
