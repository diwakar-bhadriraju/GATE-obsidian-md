---
title: "Pass By Copy-Restore in Compiler Design"
subject: "Compiler Design"
topic: "Runtime Environment"
source: "https://www.geeksforgeeks.org/compiler-design/pass-by-copy-restore-in-compiler-design/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Runtime Environment"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/runtime-environment
---


> [!abstract] Pass By Copy-Restore in Compiler Design
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Runtime Environment`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/pass-by-copy-restore-in-compiler-design/)

---

# Pass By Copy-Restore in Compiler Design

Pass by Copy-Restore is a parameter passing mechanism also known as value-result or copy-in-copy-out. It is a variation of the pass by value technique, where a copy of the actual parameter is passed to the subroutine or function. In compiler design, the function is still given the address of the argument, as it was in [call-by-reference](https://www.geeksforgeeks.org/c/difference-between-call-by-value-and-call-by-reference/).
However, the protocol for this technique dictates that the function make a copy of the argument before executing the function body. This copy is then worked with in the function body. When the function body has completed, the protocol for copy-restore dictates that the copy of the argument be “restored into” the original argument using the address of the argument, hence potentially modifying that argument.
This technique optimises the passing of parameters to subroutines in a program by creating a copy of the actual parameter and passing it to the subroutine. The subroutine modifies the copy, and when it returns, the modified copy is restored back to the original variable. This approach avoids the overhead of passing parameters by reference, which involves passing a pointer to the original variable.
Pass by copy-restore also ensures the correctness of the program by avoiding the unintended side effects that may occur when the original variable in the subroutine is being modified. It also reduces the complexity of the program by eliminating the use case of pointers and memory allocation.
#### To illustrate the pass by copy-restore technique, consider the following example in C++:
````cpp
#include <iostream>
using namespace std;
void modify(int a) {
   a = a * 2;
}
int main() {
   int num = 10;
   modify(num);
   cout << num << endl;
   return 0;
}
````
**Output:**
```
10
```
In the above example, the modify function takes an integer parameter 'a' by value. When the function is called in main using 'num' as the argument, a copy of 'num' is created which refers to 'int a' hence 'a' is initialized with that value. The 'modify' function then modifies the value of 'a' by multiplying it with 2. 
However, the value of 'num' remains unchanged after the call to the 'modify' function because the copy of num which was passed to the function is not the same as the original variable. Hence the output will be 10. To modify the original variable 'num', we need to use pass by reference or pass by copy-restore.
#### To use pass by copy-restore in the above example, we can modify the function as follows:
````cpp
#include <iostream>
using namespace std;
void modify(int& a) {
   a = a * 2;
}
int main() {
   int num = 10;
   int copy = num;
   modify(copy);
   num = copy;
   cout << num << endl;
   return 0;
}
````
**Output:**
```
20
```
In the modified example, we created a copy of 'num' and stored it in the 'copy' named variable and pass it to the function. The function modifies the value of the 'copy', and the modified 'copy' is assigned to 'num', so it replaces the previous value of 'num'. As a result, the output of the program will be 20.
## Primary Terminologies
### Subroutine
Also known User Defined Function which is basically a sequence of instructions written by the programmer to call it within the program to perform some specific task.
### Compiler
 A compiler is a special program that converts source code into machine code, bytecode or some another language. The source code is typically written in a high-level, human-readable language such as Java, C++ or Python etc.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/pass-by-copy-restore-in-compiler-design/)

## GATE CS

- Subject: Compiler Design
- Topic: Runtime Environment

> [!note] Related notes
>
> - [[Pass by Name]]
> - [[Runtime Environments]]
> - [[Ambiguous Grammar]]
> - [[Backtracking]]
> - [[Bottom Up or Shift Reduce Parsers]]
> - [[Classification of Context Free Grammars]]
> - [[Classification of top down parsers]]
> - [[Code Motion]]
> - [[Code Optimization]]
> - [[Common Sub Expression Elimination]]
