---
title: "Constant Propagation in Compiler Design"
subject: "Compiler Design"
topic: "Local Optimization"
source: "https://www.geeksforgeeks.org/compiler-design/constant-propagation-in-complier-design/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Local Optimization"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/local-optimization
---


> [!abstract] Constant Propagation in Compiler Design
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Local Optimization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/constant-propagation-in-complier-design/)

---

# Constant Propagation in Compiler Design

Local Code Optimization refers to the process of optimizing code within a basic block or a small section of the program, without considering the entire program structure. This technique is employed by a compiler to improve the performance of the generated code by reducing execution time, memory usage, and other resources, all within a single basic block or scope. Constant Propagation is one of the local code optimization technique  in Compiler Design. It can be defined as the process of replacing the constant value of variables in the expression.
## Constant Propagation
Constant propagation is executed using reaching definition analysis results in compilers, which means that if reaching definition of all variables have same assignment which assigns a same constant to the variable, then the variable has a constant value and can be substituted with the constant. 
In simpler words, we can say that if  some value is assigned a known constant, than we can simply replace the that value by constant. Constants assigned to a variable can be propagated through the flow graph and can be replaced when the variable is used. 
### Examples
**Eg. Suppose we are using pi variable and assign it value of 22/7 :**
> area=pi \* r \* r
> pi = 22/7 = 3.14
In the above code the compiler has to first perform division operation, which is an expensive operation and then assign the computed result 3.14 to the variable pi.
Now if we have to use this constant value of pi, then the compiler again has to look up for the value and again perform division operation and then assign it to pi and then use it. This is not a good idea when we can directly assign the value 3.14 to pi variable, thus reducing the time needed for code to run.
> area = 3.14 \* r \* r
Also, Constant propagation reduces the number of cases where values are directly copied from one location or variable to another, in order to simply allocate their value to another variable.
**Eg. Consider the following pseudocode :**  
> a = 30
> b = 20 - **a** /2
> c = b \* ( 30 / **a** + 2 ) - **a**
### Steps Involved in it
We can see that in the first expression value of a have assigned a constant value that is 30.
Now, when the compiler comes to execute the second expression it encounters a, so it goes up to the first expression to look for the value of a and then assign the value of 30 to a again, and then it executes the second expression.
Now it comes to the third expression and encounters b and a again, and then it needs to evaluate the first  and second expression again in order to compute the value of c.
Thus, a needs to be propagated 3 times This procedure is very time consuming.
We can instead , rewrite the same code as :
> a = **30**
> b = 20 - **30**/2
> c = b \* ( 30 / **30** + 2) - **30**
This updated code is faster as compared to the previous code as the compiler does not need to again and again go back to the previous expressions looking up and copying the value of a variable in order to compute the current expressions. This saves a lot of time and thus, reducing time complexity and perform operations more efficiently.
Eg. Consider the following pseudocode :
> x = 12.4
>  y = x/2.3
>  Replace x/2.3 as 12.4/2.3
Note : This constant propagation technique behavior depends on compiler like few compilers perform constant propagation operations within the [basic blocks](https://www.geeksforgeeks.org/compiler-design/basic-blocks-in-compiler-design/) while a few compilers perform constant propagation operations  in more complex control flow. 
> For more information regarding more techniques of Local Code Optimization you can refer to the link [Local Code Optimization](https://www.geeksforgeeks.org/compiler-design/code-optimization-in-compiler-design/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/constant-propagation-in-complier-design/)

## GATE CS

- Subject: Compiler Design
- Topic: Local Optimization

> [!note] Related notes
>
> - [[Code Motion]]
> - [[Code Optimization]]
> - [[Common Sub Expression Elimination]]
> - [[Constant Folding]]
> - [[Copy Propagation]]
> - [[Dead Code Elimination]]
> - [[Frequency Reduction]]
> - [[Function Inlining]]
> - [[Induction Variable and Strength Reduction]]
> - [[Loop Jamming]]
