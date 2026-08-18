---
title: "Differentiability of Functions"
subject: "Engineering Mathematics"
topic: "Calculus"
source: "https://www.geeksforgeeks.org/maths/differentiability-of-a-function-class-12-maths/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Calculus"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/calculus
---


> [!abstract] Differentiability of Functions
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Calculus`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/differentiability-of-a-function-class-12-maths/)

---

# Differentiability of Functions

Differentiability is a property of a function that tells us whether it has a well-defined tangent line (or slope) at a given point. A function f(x) is said to be differentiable at a point x = a if the limit
>
$$
lim_{h\to0} \frac{f(a+h)-f(a)}{h}
$$
>
> exists and is finite.
> That limit, when it exists, is the derivative of f at a, denoted f′(a).
## Conditions of Differentiability
For a function to be differentiable, the following conditions must be satisfied:
- **Condition 1:** The function should be continuous at the point. A discontinuous line is not differentiable.
- **Condition 2:** The graph should not have a sharp corner or a cusp
- **Condition 3:**The graph should not have a vertical tangent at any point.
![conditions_under_which_a_function_is_not_differentiable](assets/conditions_under_which_a_function_is_not-84bc966a9c.webp)
> **Note:** The relationship between continuity and differentiability is that all differentiable functions happen to be continuous but not all continuous functions can be said to be differentiable.
## Checking Differentiability
**Step 1: Check Continuity at x = a**
Differentiability implies continuity. If f is not continuous at a**a** it is not differentiable.
limx→a f(x) = f(a)
If discontinuos, it is not differentiable
If continuos, proceed to Step 2.
**Step 2:Compute the Derivative Using the Limit Definition**
$$
f'(a) = \lim_{h\to0} \frac{f(a+h) - f(a)}{h}
$$
For Piecewise functions or points where behaviour changes, compute left-hand derivative(LHD) and right-hand derivative(RHD).
$$
LHD = \lim_{h\to0^-} \frac{f(a+h) - f(a)}{h}
$$
$$
RHD = \lim_{h\to0^+} \frac{f(a+h) - f(a)}{h}
$$
Differentiability Condition: LHD = RHD
If LHD and RHD are equal and finite, f is differentiable at a.
## Relationship Between Differentiability and Continuity
Theorem: "Differentiability implies continuity " - If a function f is differentiable at a point x = a, then f is continuous at x = a.
Proof:
Assume f is differentiable at x = a. Then, the derivative exists:
$$
f'(a) = \lim_{h\to0} \frac{f(a+h) - f(a)}{h}
$$
Consider :
$$
\lim_{x\to a} [f(x) - f(a)]] = \lim_{h\to 0} [ f(a+h)- f(a)]
$$
Multiply and divide by h:
$$
\lim_{h\to 0} [\frac{f(a+h) - f(a)}{h} \cdot h] = f'(a) \cdot  0 = 0
$$
Because f is differentiable at a, and
$$
\lim_{h\to 0} h = 0
$$
> So:
>
>
$$
\lim_{x\to a} f(x) = f(a)
$$
Hence f is continuous at x = a. Converse is not true (e.g., |x| is continuous but not differentiable at 0).
## Differentiability of Piecewise Functions
Let us consider two important piecewise-defined functions:
1. The floor function (also known as the greatest integer function), denoted as f(x) = ⌊x⌋
2. The fractional part function, denoted as f(x) = {x}
### **F**loor function: **f(x) =** ⌊**x**⌋
The floor function returns the greatest integer less than or equal to x.
**Graph and Behavior:**
- For x ∈ [0,1), ⌊x⌋ = 0
- For x ∈ [−1,0), ⌊x⌋ = −1
![floor](assets/floor-9a6e7ac620.webp)
**Domain and Range**
- Domain: All real numbers (R).
- Range: All integers (Z).
**Differentiability Analysis:**
At Integer Points (e.g., x = 1):
- Right-hand limit (RHL): lim⁡x→1+ ⌊x⌋ = 1
- Left-hand limit (LHL): lim⁡x→1− ⌊x⌋ = 0
- Since RHL ≠ LHL, the function is not continuous at integer points.
- Differentiability requires continuity. Hence, the floor function is not differentiable at any integer point.
At Non-Integer Points (e.g., x = 2.5):
- Right-hand limit (RHL): lim⁡x→2.5+ ⌊x⌋ = 2
- Left-hand limit (LHL): lim⁡x→2.5− ⌊x⌋ = 2
- Since RHL = LHL, the function is continuous at non-integer points.
- To check differentiability, we compute the derivative:
  For x ∈ (2, 3), ⌊x⌋ = 2 (a constant value).
  Therefore, the derivative is 
$$
\frac{d}{dx}
$$
  ⌊x⌋= 0 at x = 2.5.
- Thus, the floor function is differentiable at all non-integer points, with derivative 0.
### **Fractional Part Function: f(x) = {x}**
The fractional part function is defined as {x} = x − ⌊x⌋.
**Graph and Behavior**
- For any x, {x} ∈ [0,1): For x ∈ [0,1), {x} = x, for x ∈ [1,2)**,** {x} = x − 1, etc.
![fractional_part_fn](assets/fractional_part_fn-35f6363a3b.webp)
**Domain and Range**
- Domain: All real numbers (R).
- Range: [0, 1).
**Differentiability Analysis**
At Integer Points (e.g., x = 1):
- RHL: lim⁡x→1+{x} = lim⁡x→1+(x−1) = 0
- LHL: lim⁡x→1−{x} = lim⁡x→1−(x−0) = 1 (since for x ∈ [0, 1), ⌊x⌋ = 0)
- Since RHL ≠ LHL, the function is not continuous at integer points.
- Hence, it is not differentiable at integer points.
At Non-Integer Points (e.g., x = 1.5):
- RHL: lim⁡x→1.5+{x} = 1.5 − 1 = 0.5
- LHL: lim⁡x→1.5−{x} = 1.5 − 1 = 0.5 (since ⌊1.5−⌋ = 1)
- Since RHL = LHL, the function is continuous at non-integer points.
- To check differentiability:
- For x ∈ (1,2), {x} = x − 1.
- The derivative is
$$
\frac{d}{dx}
$$
  {x} = 1 at x = 1.5.
- Thus, the fractional part function is differentiable at all non-integer points, with derivative 1.
## **Differentiability of Elementary Functions**
### **Polynomial Functions**
- Function: f(x) = anxn + an−1xn−1 + ⋯ + a1x + a0​
- Domain: R
- Differentiability: Polynomials are differentiable everywhere on R.
- Derivative: f′(x) = nanxn-1 + (n-1)an−1xn−2 + ⋯ + a1
- The derivative of a polynomial is itself a polynomial, which is defined for all real numbers.
### **Exponential Functions**
- Function: f(x) = ax, where a > 0, a ≠ 1
- Domain: R
- Differentiability: Exponential functions are differentiable everywhere on R.
- Derivative: f′(x) = axln⁡a
  Special case: If a = e, f(x) = ex, then f′(x) = ex.
- The limit defining the derivative exists for all x, and the function is smooth.
### **Logarithmic Functions**
- Function: f(x) = log⁡ax, where a > 0, a ≠ 1
- Domain: (0, ∞)
- Differentiability: Differentiable at every point in its domain (0, ∞).
- Derivative: f′(x) = 1/{xln⁡a}​
  Special case: Natural log f(x) = ln⁡x, then f′(x) = 1/x​.
- The function is continuous and smooth on (0, ∞), and the derivative exists there.
### **Trigonometric Functions**
This table explains the major trigonometric functions and their differentiability.
| Function | Domain | Differentiability | Derivative |
| --- | --- | --- | --- |
| f(x) = sin x | R | Differentiable everywhere on R. |
$$
\frac{d}{dx}(\sin{x}) = \cos{x}
$$
 |
| f(x) = cos x | R | Differentiable everywhere on R. |
$$
\frac{d}{dx}(\cos{x}) = -\sin{x}
$$
 |
| f(x) = tan x | {x ∈ R ∣ **x ≠π**​/2 + **kπ**, **k** ∈ Z} | Differentiable at every point in its domain. |
$$
\frac{d}{dx}(\tan{x}) ={sec{^2}}
$$
 |
| f(x) = sec x | {x ∈ R ∣ **x ≠π**​/2 + **kπ**, **k** ∈ Z} | Differentiable wherever they are defined (i.e., where denominators are non-zero). |
$$
\frac{d}{dx}(\sec{x}) = \sec{x} \tan{x}
$$
 |
| f(x) = cosec x | {x ∈ R ∣ **x ≠kπ**, **k** ∈ Z} | Differentiable wherever they are defined (i.e., where denominators are non-zero). |
$$
\frac{d}{dx}(\csc{x}) =- \csc{x} \cot{x}
$$
 |
| f(x) = cot x | {x ∈ R ∣ **x ≠kπ**, **k** ∈ Z} | Differentiable wherever they are defined (i.e., where denominators are non-zero). |
$$
\frac{d}{dx}(\cot{x}) = -\csc^2{x}
$$
 |
## Examples On Differentiability
**Example 1:** Prove that the greatest integer function defined by f(x) = [x] , 0 < x < 3 is not differentiable at x = 1 and x = 2.
**Solution:**
> As question given  f(x) = [x] where x is greater than 0 and also less than 3. So we have to check the function is differentiable at point x =1 and at x = 2 or not. To check the differentiability of function, as we discussed above in Differentiation that LHD at(x = a) = RHD at (x = a) which means,
>
> Lf' at (x = a) = Rf' at (x = a) if they are not equal after solving and putting the value of a in place of x then our function should not differentiable and if they both comes equal then we can say that the function is differentiable at x = a, we have to solve for two points x = 1 and x = 2.
>
> Now, let's solve for x = 1 
> f(x) = [x] 
>
> Put x = 1 + h 
>
> Rf' = limh -> 0 f(1 + h) - f(1) 
> = limh -> 0 [1 + h] - [1] 
>
> Since [h + 1] = 1 
> = limh -> 0 (1 - 1) / h = 0 
>
> Lf'(1) = limh -> 0 [f(1 - h) - f(1)] / -h 
> = limh -> 0 ( [1 - h] - [1] ) / -h
>
> Since [1 - h] = 0 
> = limh -> 0 (0 - 1) / -h 
> = -1 / -0 
> = ∞ 
>
> From the above solution it is seen that Rf' ≠ Lf', so function f(x) = [x] is not differentiable at x = 1. Now, let's check for x = 2. As we solved for x = 1 in the same we are going to solve for x = 2. Condition should be the same we have to check that, Lf' at (x = 2) = Rf' at (x = 2) or not if they are equal then our function is differentiable at x = 2 and if they are not equal our function is not differentiable at x = 2. So, let's solve.
>
> f(x) = [x] 
>
> Differentiability at x=2 
>
> Put x = 2 + h 
>
> Rf'(1) = limh -> 0 f(2 + h) - f(2) 
> = limh -> 0 ([2 + h] - [2]) / h 
>
> Since 2 + h = 2  
> = limh -> 0 (2 - 2) / h 
> = limh -> 0 0 / h 
> =0 
>
> Lf'(1) = limh -> 0 (f(2 - h) - f(2)) / -h 
> = limh -> 0 ([2 - h] - [2]) / -h 
> = limh -> 0 (1 - 2) / -h 
>
> Since [2 - h] = 1 
> = -1 / -0 
> = ∞ 
>
> From the above solution it is seen that Rf'(2) ≠ Lf'(2), so f(x) = [x] is not differentiable at x = [2]
**Example 2:** 
$$
f(x) = \left\{\begin{matrix} x\times \frac{e^{1/x} - 1, x \neq 0}{e^{1/x} + 1, x = 0} \end{matrix}\right.
$$
Show that the above function is not derivable at x = 0.
**Solution:**
> As we know to check the differentiability we have to find out Lf' and Rf' then after comparing them we get to know that the function is differentiable at the given point or not. So let's first find the Rf'(0).
>
> Rf'(0) = limh -> 0 f(0 + h) - f(0) 
> = limh -> 0 (f(h) - f(0)) / h 
> = limh -> 0 h . [{(e(1 / h) - 1) / (e(1 / h) + 1) } - 0]/h 
> = limh -> 0 (e(1 / h) - 1) / (e(1 / h) + 1) 
>
> Multiply by e(-1 / h) 
>
> = limh -> 0 {1 - e(-1 / h) / 1 + e(-1 / h)} 
> = (1 - 0) / (1 + 0) 
> = 1  
>
> After solving we had find the value of Rf'(0) is 1. Now after this let's find out the Lf'(0) and then we will check that the function is differentiable or not.
>
> Lf'(0) = limh -> 0 { **f**(0 - h) - **f**(0) } / -h 
> = limh -> 0 -h . [{e(-1 / h) - 1 / e(-1 / h) + 1} - 0] / -h 
> = limh -> 0 { (e(-1 / h) - 1) / (e(-1 / h) + 1) } 
> = limh -> 0 { (1 - e(-∞))/ (1+e(-∞))} 
> = (0 - 1) / (0 + 1) 
> = -1  
>
> As we saw after solving Lf'(0) the value we get -1. Now checking if the function is differentiable or not, Rf'(0) ≠ Lf'(0) (-1≠1). Since Rf'(0) ≠ Lf'(0), so f(x) is not differentiable at x = 0.
**Example 3:** A function is f(x) defined by 
- f(x) = 1 + x of x < 2
- f(x) = 5 - x of x ≥ 2
If function f(x) differentiable at x = 2?
**Solution:**
> So, for finding Lf'(2) we take the function **f**(x) = 1 = x, in the same way for finding Rf'(2) we take the function **f**(x) = (5 - x). Let's find out Lf'(2) and Rf'(2)
>
> Lf'(2) = limh -> 0 {f(2 - h) - f(2)} / -h 
> = limh -> 0 [[(2 - h) + 1] - [5 - 2]] / -h 
> = limh -> 0 (3 - h - 3) / -h 
> = limh -> 0 -h / -h 
> = 1
>
> Rf'(2) = limh -> 0 {f(2 + h) - f(2)} / h 
> = limh -> 0 [[5 - (2 + h)] - 3] / h  = limh-> 0 [5-2-h - 3] / h
> =limh -> 0 -h / h 
> = -1  
>
> In the first line Lf'(2) after putting in the formula, for f(2) we are putting second function (5 - x). After solving the Lf'(2) we get the value 1.
> For calculating Rf'(2) we are using the second function 5-x and putting in the formula of Rf', on solving the Rf'(2) we get the value -1.
>
> Since, Rf'(2) ≠ Lf'(2) so we can say the function f(x) is not differentiable at x = 2.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/differentiability-of-a-function-class-12-maths/)

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
> - [[Euler's Formula]]
> - [[Finding the Various nth term of any polynomial sequence]]
> - [[Indefinite Integrals]]
> - [[Indeterminate Forms]]
> - [[Lagrange’s Mean Value Theorem]]
