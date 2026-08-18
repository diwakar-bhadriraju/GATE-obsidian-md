---
title: "Taylor Series"
subject: "Engineering Mathematics"
topic: "Calculus"
source: "https://www.geeksforgeeks.org/engineering-mathematics/taylor-series/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Calculus"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/calculus
---


> [!abstract] Taylor Series
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Calculus`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/taylor-series/)

---

# Taylor Series

A Taylor series represents a function as an infinite sum of terms, calculated from the values of its derivatives at a single point.
- It is a powerful mathematical tool used to approximate complex functions with an infinite sum of terms derived from the function's derivatives at a single point.
- Each successive term in the Taylor series expansion has a larger exponent or a higher degree term than the preceding term.
- We take the sum of the initial four and five terms to find the approximate value of the function, but we can always take more terms to get the precise value of the function.
- Finding approximate values of functions helps in many fields like Machine Learning, Economics, Physics, Medicine, and Biomedical Engineering.
## Taylor Series Expansion
Taylor series expansion of the real and composite function f(x) whose differentiation exists in a closed neighborhood is,
>
$$
f(x) = f(a) + \frac{f'(a)}{1!}(x - a) + \frac{f''(a)}{2!}(x - a)^2 + \frac{f'''(a)}{3!}(x - a)^3 + \cdots
$$
**where,**
- **f(x)** is the real or complex value function that is infinitely differentiable
- **n** is the number of times the function is differentiated
- **f**(n)**is the n derivative of the function f(x)
**Taylor Series in terms of sigma notation is,**
![1](assets/1-e66f6f9501.webp)
Taylor's series formula is used to find the value of any function around a particular value. Suppose we have to find the value of the real and composite function f(x) at point a, such that the differentiation of the function is defined in the closed neighborhood of the function
## Taylor’s Series Theorem
The statement for the Taylor Series Theorem is
**For a real or complex-valued function f(x) which is differentiable on the neighbourhood of a number the Taylor series is,**
$$
f(x) = f(a) + \frac{f'(a)}{1!}(x - a) + \frac{f''(a)}{2!}(x - a)^2 + \frac{f'''(a)}{3!}(x - a)^3 + \cdots...+\frac{ f^n(x)}{n!}(x-a)^n
$$
where f n (a) = nth derivative of f
## Proof
> We know that power series is defined as,
>
>
$$
f(x) = ∑ a_nx^n = a0 + a_1x + a_2x^2 + a_3x^3 + ...
$$
>
>           (i)
>
> where, 0 ≤ n < ∞
> for x = 0
> f(x) = ao
>
> The differentiation of the function f(x) from eq (i) is,
>
>
$$
f'(x) = a_1 + 2a_2x + 3a_3x^2 + 4a_4x^3 ...
$$
>
>           (ii)
>
> substituting x = 0 in f'(x)
> f'(0) = a1
>
> Differentiating eq (ii) again,
>
>
$$
f''(x) = 2a_2 + 6a_3x + 12a_4x^2 + ...
$$
>
> substituting x = 0 in f''(x)
> f''(0) = 2a2
>
>
$$
\frac{f''(0)}{2!} =\frac{ 2a_2}{2} = a_2
$$
>
>
> similarly,
>
>
$$
\frac {f^n(0)}{n!} = a_n
$$
>
> Now substituting all these values in eq(i)
>
>
$$
f(x) = f(0) + f'(0)x + \frac{f''(0)}{2!(x)^2} + \frac{f'''(0)}{3!x^3 }+ ...
$$
>
> Generalizing the function f(x) we get,
>
>
$$
f(x) = b + b_1(x-a) + b_2(x-a)^2 + b_3(x-a)^3 + ...
$$
>
> Now taking x =a,
>
>
$$
b_n = \frac{f^{(n)}(a)}{n!}
$$
>
> Substituting the value of bn in a generalized form of f(x)
>
>
$$
f(x) = f(a) +[\frac{ f'(a)}{1!}](x-a) + [\frac{f''(a)}{2!}](x-a)^2 +...
$$
This proves the Taylor Series.
## Taylor Series of Sin x
Let's take the function f(x) = sin x
f’(x) = cos x
f’’(x) = -sin x
f’’’(x) = -cos x
f’’’’(x) = sin x
**Taylor series for sin x at x = 0 is,**
![2](assets/2-c68ede9650.webp)
## Taylor Series of Cos x
Let's take the function f(x) = cos x
f’(x) = -sin x
f’’(x) = -cos x
f’’’(x) = sin x
f’’’’(x) = -cos x
**Taylor series for cos x at x = 0 is,**
![3](assets/3-b3c4761fe0.webp)
## Taylor Series in Several Variables
Taylor series can also be represented for the function of several variables. The general form of the Taylor series in several variables is,
![taylor-series-](assets/taylor-series--219555cdb0.webp)
## **Maclaurin Series**
We know that the Taylor series is,
$$
f(x) = f(a) + \frac{f'(a)}{1!}(x - a) + \frac{f''(a)}{2!}(x - a)^2 + \frac{f'''(a)}{3!}(x - a)^3 + \cdots...+\frac{ f^n(x)}{n!}(x-a)^n
$$
If the Taylor series is centred at x = 0, i.e. the value of f(x) is found at x = 0 then this series is called the Maclaurin Series.
Then the Maclaurin Series is,
>
$$
f(x) = f(0) + [\frac{f'(0)'}{1!}](x-0) + [\frac{f''(0)}{2!}](x)^2 + [\frac{f'''(0)}{3!}](x)^3 +...+ \frac{f^{(n)}(0)}{n!}(x)^n
$$
This above series is known as the Maclaurin series.
**Example:** Maclaurin series of ex is,
>
$$
e^x = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \frac{x^4}{4!} + . . .
$$
### Applications of Taylor Series in Engineering
The Taylor series has a wide range of applications in engineering, including:
1. **Numerical Analysis**: Used to approximate functions and solve differential equations via polynomial approximations.
2. **Signal Processing:** Helps in signal approximation and filtering, reducing computational complexity.
3. **Control Systems:** Linearizes nonlinear systems, simplifying controller design and analysis.
4. **Computational Physics:** Approximates functions to solve complex physical models, enhancing simulation efficiency.
5. **Machine Learning:** Used in optimization algorithms to approximate gradients and Hessians, aiding model training.
## Examples Using Taylor Series
**Example 1:** Find the expansion for the function, f(x) = x3 centred at a = 2 using the Taylor Series Formula.
**Solution:**
> We know that Taylor Series Formula is
>
>
$$
f(x) = f(a) + \frac{f'(a)}{1!}(x - a) + \frac{f''(a)}{2!}(x - a)^2 + \frac{f'''(a)}{3!}(x - a)^3 + \cdots...+\frac{ f^n(x)}{n!}(x-a)^n
$$
>
> Given function, f(x) = x3
> Centered at a = 2
> f'(x) = 3x2
> f''(x) = 6x
> f'''(x) = 6
> f''''(x) = 0
>
> Now the Taylor Series expansion of **f(x) = x**3**is,
>
>
$$
f(x) = f(2) + [\frac{f'(2)'}{1!}](x-2) + [\frac{f''(2)}{2!}](x-2)^2 + [\frac{f'''(2)}{3!}](x-2)^3 +[\frac{ f''''(a)}{4!}](x-2)^4
$$
>
>
> f(x) = 8 + 12(x-2) + 6(x-2)2 + (x-2)3 + 0
> f(x) = (x-2)3 + 6(x-2)2 + 12x - 16
**Example 2:** Find the expansion for the function, f(x) = 4x centred at a = 1 using the Taylor Series Formula.
**Solution:**
> Given function, f(x) = 4x
> Centered at a = 1
> f'(x) = 4
> f''(x) = 0
>
> Now the Taylor Series expansion of **f(x) = 4x** is,
>
>
$$
f(x) = f(1) + [\frac{f'(1)'}{1!}](x-1) + [\frac{f''(1)}{2!}](x-1)^2
$$
>
>
> f(x) = 4 + 4(x-1) + 0
> f(x) = 4x
**Example 3:** Find the Taylor series expansion for function, f(x) = sin x, centred at
$$
x = \pi
$$
.
**Solution:**
> f(x) = sin x
> Derivatives of the six x are,
> f(x) = sin (x)
> f'(x) = cos (x)
> f''(x) = -sin (x)
> f'''(x) = -cos (x)
>
> Now,
>
>
$$
sin(x) = sin(a)+\frac{cos(a)}{1!} (x - a)−\frac{sin(a)}{2!} (x - a)^2-\frac{cos(a)}{3!} (x - a)^3+ ...
$$
>
>
> Putting **x**=**π**
>
>
$$
sin(x) = sin(\pi)+\frac{cos(\pi)}{1!} (x - \pi)−\frac{sin(\pi)}{2!} (x - \pi)^2-\frac{cos(\pi)}{3!} (x - \pi)^3+ ...
$$
>
>
>
>
$$
sin(x)=0+(−1)(x−π)− \frac{0}{2!}(x−π) ^2-\frac{-1}{3!}(x−π) ^3 +⋯
$$
>
> taylor series is
>
>
$$
sin(x)=−(x−π)+ \frac{(x−π) ^3}{6} ​ − \frac{(x−π) ^5}{120} ​ +⋯
$$
**Example 4:** Taylor Series for ex around x = 0
Solution:
> The Taylor Series for ex around x = 0 is:
>
>
$$
e^x = 1 + x + (x^2/2!) + (x^3/3!) + (x^4/4!) + ...
$$
>
> Let's use this to approximate e0.5 up to the 4th term:
>
>
$$
e^0.5 ≈ 1 + 0.5 + (0.5^2/2!) + (0.5^3/3!) + (0.5^4/4!)
$$
>
>
> ≈ 1 + 0.5 + 0.125 + 0.0208333 + 0.0026042
> ≈ 1.6484375
> The actual value of e0.5 is approximately 1.6487212, so our approximation is quite close.
**Example 5:** Taylor Series for
$$
sin(\frac{π}{6})
$$
 up to the 4th term
Solution:
> The Taylor Series for sin(x) around x = 0 is:
>
>
$$
sin(x) = x - (\frac{x^3}{3!}) + (\frac{x^5}{5!}) - (\frac{x^7}{7!}) + ...
$$
>
> Let's use this to approximate sin(π/6) up to the 4th term:
>
>
$$
sin(\frac{π}{6}) ≈ (\frac{π}{6}) - (\frac{(π/6)^3}{3!}) + (\frac{(π/6)^5}{5!}) - (\frac{(π/6)^7}{7!})
$$
>
>
> ≈ 0.5236 - 0.0023 + 0.0000 - 0.0000
> ≈ 0.5213
> The actual value of
>
>
$$
sin(\frac{π}{6})
$$
>
>  is 0.5, so our approximation is quite good.
### Related Articles:
> - [Arithmetic Progression](https://www.geeksforgeeks.org/maths/what-is-arithmetic-progression/)
> - [Geometric Progression](https://www.geeksforgeeks.org/maths/what-is-geometric-progression/)
> - [Implicit Differentiation](https://www.geeksforgeeks.org/maths/implicit-differentiation/)
## Practice Questions on Taylor Series
**Question 1:** Write the first four terms of the Taylor Series for cos(x) around x = 0.
**Question** 2: Use the Taylor Series for ex to approximate e0.3 up to the third term.
**Question 3:** What is the Taylor Series for ln(1+x) around x = 0? Write the first three terms.
**Question 4:** Approximate √(1+x) near x = 0 using the first three terms of its Taylor Series.
**Question 5:** Find the Taylor Series for 1/(1-x) around x = 0 and write the first four terms.
**Question 6:** Use the Taylor Series for sin(x) to approximate sin(π/4) up to the third term.
**Question 7:** Write the first three terms of the Taylor Series for tan(x) around x = 0.
**Question 8:** Approximate cos(0.1) using the first four terms of its Taylor Series.
**Question 9:** Find the Taylor Series for arctan(x) around x = 0 and write the first three terms.
**Question 10:** Use the Taylor Series for ex to estimate the value of e to three decimal places.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/taylor-series/)

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
