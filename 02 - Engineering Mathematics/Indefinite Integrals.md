---
title: "Indefinite Integrals"
subject: "Engineering Mathematics"
topic: "Calculus"
source: "https://www.geeksforgeeks.org/maths/indefinite-integrals/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Calculus"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/calculus
---


> [!abstract] Indefinite Integrals
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Calculus`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/indefinite-integrals/)

---

# Indefinite Integrals

Integration is the inverse process of [differentiation](https://www.geeksforgeeks.org/maths/differentiation/). Instead of finding the derivative of a function, we start with a derivative and work backwards to find the original function. This is also known as anti-differentiation.
Note that a constant added to any function doesn't affect its derivative, which is why the result of integration always includes a constant C, known as the constant of integration.
If f(x) is a continuous function on an interval I, an indefinite integral of f is a function F(x) such that:
> **F ′(x) = f(x) for all x ∈ I**
This relationship is expressed using the integral symbol without upper and lower limits:
> **∫f(x) dx = F(x) + C**
>
> Where ∫ is the symbol for integral.
The table below represents the symbols and meanings related to integrals.
| Symbol/Term | Meaning |
| --- | --- |
|
$$
\int f(x)dx
$$
 | Integral of f with respect to x |
| f(x) in 
$$
\int f(x)dx
$$
 | Integrand |
| x in 
$$
\int f(x)dx
$$
 | Variable of integration |
| Integral of f(x) | A function such that F'(x) = f(x) |
### Formulas for Indefinite Integrals
There are certain formulas and rules which, when kept in mind, help us simplify the calculating and do it fast. Some of these formulas are
- ∫ 1 dx = x + C
- ∫ P dx = Px + C
- ∫ xⁿ dx = xⁿ⁺¹ / (n + 1) + C
- ∫ ex dx = ex + C
- ∫ ax dx = ax / ln a + C
- ∫1/x dx = ln |x| + C
- ∫ cos x dx = sin x + C
- ∫ sin x dx = -cos x + C
- ∫ sec x dx = tan x + C
## Finding Indefinite Integral
Various different methods are used to calculate the indefinite integrals,
- Normal indefinite integrals are solved using direct [**integration formulas**](https://www.geeksforgeeks.org/maths/integration-formulas/).
- Integrals with rational functions are solved using the [**partial fractions method**](https://www.geeksforgeeks.org/maths/integration-by-partial-fractions/).
- Indefinite integrals can be solved using the [**substitution method**](https://www.geeksforgeeks.org/maths/integration-by-substitution/).
- [**Integration by parts**](https://www.geeksforgeeks.org/maths/integration-by-parts/) is used to solve the integral of the function where two functions are given as a product.
**Example:** Find the indefinite integral ∫ x3 cos x4 dx.
**Solution:**
> Using the substitution method. 
>
> Let x4 = t
> ⇒ 4x3 dx = dt
>
> Now, ∫ x3 cos x4 dx
> = 1/4∫cos t dt
> = 1/4 (sin t) + C
> = 1/4 sin (x4 ) + C
## Properties of Indefinite Integrals
Indefinite integrals have various properties some of the various properties of Indefinite Integral are,
**Property of Sum**
> **∫ [f(x) + g(x)]dx = ∫ f(x)dx + ∫ g(x)dx**
**Property of Difference**
> **∫ [f(x) × g(x)]dx = ∫ f(x)dx × ∫ g(x)dx**
**Property of Constant Multiple**
> **∫ k f(x)dx = k∫ f(x)dx**
Some of the other properties of the indefinite integral are,
- ∫ f(x) dx = ∫ g(x) dx if ∫ [f(x) - g(x)] dx = 0
- ∫ [k₁f₁(x) + k₂f₂(x) + ...+knfn(x)]dx = k₁∫ f₁(x)dx + k₂∫ f₂(x)dx + ... + kₙ∫ fₙ(x)dx
## Indefinite Integral vs Definite Integral
| Aspect | Indefinite Integrals | Definite Integrals |
| --- | --- | --- |
| Definition | Integration of a function without any bounds. | Integration of a function over a specific interval (bounded by lower and upper limits). |
| Notation | ∫ f(x) dx = F(x) + C | ∫abf(x) dx = F(b) - F(a) |
| Result | Gives a function + constant (F(x) + C) | Gives a numerical value (F(b) − F(a)) |
| Geometric Meaning | Family of curves (general solution). | Area under the curve between x = a and x = b. |
| Use Case | Used to find the general form of the antiderivative of a function. | Used to find the exact value of the accumulated quantity between specific limits. |
## Solved Examples
**Example 1:** Find the integral for the given function f(x), f(x) = sin(x) + 1.
**Solution:**
> Given f(x) = sin(x) + 1
>
> sin(x) is a standard function, and it's anti-derivative is,
>
> ∫ f(x)dx
> = ∫ (sin(x) + 1)dx
> = 
>
>
$$
\int sin(x)dx  + \int 1dx
$$
>
>
> = 
>
>
$$
-cos(x) + x + C
$$
**Example 2:** Find the integral for the given function f(x), f(x) = 2eˣ. .
**Solution:**
> Given f(x) = 2ex 
>
> ex is a standard function, and it's anti-derivative is,
>
> = 
>
>
$$
\int f(x)dx
$$
>
>
> = 
>
>
$$
\int 2e^xdx
$$
>
> Using the property 1 mentioned above, 
>
> = 
>
>
$$
2\int e^xdx
$$
>
>
> = 2ex + C
**Example 3:** Find the integral for the given function f(x), f(x) = 5x - 2.
**Solution:**
> Given f(x) = 5x-2
>
> Using reverse power rule
>
> = 
>
>
$$
\int f(x)dx
$$
>
>
> = 
>
>
$$
\int 5x^{-2}dx
$$
>
> Using property 1 mentioned above, 
>
> = 
>
>
$$
5\int x^{-2}dx
$$
>
>
> = 
>
>
$$
\frac{-5}{x} + C
$$
**Example 4:** Find the integral for the given function f(x), f(x) = sin(x) + 5cos(x).
**Solution:**
> Given f(x) = sin(x) + 5cos(x)
>
> sin(x) and cos(x) are standard functions, and its integral is,
>
> = 
>
>
$$
\int f(x)dx
$$
>
>
> = ∫ (sin(x) + 5cos(x))dx
> = 
>
>
$$
\int sin(x)dx  + 5\int cos(x)dx
$$
>
>
> = 
>
>
$$
-cos(x) + 5sin(x) + C
$$
**Example 5:** Find the integral for the given function f(x), f(x) = 5x - 2 + x4 + x.
**Solution:**
> Given f(x) = 5x-2 + x4 + x
>
> Using reverse power rule
>
> = 
>
>
$$
\int f(x)dx
$$
>
>
> = 
>
>
$$
\int (5x{-2} + x^4  + x)dx
$$
>
>
> = 
>
>
$$
\int (5x{-2} + x^4  + x)dx
$$
>
>
> = 
>
>
$$
5\int x^{-2}dx + \int x^4dx   + \int xdx
$$
>
>
> = 
>
>
$$
\frac{-5}{x} + \frac{x^5}{5}   + \frac{x^2}{2}
$$
### **Related Articles:**
> - [Calculus](https://www.geeksforgeeks.org/maths/math-calculus/)
> - [Integral Calculus](https://www.geeksforgeeks.org/maths/integral-calculus/)
> - [Application of Integrals](https://www.geeksforgeeks.org/maths/application-of-integrals/)
> - [Integration Methods](https://www.geeksforgeeks.org/maths/methods-of-integration/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/indefinite-integrals/)

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
> - [[Indeterminate Forms]]
> - [[Lagrange’s Mean Value Theorem]]
