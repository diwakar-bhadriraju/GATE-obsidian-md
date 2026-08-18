---
title: "Common Sub Expression Elimination"
subject: "Compiler Design"
topic: "Local Optimization"
source: "https://www.geeksforgeeks.org/compiler-design/common-sub-expression-elimination/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Local Optimization"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/local-optimization
---


> [!abstract] Common Sub Expression Elimination
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Local Optimization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/common-sub-expression-elimination/)

---

# Common Sub Expression Elimination

Common subexpression elimination (CSE) is a technique used to optimize the codes. It works by computing the value of the subexpression and assigning the value to a variable. Now, the initial common subexpression is replaced by that variable. It helps in reducing the number of repeated computations. CSE focuses on identifying and eliminating redundant calculations within a program, leading to faster and more efficient code execution.
## How Common Subexpression Elimination Works?
CSE operates on the principle of recognizing recurring subexpressions in code. A subexpression is a portion of code that computes a value and can be a part of multiple larger expressions. Instead of recomputing the same subexpression every time it appears in the code, CSE calculates it once and stores the result in a temporary [variable](https://www.geeksforgeeks.org/cpp/cpp-variables/). This variable is then used wherever the subexpression occurs in the code, effectively replacing the repetitive calculations with a single reference.
## Benefits of Common Subexpression Elimination
- **Improved Performance**: The primary advantage of CSE is enhanced performance. By reducing redundant computations, CSE significantly decreases the execution time of a program. This optimization is particularly beneficial in computationally intensive applications.
- **Simplified Code**: CSE simplifies code by removing unnecessary redundancy. Cleaner code is easier to read, maintain, and debug, leading to fewer programming errors and improved software quality.
- **Reduced Resource Usage**: Reducing redundant calculations conserves computational resources such as [CPU](https://www.geeksforgeeks.org/computer-science-fundamentals/central-processing-unit-cpu/) time and memory. This can be especially advantageous in resource-constrained environments.
## Example 1
````cpp
// before CSE
int main()
{
    a = b + c * 2; //(c*2) is a common subexpression
    x = y + c * 2;
    ans = a + x;
}
// after CSE
int main()
{
    int temp = c * 2; //(c*2) is assigned to a variable temp
    a = b + temp; // thus saving the time of computing (c*2)
                  // again
    x = y + temp;
    ans = a + x;
}
````
## Example 2
````cpp
// before CSE
int main()
{
    a = b * c;
    b = x + y + 2; //(x+y) is a common subexpression
    c = x + y + 3;
}
// after CSE
int main()
{
    int temp = x + y; //(x+y) is assigned to a variable temp
    a = b * c;
    b = temp
        + 2; // thus saving the time of computing x+y again
    c = temp + 3;
}
````
## Conclusion
Common subexpression elimination (CSE) is a powerful code optimization technique that reduces redundant calculations, leading to improved program performance, cleaner code, and resource savings. While the example here is simple, CSE becomes even more critical in complex [algorithms](https://www.geeksforgeeks.org/dsa/dsa-tutorial-learn-data-structures-and-algorithms/) and computations. As a best practice, developers should be aware of CSE and use it where applicable to create faster and more efficient software.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/common-sub-expression-elimination/)

## GATE CS

- Subject: Compiler Design
- Topic: Local Optimization

> [!note] Related notes
>
> - [[Code Motion]]
> - [[Code Optimization]]
> - [[Constant Folding]]
> - [[Constant Propagation]]
> - [[Copy Propagation]]
> - [[Dead Code Elimination]]
> - [[Frequency Reduction]]
> - [[Function Inlining]]
> - [[Induction Variable and Strength Reduction]]
> - [[Loop Jamming]]
