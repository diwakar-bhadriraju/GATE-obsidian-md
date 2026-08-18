---
title: "Limits in Calculus"
subject: "Engineering Mathematics"
topic: "Calculus"
source: "https://www.geeksforgeeks.org/maths/limits/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Calculus"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/calculus
---


> [!abstract] Limits in Calculus
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Calculus`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/limits/)

---

# Limits in Calculus

In mathematics, a limit is a fundamental concept that describes the behavior of a function or sequence as its input approaches a particular value.
> Limits are used in calculus to define [derivatives](https://www.geeksforgeeks.org/maths/derivatives/), [continuity](https://www.geeksforgeeks.org/maths/continuity-of-functions/), and [integrals](https://www.geeksforgeeks.org/maths/integrals/), and they represent the value that a function approaches as the input approaches a certain value.
![](assets/Screenshot20210422at41221PM-b26e812f5c.png)
- Let's say we have a function f(x) = x2. In the graph given above, notice that as x⇢0, f(x) also tends to become zero.
- This can be written in terms of a limit as
$$
\bold{\lim_{x \to 0} f(x) = 0}
$$
  .
- It is read as the limit of f(x) as x tends to zero.
> In general, as x ⇢ a, f(x) ⇢ l, then l is called the limit of the function f(x). It can also be written as, 
>
>
$$
\bold{\lim_{x \to a}f(x) = l}
$$
![limit_of_function](assets/limit_of_function-a6a4a4708a.webp)
Sometimes some functions are not continuous. That is, they appear to be approaching two different values when they are approached from two sides. For example, let's see this step function given in the figure below. 
![](assets/Screenshot20210422at42119PM-707ed79dca.png)
This function can be defined as, 
>
$$
f(x)= \begin{cases}  1,& \text{if } x > 0\\  0,& \text{if } x = 0\\  -1,& \text{if x < 0}\end{cases}
$$
Suppose we want to find the limit of this function as x approaches zero. This naturally leads to directions from which we can approach. Left-hand side and the right-hand side limits.
The right-hand side limit is the value of the function that it takes while approaching it from the right-hand side of the desired point. Similarly, the left-hand-side limit is the value of the function while approaching it from the left-hand side. 
For this particular function,
> Left-hand side limit, limx→0- f(x) = -1
>
> Right-hand side limit, limx→0+ f(x) = 1
### **Mathematical Expression for Limit**
To define the limit of a function, let us consider a real-valued function “f” and the real number “a”such that the variable of the function approaches the value "a"; then the limit is normally defined as
> limx⇢a f(x) = L
It is read as “the limit of f of x, as x approaches a, equals L."
For any function f(x) defined for all x ≠ a over an open interval containing a. Now suppose we have a real number L such that,
> limx⇢a f(x) = L
Then for every ε > 0, there exists a δ > 0, such that, 0 < |x - a| < δ.
> |f(x) - L| < ε
## **Types of Limits**
Limits in math are of several types, each describing different situations and behaviors of functions as the independent variable approaches a certain value or infinity. Here are the main types of limits:
### One-Sided Limits
There are two paths to approach any point in 2D space along a curve. That are from Left Hand Side of the Curve or Right Hand Side of the Curve. Approaching the curve from either side allows us to find two separate limits of the function. These two limits are called the following:
- **Left Hand Limit (LHL):** The limit as the variable approaches the value from the left side. It is represented as
$$
\lim_{x \to a^-} f(x) = L
$$
  .
- **Right-Hand Limit (RHL):** The limit as the variable approaches the value from the right side. It is represented as
$$
\lim_{x \to a^+} f(x) = L
$$
  .
### Two-Sided Limits
Two-sided limits, also known as bilateral limits, are a fundamental concept in calculus that describe the behavior of a function as the independent variable approaches a particular value from both the left and the right sides simultaneously.
Formally, let f(x) be a function defined on an open interval containing **x**=**c**, except possibly at **x**=**c** itself. The two-sided limit of f(x) as **x** approaches **c**, denoted as
> limx→c​ f(x)
exists if and only if both the left-hand limit (as **x** approaches **c** from the left) and the right-hand limit (as **x** approaches **c** from the right) exist and are equal.
### **Infinite Limits**
Infinite limits occur when the value of a function approaches positive or negative infinity as the independent variable approaches a particular point. Formally, if the value of f(x) becomes arbitrarily large (positive or negative) as **x** approaches a certain value **c**, the limit is said to be infinite.
- **Positive Infinite Limit**: If f(x) increases without bound as **x** approaches **c**, the limit is denoted as lim x→c​f(x) **= +∞**.
- **Negative Infinite Limit**: If f(x) decreases without bound as **x** approaches **c**, the limit is denoted as limₓ→cf(x) **= −∞**.
For instance, consider the function f(x) = 1/x2​. As **x** approaches 0 from either the positive or negative direction, f(x) becomes increasingly large (approaches infinity), so the limit of f(x) as **x** approaches 0 is +∞.
### **Limits at Infinity**
[Limit at infinity](https://www.geeksforgeeks.org/maths/limits-at-infinity/) describes the behavior of a function as the independent variable grows without bound (approaches positive or negative infinity).
- **Limit at Positive Infinity**: If f(x) approaches a finite limit as **x** goes to positive infinity, it is denoted as lim x→+∞ ​f(x) = L.
- **Limit at Negative Infinity**: If f(x) approaches a finite limit as **x** goes to negative infinity, it is denoted as limₓ→−∞ ​f(x) = L.
For example, consider the function f(x) = 1/x​. As **x** grows without bound (either positively or negatively), f(x) approaches 0. Thus, limₓ→+∞ ​1/x = 0 and limₓ→−∞ 1/​x ​= 0.
### Algebra of Limit
Algebra of the limit of the function are added below.
| Law of Addition | limx⇢a {f(x) + g(x)} = limx⇢a f(x) + limx⇢a g(x) |
| Law of Subtraction | limx⇢a {f(x) - g(x)} = limx⇢a f(x) - limx⇢a g(x) |
| Law of Multiplication | limₓ⇢a {f(x) . g(x)} = limₓ⇢a f(x). limₓ⇢a g(x) |
| Law of Division | limx⇢a {f(x) / g(x)} = limx⇢a f(x) / limx⇢a g(x) |
### Special Rules of Limit
Various rules that are used to simplify the limit of the function are,
-
$$
\lim_{x \to a}\frac{x^n-a^n}{x-a}=na^{\,n-1}
$$
-
$$
\lim_{x \to 0}\frac{\sin x}{x}=1
$$
-
$$
\lim_{x \to 0}\frac{\tan x}{x}=1
$$
-
$$
\lim_{x \to 0}\frac{1-\cos x}{x}=0
$$
-
$$
\lim_{x \to 0}\cos x=1
$$
-
$$
\lim_{x \to 0}e^x=1
$$
-
$$
\lim_{x \to 0}\frac{e^x-1}{x}=1
$$
-
$$
\lim_{x \to \infty}\left(1+\frac{1}{x}\right)^x=e
$$
**Note:**
> - The limits involving trigonometric and exponential functions (such as
>
>
$$
\frac{\sin x}{x}, \frac{\tan x}{x},\frac{1 - \cos x}{x}, and \  \frac{e^x - 1}{x}
$$
>
>    )are valid only as x→0 .
> - The formula
>
>
$$
\lim_{x \to a} \frac{x^n - a^n}{x - a} = n a^{n-1}
$$
>
>    holds for any real value of a.
> - The limit
>
>
$$
\lim_{x \to \infty} (1 + \frac{1}{x})^x = e
$$
>
>    defines the mathematical constant e.
## **Solved Examples**
**Example 1:** limₓ⇢6 x/3 
**Solution:**
> limx⇢6 x/3 = 6/3 = 2
**Example 2:** limₓ⇢2 (x2 - 4)/(x - 2)
**Solution:**
> As we know, (x2 - 4) = (x2 - 22) = ( x - 2 )( x - 2 ) 
>
> Now, limx⇢2 (x2 - 4)/(x - 2)
> = limx⇢2 (x- 2)(x + 2)/(x - 2)
> = limx⇢2 (x + 2)
> = 4
**Example 3:** limₓ⇢1/2(2x - 1)/(4x2 - 1)
**Solution:**
> As we know, 4x2 - 1 = (2x2) - (12) = (2x + 1) (2x - 1)
>
> Now, limx⇢1/2(2x - 1)/(4x2 - 1)
> = limx⇢1/2(2x- 1)/(2x - 1) (2x + 1)
> = limx⇢1/ 2 1/(2x + 1)
> = 1/{2 × (1/2) + 1} = 1/2
**Example 4:** Find the right-handed limit:
$$
\lim_{x \to 0^+} f(x) \quad \text{where} \quad f(x) = \begin{cases} 1 & \text{if } x > 0 \\0 & \text{if } x = 0 \\-1 & \text{if } x < 0\end{cases}
$$
**Solution:**
> Since we're asked to find the **right-hand limit** (x→0+), we are interested in the value of the function as xxx approaches 0 from the **positive side** (i.e., from values greater than 0).
>
> - For x > 0, the function f(x) = 1
> - Thus, the right-hand limit is:
>
>
$$
\lim_{x \to 0^+} f(x) = 1
$$
### Practice Questions
1. limx→-2 (x² - 1)/(x + 2)
2. limx→3 (x³ - 27)/(x - 3)
3. limx→5 (x² + 2x - 15)/(x - 5)
4. Find the right-handed limit: lim x→2 (x² - 4)/(x - 2)
### Related Article
> - [Properites of Limits](https://www.geeksforgeeks.org/maths/properties-of-limits/)
> - [Limits of Functions](https://www.geeksforgeeks.org/maths/what-is-the-limit-of-a-function/)
> - [Limit Formulas](https://www.geeksforgeeks.org/maths/limit-formula/)
> - [L'Hopital's Rule](https://www.geeksforgeeks.org/maths/l-hopital-rule/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/limits/)

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
