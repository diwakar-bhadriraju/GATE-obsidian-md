---
title: "Constant Folding"
subject: "Compiler Design"
topic: "Local Optimization"
source: "https://www.geeksforgeeks.org/compiler-design/constant-folding/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Local Optimization"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/local-optimization
---


> [!abstract] Constant Folding
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Local Optimization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/constant-folding/)

---

# Constant Folding

As we all know humans understand only programming languages like [C](https://www.geeksforgeeks.org/c/c-programming-language/), C++, [Python](https://www.geeksforgeeks.org/python/python-programming-language-tutorial/), [Java,](https://www.geeksforgeeks.org/java/java/) etc. whereas a computer can only understand bytecodes or machine languages. So compiler acts as a converter. Its aim is to convert the [high-level language](https://www.geeksforgeeks.org/computer-science-fundamentals/difference-between-high-level-and-low-level-languages/) to [machine-level language.](https://www.geeksforgeeks.org/computer-organization-architecture/difference-between-machine-language-and-assembly-language/) However, during conversion, some optimization processes are followed to make the code more efficient thereby increasing the execution speed as well. One such [optimization](https://www.geeksforgeeks.org/compiler-design/optimization-of-basic-blocks/) technique is Constant Folding.
## Constant Folding
Constant folding is an optimization technique in which the expressions are calculated beforehand to save execution time. The expressions which generate a constant value are evaluated and during the compilation time, the expressions are calculated and stored in the designated variables. This method also reduces the code sizes as well.
## How does Constant Folding work?
The constant Folding Technique is used during the compilation time. Let us elaborate on it with the help of an example
Suppose we have written some code in C++. The code is as follows
````cpp
#include <iostream>
using namespace std;
int main()
{
    float x=5+2.3*2;// x is variable of type float
    int y = x + 2.3;//y is integer type
    cout<<y;//displaying the value
    return 0;
}
````
In the above code, we have assigned an expression to x. The value of the expression is added to 2.3 and we display the value of y. Since the expression always generates a constant value, therefore during the [compile time](https://www.geeksforgeeks.org/c/difference-between-compile-time-errors-and-runtime-errors/) the compiler calculates the value of the expression. Here the value of x is 9.6. Therefore whenever the code gets executed the compiler directly replaces the value of x with 9.6 and performs further executions.
**Example:**
Another example is as follows
````cpp
#include <iostream>
using namespace std;
int main()
{
    // performing division
    int a = 4;
    int b = 5 / a;
    cout << b;
    return 0;
}
````
In this case the value of a is 4. The value of b is found by dividing 5 by 4. So during the compile time the compiler performs one time substitution and directly replaces the value of a in the division expression with 4. So whenever the code gets executed the compiler directly performs the division 5/4.
## Advantages of Constant Folding
There are many benefits of Constant Folding. They are as follows:
- Constant Folding is used to decrease the execution time.
- It optimizes the code.
- This technique also reduces Lines of Code.
- Constant Folding also helps in efficient memory management.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/constant-folding/)

## GATE CS

- Subject: Compiler Design
- Topic: Local Optimization

> [!note] Related notes
>
> - [[Code Motion]]
> - [[Code Optimization]]
> - [[Common Sub Expression Elimination]]
> - [[Constant Propagation]]
> - [[Copy Propagation]]
> - [[Dead Code Elimination]]
> - [[Frequency Reduction]]
> - [[Function Inlining]]
> - [[Induction Variable and Strength Reduction]]
> - [[Loop Jamming]]
