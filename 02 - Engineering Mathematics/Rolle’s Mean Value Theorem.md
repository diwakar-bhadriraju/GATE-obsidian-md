---
title: "Rolle's Mean Value Theorem"
subject: "Engineering Mathematics"
topic: "Calculus"
source: "https://www.geeksforgeeks.org/engineering-mathematics/rolles-theorem/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Calculus"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/calculus
---


> [!abstract] Rolle's Mean Value Theorem
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Calculus`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/rolles-theorem/)

---

# Rolle's Mean Value Theorem

In calculus, there exists a theorem that guarantees the existence of a point where the slope of the tangent is zero if a function starts and ends at the same value on an interval. This result is known as Rolle’s Theorem. It is one of the core theorems in differential calculus.
![Rolle-Theorem](assets/Rolle-Theorem-0f194899b8.webp)
Rolle's Theorem Graph
**Formula used for Rolle's Theorem:**
> **f'(c) = 0**
## Statement
A function **f** is defined in the closed interval [a, b] in such a way that it satisfies the following condition:
1. f(x) is continuous in the closed interval a ≤ x ≤ b
2. f(x) is differentiable in the open interval a < x < b
3. f(a) = f(b)
Then, there exists at least one point 'c' in the open interval (a, b) such that:
> **f'(c) = 0**
## Geometric Interpretation of Rolle’s Theorem
We can visualize Rolle's theorem from the figure(1) added below,
![Geometric Interpretation of Rolle’s Theorem](assets/mathematices1-2fa6b818d4.png)
In the above figure the function satisfies all three conditions given above. So, we can apply Rolle's theorem, according to which there exists at least one point 'c' such that:
> **f'(c) = 0**
which means that there exists a point at which the slope of the tangent at that is equal to 0. We can easily see that at point 'c' slope is 0. Similarly, there could be more than one points at which slope of tangent at those points will be 0. Figure(2) added below is one of the example where exists more than one point satisfying Rolle's theorem.
![Geometric Interpretation of Rolle’s Theorem](assets/mathematices2-5eddf2c165.png)
## Proof of Rolle's Mean Value Theorem
Consider a function f that satisfies the conditions of Rolle's Theorem:
1. Since f is continuous on [a,b] and differentiable on (a,b) by the Extreme Value Theorem, f attains its maximum and minimum values on [a,b].
2. If the maximum or minimum value is attained at some point c in (a,b), then f′(c)=0 since the tangent line at c is horizontal.
3. If the maximum and minimum values are attained at the endpoints a or b, then f is constant on [a,b] and f′(x)=0 for all x in (a,b).
Therefore, there exists at least one point c in (a,b) such that f′(c) = 0.
### **Related Articles:**
> - [Mean Value Theorem](https://www.geeksforgeeks.org/maths/mean-value-theorem/)
> - [Rolle's Theorem and Lagrange's Mean Value Theorem](https://www.geeksforgeeks.org/maths/rolles-theorem-and-lagranges-mean-value-theorem/)
> - [Lagrange's Mean Value Theorem](https://www.geeksforgeeks.org/engineering-mathematics/lagranges-mean-value-theorem/)
## Applications of Rolle's Mean Value Theorem in CS
Various applications of Rolle's Mean Value theorem in CS field:
- **Algorithm Correctness:** In analyzing functions used in algorithms, Rolle’s theorem guarantees the existence of critical points (where derivative = 0), important in optimization and proving algorithm stability.
- **Signal Processing:** When signals start and end at the same value, Rolle’s theorem ensures that somewhere in between the rate of change of the signal is zero (flat point), useful in compression and smoothing.
- **Computer Graphics & Animation:** While designing curves that begin and end at the same height, Rolle’s theorem ensures there will be at least one point of horizontal tangent, useful for smooth rendering.
## Solved Examples on Rolle's Theorem
**Example 1:** Verify Rolle’s theorem for function y = x2 + 4, a = –1 and b = 1.
**Solution:**
> Given function y = x2 + 4, as it is a polynomial function, is continuous in [– 1, 1] and differentiable in (–1, 1). Also,
>
> f(-1) = (-1)2 + 4 = 1 + 4 = 5
>
> f(1) = (1)2 + 4 = 1 + 4 = 5
>
> Thus, f(– 1) = f(1) = 5
>
> Hence, the function f(x) satisfies all conditions of Rolle's theorem.
>
> Now, f'(x) = 2x
>
> Rolle’s theorem states that there is a point c ∈ (– 1, 1) such that f′(c) = 0.
>
> 2c = 0
>
> c = 0, where c = 0 ∈ (–1, 1)
**Example 2:** Verify Rolle’s theorem for function y = 2x + 8, a = –1 and b = 1.
**Solution:**
> Given function y = 2x + 8, as it is a polynomial function, is continuous in [– 1, 1] and differentiable in (–1, 1). Also,
>
> f(-1) = 2(-1) + 8 = -2 + 8 = -6
>
> f(1) = 2(1) + 8 = 2 + 8 = 10
>
> Thus, f(– 1) ≠ f(1)
>
> Hence, Rolle's theorem is not applicable.
**Example 3:** Verify Rolle's theorem for f(x) = 3x - 2, a = 0 and b = 2.
**Solution:**
> f(x) = 3x - 2 is a polynomial, so it's continuous on [0, 2] and differentiable on (0, 2).
>
> f(0) = 3(0) - 2 = -2
>
> f(2) = 3(2) - 2 = 4
>
> Thus, f(0) ≠ f(2)
>
> Hence, Rolle's theorem is not applicable.
**Example 4:** Verify Rolle's theorem for f(x) = x² + 1, a = -2 and b = 2.
**Solution:**
> f(x) = x² + 1 is a polynomial, so it's continuous on [-2, 2] and differentiable on (-2, 2).
>
> f(-2) = (-2)² + 1 = 5
>
> f(2) = (2)² + 1 = 5
>
> Thus, f(-2) = f(2)
>
> Rolle's theorem is applicable. (c = 0 where f'(c) = 0)
**Example 5:** Verify Rolle's theorem for f(x) = |x|, a = -1 and b = 1.
**Solution:**
> f(x) = |x| is continuous on [-1, 1], but not differentiable at x = 0.
>
> f(-1) = |-1| = 1
>
> f(1) = |1| = 1
>
> Thus, f(-1) = f(1)
>
> However, f(x) is not differentiable on the entire open interval (-1, 1).
>
> Hence, Rolle's theorem is not applicable.
**Example 6:** Verify Rolle's theorem for f(x) = ex, a = 0 and b = ln(2).
**Solution:**
> f(x) = ex is continuous and differentiable everywhere.
>
> f(0) = e0 = 1
>
> f(ln(2)) = e(ln(2)) = 2
>
> Thus, f(0) ≠ f(ln(2))
>
> Hence, Rolle's theorem is not applicable.
**Example 7:** Verify Rolle's theorem for f(x) = cos(x), a = 0 and b = 2π.
**Solution:**
> f(x) = cos(x) is continuous and differentiable everywhere.
>
> f(0) = cos(0) = 1
>
> f(2π) = cos(2π) = 1
>
> Thus, f(0) = f(2π)
>
> Rolle's theorem is applicable. (c = π where f'(c) = 0)
**Example 8:** Verify Rolle's theorem for f(x) = x³ - x, a = -1 and b = 1.
**Solution:**
> f(x) = x³ - x is a polynomial, so it's continuous on [-1, 1] and differentiable on (-1, 1).
>
> f(-1) = (-1)³ - (-1) = -1 + 1 = 0
>
> f(1) = (1)³ - (1) = 1 - 1 = 0
>
> Thus, f(-1) = f(1) = 0
>
> Rolle's theorem is applicable. (c = 0, ±1/√3 where f'(c) = 0)
**Example 9:** Verify Rolle's theorem for f(x) = 1/x, a = 1 and b = 2.
**Solution:**
> f(x) = 1/x is continuous and differentiable for x > 0, so it's continuous on [1, 2] and differentiable on (1, 2).
>
> f(1) = 1/1 = 1
>
> f(2) = 1/2 = 0.5
>
> Thus, f(1) ≠ f(2)
>
> Hence, Rolle's theorem is not applicable.
**Example 10:** Verify Rolle's theorem for f(x) = sin(x), a = 0 and b = π.
**Solution:**
> f(x) = sin(x) is continuous and differentiable everywhere.
>
> f(0) = sin(0) = 0
>
> f(π) = sin(π) = 0
>
> Thus, f(0) = f(π) = 0
>
> Rolle's theorem is applicable. (c = π/2 where f'(c) = 0)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/rolles-theorem/)

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
