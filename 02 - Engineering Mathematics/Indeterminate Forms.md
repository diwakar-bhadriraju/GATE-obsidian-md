---
title: "Indeterminate Forms"
subject: "Engineering Mathematics"
topic: "Calculus"
source: "https://www.geeksforgeeks.org/engineering-mathematics/indeterminate-forms/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Calculus"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/calculus
---


> [!abstract] Indeterminate Forms
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Calculus`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/indeterminate-forms/)

---

# Indeterminate Forms

An indeterminate form is a mathematical expression obtained while evaluating a limit that does not immediately reveal the limit's value. The expression alone is insufficient to determine whether the limit exists or what its value might be.
![intermediate_forms](assets/intermediate_forms-4222dd917c.webp)
> **For example**:
>
>
$$
\lim\limits_{x\to 0}\frac{x}{x}
$$
>
> Direct substitution gives:
>
>
$$
\frac{0}{0}
$$
>
> However, the actual limit is: 1
>
> This shows that the form (0/0) does not determine the limit by itself.
### Types of Indeterminate Forms
**1. Zero by Zero Form (0/0)**: This form occurs when both the numerator and denominator approach zero.
> #### Example:
$$
\lim_{x\to 2}\frac{x^2-4}{x-2}
$$
>
> Substituting (x=2):
>
>
$$
\frac{0}{0}
$$
**2. Infinity by Infinity Form (∞/∞):** This form occurs when both the numerator and denominator grow without bound.
> #### Example:
$$
\lim\limits_{x\to\infty}\frac{3x^2+1}{x^2+5}
$$
>
> Direct substitution gives:
>
>
$$
\frac{\infty}{\infty}
$$
**3. Zero Times Infinity Form (0 × ∞):** This form arises when one factor approaches zero while another approaches infinity.
> #### Example:
$$
\lim\limits_{x\to0^+}x\ln x
$$
>
> Here,
>
>
$$
x\to0 \text \ {and}\ \ln x\to-\infty
$$
>
>  resulting in the indeterminate form:
>
>
$$
0\times\infty
$$
**4. Infinity Minus Infinity Form (∞ − ∞):** This form occurs when two expressions approaching infinity are subtracted.
> #### Example:
$$
\lim\limits_{x\to\infty}\left(\sqrt{x^2+x}-x\right)
$$
>
> Direct substitution gives:
>
>
$$
\infty-\infty
$$
**5. Zero Raised to Zero Form (0⁰):** This exponential form occurs when the base approaches zero and the exponent also approaches zero.
> #### Example:
$$
\lim\limits_{x\to0^+}x^x
$$
>
> Since both the base and exponent approach zero, the form is:
>
>
$$
0^0
$$
**6. Infinity Raised to Zero Form (∞⁰):** This form occurs when the base approaches infinity while the exponent approaches zero.
> #### Example:
$$
\lim\limits_{x\to\infty}x^{\frac{1}x}
$$
>
> Direct substitution gives:
>
>
$$
\infty^0
$$
**7. One Raised to Infinity Form (1∞):** This form occurs when the base approaches 1 and the exponent approaches infinity.
> #### Example:
$$
\lim\limits_{x\to\infty}\left(1+\frac1x\right)^x
$$
>
> Direct substitution produces:
>
>
$$
1^\infty
$$
### Methods to Evaluate Indeterminate Forms
**1. Algebraic Simplification**: Many indeterminate forms can be resolved by simplifying the expression before evaluating the limit.
Common techniques include:
- Factoring
- Rationalization
- Expanding expressions
- Combining fractions
> **Example:**
>
>
$$
\lim\limits_{x\to2}\frac{x^2-4}{x-2}
$$
>
> Factor the numerator:
>
>
$$
\frac{(x-2)(x+2)}{x-2}
$$
>
> Cancel the common factor:
>
>
$$
\lim\limits_{x\to2}(x+2) =4
$$
**2. L'Hôpital's Rule:** L'Hôpital's Rule is used when a limit results in the forms intermediate forms and caanot be solved by algebric simplification.
> **Example:**
>
>
$$
\lim\limits_{x\to0}\frac{\sin x}{x}
$$
>
> Substitution gives:
>
>
$$
\frac{0}{0}
$$
>
> Applying L'Hôpital's Rule:
>
>
$$
\lim\limits_{x\to0}\frac{\cos x}{1} = 1
$$
**3. Logarithmic Transformation:**  This method is particularly useful for evaluating:
$$
(0^0), (1^\infty),(\infty^0)
$$
> Let:
>
>
$$
y=f(x)^{g(x)}
$$
>
> Take the natural logarithm:
>
>
$$
\ln y=g(x)\ln(f(x))
$$
>
> Evaluate the limit of (ln y ), then exponentiate the result.
## Solved Example
**Example 1:** Evaluate:
$$
\lim\limits_{x\to3}\frac{x^2-9}{x-3}
$$
> Factor:
>
>
$$
\frac{(x-3)(x+3)}{x-3} =x+3
$$
>
> Substitute (x=3) gives 3 + 3 = 6
**Example 2:** Evaluate: \lim\_{x\to\infty}\frac{5x^2+1}{2x^2+3}
> Divide by (x2):
>
>
$$
\lim\limits_{x\to\infty} \frac{5+\frac1{x^2}} {2+\frac3{x^2}} =\frac52
$$
**Example 3:** Evaluate:
$$
\lim\limits_{x\to0^+}x\ln x
$$
> Rewrite as:
>
>
$$
\frac{\ln x}{\frac{1}x}
$$
>
> Apply L'Hôpital's Rule:
>
>
$$
\lim\limits_{x\to0^+}\frac{1/x}{-1/x^2}\\[3pts]\lim\limits_{x\to0^+}(-x) =0
$$
**Example 4:** Evaluate:
$$
\lim\limits_{x\to\infty} \left(\sqrt{x^2+x}-x\right)
$$
> Multiply by the conjugate:
>
>
$$
\frac{x^2+x-x^2}{\sqrt{x^2+x}+x}=\frac{x}{\sqrt{x^2+x}+x}
$$
>
> Divide by (x):
>
>
$$
\frac{1} {\sqrt{1+\frac1x}+1} =\frac12
$$
**Example 5:** Evaluate:
$$
\lim\limits_{x\to\infty}\left(1+\frac1x\right)^x
$$
> Let,
>
>
$$
y=\left(1+\frac1x\right)^x
$$
>
> Taking logarithms:
>
>
$$
\ln y= x\ln\left(1+\frac1x\right)
$$
>
> Evaluating the limit gives: ln y=1
>
> Therefore, y=e
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/indeterminate-forms/)

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
> - [[Lagrange’s Mean Value Theorem]]
