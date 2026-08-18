---
title: "Absolute Minima and Maxima"
subject: "Engineering Mathematics"
topic: "Calculus"
source: "https://www.geeksforgeeks.org/maths/absolute-minima-and-maxima/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Calculus"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/calculus
---


> [!abstract] Absolute Minima and Maxima
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Calculus`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/absolute-minima-and-maxima/)

---

# Absolute Minima and Maxima

Absolute maxima and absolute minima are the highest and lowest values of a function on its entire domain or on a given interval. They are also known as global maxima and global minima.
![absolute_maxima](assets/absolute_maxima-4e2884ed5d.webp)
Points A, C are minima, and points B, D are maxima.
- Points A and D are global minima and global maxima.
- B and C are local maxima and local minima respectively.
This means that these points are maximum and minimum in their locality but not necessarily on a global level.
### **Extreme Value Theorem**
It states that if a function f(x) is continuous on a closed interval [a, b], it is guaranteed to attain both an absolute maximum and an absolute minimum on [a, b], though it does not tell us where these values occur.
> There exist points c and d in [a, b] such that f(c) ≤ f(x) ≤ f(d) for all x in [a, b], where f(c) is the absolute minimum and f(d) is the absolute maximum.
## **Absolute Minima and Maxima in Closed Interval**
Let's say we have a function f(x) and a region D. Now to find the extreme points in any interval:
> **Step 1:** Find the critical points of the function in the interval D, f'(x) = 0
>
> **Step 2:** Find the value of the function at the extreme points of interval D. 
>
> **Step 3:** The largest value and smallest value found in the above two steps are the absolute maximum and absolute minimum of the function. 
## **Absolute Minima and Maxima in Entire Domain**
We need to follow some steps to find out the absolute maxima and minima for the entire domain:
> **Step 1:** Find the critical points of the function wherever it is defined. 
>
> **Step 2:** Find the value of the function at these extreme points. 
>
> **Step 3:** Check for the value of the function when x tends to infinity and negative infinity. Also, check for the points of discontinuity. 
>
> **Step 4:** Maximum and minimum of all these values give us the absolute maximum and absolute minimum for the function in its entire domain. 
### Local Maxima and Minima
These are the maximum and minimum value of the function relative to other points over a specific interval of the function. [Local maxima and minima](https://www.geeksforgeeks.org/maths/maxima-and-minima/#:~:text=If%20the%20sign%20of%20f,the%20point%20of%20local%20minima.) of any function can be similar or not similar to Absolute maxima and minima of the function.
Let's say we have a function f(x) which is twice differentiable. Its critical points are given by the f'(x) = 0. Second Derivative Test allows us to check whether the calculated critical point is minima or maxima. 
- If f''(x) > 0, then the point x is a Local Minimum.
- If f''(x) < 0, then the point x is a Local Maximum
## Solved Examples
**Example 1:** Find the absolute maximum and absolute minimum values of the function f(x) = 5x + 2 in the interval [0,2]. 
**Solution:**
> Given function, f(x) = 5x + 2
>
> First step is to find the critical points by differentiating the function f(x), 
>
> f'(x) = 5
>
> This equation has no roots, therefore there are no critical points.
> This function is continuously increasing. Thus, the maxima and minima will occur at the end points of the interval. 
>
> - f(0) = 2
> - f(2) = 12
>
> Thus, f(0) = 2 is the minimum and f(2) = 12 is the maximum value of the function.
**Example 2:** Find the absolute maximum and absolute minimum values of the function f(x) = x2 - 2x + 5 in the interval [0,2]. 
**Solution:**
> Given function, f(x) = x2 - 2x + 5
>
> First step is to find the critical points by differentiating the function f(x), 
>
> f'(x) = 2x - 2
>
> f'(x) = 0 
>
> ⇒ x = 1 
>
> Thus, x = 1 is the critical point of the function
>
> f(1) = (1)2 - 2(1) + 5 = 4
>
> Checking the End Points of the Interval, 
>
> - f(0) = 5
> - f(2) = 5
>
> Out of all these values,
>
> Minimum value is at x = 1, f(1) = 4
>
> Maximum value is at x = 0 and 2, f(0) = f(2) = 5
>
> Thus, absolute maximum and absolute minimum values of the function are 5 at x = 0 and 2, and 4 at x = 1 respectively.
**Example 3:** Find the absolute maximum and absolute minimum values of the function f(x) = 1/(x + 4) in the interval [0, 1]. 
**Solution:**
> Given, f(x) = 1/(x + 4)
>
> Find the critical points by differentiating the function f(x), 
>
> f'(x) = -1/(x + 4)2
>
> This equation will not be zero for any value of x in the interval. So, it is monotonically increasing or decreasing in the interval. Checking at the boundary points. 
>
> f(0) = 1/4
>
> f(1) = 1/5
>
> Out of all these values,
>
> Maximum Value is at x = 0, f(0) = 1/4
>
> Minimum Value is at x = 1, f(1) = 1/5
>
> Thus, absolute maximum and absolute minimum values of the function are 1/4 and 1/5 respectively.
**Example 4:** Find the absolute maximum and absolute minimum values of the function f(x) = x3 - 2x2+ 5 in the interval [-2,2]. 
**Solution:**
> Given function,
>
> f(x) = x3 - 2x2+ 5
>
> First step is to find the critical points by differentiating the function f(x), 
>
> f'(x) = 3x2 - 4x
>
> x(3x - 4) = 0 
>
> Thus, x = 0 and 4/3 are Critical Points of the function. 
>
> f(0) = 5
>
> f(4/3) = (4/3)3 - 2(4/3)2 + 5
>
> = 64/27 - 32/9 + 5
>
> = 103/27
>
> Checking End points of the Interval, 
>
> f(-2) =(-2)3 - 2(-2)2+ 5 =-11 
>
> f(2) = (2)3 - 2(2)2+ 5 = 5
>
> Out of all these values,
>
> Minimum value is at x = -2, f(-2) = -11
>
> Maximum value is at x = 0 and 2, f(0) = f(2) = 5
>
> Thus, absolute maximum and absolute minimum values of the function are 5 and -11 respectively.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/absolute-minima-and-maxima/)

## GATE CS

- Subject: Engineering Mathematics
- Topic: Calculus

> [!note] Related notes
>
> - [[Application of Derivative]]
> - [[Cauchy’s mean value theorem]]
> - [[Chain Rule Derivative]]
> - [[Continuity]]
> - [[Differentiability]]
> - [[Euler's Formula]]
> - [[Finding the Various nth term of any polynomial sequence]]
> - [[Indefinite Integrals]]
> - [[Indeterminate Forms]]
> - [[Lagrange’s Mean Value Theorem]]
