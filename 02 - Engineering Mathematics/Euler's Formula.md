---
title: "Euler's Formula"
subject: "Engineering Mathematics"
topic: "Calculus"
source: "https://www.geeksforgeeks.org/maths/eulers-formula/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Calculus"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/calculus
---


> [!abstract] Euler's Formula
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Calculus`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/eulers-formula/)

---

# Euler's Formula

Euler’s formula establishes a fundamental relationship between [exponential functions](https://www.geeksforgeeks.org/maths/exponential-functions/) and [trigonometric functions](https://www.geeksforgeeks.org/maths/trigonometric-functions/). It shows how complex exponentials can be expressed using sine and cosine.
>
$$
e^{i\theta} = \cos\theta + i\sin\theta
$$
>
> **Where:**
>
> - θ is a real number (in radians)
> - e is the base of the natural logarithm
> - sinθ and cosθ are trigonometric functions
> - i is the [imaginary](https://www.geeksforgeeks.org/maths/imaginary-numbers/) unit (i² = −1)
![](assets/eulerderiv1-300x256-b0d59c2207.png)
The complex exponential
$$
e^{i\theta}
$$
 represents a point on the unit circle in the complex plane, where θ is a real number measured in radians.
**Derivation**
> Consider the power series expansion of the exponential function:
>
>
$$
e^x = 1 + x + x²/2! + x³/3! + x⁴/4! + ...
$$
>
> Substituting
>
>
$$
x = iθ:
$$
>
>
$$
e^{iθ} = 1 + iθ + (iθ)²/2! + (iθ)³/3! + (iθ)⁴/4! + ...
$$
>
> Using i² = −1 and simplifying:
>
>
$$
e^{iθ} = 1 + iθ − θ²/2! − iθ³/3! + θ⁴/4! + iθ⁵/5! − ...
$$
>
> Grouping real and imaginary parts:
>
>
$$
e^{iθ} = (1 − θ²/2! + θ⁴/4! − ...)
$$
>
> -
$$
i(θ − θ³/3! + θ⁵/5! − ...)
$$
>
> Using the series expansions of cosine and sine:
>
>
$$
cosθ = 1 − θ²/2! + θ⁴/4! − ...
$$
>
>
>
>
$$
sinθ = θ − θ³/3! + θ⁵/5! − ...
$$
>
> Since the real and imaginary parts match the Maclaurin series of cosθ and sinθ respectively, therefore
>
>
$$
e^{iθ} = cosθ + i sinθ
$$
### **Formula for Polyhedral**
Euler’s polyhedral formula states that for any [polyhedron](https://www.geeksforgeeks.org/maths/polyhedrons/) that does not self-intersect, the numbers of faces, vertices, and edges are related in a specific way. According to the formula, the sum of the number of faces and vertices is two greater than the number of edges.
> F + V - E = 2
>
> where,
>
> - F is the number of faces,
> - V the number of vertices,
> - E the number of edges.
**Derivation**
> Euler's formula can be proven for five platonic solids: cube, tetrahedron, octahedron, dodecahedron and the icosahedron.
>
> | **Solids** | **Number of faces (F)** | **Number of vertices (V)** | **Number of edges (E)** | **F + V - E** |
> | **Cube** | 4 | 4 | 6 | 2 |
> | **Tetrahedron** | 4 | 6 | 4 | 6 |
> | **Octahedron** | 8 | 6 | 12 | 2 |
> | **Dodecahedron** | 12 | 20 | 30 | 2 |
> | **Icosahedron** | 20 | 12 | 30 | 2 |
### Applications
Euler’s formula is one of the most important equations in mathematics and has many useful applications. Some of the major applications are:
- Deriving the famous Euler’s identity
- Writing [complex numbers](https://www.geeksforgeeks.org/maths/complex-numbers/) in exponential form
- Providing alternative definitions of trigonometric and hyperbolic functions
- Extending exponential and [logarithmic functions](https://www.geeksforgeeks.org/maths/logarithmic-function/) to complex numbers
- Giving alternative proofs of [De Moivre’s theorem](https://www.geeksforgeeks.org/maths/de-moivres-theorem/) and trigonometric addition formulas.
### **Euler’s Identity**
Euler’s identity is considered one of the most beautiful equations in mathematics because it connects five fundamental constants in a single simple expression:
>
$$
e^{i\pi} + 1 = 0
$$
>
> It combines:
>
> - 0 — additive identity
> - 1 — unity
> - π — circle constant
> - e — base of the natural logarithm
> - i — imaginary unit (i² = −1)
>
> Euler’s identity is obtained as a special case of Euler’s formula by substituting θ = π into
>
>
$$
e^{i\theta} = \cos\theta + i\sin\theta
$$
>
> Since
>
>
$$
cosπ = −1
$$
>
>  and
>
>
$$
sinπ = 0
$$
>
> , we get
>
>
$$
e^{i\pi}= -1
$$
>
> which leads to
>
>
>
$$
e^{i\pi} + 1 = 0
$$
### **Sample Problems**
**Problem 1.** Express eiπ/2 in the general form using Euler's formula.
**Solution:**
> We have,
>
> x = π/2
>
> Using the formula we get,
> eix = cos x + i sin x
> = cos π/2 + i sin π/2
> = 0 + i (1)
> = 0 + i 
**Problem 2.** Express e6i in the general form using Euler's formula.
**Solution:**
> We have,
>
> x = 6
>
> Using the formula we get,
>
> eix = cos x + i sin x
> = cos 6 + i sin 6
> = 0.96 + i (-0.279)
> = 0.96 - 0.279i
**Problem 3.** Express e10i in the general form using Euler's formula.
**Solution:**
> We have,
>
> x = 10
>
> Using the formula we get,
>
> eix = cos x + i sin x
> = cos 10 + i sin 10
> = -0.83 + i (-0.544)
> = -0.83 - 0.544i
**Problem 4.** Express eiπ/3 in the general form using Euler's formula.
**Solution:**
> We have,
>
> x = π/3
>
> Using the formula we get,
>
> eix = cos x + i sin x
> = cos π/3 + i sin π/3
> = 0.5 + i (0.86)
> = 0.5 + 0.86i
**Problem 5.** Verify Euler's formula for a triangular prism.
**Solution:**
> We have a triangular prism. It is known that,
>
> Number of faces (F) = 5
>
> Number of vertices (V) = 6 
>
> Number of edges (E) = 9
>
> Using the formula we have,
>
> F + V − E = 5 + 6 − 9
> = 11 - 9
> = 2
>
> As the value of F + V − E is 2, the Euler's formula is verified.
**Problem 6.** Verify Euler's formula for a square pyramid.
**Solution:**
> We have a square pyramid. It is known that,
>
> Number of faces (F) = 5
>
> Number of vertices (V) = 5
>
> Number of edges (E) = 8
>
> Using the formula we have,
>
> F + V − E = 5 + 5 − 8
> = 10 - 8
> = 2
>
> As the value of F + V − E is 2, the Euler's formula is verified.
**Problem 7.** Find the number of vertices of a polyhedral if the number of faces is 20 and the number of edges is 30.
**Solution:**
> We have,
>
> F = 20
>
> E = 30
>
> Using the formula we get,
>
> F + V − E = 2
> => V = E + 2 - F
> = 30 + 2 - 20
> = 32 - 20
> = 12
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/eulers-formula/)

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
> - [[Finding the Various nth term of any polynomial sequence]]
> - [[Indefinite Integrals]]
> - [[Indeterminate Forms]]
> - [[Lagrange’s Mean Value Theorem]]
