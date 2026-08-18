---
title: "Classes of Functions"
subject: "Discrete Mathematics"
topic: "Algebraic and Set-Theoretic Structures"
source: "https://www.geeksforgeeks.org/maths/functions/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Algebraic and Set-Theoretic Structures"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/algebraic-and-set-theoretic-structures
---


> [!abstract] Classes of Functions
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Algebraic and Set-Theoretic Structures`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/functions/)

---

# Classes of Functions

In mathematics, functions help us understand how one quantity depends on another. But not all functions behave the same way when connecting inputs to outputs. Some functions match each input to a unique output, some make sure every output is used, and some do both!
To study these differences, we classify functions into three types: **injective (one-one)**, **surjective (onto)**, and **bijective (both one-one and onto)**.
These types help us understand how functions work and are especially important in higher-level math like algebra, calculus, and computer science.
### **1. Injective Functions (One-to-One)**
A function is called one-to-one if for all elements a and b in A, if f(a) = f(b), then it must be the case that a = b. It never maps distinct elements of its **domain** to the same element of its **co-domain**. ![fun_1](assets/OneToOne-aed091f6f6.png)
**Properties of Injective Functions:**
- An [injective function](https://www.geeksforgeeks.org/maths/injective-functions/) does not map two different elements in the domain to the same element in the codomain.
- If a function is injective, it has an inverse function on its image.
### **2. Surjective Functions (Onto)**
If every element b in B has a corresponding element a in A such that f(a) = b. It is not required that a is unique; The function f may map one or more elements of A to the same element of B.
![fun_2](assets/OnTo-2412c40c52.png)
**Properties of Surjective Functions**
- A surjective function covers the entire codomain.
- If a function is surjective, it can have an inverse function if restricted to its range.
### 3. **Bijective Functions (One-to-One Correspondence)**
A function is a Bijective function if it is both one to one and onto function.
![8](assets/8-3-d628641ab9.png)
**Properties of Bijective Functions**
- A bijective function has both an inverse function and a unique mapping for each element in the domain and codomain.
- If a function is bijective, it establishes a one-to-one correspondence between the sets A and B.
## **Composition of Functions**
Let g be a function from B to C and f be a function from A to B, the composition of f and g, which is denoted as fog(a) = f(g(a)).
### **Properties of Function Composition**
- fog ≠ gof
- f-1 of = f-1 (f(a)) = f-1(b) = a.
- fof-1 = f(f-1 (b)) = f(a) = b.
- If f and g both are [one to one function](https://www.geeksforgeeks.org/maths/one-to-one-functions/), then fog is also one to one.
- If f and g both are onto function, then fog is also onto.
- If f and fog both are one to one function, then g is also one to one.
- If f and fog are onto, then it is not necessary that g is also onto.
- (fog)-1 = g-1 o f-1
## Applications in Engineering
Understanding injective, surjective, and bijective functions is crucial in various engineering disciplines:
- **Data Encryption:** In computer engineering, bijective functions are used in encryption algorithms to ensure that each plaintext maps to a unique ciphertext and vice versa, enabling secure communication.
- **Signal Processing:** In signal processing, injective functions help in ensuring that distinct signals remain distinct after transformation, which is essential for accurate signal reconstruction.
- **Network Design:** In network design and analysis, surjective functions are used to ensure that resources are optimally utilized, and every demand is met by at least one resource.
- **Control Systems**: In control systems engineering, bijective functions are important for designing controllers that map system states to control actions uniquely and efficiently.
## Solved Examples - Classes of Functions
**Problem 1:** Determine if the function f(x) = 2x+1 is injective.
**Solution**:
> To check if f is injective, assume f(x1) = f(x2)): 2x1+1 = 2x2+1
>
> Subtract 1 from both sides: 2x1 = 2x2
>
> Divide by 2: x1 = x2
>
> Sincex1 = x2​ follows from f(x1) = f(x2), f is injective.
**Problem 2:** Determine if the function f(x) = x2 for x∈R is surjective when the codomain is R.
**Solution**:
> For f(x) = x2 to be surjective, every y∈R must have a corresponding x∈R such that x2 = y. However, x2 ≥ 0 for all real x, so f(x) = x2 cannot produce negative values. Therefore, f is not surjective when the codomain is R.
>
> If the codomain were [0,∞), then f would be surjective.
**Problem 3: Determine if the function f(x) = 3x − 2 is bijective if the domain and codomain are both R.**
**Solution**:
> - **Injective Check**: As shown in Example Problem 1, f(x) = 3x−2 is injective.
> - **Surjective Check**: For any y∈R, solve y = 3x − 2 for x: x = y+2/3. ​Since x is always a real number for any real y, f is surjective.
>
> Since f is both injective and surjective, it is bijective.
### Related Articles
> - [Bijective Function](https://www.geeksforgeeks.org/maths/bijective-function/)
> - [Functions in Discrete Mathematics](https://www.geeksforgeeks.org/engineering-mathematics/functions-in-discrete-mathematics/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/functions/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Algebraic and Set-Theoretic Structures

> [!note] Related notes
>
> - [[Cartesian Product of Two Sets]]
> - [[Closure of Relations]]
> - [[Composition of Functions]]
> - [[Equivalence Relations]]
> - [[Groups]]
> - [[Hasse Diagrams]]
> - [[Introduction to Set Theory]]
> - [[Inverse Functions]]
> - [[Modular Addition]]
> - [[Multiplication Modulo]]
