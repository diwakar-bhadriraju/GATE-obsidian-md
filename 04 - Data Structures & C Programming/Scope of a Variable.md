---
title: "Static and Dynamic Scoping"
subject: "Data Structures & C Programming"
topic: "Programming in C"
source: "https://www.geeksforgeeks.org/dsa/static-and-dynamic-scoping/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Data Structures & C Programming/Programming in C, Compiler Design/Lexical Analysis, Parsing, Syntax-directed"
tags:
  - gate/cs
  - subject/data-structures-c-programming
  - topic/programming-in-c
---


> [!abstract] Static and Dynamic Scoping
> 
> **Subject:** `Data Structures & C Programming` &nbsp;|&nbsp; **Topic:** `Programming in C`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/static-and-dynamic-scoping/)

---

# Static and Dynamic Scoping

The scope of a variable refers to the region of a program where that variable can be accessed. Scoping helps keep variables used in different parts of a program separate from one another, even if they have the same name. This is important because programmers often reuse common variable names such as `i`, `x`, or `count` in different parts of a program.
Scoping is generally divided into two types:
1. Static Scoping
2. Dynamic Scoping
## **Static Scoping:**
Also known as lexical scoping, determines the scope of a variable based on the structure of the program code. In this approach, the binding of a variable can be determined by examining the program text, regardless of how the program executes at runtime. The compiler searches for a variable in the following order: Current block, Enclosing blocks, Global scope. Most modern programming languages such as C, C++, Java, and Python use static scoping. Because the scope is known at compile time, it makes programs easier to understand, debug, and optimize.
````c
// A C program to demonstrate static scoping.
#include<stdio.h>
int x = 10;
// Called by g()
int f()
{
   return x;
}
// g() has its own variable
// named as x and calls f()
int g()
{
   int x = 20;
   return f();
}
int main()
{
  printf("%d", g());
  printf("\n");
  return 0;
}
````
Output : 
```
10
```
## **Dynamic Scoping:**
The value of a variable is determined by the most recent function call in the program’s call stack. Instead of following the program structure, the runtime system searches for variable definitions in the chain of active function calls. The search order is: Current function, Calling function, Functions higher in the call stack. Rarely used in modern programming languages.
````c
// Since dynamic scoping is very uncommon in
// the familiar languages, we consider the
// following pseudo code as our example. It
// prints 20 in a language that uses dynamic
// scoping.
int x = 10;
// Called by g()
int f()
{
   return x;
}
// g() has its own variable
// named as x and calls f()
int g()
{
   int x = 20;
   return f();
}
main()
{
  printf(g());
}
````
Output in a language that uses Dynamic Scoping : 
```
20
```
## **Static Vs Dynamic Scoping**
| Aspect | Static Scoping (Lexical Scoping) | Dynamic Scoping |
| --- | --- | --- |
| Scope Determination | By its position in the source code, independent of how the program executes. | By the order of function calls during program execution. |
| Time of Binding | Resolved at compile time, allowing the compiler to know exactly which variable is being referenced. | Resolved at runtime based on the current call stack. |
| Variable Lookup | The compiler searches for variables in enclosing lexical blocks following the program’s textual structure. | The runtime system searches for variables in the chain of active function calls. |
| Predictability | Program behavior is predictable because variable access can be understood by reading the source code alone. | Program behavior is harder to predict since it depends on the execution path taken at runtime. |
| Performance | Access to variables is faster because their locations are determined during compilation. | Access to variables is slower due to runtime stack traversal to resolve bindings. |
| Compiler Optimization | Enables optimizations such as register allocation, inlining, and dead code elimination. | Limits compiler optimizations because variable bindings are not known in advance. |
| Safety | Prevents accidental access or modification of variables outside their intended lexical scope. | Increases the possibility of unintended variable modification from unrelated functions. |
| Debugging | Simpler, due to fixed and well-defined scope boundaries. | Complex as variable bindings may change during execution. |
| Language Support | Supported by most modern programming languages such as C, C++, Java, and Python. | Rarely supported; seen in limited form in languages like Perl using `local`. |
| Use in Closures | Fully supports closures and nested functions with well-defined environments. | Does not support closures because bindings are determined dynamically. |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/static-and-dynamic-scoping/)

## GATE CS

- Subject: Data Structures & C Programming
- Topic: Programming in C

> [!note] Related notes
>
> - [[Ambiguous Grammar]]
> - [[Backtracking]]
> - [[Bottom Up or Shift Reduce Parsers]]
> - [[Classification of Context Free Grammars]]
> - [[Classification of top down parsers]]
> - [[Data Types in C]]
> - [[Enum, Struct & Union in C]]
> - [[Error detection and Recovery in Compiler]]
> - [[Error Handling in Compiler Design]]
> - [[Fast Lexical Analyzer Generator]]
