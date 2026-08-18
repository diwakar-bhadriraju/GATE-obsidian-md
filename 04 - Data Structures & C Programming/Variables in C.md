---
title: "Variables in C"
subject: "Data Structures & C Programming"
topic: "Programming in C"
source: "https://www.geeksforgeeks.org/c/variables-in-c/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Data Structures & C Programming/Programming in C"
tags:
  - gate/cs
  - subject/data-structures-c-programming
  - topic/programming-in-c
---


> [!abstract] Variables in C
> 
> **Subject:** `Data Structures & C Programming` &nbsp;|&nbsp; **Topic:** `Programming in C`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/c/variables-in-c/)

---

# Variables in C

A variable in C is a named piece of memory which is used to store data and access it whenever required.
- It allows us to use the memory without having to memorize the exact memory address.
- To create a variable in C, we have to specify a name and the type of data it is going to store.
- C provides different [**data types**](https://www.geeksforgeeks.org/c/data-types-in-c/) that can store almost all kinds of data. For example, int, char, float, double, etc.
- Every variable must be declared before it is used. We can also declare multiple variables of same data type in a single statement by separating them using comma .
````c
#include <stdio.h>
int main()
{
    // integer variable
    int age = 20;
    // floating-point variable
    float height = 5.7;
    // character variable
    char grade = 'A';
    printf("Age: %d\n", age);
    printf("Height: %.1f\n", height);
    printf("Grade: %c\n", grade);
    return 0;
}
````
**Output**
```
Age: 20
Height: 5.7
Grade: A
```
### **Rules for Naming Variables in C**
We can assign any name to a C variable as long as it follows the following rules:
- A variable name must only contain letters, digits, and underscores.
- It must start with an alphabet or an underscore only. It cannot start with a digit.
- No white space is allowed within the variable name.
- A variable name must not be any reserved word or keyword.
- The name must be unique in the program.
## C Variable Initialization
- Once the variable is declared, we can store useful values in it. The first value we store is called initial value and the process is called **Initialization**. It is done using [assignment operator **(=)**](https://www.geeksforgeeks.org/c/assignment-operators-in-c-c/).
- It is important to initialize a variable because a C variable only contains garbage value when it is declared. We can also initialize a variable along with declaration.
````cpp
#include <stdio.h>
int main()
{
    // 1. Initialization at the time of declaration
    int age = 20;
    float height = 5.7;
    // 2. Initialization after declaration
    char grade;
    grade = 'A';
    printf("Age: %d\n", age);
    printf("Height: %.1f\n", height);
    printf("Grade: %c\n", grade);
    return 0;
}
````
**Output**
```
Age: 20
Height: 5.7
Grade: A
```
> **Note:** Values should be type-compatible, otherwise C performs implicit or explicit type conversion.
## Accessing Variables
The data stored inside a C variable can be easily accessed by using the variable's name.
````c
#include <stdio.h>
int main() {
    // Create integer variable
    int num = 3;
    // Access the value stored in
    // variable
    printf("%d", num);
    return 0;
}
````
**Output**
```
3
```
## Changing Stored Values
We can also update the value of a variable with a new value whenever needed by using the assignment operator =.
````c
#include <stdio.h>
int main()
{
    // initial value
    int number = 10;
    printf("Initial value: %d\n", number);
    // updating value
    number = 25;
    printf("Updated value: %d\n", number);
    // updating again using expression
    number = number + 5;
    printf("After adding 5: %d\n", number);
    return 0;
}
````
**Output**
```
Initial value: 10
Updated value: 25
After adding 5: 30
```
## How to use variables in C?
Variables act as name for memory locations that stores some value. It is valid to use the variable wherever it is valid to use its value. It means that a variable name can be used anywhere as a substitute in place of the value it stores.
````c
#include <stdio.h>
int main()
{
    // Expression that uses values
    int sum1 = 20 + 40;
    // Defining variables
    int a = 20, b = 40;
    // Expression that uses variables
    int sum2 = a + b + 10;
    printf("%d\n%d", sum1, sum2);
    return 0;
}
````
**Output**
```
60
70
```
## Memory Allocation of C Variables
When a variable is **declared**, the compiler is told that the variable with the given name and type exists in the program. But no memory is allocated to it yet. Memory is allocated when the variable is **defined**.
Most programming languages like C generally declare and define a variable in the single step. For example, in the above part where we create a variable, variable is declared and defined in a single statement.
The size of memory assigned for variables depends on the type of variable. We can check the size of the variables using [**sizeof operator**](https://www.geeksforgeeks.org/c/sizeof-operator-c/)**.**
````c
#include <stdio.h>
int main() {
    int num = 22;
    // Finding size of num
    printf("%d bytes", sizeof(num));
    return 0;
}
````
**Output**
```
4 bytes
```
Variables are also stored in different parts of the memory based on their [**storage classes**](https://www.geeksforgeeks.org/c/storage-classes-in-c/)**.**
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/c/variables-in-c/)

## GATE CS

- Subject: Data Structures & C Programming
- Topic: Programming in C

> [!note] Related notes
>
> - [[Data Types in C]]
> - [[Enum, Struct & Union in C]]
> - [[Functions in C]]
> - [[Introduction to C Programming]]
> - [[Operators in C]]
> - [[Pointers in C]]
> - [[Scope of a Variable]]
> - [[Type Casting in C]]
> - [[1D, 2D and 3D Arrays]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
