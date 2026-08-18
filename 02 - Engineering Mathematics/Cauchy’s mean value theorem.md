---
title: "Cauchy's Mean Value Theorem"
subject: "Engineering Mathematics"
topic: "Calculus"
source: "https://www.geeksforgeeks.org/engineering-mathematics/cauchys-mean-value-theorem/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Calculus"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/calculus
---


> [!abstract] Cauchy's Mean Value Theorem
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Calculus`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/cauchys-mean-value-theorem/)

---

# Cauchy's Mean Value Theorem

**Cauchy's Mean Value Theorem** provides a relation between the change of two functions over a fixed interval with their derivative. It is a special case of the [Lagrange Mean Value Theorem.](https://www.geeksforgeeks.org/engineering-mathematics/lagranges-mean-value-theorem/) It is also called the Extended Mean Value Theorem or the Second Mean Value Theorem.
> According to the theorem, if a function passes through two points given as [a, f(a)] and [b, f(b)] then there exist a point through which tangent on the curve passes which is parallel to the secant passing through the two given points.
For the [function](https://www.geeksforgeeks.org/maths/what-is-a-function/) f(x) continuous over [a, b] and differentiable over (a, b), there exists a point c in the interval (a, b) such that
$$
f'(c) = \frac{[f(b) - f(a)]}{(b - a)}
$$
The image for the Mean Value Theorem is added below:
![Mean-Value-Theorem](assets/Mean-Value-Theorem-768-254f146159.png)
### Statement
Cauchy's Mean Value Theorem states that, for any two functions, f(x) and g(x) satisfying the following conditions,
- f(x), g(x) are continuous in the closed interval a ≤ x ≤ b, x ϵ [a, b]
- f(x), g(x) are differentiable in the open interval a < x < b, i.e. x ϵ (a, b)
-
$$
g'(x)  \ne0
$$
   for all x belongs to the open interval a < x < b, i.e. x ϵ (a, b)
Then there exists a point c in the open interval a < c < b such that,
>
$$
\frac{[f(b) - f(a)]}{ [g(b) - g(a)]}= \frac{f'(c)}{g'(c)}
$$
**Example:** Consider
$$
f(x) = x^2
$$
 and g(x)= x over the interval [1 , 3].
1. f (1) = 1, f (3) = 9, g (1) = 11, g (3) = 3.
2. Derivatives: f′ (x) = 2x, g′ (x) = 1.
Applying CMVT:
$$
\frac{f'(c)}{g'(c)} = \frac{f(3) - f(1)}{g(3) - g(1)} \Rightarrow \frac{2c}{1} = \frac{8}{2} \Rightarrow c = 2.
$$
So, c = 2 satisfies the theorem.
## Proof of Cauchy's Mean Value Theorem
Cauchy's mean value theorem is easily proved using the Rolle's Mean Value Theorem. Cauchy's mean value theorem states that, for any two function f(x) and g(x) continuous on [a, b] and differentiable on (a, b) there exist a point in the interval (a, b) such that,
>
$$
\frac{f'(c) }{g'(c)} = \frac{[f(b) - f(a)]}{ [g(b) - g(a)]}
$$
Now, let's take the auxiliary function F(x) such that,
F(x) = f(x) + P×g(x)...(i)
In the above equation, P is chosen such that F(x) always satisfies the Rolle's Theorem in [a, b], Now by definition of Rolle's theorem,
F(a) = F(b)
⇒ f(a) + P×g(a) = f(b) + P×g(b)
⇒ f(b) - f(a) = P{g(b) - g(a)}
⇒
$$
P = \frac{[f(b) - f(a)]}{[g(b) - g(a)]}
$$
In eq.(i)
$$
F'(x) = f'(x) – {\frac{[f(b) – f(a)]}{[g(b) – g(a)]}}×g'(x)
$$
As, F(x) satisfies Rolles Theorem, F(c) = 0 where, c ϵ (a, b)
⇒
$$
f'(c) - {\frac{[f(b) - f(a)]}{[g(b) - g(a)]}}×g'(c) = 0
$$
⇒
$$
\frac{f'(c) }{g'(c)} = \frac{[f(b) - f(a)] }{ [g(b) - g(a)]}
$$
Thus, Cauchy's Theorem is proved.
### Limitations of Cauchy's Mean Value Theorem
There are few limitations of the Cauchy's Mean Value Theorem that are,
- Cauchy's Mean Value Theorem is applicable only for continuous function.
- Cauchy's Mean Value Theorem is applicable only for differentiable function.
### Applications of Cauchy's Mean Value Theorem
Various applications of Cauchy's Mean Value theorem are,
- It is used to solve various problem in Real Analysis.
- It is used to predict the behaviours of various curves.
- It is used to derive Lagrange's and Rolle's Mean value theorems, etc.
### **Related Articles**
> - [Rolle’s Theorem and Lagrange’s Mean Value Theorem](https://www.geeksforgeeks.org/maths/rolles-theorem-and-lagranges-mean-value-theorem/)
> - [Continuity and Discontinuity](https://www.geeksforgeeks.org/maths/continuity-and-discontinuity-in-calculus-class-12-cbse/)
> - [Critical Points](https://www.geeksforgeeks.org/maths/critical-points/)
## Solved Examples on Cauchy's Mean Value Theorem
**Example 1:** Find 'c' of Cauchy’s Mean Value Theorem for the functions f(x) = 3x2 + 4x + 5 and g(x) = x2 - x + 25 in the interval [1, 2]
**Solution:**
> Given,
>
> - f(x) = 3x2 + 4x + 5
> - g(x) = x2 - x + 25
>
> f(x) and g(x) are polynomial functions and thus,
>
> - f(x), g(x) are continuous in the closed interval
>
>
$$
a \leqslant x \leqslant b, x \in [1, 2]
$$
> - f(x), g(x) are differentiable in the open interval a < x < b, i.e. x ϵ (1, 2)
>
> And g'(x) = 2x - 1, is not equal to 0 in the interval
>
>
$$
x \in [1, 2]
$$
>
>
> Thus, Cauchy's Mean value theorem is applicable on f(x) and g(x)
>
> - f(x) = 3x2 + 4x + 5
> - g(x) = x2 - x + 25
>
> Differentiating f(x) and g(x) with respect to x
>
> - f'(x) = 6x + 4
> - g'(x) = 2x - 1
>
> Now,
>
> f(a) = f(1) = 12,
> f(b) = f(2) = 25,
> g(a) = g(1) = 25,
> g(b) = g(2) = 27,
> f'(c) = 6c + 4, and g'(c) = 2c - 1
>
> Using Cauchy Mean Value Theorem,
>
>
$$
\frac{f'(c)}{ g'(c)} = \frac{[f(b) - f(a)]}{[g(b) - g(a)]}
$$
>
>
> ⇒
>
>
$$
\frac{(6c + 4)}{(2c - 1)} = \frac{(25 - 12)}{(27 -25)}
$$
>
>
> ⇒
>
>
$$
\frac{(6c + 4)}{(2c - 1)} = \frac{13}{2}
$$
>
>
> ⇒
>
>
$$
(6c + 4).2 = 13.(2c - 1)
$$
>
>
> ⇒
>
>
$$
12c + 8 = 26c - 13
$$
>
>
> ⇒
>
>
$$
26c - 12c = 13 + 8
$$
>
>
> ⇒
>
>
$$
14c = 21
$$
>
>
> ⇒
>
>
$$
c = \frac{21}{14} = \frac{3}{2} = 1.5 \in[1, 2]
$$
**Example 2:** Find 'c' of Cauchy’s Mean Value Theorem for the functions f(x) = 2.ln x and g(x) = x2 - 1 in the interval [2, 3]
**Solution:**
> Given,
>
> - f(x) = 2.ln x
> - g(x) = x2
>
> f(x) is a polynomial functions and g(x) is a polynomial function both are continuous and differentiable on the given interval
>
> - f(x), g(x) are continuous in the closed interval
>
>
$$
a \leqslant x \leqslant b, x \in[2, 3]
$$
> - f(x), g(x) are differentiable in the open interval a < x < b, i.e.
>
>
$$
x \in (2, 3)
$$
>
> And g'(x) = 2x, is not equal to zero(0) in the interval x ϵ [1, 2]
> Thus, Cauchy's Mean value theorem is applicable on f(x) and g(x)
>
> - f(x) = 2.ln x
> - g(x) = x2
>
> Differentiating f(x) and g(x) with respect to x
>
> - f'(x) = 2/x
> - g'(x) = 2x
>
> Now,f(a) = f(2) = 2. ln 2
> f(b) = f(3) = 2. ln 3
> g(a) = g(2) = 4
> g(b) = g(3) = 9
> f'(c) = 2/c
> g'(c) = 2c
>
> Using Cauchy Mean Value Theorem,
>
>
$$
\frac{f'(c) }{ g'(c)}= \frac{[f(b) - f(a)]} {[g(b) - g(a)]}
$$
>
>
> ⇒
>
>
$$
\frac{(\frac{2}{c})}{(2c)}= \frac{(2. ln 3 - 2. ln 2)}{(9 - 4)}
$$
>
>
> ⇒ 1/c2 = 2(ln 3 - ln 2)/5
> ⇒ 1/c2 = 2(ln 3/2)/5
> ⇒
>
>
$$
\frac{5}{2}[\frac{1}{ln(\frac{3}{2})}] = c^2
$$
>
>
> ⇒
>
>
$$
c = \sqrt{\frac{(5/2)}{ln(3/2)}}
$$
>
>
> ⇒
>
>
$$
c = 2.9 \in [2, 3]
$$
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/cauchys-mean-value-theorem/)

## GATE CS

- Subject: Engineering Mathematics
- Topic: Calculus

> [!note] Related notes
>
> - [[Absolute Minima and Maxima]]
> - [[Application of Derivative]]
> - [[Chain Rule Derivative]]
> - [[Continuity]]
> - [[Differentiability]]
> - [[Euler's Formula]]
> - [[Finding the Various nth term of any polynomial sequence]]
> - [[Indefinite Integrals]]
> - [[Indeterminate Forms]]
> - [[Lagrange’s Mean Value Theorem]]
