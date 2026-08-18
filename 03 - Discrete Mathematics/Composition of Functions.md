---
title: "Function Composition"
subject: "Discrete Mathematics"
topic: "Algebraic and Set-Theoretic Structures"
source: "https://www.geeksforgeeks.org/maths/composition-of-functions/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Algebraic and Set-Theoretic Structures"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/algebraic-and-set-theoretic-structures
---


> [!abstract] Function Composition
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Algebraic and Set-Theoretic Structures`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/composition-of-functions/)

---

# Function Composition

The composition of functions is a process where you combine two functions into a new function. Specifically, it involves applying one function to the result of another function. In simpler terms, the output of one function becomes the input for the other function.
For example, if two functions f and g are given, then applying g to the output of f gives a new function h(x) = g(f(x)). This is known as the composition of functions.
![420046940](assets/420046940-873422cce2.webp)
Breakdown of the diagram:
1. **x**:The initial input value.
2. **g(x)**: The first function g is applied to the input X, producing the output g(x).
3. **f(g(x))**: The second function f is then applied to the result of g(x), leading to the final output f(g(x))
> This illustrates the composition (f ∘ g)(x) = f(g(x)), where the output of the first function g(x) is fed into the second function f(x).
Mathematically, the composition of two functions, f and g, is denoted as:
> (f ∘ g)(x) = f(g(x))
- First, apply the function g to the input x, resulting in g(x)
- Then, apply the function f to the result g(x), resulting in f(g(x))
So, the output of **g** becomes the input of **f**.
**Example:** If f(x) = x2 and g(x) = x + 3. Then calculate the composition g(f(x)) and f(g(x)). 
**Solution:**
> g(f(x)) = g(x2) = x2 + 3
>
> Similarly, we can easily calculate the f(g(x)) or (f ∘ g)(x) where g(x) is computed first.
>
> f(g(x)) = f(x + 3) = (x + 3)2
Notice that g(f(x)) is not equal to f(g(x)); they can or cannot be equal depending on the functions f(x) and g(x). The composition of a function is also called the function of a function. Thus, we can say that,
- For f(g(x)), g(x) is the input of the function f(x).
- For g(f(x)), f(x) is the input of the function g(x).
### Symbol
The composition of functions is represented using the symbol **∘**. We can also represent the composition of functions by simply using the parenthesis (). For any two given functions f(x) and g(x), we can find the composition of the function by using the formula,
> (f ∘ g)(x) = f(g(x))
The above function is read as "f of g of x." Here, first x is passed to g(x), which gives the answer in x, and then the answer is passed to f(x) to find the desired composition of the function.
> (g ∘ f)(x) = g(f(x))
The above function is read as "g of f of x." Here, first x is passed to f(x), which gives the answer in x, and then the answer is passed to g(x) to find the desired composition of the function.
## Solving Composite Function
The composition of functions means applying one function to the result of another. It is written as (f ∘ g)(x) = f(g(x)), which means you first find the value of g(x), then use that result as the input for f. Similarly, g(f(x)) means you solve f(x) first and then apply g to it.
It’s just like solving an expression using the BODMAS rule—work from the inside out. The correct order matters a lot; if you reverse it, you'll get a completely different answer.
This idea helps solve many math problems more clearly and step-by-step.
For f(g(x)):
> - First solve g(x)
> - Then plug that into f(x) to get f(g(x))
For g(f(x)):
> - First solve f(x)
> - Then plug that into g(x) to get g(f(x))
This can be easily understood with the help of an example
**Example:** If f(x) = x + 2 and g(x) = (2x)2, find f(g(x)) and g(f(x))
**Solution:**
> For f(g(x))
> Given, g(x) = (2x)2 = 4x2
> Thus, f(g(x)) = f(4x2) = 4x2 + 2
>
> Now for g(f(x))
>
> Given, f(x) = x + 2
> Thus, g(f(x)) = (2(x+2))2 = (2x + 4)2
> ⇒ g(f(x)) = 4x2 + 16 + 16x
### Finding Composite Function From Graph
If the functions are not given algebraically and only their graphical value is given, then also they can be easily calculated using the graphs given.
To find the composite function of two functions f(x) and g(x) whose graphs are given, if (x, y) is a point on a function f(x), then f(x) = y. We can find f(g(a)) (i.e., f(g(x)) at x = a) using the above information.
- **Step 1:** Firstly find g(a), i.e., the y-coordinate on the graph of g(x) at x = a
- **Step 2:** Now find f(g(a)), i.e., the y-coordinate on the graph of f(x) at x = g(a).
This can be understood using the image discussed below.
![Composite Function Graph](assets/Screenshot-from-2023-05-24-15-51-51-7dff1b00ba.png)
### Finding Composite Function From Table
A composite function, or composition of a function, can also be easily calculated using the table in which the values of the function corresponding to a given input value are given. Let's find the composite function using the table given below.
**Example:** From the following tables of f(x) and g(x), find g(f(1)).
For f(x), the table is,
| x | 1 | 2 | 3 |
| f(x) | 3 | 4 | 5 |
For g(x), the table is,
| x | 1 | 2 | 3 |
| g(x) | 1 | 4 | 9 |
**Solution:**
> f(1) = 3 (from the first table)
> g(f(1)) = g(3) 
>
> Now using the second table we can get the above value.
> g(3) = 9
>
> Thus, the required solution for g(f(1)) is 9
### Self-Composition
We can also compose a function with itself, and it is called a self-composite function. For any given function f(x), the function composition with itself is f(f(x)); it is also defined as (f∘f)(x). Now,
> (f ∘ f)(x) = f(f(x))
It can be better understood with the help of an example
**Example:** If f(x) = x3, then find (f ∘ f)(x).
**Solution:**
> Given: f(x) = x3
>
> (f ∘ f)(x) = f(f(x))
> = f (x3)
> = (x3)3
>
> (f ∘ f)(x) = x9
## **Domain and Range of Composition of Functions**
It is not possible to compose any two functions; some functions cannot be composed together. For example, let's say f(x) = ln(x) and g(x) = -x. If we try to compose f(g(x)), it is not possible for the positive value of x, as the logarithmic function cannot take negative input values, so f(g(x)) is not possible. So, there are certain things that should be kept in mind while deciding on composing the function.
So before composing any two functions, first we have to find the [domain and range](https://www.geeksforgeeks.org/maths/introduction-to-domain-and-range-relations-and-functions/) of the function.
### Domain of Composite Functions
For any function f(x) and g(x) defined as g: X → Y and f: Y → Z, then f(g(x)) is defined as f∘g: X → Z, i.e., the domain of f ∘ g is X and the range is Z. 
If the functions are defined algebraically, then also we can easily define their domain. To find the domain of the composite function, use the following steps. If we have to find the domain of f(g(x))
> **Step 1:** Firstly we will find the domain of the inner function g(x)
>
> **Step 2:** Then we find the domain of the function obtained by finding f(g(x))
>
> **Step 3:** Now the intersection of the domain of g(x) and the domain of f(g(x)) is the domain of f(g(x))
### Range of Composite Functions
The range of a composite function is the set of all output values obtained when one function is applied to the result of another.
**Example:** Find the domain and range of f(g(x)) when f(x) = x + 2 and g(x) = x2.
**Solution:**
> For f(g(x)), 
>
> The inner function is g(x) and its domain is A = R
>
> Now f(g(x)) = f(x2)
>
> f(g(x)) = x2 + 2
>
> The domain of x2 + 2 is R (say B)
>
> Now the intersection of A and B is the domain of f(g(x))
>
> Domain of f(g(x)) = A∩B = R
>
> The range of f(g(x)) is the range of x2 + 2
>
> Now the range is [2, ∞)
## Properties of Composition of Function
There are various properties of the composition of a function:
- **Associativity Property:** For functions f, g, and h, the composition of these functions is associative, if and only if
> (f ∘ g) ∘ h = f ∘ (g ∘ h)
- **Identity Property:** For any function f, the identity function I(x) = x acts as the identity element for composition, meaning
> f ∘ I = I ∘ f = f
- **Inverse Property:** If a function f has an inverse function f⁻¹, then
> (f ∘ f⁻¹) = I = (f⁻¹∘ f)
Some other properties of the composition of functions are
- The composition of two or more one-to-one functions (injective) is always one-to-one.
- The composition of onto functions (surjective) is always onto.
- Also, the composition of two or more bijections (one-to-one and onto) is always a bijection.
- The inverse function of the composition of two [invertible functions](https://www.geeksforgeeks.org/dsa/invertible-functions/) has the property that (f ∘ g)−1 = g−1∘ f−1.
## Solved Examples
**Example 1:** For the given functions f(x) = ex and g(x) = x2 + 1. Find out the values of f(g(x)) and g(f(x)). 
**Solution:**
> The domain of both the functions are real numbers, so there is no need to modify the domain for the first function in any case. 
>
> For f ∘ g(x),
>
> f ∘ g(x) = f(g(x)) 
> ⇒ f ∘ g(x) = f(x2 + 1) 
> ⇒ f ∘ g(x) = 
>
>
$$
e^{x^2 + 1}
$$
>
> For g∘ f(x) 
>
> g ∘ f(x) = g(f(x)) 
> ⇒ g ∘ f(x) = g(ex) 
> ⇒ g ∘ f(x) = (ex)2 + 1
> ⇒ g ∘ f(x) = e2x + 1
**Example 2:** For the given functions f(x) = 2x and g(x) = x2 + 1. Find out the values of f(g(x)) and g(f(x)) at x = 2. 
**Solution:**
> The domain of both the functions are real numbers, so there is no need to modify the domain for the first function in any case. 
>
> f ∘ g(x) = f(g(x)) 
> ⇒ f ∘ g(x) = f(x2 + 1) 
> ⇒ f ∘ g(x) = 2(x2 + 1) 
>
> At x = 2, 
>
> ⇒ f(g(2)) = 2(4 + 1) 
> ⇒ f(g(2)) = 10
>
> g ∘ f(x) = g(f(x))
>
> ⇒ g ∘ f(x) = g(2x) 
> ⇒ g ∘ f(x) = (2x)2 + 1
> ⇒ g ∘ f(x) = 4x2 + 1
>
> At x = 2 
>
> g(f(2)) = 4(22) + 1 
> ⇒ g(f(2)) = 4(4) + 1 
> ⇒ g(f(2)) = 17
**Example 3:** For the given functions f(x) = sin(x) and g(x) = x2. Find out the domain and range for f ∘ g(x) and g ∘ f(x).
**Solution:**
> f(x) = sin x has domain as all real numbers and range [-1,1]. 
>
> While g(x) = x2 has domain all the real numbers and range R+. 
>
> f ∘ g(x) = f(g(x)) = f(x2) = sin(x2)
>
> Domain is all real numbers, the range is [-1,1]
>
> g ∘ f(x) = g(f(x) = g(sinx) = sin2x
>
> Domain is all real numbers, the range is between 0 and 1. 
**Example 4:** For the given functions f(x) = log(x) and g(x) = x + 1, find out the values of f(g(x)).
**Solution:**
> Domain of f(x) is all positive numbers i.e R+ and range is all real numbers. 
>
> Domain and range for g(x) is all real numbers. 
>
> f(g(x)) = f(x + 1) = log(x + 1)
>
> While doing this, the domain of f(x) must be kept in mind as it is logarithmic function it only takes positive values.
> x + 1 > 0 
> x > -1
>
> So, 
> Domain is (-1, ∞)
> Range is all real numbers (R)
### Practice Questions
**Question 1:** Let f(x) = 2x + 3 and g(x) = x2. Find
$$
(f \circ g)(x)
$$
.
**Question 2:** Let f(x) = \sqrt{x} and g(x) = x + 1. Find
$$
(g \circ f)(x)
$$
.
**Question 3:** Let f(x) = ln⁡(x) and g(x) = ex. Find
$$
(f \circ g)(x)
$$
.
**Question 4:** Let f(x) = sin⁡(x) and g(x) = x2. Find
$$
(f \circ g)(x)
$$
.
**Question 5:** Let f(x) = 1/x and g(x) = 3x + 2. Find
$$
(f \circ g)(x)
$$
.
**Question 6:** Let f(x) = x3 and g(x) = 2x − 1. Find
$$
(g \circ f)(x)
$$
.
**Question 7:** Let f(x) = |x| and g(x) = x − 4. Find
$$
(f \circ g)(x)
$$
.
**Question 8:** Let f(x) = cos⁡(x) and g(x) = 2x + π. Find
$$
(f \circ g)(x)
$$
.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/composition-of-functions/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Algebraic and Set-Theoretic Structures

> [!note] Related notes
>
> - [[Cartesian Product of Two Sets]]
> - [[Classes of Functions]]
> - [[Closure of Relations]]
> - [[Equivalence Relations]]
> - [[Groups]]
> - [[Hasse Diagrams]]
> - [[Introduction to Set Theory]]
> - [[Inverse Functions]]
> - [[Modular Addition]]
> - [[Multiplication Modulo]]
