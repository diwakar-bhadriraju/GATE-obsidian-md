---
title: "Functions in C"
subject: "Data Structures & C Programming"
topic: "Programming in C"
source: "https://www.geeksforgeeks.org/c/c-functions/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Data Structures & C Programming/Programming in C"
tags:
  - gate/cs
  - subject/data-structures-c-programming
  - topic/programming-in-c
---


> [!abstract] Functions in C
> 
> **Subject:** `Data Structures & C Programming` &nbsp;|&nbsp; **Topic:** `Programming in C`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/c/c-functions/)

---

# Functions in C

A function is a named block of code that performs a specific task. A function can take inputs (called parameters), execute a block of statements, and optionally return a result.
- A function allows you to write a piece of logic once and reuse it wherever needed in the program.
- This helps keep your code clean, organized, easier to understand and manage.
````c
#include <stdio.h>
// function definition
int square(int x)
{
    return x * x;
}
int main()
{
    // Calling the function
    int result = square(5);
    printf("Square of 5 is: %d", result);
    return 0;
}
````
**Output**
```
Square of 5 is: 25
```
### Syntax
![keyword](assets/keyword-0c1556f115.webp)
- **Return type**: Specifies the type of value the function will return. Use void if the function does not return anything.
- **Function name**: A unique name that identifies the function. It follows the same naming rules as variables.
- **Parameter list**: A set of input values passed to the function. If the function takes no inputs, this can be left empty or written as void.
- **Function body**: The block of code that runs when the function is called. It is enclosed in curly braces { }.
![Why-Use-Functions__](assets/Why-Use-Functions__-c59528de24.webp)
## Function Declaration Vs Definition
It's important to understand the difference between declaring a function and defining it. Both play different roles in how the compiler understands and uses your function.
### Function Declaration
A declaration tells the compiler about the function's name, return type, and parameters before it is actually used. It does not contain the function's body. This is often placed at the top of the program or in a header file.
> int add(int a, int b);
### Function Definition
A definition provides the actual implementation of the function. It includes the full code or logic that runs when the function is called.
> int add(int a, int b) {
>  return a + b;
> }
### Calling a Function
Once a function is defined, you can use it by simply calling its name followed by parentheses. This tells the program to execute the code inside that function.
````c
#include <stdio.h>
// Function definition
int add(int a, int b) {
    return a + b;
}
int main() {
    // Function call
    int result = add(5, 3);
    printf("The sum is: %d", result);
    return 0;
}
````
**Output**
```
The sum is: 8
```
**Explanation**
- The add() function is called with the values 5 and 3, computes their sum, and returns the result, which is stored in the variable result.
- A function can be called multiple times from main() or other functions, allowing the same code to be reused whenever needed.
- Function calls improve code reusability, reduce duplication, and make programs easier to read, maintain, and debug.
## Types of Function in C
In C programming, functions can be grouped into two main categories: [**library functions**](https://www.geeksforgeeks.org/c/c-library-functions/) and [**user-defined functions**](https://www.geeksforgeeks.org/c/user-defined-function-in-c/). Based on how they handle input and output, user-defined functions can be further classified into different types.
### Library Functions
These are built-in functions provided by C, such as [printf()](https://www.geeksforgeeks.org/c/printf-in-c/), [scanf()](https://www.geeksforgeeks.org/c/scanf-in-c/), [sqrt()](https://www.geeksforgeeks.org/c/sqrt-function-in-c/), and many others. You can use them by including the appropriate [header file](https://www.geeksforgeeks.org/c/header-files-in-c-cpp-and-its-uses/), like #include <stdio.h> or #include <math.h>.
### User-Defined Functions
These are functions that you create yourself to perform specific tasks in your program. Depending on whether they take input or return a value, they can be of four types:
- **No arguments, no return value:** The function neither takes input nor returns any result.
- **Arguments, no return value:** The function takes input but does not return anything.
- **No arguments, return value:** The function does not take input but returns a result.
- **Arguments and return value:** The function takes input and returns a result.
Each type serves different purposes depending on what the program needs. Using the right type helps make your code more organized and efficient.
## Memory Management of Functions
When a function is called, the system allocates memory for its parameters and local variables in a stack frame, which is automatically released when the function finishes execution.
- **Automatic Memory Allocation:** Each function call creates a separate stack frame to store its local variables, parameters, and return information.
- **Automatic Memory Deallocation:** Once the function returns, its stack frame is removed from the call stack, freeing the allocated memory automatically.
## Advantages
Functions help organize a program into smaller, reusable blocks, making the code easier to develop and maintain.
- Write a function once and call it multiple times, reducing code duplication.
- Breaks large programs into smaller, meaningful modules that are easier to understand.
- Changes made in a function are automatically reflected wherever it is called.
- Individual functions can be tested and debugged independently.
## Disadvantages
Although functions improve code organization, they also have a few limitations.
- Each function call adds a small execution overhead due to parameter passing and returning control.
- Frequent calls to very small functions can slightly affect performance in time-critical applications.
- Excessive use of functions may make the program flow harder to follow across multiple files or modules.
- Since local variables are limited to their function, sharing data between functions may require parameters or global variables.
### Related Article
> - [function declaration and function definition](https://www.geeksforgeeks.org/computer-science-fundamentals/function-declaration-vs-function-definition/).
> - [Function Call Stack in C](https://www.geeksforgeeks.org/c/function-call-stack-in-c/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/c/c-functions/)

## GATE CS

- Subject: Data Structures & C Programming
- Topic: Programming in C

> [!note] Related notes
>
> - [[Data Types in C]]
> - [[Enum, Struct & Union in C]]
> - [[Introduction to C Programming]]
> - [[Operators in C]]
> - [[Pointers in C]]
> - [[Scope of a Variable]]
> - [[Type Casting in C]]
> - [[Variables in C]]
> - [[1D, 2D and 3D Arrays]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
