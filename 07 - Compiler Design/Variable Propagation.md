---
title: "What is Variable Propagation?"
subject: "Compiler Design"
topic: "Local Optimization"
source: "https://www.geeksforgeeks.org/compiler-design/what-is-variable-propagation/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Local Optimization"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/local-optimization
---


> [!abstract] What is Variable Propagation?
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Local Optimization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/what-is-variable-propagation/)

---

# What is Variable Propagation?

In the compilation process, after generating the Intermediate code, the Compiler does code optimization to improve the performance of the code. So, before actually modifying the code for optimization, the compiler analyses the flow of variables in the code, that is compiler analyzes the code and variables, and based upon this analysis, the optimizer component of the compiler does code optimization. This analysis of the flow of variables throughout the code by the compiler is called variable propagation.
## What is a Compiler?
A [Compiler](https://www.geeksforgeeks.org/compiler-design/introduction-to-compilers/) is a software or a program that converts the human-readable code into something that a machine can understand. For example, the code that we write either in [Java](https://www.geeksforgeeks.org/java/introduction-to-java/) [C++,](https://www.geeksforgeeks.org/cpp/c-plus-plus/) or [C](https://www.geeksforgeeks.org/c/getting-started-with-c/) language gets converted into machine-understandable binary code or assembly language by compilers.
**Variable:** A [Variable](https://www.geeksforgeeks.org/cpp/cpp-variables/) is something like a named container for our data in the memory, that we can access and modify this data using the variable name.
**Propagation:** Propagation in simpler terms refers to the multiplication of something or the increase or spreading of something.
**Code Optimization:** [Code optimizing](https://www.geeksforgeeks.org/compiler-design/code-optimization-in-compiler-design/) refers to the process of modifying the code without changing the original functionality of the program so that it runs efficiently in terms of memory and speed. Optimized code generally takes less space time or both to finish the program.
**Constant Propagation:** Replacing the variables in the code with the known constants.
## **Variable Propagation**
Variable propagation is one of the internal processes of analyzing the flow of variables throughout the code enabling the optimizer to do the optimizations. In broader terms, It is an analysis of the flow of variables throughout the code about how and what variables are assigned, modified and what variables are used what variables are declared but not used in computations, what code is redundant, and which variables can be replaced, so that the optimizer can perform optimizations like [constant propagation](https://www.geeksforgeeks.org/compiler-design/constant-propagation-in-complier-design/#:~:text=It%20can%20be%20defined%20as,the%20that%20value%20by%20constant.), [constant folding](https://www.geeksforgeeks.org/compiler-design/constant-folding/#:~:text=Constant%20folding%20is%20an%20optimization,stored%20in%20the%20designated%20variables.) etc., in the code. Variable propagation is done before actually modifying the code by the optimizer.
## **Step-by-Step Process**
- The compiler receives the intermediate code generated.
- It analyzes the variables flow throughout the code like where they are used, where they are modified, and whether they are modified or not and whether they are used in the code anywhere or not etc.
- Now, optimizer part of the compiler will look at this analysis.
- It does optimizations on the code based on the analysis like [eliminating dead code](https://www.geeksforgeeks.org/compiler-design/dead-code-elimination/), replacing variables with constants etc.
![Compilation process and Code optimization Steps.](assets/compiler_process--1--a1c194e99d.jpg)
Compilation process and Code optimization Steps.
## **Example**
### **Before Variable Propagation**
````c
#include <stdio.h>
int main()
{
    int x = 3;
    int y = x;
    int z = x + y + 2;
    printf("%d", z);
    return 0;
}
````
**Output**
```
8
```
### **Explanation of Above Code after Variable Propagation**
- Now analysis has been done on the flow of variables.(Variable propagation).
- Here, we declared three variables x, y, z .
- It checks that y is equal to x, so it replaces y with the value of x i.e, 3. (Constant propagation)
````c
int z=x+y+2;
````
- Again based on the analysis, it also knows that x remained constant through out the program, so in the above line it replaces x and y values with 3. (constant propagation).
````c
int z = 3 + 3 + 2; // after constant propagation.
````
- Now, again in the above line will result in a constant expression which is int z= 3+3+2; as this is a constant, now optimizer will optimize the code further , evaluates the values and assigns to 'z'. (Constant folding).
- The resulting code after code optimization is
### **After Variable Propagation and Code Optimization**
````c
#include <stdio.h>
int main()
{
    int x = 2;
    int y = 3;
    int z = 8;
    printf("%d", z);
}
````
**Output**
```
8
```
So, Before variable propagation, the code is not optimized and after variable propagation, the compiler analyses the the variable flow in the code and based on the analysis, the optimizer component of the compiler will try to optimize the code by using techniques like constant folding, constant propagation etc.. and results in the above code.
## Conclusion
Variable propagation is an important step that occurs prior to code optimization and refers to the process of analyzing the flow of code and variables in the program and this step helps the optimizer component of the compiler to properly optimize the code using techniques like dead code elimination, constant folding etc.
### Q.2: Difference between Constant Propagation and Variable Propagation?
**Answer**:
> Constant propagation is a optimization technique where we replace the variables with the known constants, where as in variable propagation, we just analyze the code and this analyzation helps the optimizer to know which code to replace, which code to eliminate etc..
### Q.3: When does variable propagation step takes place?
**Answer**:
> Right after the Generation of Intermediate code, The analysis of Intermediate code generation takes place and after this, code optimization takes place.
### Q.4: Will variable propagation step modifies the code?
**Answer**:
> No, the variable propagation directly does not modify the code any, but it will help the optimizer to modify the code.
### Q.5: Will modifying the code by optimization changes the functionality?
**Answer**:
> No, The optimization takes place such that it modifies the code and improves the efficiency of code in terms of memory and speed without changing the core functionality of the code.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/what-is-variable-propagation/)

## GATE CS

- Subject: Compiler Design
- Topic: Local Optimization

> [!note] Related notes
>
> - [[Code Motion]]
> - [[Code Optimization]]
> - [[Common Sub Expression Elimination]]
> - [[Constant Folding]]
> - [[Constant Propagation]]
> - [[Copy Propagation]]
> - [[Dead Code Elimination]]
> - [[Frequency Reduction]]
> - [[Function Inlining]]
> - [[Induction Variable and Strength Reduction]]
