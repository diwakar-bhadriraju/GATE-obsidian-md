---
title: "Inverse Functions"
subject: "Discrete Mathematics"
topic: "Algebraic and Set-Theoretic Structures"
source: "https://www.geeksforgeeks.org/maths/inverse-functions/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Algebraic and Set-Theoretic Structures"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/algebraic-and-set-theoretic-structures
---


> [!abstract] Inverse Functions
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Algebraic and Set-Theoretic Structures`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/inverse-functions/)

---

# Inverse Functions

**Inverse Functions** are an important concept in mathematics. An inverse function basically reverses the effect of the original function. If you apply a function to a number and then apply its inverse, you get back the original number. For example, if a function turns 2 into 5, the inverse function will turn 5 back into 2.
![420046937](assets/420046937-850e2169d4.webp)
**In mathematical terms:**
If functions f(x) and g(x) are inverses of each other, then f(x) = y only if g(y) = x. 
> g(f(x)) = x
### Inverse Function Example
Let's say we have a function f(x) = x2. Now we are asked to find out the inverse of this function. This function is squaring its inputs; we know we need to take the square root to calculate the inverse.
> f(x) =  x2
> f-1(x) = √x
> f-1(f(x))  = √x2 = ±x
We see that there are two possible answers, but which one to choose? In such cases, the inverse is not possible. So, there are things we need to notice for the functions for which inverses are possible. Also, the function whose inverse exists is called an [invertible function](https://www.geeksforgeeks.org/dsa/invertible-functions/).
## Conditions for an Inverse Function
For a function to have an inverse, it must be [bijective](https://www.geeksforgeeks.org/maths/bijective-function/):
- **One–One (**[**Injective**](https://www.geeksforgeeks.org/maths/injective-functions/)**):**  Every output value must come from **only one** input value.
- **Onto (**[**Surjective**](https://www.geeksforgeeks.org/maths/onto-functions/)**):** Every element of the codomain must be covered by the function.
### Checking the Graph for One–One Behavior
Consider the graph shown below (a [parabola](https://www.geeksforgeeks.org/maths/what-is-parabola/))
![Example of graph for bijection.](assets/graph-of--parabola-f87f9adbc3.png)
A quick way to check if a function is one–to–one is the [Horizontal Line Test](https://www.geeksforgeeks.org/maths/horizontal-line/#:~:text=is%20always%20constant.-,Horizontal%20Line%20Test,-A%20test%20that):
- If any horizontal line intersects the graph more than once, the function is not one–to–one, and therefore it cannot have an inverse on its full domain.
In the parabola shown:
- A horizontal line, such as y = 1, intersects the curve at two points.
- This means that the function takes the same output value for two different inputs.
So, the function fails the one–to–one condition. Therefore, it does not have an inverse unless we restrict its domain (for example, choosing only the left half or right half of the parabola).
## How to Find the Inverse of a Function?
> **Step 1:** Substitute f(x) in the given function by "y".
>
> **Step 2:** Solve for "x" for the newly formed equation.
>
> **Step 3:** Switch the positions of "x" and "y".
>
> **Step 4:** Substitute the y with notation of inverse function f -1(x).
**Example:** Find the inverse of f(x) = 6x + 10. 
**Solution:**
> We know, f(x) = 6x + 10. Let's substitute y in place of f(x). 
>
> y = 6x + 10
> ⇒ y - 10 = 6x
> ⇒ x = (y - 10)/6
> ⇒ y = (x - 10)/6
> ⇒ f -1(x) = (x - 10)/6 
## Inverses of Common Functions
The table given below describes the inverses of some common functions, which may come in handy while calculating the inverses for complex functions.
| Function | Inverse | Corner Cases |
| --- | --- | --- |
| xn |
$$
x^{\frac{1}{n}}
$$
 | Negative values are not allowed when n is even |
| ax | logax | x > 0 and a > 0 |
| sin(x) | sin-1(x) | Only values between -1 to 1 are allowed |
| cos(x) | cos-1(x) | Only values between -1 to 1 are allowed |
| tan(x) | tan-1(x) | --- |
## Inverse Functions Graphs
To understand the graph of the inverse function, let's say we have f(x) = ex and assume it has an inverse i.e., g(x). We know that the inverse of an exponential function is a logarithmic function. So, g(x) = logex. The figure below shows the graph for both of the functions. 
![Graphs of Inverse Functions](assets/inverse-of-exponential-function-75dec37d10.png)
We can see that both graphs are mirror images of each other with respect to the line y = x.
> **Note:** Inverse of a function is a mirror image of the function when seen through the line y = x. There is no shortcut way to plot the graph of the inverse function if the graph of the original function is not given.
## Inverse Function Types
There are various types of inverse functions for common functions; some of these types are discussed as follows:
### Inverse Trigonometric Function
[Inverse Trigonometric Functions](https://www.geeksforgeeks.org/maths/inverse-trigonometric-functions/) are the inverse functions of the [trigonometric ratios](https://www.geeksforgeeks.org/maths/trigonometric-ratios/), and the table for the range and domain of all the Inverse Trigonometric Functions is as follows:
| Inverse Trigonometric Function | Domain | Range |
| --- | --- | --- |
| **sin**-1**(x)** | [-1, 1] | [-π/2 , π/2] |
| **cos**-1**(x)** | [-1, 1] | [0, π] |
| **tan**-1**(x)** | R | (-π/2 , π/2) |
| **sec**-1**(x)** | R - (-1, 1) | [0, π] - {π/2} |
| **cosec**-1**(x)** | R - (-1, 1) | [ -π/2, π/2] - {0} |
| **cot**-1**(x)** | R | (0, π) |
### Exponential and Logarithm Function
Another example of inverse pair is the exponential and logarithm function, both are inverse of each other. For an exponential function f(x) = ax, its inverse is given by logarithm i.e., logax, and vice versa.
### Inverse Hyperbolic Function
Similar to the Inverse Trigonometric Function, there are [inverse hyperbolic functions,](https://www.geeksforgeeks.org/maths/explain-inverse-hyperbolic-functions-formula/) which are the inverse of the hyperbolic trigonometric function i.e., sinh x, cosh x, tanh x, and so on. Inverse Hyperbolic Function are sinh-1, cosh-1x, tanh-1x, cosech-1x, coth-1x, and sech-1x.
## Solved Examples of Problems on Inverse Functions
**Problem 1:** Find the inverse of the function f(x) = ln x + 5. 
**Solution:**
> f(x) = lnx + 5 
>
> Substituting the f(x) with y
> y = lnx + 5 
> ⇒ lnx= y - 5
> ⇒ x = e(y - 5)
>  f-1(y) = e(y - 5)
**Problem 2:** Find the inverse of the function f(x) = 
$$
\frac{x + 4}{2x + 1}
$$
**Solution:**
>  
>
>
$$
f(x) = \frac{x + 4}{2x + 1}
$$
>
> Substituting f(x) with y
>
>
$$
y = \frac{x + 4}{2x + 1}
$$
>
> ⇒ 
>
>
$$
y(2x + 1) = x + 4
$$
>
>
> ⇒ 2xy + y = x + 4 
> ⇒ x(2y - 1) = 4 - y
>
> ⇒ x = 
>
>
$$
\frac{4 - y}{2y - 1}
$$
>
> Thus, f-1(y) = 
>
>
$$
\frac{4 - y}{2y - 1}
$$
**Problem 3:** Find the inverse of the following function and draw its graph: f(x) = ex + 20
**Solution:**
> f(x) = ex + 20
>
> Substituting the f(x) with y 
> ⇒y = ex + 20
> ⇒y - 20 = ex
> ⇒ln(y - 20) = x
>
> f-1(y) = ln(y - 20)
>
> The figure below, shows the graphs for f(x) and it's inverse. 
>
> ![Graphs of Inverse Functions Problem-3](assets/graph-of-exponential-function-7d293e72f4.png)
>
> Notice that y > 20 for this function. 
**Problem 4:** State whether the statement is True or False. For the given function f(x) = x2 + 4, the inverse does not exist for all values of x. 
**Solution:**
> We know that f(x) = x2 + 4 is not bijective. For example, 
>
> f(-2) = 8 and f(2) = 8. So, the inverse for this function cannot exist for all values of x. Thus, this statement is called False. 
**Problem 5:** Find the inverse for the following function: **f(x) =**
$$
\frac{x}{5x + 1}
$$
**Solution:**
> f(x) = 
>
>
$$
\frac{x}{5x + 1}
$$
>
>  
>
> Substituting f(x) with y. 
>
>
$$
y = \frac{x}{5x + 1}
$$
>
> ⇒ 
>
>
$$
y = \frac{x}{5x + 1}
$$
>
> ⇒ y(5x + 1) = x
> ⇒ 5xy + y = x
> ⇒ x(5y - 1) = -y 
>
> ⇒ x =
>
>
$$
\frac{-y}{5y - 1}
$$
>
> Thus, f-1(y) = 
>
>
$$
\frac{-y}{5y - 1}
$$
## Unsolved Questions of problems on Inverse Functions
**Problem 1:** Find the inverse of the function
$$
f(x) = In(x-3)
$$
**.**
**Problem 2:** Find the inverse of the function
$$
f(x)= \frac{3x-2}{x+5}
$$
.
**Problem 3:** Find the inverse of the exponential function
$$
f(x) = 4e^{2x}
$$
.
**Problem 4:** Determine whether the following function has an inverse. Justify your answer.
$$
f(x) = |x-2|
$$
**.**
**Problem 5:** Find the inverse of the function
$$
f(x) = \frac{2x + 7}{5x -1}
$$
**.**
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/inverse-functions/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Algebraic and Set-Theoretic Structures

> [!note] Related notes
>
> - [[Cartesian Product of Two Sets]]
> - [[Classes of Functions]]
> - [[Closure of Relations]]
> - [[Composition of Functions]]
> - [[Equivalence Relations]]
> - [[Groups]]
> - [[Hasse Diagrams]]
> - [[Introduction to Set Theory]]
> - [[Modular Addition]]
> - [[Multiplication Modulo]]
