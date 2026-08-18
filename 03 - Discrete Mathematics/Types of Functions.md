---
title: "Types of Functions"
subject: "Discrete Mathematics"
topic: "Algebraic and Set-Theoretic Structures"
source: "https://www.geeksforgeeks.org/maths/types-of-functions/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Algebraic and Set-Theoretic Structures"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/algebraic-and-set-theoretic-structures
---


> [!abstract] Types of Functions
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Algebraic and Set-Theoretic Structures`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/types-of-functions/)

---

# Types of Functions

Functions are defined as the relations that give a particular output for a particular input value. A function has a domain and a codomain. The range is the set of all actual outputs. f(x) usually denotes a function where x is the input of the function. In general, a function is written as **y = f(x).**
Let A and B be two nonempty sets. A function or mapping **f** from A to B is written as f: A → B is a rule by which each element a ∈ A is associated with a unique element **b ∈ B**.
![function](assets/function-3b99228a99.webp)
### Domain, Codomain, and Range of a Function
The elements of set X are called the domain of f and the elements of set Y are called the codomain of f. The images of the elements of set X are called the range of function, which is always a subset of Y. The image given below demonstrates the domain, codomain, and range of the function.
![domain](assets/domain-2f2ee512ad.webp)
The image demonstrates the domain, co-domain, and range of the function. Remember the element which is mapped only will be counted in the range as shown in the image. The domain, codomain, and range of the above function are:
> - Domain = {a, b, c}
> - Codomain = {1, 2, 3, 4, 5}
> - Range = {1, 2, 3}
### **Representation of Function**
There are three different forms of representation of functions. The function needs to be represented to showcase the domain values and the relationship between them. The function can be represented in algebraic form, graphical formats, and other roster form.
- **Algebraic Form:**  A function is usually denoted by the equation y = f(x) which connects the values on the y-axis.
- **Graphical Form**: Functions are easy to understand if they are represented in a graphical form with the help of coordinate axes, which helps us to understand the changing behavior of the function if the function is increasing or decreasing.
- **Roster Form:** Roster notation of a set is a simple mathematical representation of the set in mathematical form. In this notation, a function is represented with a set in mathematical form. In this notation, a function is represented with a set of points on its graph with the first and second element of domain and range respectively.
There are several types of functions in maths. Some of the important types are:
### 1. One to One (Injective) function
A function f: X → Y is said to be a [one-to-one function](https://www.geeksforgeeks.org/maths/one-to-one-functions/) if the images of distinct elements of X under f are distinct. Thus, f is one to one if **f(x**1**) = f(x**2**)**
- **Property:** A function **f**: A → B is one-to-one if f(x1) = f(x2) implies x1 = x2, i.e., an image of a distinct element of **A** under **f** mapping (function) is distinct.
- **Condition to be One-to-One function:** Every element of the domain has a single image with a codomain after mapping.
![one_to_one_function](assets/one_to_one_function-1d48c8926c.webp)
**Examples of One-to-One Functions**
- f(**x**) = **x** (Identity function)
- k(x) = 2x + 3 (Linear Polynomial)
- **g**(**x**) = **e**x** (Exponential function)
- **h**(**x**) = √**x**​ (Square root function, defined for **x** ≥ 0)
### 2. Many to One Function
If the function is not one to one function, then it should be [many-one function](https://www.geeksforgeeks.org/maths/many-one-functions/) means every element of the domain has more than one image at codomain after mapping.
- **Property:** One or more elements having the same image in the codomain
- **Condition to be Many to One function:** Two or more elements of the domain have the same image in the codomain.
![many_to_one_function](assets/many_to_one_function-df4475de5f.webp)
**Examples of Many to One Function**
Some of the most common examples of many-to-one functions are:
- **f**(**x**) = **x**2 ([Squared function](https://www.geeksforgeeks.org/maths/square-function/))
- **g**(**x**) = sin(**x**) ([Sine function](https://www.geeksforgeeks.org/maths/sine-function/))
- **h**(**x**) = cos(**x**) ([Cosine function](https://www.geeksforgeeks.org/maths/cosine-function/))
- **k**(**x**) = tan(**x**) ([Tangent function](https://www.geeksforgeeks.org/maths/tangent-function/))
- **m**(**x**) = ∣**x**∣ ([Absolute value function](https://www.geeksforgeeks.org/maths/absolute-value-function/))
### 3. Onto (Surjective) Function
A function f: X → Y is said to be an [onto function](https://www.geeksforgeeks.org/maths/onto-functions/) if every element of Y is an image of some element of set X under f, i.e. for every y ∈ Y there exists an element x in X such that f(x) = y.
**Properties:**
- The range of functions should be equal to the codomain.
- Every element of B is the image of some element of A.
**Condition to be onto function:** The range of function should be equal to the codomain.
![onto_function](assets/onto_function-c90a92de2d.webp)
As we see in the above two images, the range is equal to the codomain means that every element of the codomain is mapped with the element of the domain, as we know that elements that are mapped in the codomain are known as the range. So these are examples of the Onto function.
**Examples of Onto Functions**
Some of the most common examples of onto functions are:
- f(x) = x (Identity function)
- g(x) = ex (Exponential function)
- h(x) = sin(x) (Sine function within a limited domain, e.g., h: R→[−1,1])
- k(x) = cos(x) (Cosine function within a limited domain, e.g., k : [0,π]→[−1,1])
- m(x) = x3 (Cubic function)
### 4. Into Function
A function **f: X → Y** is said to be an into a function if there exists at least one element or more than one element in Y, which does not have any pre-images in X, which simply means that every element of the codomain is not mapped with elements of the domain.
**Properties:**
- The Range of function is the proper subset of B
- The Range of functions should not equal B, where B is the codomain.
![into_function](assets/into_function-a93377b66a.webp)
From the above image, we can see that every element of the codomain is not mapped with elements of the domain means the 10th element of the codomain is left unmapped. So this type of function is known as the Into function.
**Examples of Into Functions**
Some examples of functions you can consider are:
- **f(x) = sin(x) where f: R→[−1, 1] is not onto because it doesn't cover all values in the interval [−1, 1].**
- g(x) = x2 where g: R→R+ (positive real numbers) is not onto because it doesn't map to any negative real numbers.
- h(x) = ex where h: R→(0,∞) is not onto because it doesn't map to zero.
### Related Article:
> - [Domain and Range of Trigonometric Functions](https://www.geeksforgeeks.org/maths/domain-and-range-of-trigonometric-functions/)
> - [Range of a Function](https://www.geeksforgeeks.org/maths/range-of-a-function/)
> - [Relations and Functions](https://www.geeksforgeeks.org/maths/relations-and-functions/)
> - [Composition of Functions](https://www.geeksforgeeks.org/maths/composition-of-functions/)
> - [Hyperbolic Function](https://www.geeksforgeeks.org/engineering-mathematics/hyperbolic-function/)
## **Solved Examples of Types of Function**
**Example 1:** Check whether the function f(x) = 2x + 3, is one-to-one or not if Domain = {1, 2, 1/2} and Co-domain = {5, 7, 4}.
**Solution:**
> Putting 1, 2, 1/2 in place of x in f(x) = 2x + 3, we get
>
> f(1) = 5,
> f(2) = 7,
> f(1/2) = 4
>
> As, for every value of x we get a unique f(x) thus, we can conclude that our function f(x) is One to One.
**Example 2:** Check whether the function is one-to-one or not: f(x) = 3x - 2.
**Solution:**
> To check whether a function is one to one or not, we have to check that elements of the domain have only a single pre-image in codomain or not. For checking, we can write the function as,
>
> f(x1) = f(x2) 
> 3x1 - 2 = 3x2 - 2 
> 3x1 = 3x2 
> x1 = x2  
>
> Since both x1 =  x2 which means that elements of the domain having a single pre-image in its codomain. Hence the function f(x) = 3x - 2 is one to one function.
**Example 3:** Check whether the function is one-to-one or not: f(x) = x2 + 3.
**Solution:**
> To check whether the function is One to One or not, we will follow the same procedure. Now let's check, we can write the function as,
>
> f(x1) = f(x2) 
> (x1)2 + 3 = (x2)2 + 3
>  (x1)2 = (x2)2  
>
> Since (x1)2 = (x2)2 is not always true.
>
> Hence the function **f**(x) = x2 + 3 is not one to one function
**Example 5:** f(x) = x2, check whether the function is Many to One or not.
**Solution:**
> Domain = {1, -1, 2, -2}, let's put the elements of the domain in the function
>
> f(1) = 12 = 1
> f(-1) = (-1)2 = 1
> f(2) = (2)2 = 4
> f(-2) = (-2)2 = 4
>
> Thus, we can see that more than one element of the domain have similar image after mapping. So this is Many to One function.
**Example 4:** If N: → N, f(x) = 2x + 1 then check whether the function is injective or not.
**Solution:**
> In question N → N, where N belongs to Natural Number, which means that the domain and codomain of the function is a natural number. For checking whether the function is injective or not, we can write the functions as,
>
> Let, f(x1) = f(x2)
> 2x1 + 1= 2x2 + 1
> 2x1 = 2x2 0
> x1 = x2
>
> Since x1 = x2, means all elements of the domain are mapped with a single element of the codomain. Hence function f(x) = 2x + 1 is Injective (One to One).
**Example 6:** If f(x) = 2x + 1 is defined on R:→ R. Then check whether the following function is Onto or not.
**Solution:**
> For checking the function is Onto or not, Let's first put the function f(x) equal to y
>
> f(x) = y
> y = 2x + 1
> y - 1 = 2x
> x = (y - 1) / 2
>
> Now put the value of x in the function f(x), we get,
>
> f((y - 1) / 2) = 2 × [(y - 1) / 2] +1
>
> Taking LCM 2, we get
>
> = [2(y - 1) + 2] / 2
> = (2y - 2 + 2) / 2
> = y
>
> Since we get back y after putting the value of x in the function. Hence the given function f(x) = 2x + 1 is Onto function.
**Example 7:** If f: N → N is defined by f(x) = 3x + 1. Then prove that function f(x) is Surjective.
**Solution:**
> To prove that the function is Surjective or not, firstly we put the function equal to y. Then find out the value of x and then put that value in the function. So let's start solving it.
>
> Let f(x) = y
> 3x + 1 = y
> 3x = y - 1
> x = (y - 1) / 3
>
> Now put the value of x in the function f(x), we get
>
> f((y - 1) / 3) = {3 (y - 1) / 3} + 1
> = y - 1 + 1
> = y
>
> Since we get back y after putting the value of x in the function. Hence the given function f(x) = (3x + 1) is Onto function.
**Example 9:** A = {1, 2, 3, 4}, B = {a, b, c, d} then the function is defined as f= {(1, a), (2, b), (3, c), (4, d)}. Check whether the function is One to One Onto or not.
**Solution:** 
> To check whether the function is One to One Onto or not. We have to check for both one by one. 
>
> Let's check for One to One:
>
> As we know the condition for One to One that all the elements of the domain are having a single image in the codomain. As we see in the mapping that all the elements of set A are mapped with set B and each having a single image after mapping. 
>
> So the function is One to One.
>
> Now let's check for Onto:
>
> As we know the condition for the function to be Onto is that, Range = Codomain means all the elements of codomain are mapped with domain elements, in this case, codomain will equal to the domain. As we see in the mapping that the condition of the function to be Onto is satisfied. 
>
> So the function is Onto. 
>
> Since we had proved that the function is both One to One and Onto. 
>
> Hence function is One to One Onto (Bijective).
**Example 10:** A = {1, 2, 3, 4}, B = {a, b, c, d}. The function is defined as f= {(1, a), (2, b), (3, c), (4, c)}. Check whether the function is Many to One Into or not.
**Solution:**
> To check the function is Many to One Into or not. We have to check for both one by one.
>
> Let's first check for Many to One function:
>
> As we know the condition for Many to One function is that more than one element of domain should have more same image in codomain. From the above mapping we can see that the elements of A {3, 4 } are having same image in B { c }, so the function is Many to One.
>
> Now let's check for Into function:
>
> As we know the condition for Into function is that the Range of function should be the subset of codomain and also not equal to codomain. Let's check both the conditions are satisfied or not.
>
> - Range of function = {a, b, c}
> - Codomain of function = {a, b, c, d}
>
> Range of function ≠ Codomain of function
>
> As we check that the range of function is not equal to codomain of the function. Hence we can say that the function is Into function. As we prove that the function is Many to One and Into. 
>
> Hence the function is Many to One Into.
**Example 8:** If A = R - {3} and B = R - {1}. Consider the function f: A → B defined by f(x) = (x - 2)/(x - 3), for all x ∈ A. Then show that the function f is bijective.
> **Solution:** To show the function is bijective we have to prove the given function both One to One and Onto.
>
> Let's first check for One to One:
>
> Let x1, x2 ∈  A such that f(x1) = f(x2) 
>
> Then, (x1 - 2) / (x1 - 3) = (x2 - 2) / (x2 - 3)
> (x1 - 2) ( x2 - 3) = (x2 - 2) (x1 - 3)
> x1 . x2 - 3x1 - 2x1 + 6 = x1 . x2 - 3x2 -2x1 + 6
> -3x1 - 2x2 = -3x2 - 2x1
> -3( x1 - x2) + 2( x1 - x2) = 0
> -( x1 - x2) = 0
> x1 - x2  = 0 
> ⇒ x1 = x2
> Thus, f(x1) = f(x2) ⇒ x1 = x2, ∀ x1, x2  ∈ A
> So, the function is a One to One
>
> Now let us check for Onto:
>
> Let y ∈ B = R - {1} be any arbitrary element.
>
> Then, f(x) = y
>
> ⇒ (x - 2) / (x - 3) = y
> ⇒ x - 2 = xy - 3y
> ⇒ x - xy = 2 - 3y
> ⇒ x(1 - y) = 2 - 3y
> ⇒ x =  (2 - 3y) / (1 - y) or x = (3y - 2) / (y - 1)
> Now put the value of x in the function f(x) 
>
> f((3y - 2) / (y - 1)) = { (3y - 2) / (y - 1) } - 2 / { (3y - 2) / (y - 1) - 3 }
> = (3y - 2 - 2y + 2) / (3y - 2 - 3y + 3)
> = y
>
> Hence f(x) is Onto function. Since we proved both One to One and Onto this implies that the function is Bijective.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/types-of-functions/)

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
> - [[Inverse Functions]]
> - [[Modular Addition]]
