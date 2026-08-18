---
title: "Frequency Reduction in Code Optimization"
subject: "Compiler Design"
topic: "Local Optimization"
source: "https://www.geeksforgeeks.org/compiler-design/frequency-reduction-in-code-optimization/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Local Optimization"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/local-optimization
---


> [!abstract] Frequency Reduction in Code Optimization
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Local Optimization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/frequency-reduction-in-code-optimization/)

---

# Frequency Reduction in Code Optimization

**Prerequisite -** [Compiler Design | Code Optimization](https://www.geeksforgeeks.org/compiler-design/code-optimization-in-compiler-design/)
**Frequency reduction** is a type in [loop optimization](https://www.geeksforgeeks.org/compiler-design/loop-optimization-in-compiler-design/) process which is machine independent. In frequency reduction code inside a loop is optimized to improve the running time of program. Frequency reduction is used to decrease the amount of code in a loop. A statement or expression, which can be moved outside the loop body without affecting the semantics of the program, is moved outside the loop. Frequency Reduction is also called Code Motion.
**Objective of Frequency Reduction:**
The objective of frequency reduction is:
- To reduce the evaluation frequency of expression.
- To bring loop invariant statements out of the loop.
Below is the example of Frequency Reduction:
**Program 1:**
````cpp
// This program does not uses frequency reduction.
#include <bits/stdc++.h>
using namespace std;
int main()
{
    int a = 2, b = 3, c, i = 0;
    while (i < 5) {
        // c is calculated 5 times
        c = pow(a, b) + pow(b, a);
        // print the value of c 5 times
        cout << c << endl;
        i++;
    }
    return 0;
}
````
**Program 2:**
````cpp
// This program uses frequency reduction.
#include <bits/stdc++.h>
using namespace std;
int main()
{
    int a = 2, b = 3, c, i = 0;
    // c is calculated outside the loop
    c = pow(a, b) + pow(b, a);
    while (i < 5) {
        // print the value of c 5 times
        cout << c << endl;
        i++;
    }
    return 0;
}
````
**Output:**
```
17
17
17
17
17
```
**Explanation:**
Program 2 is more efficient than Program 1 as in Program 1 the value of c is calculated each time the while loop is executed. Hence the value of c is calculated outside the loop only once and it reduces the amount of code in the loop.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/frequency-reduction-in-code-optimization/)

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
> - [[Function Inlining]]
> - [[Induction Variable and Strength Reduction]]
> - [[Loop Jamming]]
