---
title: "Function Inlining"
subject: "Compiler Design"
topic: "Local Optimization"
source: "https://www.geeksforgeeks.org/compiler-design/function-inlining/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Local Optimization"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/local-optimization
---


> [!abstract] Function Inlining
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Local Optimization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/function-inlining/)

---

# Function Inlining

Prerequisite: [Phases of Compiler](https://www.geeksforgeeks.org/compiler-design/phases-of-a-compiler/)
The fifth phase of a compiler is code optimization. This phase applies various optimization techniques to the intermediate code to improve the performance of the generated machine code. Function inlining is used to improve the performance of the code. The function call is replaced by the code of the function being called. Function inlining should be applied to small functions only. With the help of function inlining, we can reduce the execution time. It reduces the function call overhead and saves the time of pushing the function into and out of the stack.
![32.png](assets/32-0cc9117ead.png)
Before function inlining
![32.png](assets/32-02281c9645.png)
After function inlining
Function inlining helps in enabling more optimizations. With the help of inlined code, code optimizations like copy propagation and constant folding can be applied easily. Thus reducing the execution time.
````cpp
int multiply(int a,int b)  //called function
{
  return a*b;
}
int func(int x,int y)      //calling function
{
  return multiply(x,y);   //function call
}
//after function inlining
int func(int x,int y)
{
  return x*y;           //function call replaced with called function
}
````
In the above example, we are performing multiplication in function func() by passing the variables to multiply(). A function call introduces overhead such as parameter passing, stack frame creation, and return operations. Inlining removes this overhead, which can improve performance when small functions are called frequently.
To simplify this, we will apply function inlining and will replace the function call with the called function's body. This helps in saving the extra computation time and performs the same task of multipling the same numbers.
### Advantages
- Reduces function call overhead
- Improves execution speed for small functions
- Enables other optimizations (constant folding, propagation)
- Improves instruction locality
### Disadvantages
- Increased code size
- Increased compilation time
- Reduced maintainability
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/function-inlining/)

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
> - [[Induction Variable and Strength Reduction]]
> - [[Loop Jamming]]
