---
title: "Continuity of Functions"
subject: "Engineering Mathematics"
topic: "Calculus"
source: "https://www.geeksforgeeks.org/maths/continuity-of-functions/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Calculus"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/calculus
---


> [!abstract] Continuity of Functions
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Calculus`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/continuity-of-functions/)

---

# Continuity of Functions

In mathematics,continuity describes how smoothly a function behaves without sudden jumps, breaks, or holes. It is an important unit of [calculus](https://www.geeksforgeeks.org/maths/math-calculus/) as it forms the base, and it helps us further to prove whether a function is differentiable or not.
In simple terms, a function is continuous if you can draw its graph without lifting your pen from the paper.
![Continuity-of-Functions-1-min](assets/Continuity-of-Functions-1-min-52a725ae61.webp)
## Continuity at a Point
Formally, a function f(x) is continuous at a point x = a if three conditions hold:
- f(a) is defined (the function has a value at a).
- limₓ→ₐ f(x) exists (limₓ→ₐ⁻ f(x) = limₓ→ₐ⁺ f(x))
- limₓ→ₐ f(x) = f(a) (The limit value and the actual function value are equal)
The above three conditions are respectively called Function Condition, Limit Condition, and Equality (Point) Condition respectively.
![function-2](assets/function-2-f1cf735058.webp)
The above figure shows the left-hand limit, right-hand limit, and the actual function value at x = a. When all three are equal, the graph has no break at that point, and the function is continuous.
## Continuity Over an Interval
A function is said to be continuous on an interval if it is continuous at every point within that interval. In other words, the graph of the function shows no breaks, jumps, or discontinuities throughout the interval.
If a function is continuous at every point in its domain, it is said to be continuous everywhere.
> **Note:** Discontinuity occurs when any of the above conditions fail, leading to breaks, holes, or jumps in the curve.
## Continuity of Function Examples
Some common examples of continuous functions include polynomial functions and trigonometric functions like sin x and cos x, which are continuous for all real numbers.
Let us check the continuity of the function f(x) = sin (x) at a = 0
> Let us find the value of the function at a=0
>
> f(0) = sin(0) = 0
>
> Now calculating the Left-Hand limits and the Right Hand Limits respectively we get
>
> LHL = limx → 0- f(x)
> ⇒ LHL = limh → 0 f(0 - h)
> ⇒ LHL = limh → 0 sin(-h)
> ⇒ LHL = - limh → 0 sin(h)
> ⇒ LHL = 0
>
> RHL = limx → 0+ f(x)
> ⇒ RHL = limh → 0 f(0 + h)
> ⇒ RHL = limh → 0 sin(h)
> ⇒ RHL = limh → 0 sin(h)
> ⇒ RHL = 0
>
> The condition Iim(x→0-)f(x)=f(0)=Iim(x→0+)f(x) is satisfied. Hence the function is continuous at x = 0
**Note:** All Polynomial, logarithmic, and exponential functions such as ex are continuous in all the domains.
## Discontinuity
A function that is not continuous is called a discontinuous function. In simple words, the graph of such a function has a break, jump, or hole at some point.
A function becomes discontinuous if any of the continuity conditions fails.
The different types of discontinuities are shown in the figure below.
![limits](assets/limits-11ac73498f.webp)
### Jump Discontinuity
Jump discontinuity occurs when the left-hand limit and right-hand limit at a point both exist, but their values are different.In this case, lim x → a⁻ f(x) ≠ lim x → a⁺ f(x)
Since the two limits are not equal, the overall limit does not exist, and the function is discontinuous at that point.
**Example:** Let f(x) = x + 1, if x < 3 and f(x) = x + 5, if x ≥ 3. Check whether the function is continuous at x = 3.
**Solution:**
> Given,
>  f(x) = x + 1, if x < 3
>  f(x) = x + 5, if x ≥ 3
>
> Left-hand limit (LHL):
>  lim x → 3⁻ f(x) = 3 + 1 = 4
>
> Right-hand limit (RHL):
>  lim x → 3⁺ f(x) = 3 + 5 = 8
>
> Since LHL ≠ RHL, the limit does not exist.
>
> Therefore, the function is not continuous at x = 3 and has a jump discontinuity at that point.
### Removable Discontinuity
Removable discontinuity occurs at a point where the limit of the function exists, but the function value is either not defined or not equal to the limit (lim x → a f(x) exists, but lim x → a f(x) ≠ f(a)).
This type of discontinuity can be removed by redefining the function at that point
**Example:**Check whether the function is continuous at x = 1.
$$
\bold{f(x) = \frac{x^2 - 1}{x - 1}}
$$
**Solution:**
> Given,
>  f(x) = (x² − 1) / (x − 1), for x ≠ 1
>
> First, factorize the numerator:
>
> x² − 1 = (x − 1)(x + 1)
>
> So, f(x) = (x − 1)(x + 1) / (x − 1)
>
> For x ≠ 1, cancel (x − 1):
>
> f(x) = x + 1
>
> Now find the limit at x = 1:
>
> LHL = lim x → 1⁻ (x + 1) = 2
>  RHL = lim x → 1⁺ (x + 1) = 2
>
> Since LHL = RHL,
>  lim x → 1 f(x) = 2
>
> But f(1) is not defined in the original function.
>
> Therefore, the function is not continuous at x = 1.
>  It has a removable discontinuity at x = 1.
>
> The discontinuity can be removed by defining f(1) = 2.
### Infinite Discontinuity
Infinite discontinuity occurs at a point x = a when the value of the function increases or decreases without bound as x approaches a.
In this case, one or both of the limits, lim x → a⁻ f(x) or lim x → a⁺ f(x), become +∞ or −∞.
**Example:** Check the continuity of the following function at x = 0,
$$
\bold{f(x)=\frac{1}{x}}
$$
**Solution:**
> LHL = limx → 0- f(x)
> ⇒ LHL = limx → 0- (1 / x)
> ⇒ LHL = limh → 0 (1 / (0 - h))
> ⇒ LHL = -∞
>
> and, 
>
> RHL = limx → 0+ f(x)
> ⇒ RHL = limx → 0+ (1 / x)
> ⇒ RHL = limh → 0 (1 / (0 + h))
> ⇒ RHL = +∞
>
> Thus, at x = 0 function has Infinite Discontinuity.
## Solved Examples on Continuity
**Example 1:**For function f(x) defined as 
$$
\bold{f(x) = \begin{cases} 4x, & \text{if } x < 2 \\ ~~~~8, & \text{if } x = 2 \\ 3x+2, & \text{if } x > 2\end{cases}}
$$
Check the continuity at x =2.
**Solution:**
> We will calculate the limits at x = 2
>
> LHL = Iim(x→2-) f(x) = Iim(h→0) f(2-h)
>
> ⇒ LHL = Iim(h→0)4×(2-h)
>
> ⇒ LHL = 4×(2-0)
>
> ⇒ LHL = 8
>
> RHL = Iim(x→0+) f(x) = Iim(h → 0) f(0+h)
>
> ⇒ RHL = Iim(h → 0)3×(2+h)+2
>
> ⇒ RHL = 3×(2+0)+2
>
> ⇒ RHL = 8
**Example 2:** Find the value of 'm' at which the function is continuous at x = 9
$$
\bold{f(x) = \begin{cases}mx+5 & \text{if} ~x ≠ 9\\ 8x & \text{if} ~x = 9\end{cases}}
$$
**Solution:**
> limx → 9- f(x) = lim (h → 0) f(9 - h)
> LHL = limh → 0 [m × (9 - h) + 5]
> LHL = 9m + 5
>
> RHL = limx → 9+ f(x)
> ⇒ RHL = limh → 0 f(9 + h)
> ⇒ RHL = limh → 0 [8 × (9 + h)]
> ⇒ RHL = 72
>
> For a function to be continuous Left Hand Limit is equal to Right Hand Limit
>
> Thus, 9m + 5 =72
>
> ⇒ m = 7.4444.....
>
> For the function to be continuous the value of m should be 7.444.....
**Example 3:** Test the continuity at x = 1, for the following function.
$$
\bold{f(x) = \begin{cases}\frac{x^2-3x+2}{x-1} & \text{if} ~x ≠ 1\\ 9x & \text{if} ~x = 1\end{cases}}
$$
**Solution:**
> To test the continuity of the function f(x) at x = 1, the following conditions must be checked:
>
> 1. f(1) is defined.
> 2. lim⁡x→1 f(x) exists.
> 3. lim⁡x→1 f(x) = f(1).
>
> **Step 1.** Evaluate f(1):
>
> Given that f(x) = 9x  when x = 1:
> f(1) = 9⋅1 = 9
> Thus, f(1) is defined and equals 9.
>
> **Step 2.** Evaluate lim⁡x→1 f(x)
>
> For x ≠ 1, 
>
>
$$
f(x) = \frac{x^2 - 3x + 2}{x - 1}
$$
>
>
> x = 1 gives undefined value (i.e., 0/0)
>
> **Factorize and simplify the function.**
> **x**2 − 3**x** + 2 = (**x** − 1)(**x** − 2)
>
> Thus, for x ≠ 1,
>
>
$$
f(x)= \frac{(x−1)(x−2)}{x -1 }= x -2
$$
>
> Therefore, lim⁡x→1 f(x) = lim⁡x→1 (x − 2) = 1 − 2 = −1
> The limit exists and equals −1.
>
> **Step 3.** Compare lim⁡x→1 f(x) and f(1)
>
> - lim **x**→1 ​**f**(**x**) = −1
> - f(1) = 9
>   Since −1 ≠ 9, the limit does not equal the function value at x = 1.
>
> The function f(x) is discontinuous at x = 1 because lim⁡x→1 f(x) ≠ f(1).
**Example 4:** 
$$
\bold{f(x) = \begin{cases}\frac{sin(x-2)}{x^2-4} & \text{if} ~x ≠ 2\\ 0.25 & \text{if} ~x = 2\end{cases}}
$$
Test the continuity at x = 2 of the above-mentioned function.
**Solution:**
> If we put x = 2 in the function sin(x - 2) / (x2 - 4) then the function is undefined. Therefore we need to factorize and simplify the function.
>
>
$$
\lim_{x\to 2}f(x) = \lim_{x\to 2} \frac{sin(x - 2)}{x^2 - 4} \\ \Rightarrow \lim_{x\to 2} f(x) = \lim_{x\to 2} \frac{sin(x - 2) }{(x - 2)\times (x + 2)} \\ \Rightarrow \lim_{x\to 2} f(x) = \lim(x\to 2) \frac{1}{x + 2}\times \lim(x\to 2) \frac{sin(x - 2)}{x - 2}
$$
>
> ⇒ lim**x**→2 ​**f**(**x**) = 1/4 = 0.25
> ⇒ lim**x**→2 ​**f**(**x**) = **f**(2) = 0.25
>
> Thus, the function is continuous at x = 2.
**Example 5:** Find the relation between m and n if the function is continuous at point x = -5
$$
\bold{f(x) = \begin{cases}mx^2 & \text{if} ~x < -5\\ nx+5 & \text{if} ~x \geqslant -5\end{cases}}
$$
**Solution:**
> We will compute the Left Hand Limit and Right Hand Limit separately
>
> LHL = limx→−5 − mx2
> ⇒ LHL = limh→0 m×(−5−h)2
> ⇒ LHL = 25m
>
> RHL = lim x→−5 + nx+5 
> ⇒ RHL = limh→0n×(-5+h)+5 
> ⇒ RHL = -5n + 5
>
> For a function to be continuous LHL = RHL
>
> 25m = -5n + 5 
> ⇒ 25m + 5n = 5
> ⇒ 5m + n = 1
### **Related Articles**
> - [Continuity and Discontinuity](https://www.geeksforgeeks.org/maths/continuity-and-discontinuity-in-calculus-class-12-cbse/)
> - [Calculus in Maths](https://www.geeksforgeeks.org/maths/math-calculus/)
> - [Introduction to Limit](https://www.geeksforgeeks.org/maths/limits/)
> - [Properties of Limits](https://www.geeksforgeeks.org/maths/properties-of-limits/)
> - [Real Life Applications of Discontinuity](https://www.geeksforgeeks.org/maths/real-life-applications-of-discontinuity/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/continuity-of-functions/)

## GATE CS

- Subject: Engineering Mathematics
- Topic: Calculus

> [!note] Related notes
>
> - [[Absolute Minima and Maxima]]
> - [[Application of Derivative]]
> - [[Cauchy’s mean value theorem]]
> - [[Chain Rule Derivative]]
> - [[Differentiability]]
> - [[Euler's Formula]]
> - [[Finding the Various nth term of any polynomial sequence]]
> - [[Indefinite Integrals]]
> - [[Indeterminate Forms]]
> - [[Lagrange’s Mean Value Theorem]]
