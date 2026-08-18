---
title: "Copy Propagation"
subject: "Compiler Design"
topic: "Local Optimization"
source: "https://www.geeksforgeeks.org/compiler-design/copy-propagation/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Local Optimization"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/local-optimization
---


> [!abstract] Copy Propagation
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Local Optimization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/copy-propagation/)

---

# Copy Propagation

Copy propagation is defined as an optimization technique used in compiler design. Copy propagation is used to replace the occurrence of target variables that are the direct assignments with their values. Copy propagation is related to the approach of a common subexpression. In common subexpression, the expression values are not changed since the first expression is computed.
The goal of copy propagation is to reduce the unnecessary expression variables. Which in turn results in faster execution and less memory utilization. Copy propagation can be used or applied only when the exact value of the variable is known at the time of compilation and the value can be inferred from the context of the program.
## Types of Copy Propagation
### 1. Local Copy Propagation
Local copy propagation is a type of propagation that is limited or restricted within a specific block of code. The [optimization](https://www.geeksforgeeks.org/compiler-design/optimization-of-basic-blocks/) of code is limited to the current working block in local copy propagation and cannot be extended beyond its boundaries.
### Example:
### Before Local Copy Propagation
````cpp
// Example for Local Copy Propagation
// Before applying Copy Propagation
#include <iostream>
using namespace std;
int main()
{
    int a = 1 + 2;
    int b = a;
    int ans = b + 6;
    cout << "Before copy propagation, ans= " << ans;
    return 0;
}
````
#### Output:
```
Before copy propagation, ans= 9
```
### After Local Copy Propagation
````cpp
// Example for Local Copy Propagation
// After applying Copy Propagation
#include <iostream>
using namespace std;
int main()
{
    int a = 1 + 2;
    int ans = a + 6;
    cout << "After copy propagation, ans= " << ans;
    return 0;
}
````
#### Output:
```
After copy propagation, ans= 9
```
### 2. Global Copy Propagation
Global copy propagation is a type of propagation that is not limited to a specific block of code. It can access and use the values that belong to other blocks than the current working block. Global copy propagation has an advantage as compared to local copy propagation in that it eliminates redundant computations on a large scale.
### Example:
### Before Global Copy Propagation
````cpp
// Example of Global copy propagation
// Before Global copy propagation
#include <iostream>
using namespace std;
int globalVariable = 10;
int h;
int function1() { int h = globalVariable + 2; }
int function2()
{
    int a = globalVariable;
    int b = a + 15;
    int ans = b;
    return ans;
}
int main()
{
    int result = function2();
    cout << "Result before Global copy propagation: "
         << result;
    return 0;
}
````
#### Output:
```
Result before Global copy propagation: 25
```
### After Global Copy Propagation
````cpp
// Example of Global copy propagation
// After Global copy propagation
#include <iostream>
using namespace std;
int globalVariable = 10;
int h;
int function1() { int h = globalVariable + 2; }
int function2()
{
    int ans = globalVariable + 15;
    return ans;
}
int main()
{
    int result = function2();
    cout << "Result after Global copy propagation: "
         << result;
    return 0;
}
````
#### Output:
```
The result after Global copy propagation: 25
```
### Advantages of Copy Propagation
- Copy propagation reduces the required computation time by eliminating the redundant and unnecessary variable assignments in the expressions.
- Copy propagation ensures memory optimization. Only the required memory assignments and variables require memory, irrelevant memory expressions are being eliminated.
- Copy propagation simplifies the available code by eliminating the expressions that are not required making code easily understandable.
## Conclusion
Copy Propagation is an optimization technique used in compiler design. It replaces the irrelevant variable assignments with the previously calculated values that are not changed in the future. this approach improves memory utilization, and efficiency of the code and therefore requires less time for overall computation.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/copy-propagation/)

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
> - [[Dead Code Elimination]]
> - [[Frequency Reduction]]
> - [[Function Inlining]]
> - [[Induction Variable and Strength Reduction]]
> - [[Loop Jamming]]
