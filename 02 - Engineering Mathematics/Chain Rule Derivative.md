---
title: "Chain Rule: Theorem, Formula and Solved Examples"
subject: "Engineering Mathematics"
topic: "Calculus"
source: "https://www.geeksforgeeks.org/maths/chain-rule-formula/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Calculus"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/calculus
---


> [!abstract] Chain Rule: Theorem, Formula and Solved Examples
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Calculus`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/chain-rule-formula/)

---

# Chain Rule: Theorem, Formula and Solved Examples

The chain rule is a way to find the derivative of composite functions.
- It allows us to differentiate complex expressions by differentiating the outer function and then multiplying by the derivative of the inner function.
- It helps us to find the derivative of composite functions such as (3x2 + 1)4, (sin 4x), e3x, (ln x)2.
![2056958432](assets/2056958432-1b84ddac2b.webp)
Let y = f(g(x)) be a composite function, where g(x) is the inner function and f(x) is the outer function. If both f and g are differentiable, then the derivative of the composite function is given by:
**Formula 1:** Function Notation
>
$$
\frac{d}{dx}[f(g(x))] = f'(g(x))\cdot g'(x)
$$
>
> where:
>
> - f(g(x)) is the composite function
> - f′(g(x)) is the derivative of the outer function
> - g′(x) is the derivative of the inner function
**Formula 2:** Leibniz Notation
>
$$
\frac{dy}{dx} = \frac{dy}{du}\cdot\frac{du}{dx}
$$
>
> This form is useful when substitutions are involved.
In words, the derivative of a composite function is equal to the derivative of the outer function evaluated at the inner function multiplied by the derivative of the inner function.
## Proof
> The Chain Rule can be derived using the definition of a derivative.
>
> Let y = f(u) and u = g(x)
>
> Then, y=f(g(x))
>
> Using Leibniz notation,
>
>
$$
\frac{dy}{dx} = \frac{dy}{du}\cdot\frac{du}{dx}
$$
>
> From the definition of derivatives,
>
>
$$
\frac{dy}{dx} = \lim\limits_{\Delta x\to0} \frac{\Delta y}{\Delta x}
$$
>
> Multiplying and dividing by Δu,
>
>
$$
\frac{dy}{dx} = \lim\limits_{\Delta x\to0} \left( \frac{\Delta y}{\Delta u} \cdot \frac{\Delta u}{\Delta x} \right)
$$
>
> Since u = g(x) is differentiable, Δu→0 as Δx→0
>
> Therefore,
>
>
$$
\frac{dy}{dx} = \left( \lim\limits_{\Delta u\to0} \frac{\Delta y}{\Delta u} \right) \left( \lim\limits_{\Delta x\to0} \frac{\Delta u}{\Delta x} \right)
$$
>
> Hence,
>
>
$$
\frac{d}{dx}[f(g(x))] = f'(g(x))\cdot g'(x)
$$
>
> This proves the Chain Rule.
### Steps to use chain rule
The following steps can be used to differentiate a composite function.
> **Step 1:** Identify whether the given function is a composite function.
>
> **Step 2:** Separate the function into outer and inner functions.
>
> **Step 3:** Differentiate the outer function while keeping the inner function unchanged.
>
> **Step 4:** Differentiate the inner function.
>
> **Step 5:** Multiply the derivatives obtained in Steps 3 and 4.
### Double Chain Rule of Differentiation
When a function contains more than two nested functions, the Chain Rule is applied repeatedly. This repeated application of the Chain Rule is known as the Double Chain Rule or Multiple Chain Rule. Now for any three functions f, g, and h and a composite function y where y is a composite of f, g, and h such that, y = f[g{h(x)}], then its derivative is given as,
>
$$
\frac{dy}{dx}=\frac{dy}{du}\cdot \frac{du}{dv}\cdot \frac{dv}{dx}
$$
**Example:** Differentiate, y = (sin 2x)2
> y = (sin 2x)2
> y' = 2( sin 2x) . (cos 2x). (2)
> y' = 4 sin2x . cos 2x
### Chain Rule for Partial Derivatives
The concept of chain rule also works for partial derivatives. Partial derivatives are found when in the differentiation of any function one or more variable is kept constant with respect to the differentiating variable.
Suppose z = f(u) and u = g(x)
> Then,
>
>
$$
\frac{\partial z}{\partial x} = \frac{\partial z}{\partial u} \cdot \frac{\partial u}{\partial x}
$$
This formula helps determine how a dependent variable changes when one independent variable changes indirectly through another variable.
## Application
This chain rule is widely used in mathematics to find the differentiation of complex functions. Some of its uses are discussed below,
- For finding the rate of change of the pressure with respect to time.
- For finding the rate of change of the average molecular speed.
- To determine if the given function is increasing or decreasing.
- For finding the rate of change of distance between two moving objects,
**➢Practice:**[Solved Examples](https://www.geeksforgeeks.org/aptitude/chain-rule/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/chain-rule-formula/)

## GATE CS

- Subject: Engineering Mathematics
- Topic: Calculus

> [!note] Related notes
>
> - [[Absolute Minima and Maxima]]
> - [[Application of Derivative]]
> - [[Cauchy’s mean value theorem]]
> - [[Continuity]]
> - [[Differentiability]]
> - [[Euler's Formula]]
> - [[Finding the Various nth term of any polynomial sequence]]
> - [[Indefinite Integrals]]
> - [[Indeterminate Forms]]
> - [[Lagrange’s Mean Value Theorem]]
