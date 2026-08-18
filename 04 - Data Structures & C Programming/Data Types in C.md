---
title: "Data Types in C"
subject: "Data Structures & C Programming"
topic: "Programming in C"
source: "https://www.geeksforgeeks.org/c/data-types-in-c/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Data Structures & C Programming/Programming in C"
tags:
  - gate/cs
  - subject/data-structures-c-programming
  - topic/programming-in-c
---


> [!abstract] Data Types in C
> 
> **Subject:** `Data Structures & C Programming` &nbsp;|&nbsp; **Topic:** `Programming in C`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/c/data-types-in-c/)

---

# Data Types in C

Data types form the foundation of data representation in C. Every variable in C must be associated with a data type that defines the kind of value it can store and how the compiler handles it.
- Data types define memory allocation, value range, and valid operations on a variable.
- Understanding data types is essential for writing correct and efficient C programs.
## Classification of Data Types in C
Data types in C are broadly classified into three categories:
![data_type_in_c](assets/data_type_in_c-2411981c3b.webp)
Data Types in C
## Primitive Data Types
Primitive data types are the basic built-in data types in C used to store simple values like integers, characters, and floating-point numbers.
### Integer Data Type
- Stores whole numbers (positive, negative, or zero).
- We use [int keyword](https://www.geeksforgeeks.org/c/int-1-sign-bit-31-data-bits-keyword-in-c/) to declare the integer variable:
- Size: typically 4 bytes, Range: -2,147,483,648 to 2,147,483,647.
- Format specifier: %d.
[Format specifiers](https://www.geeksforgeeks.org/c/format-specifiers-in-c/) are the symbols that are used for printing and scanning values of given data types.
````cpp
#include <stdio.h>
int main() {
    int var = 22;
    printf("var = %d", var);
    return 0;
}
````
**Output**
```
var = 22
```
### Character Data Type
- Stores a single character (like ‘A’, ‘b’, or ‘5’).
- Size: typically 1 byte, Range: -128 to 127 (signed by default).
- Format specifier: %c.
````cpp
#include <stdio.h>
int main() {
    char ch = 'A';
    printf("ch = %c", ch);
    return 0;
}
````
**Output**
```
ch = A
```
### Float Data Type
- Stores decimal numbers (numbers with fractional part).
- Size: typically 4 bytes, Approximate range: 3.4e-38 to 3.4e+38.
- Format specifier: %f.
````cpp
#include <stdio.h>
int main() {
    float val = 12.45;
    printf("val = %f", val);
    return 0;
}
````
**Output**
```
val = 12.450000
```
### Double Data Type
- Stores decimal numbers with more precision than float.
- Size: typically 8 bytes, Approximate range: 1.7e-308 to 1.7e+308.
- Format specifier: %lf.
````cpp
#include <stdio.h>
int main() {
    double val = 1.4521;
    printf("val = %lf", val);
    return 0;
}
````
**Output**
```
val = 1.452100
```
### Void Data Type
- Represents no value or empty type.
- Used in functions that do not return any value.
- Can also be used for generic pointers (void \*) in memory operations.
````cpp
#include <stdio.h>
// Function with void return type
void greet()
{
    printf("Hello, welcome!\n");
}
int main()
{
    greet();
    return 0;
}
````
**Output**
```
Hello, welcome!
```
## Derived Data Types in C
Derived data types are created from primitive data types.
### Arrays
An array stores multiple values of the same type in contiguous memory locations.
> int arr[5] = {1, 2, 3, 4, 5};
### Pointers
A pointer stores the memory address of another variable.
> int x = 10;
> int \*ptr = &x;
### Functions
Functions are also considered derived types based on return type and parameters.
> int add(int a, int b) {
>  return a + b;
> }
## User Defined Data Types in C
User-defined data types allow programmers to create custom data structures.
### Structure (struct)
A structure groups related variables under one name
> struct Student {
>  char name[50];
>  int age;
> };
### Union
A union allows multiple members to share the same memory location.
> union Data {
>  int i;
>  float f;
> };
### Enumeration (enum)
Enum is used to define named integer constants.
> enum Day {
>  MON, TUE, WED, THU, FRI, SAT, SUN
> };
## Size of Data Types in C
The size of the data types in C is dependent on the size of the architecture, so we cannot define the universal size of the data types. For that, the C language provides the **sizeof()** operator to check the size of the data types.
````c
#include <stdio.h>
int main()
{
    // Use sizeof() to know size of the data types
    printf("The size of int: %d\n", sizeof(int));
    printf("The size of char: %d\n", sizeof(char));
    printf("The size of float: %d\n", sizeof(float));
    printf("The size of double: %d", sizeof(double));
    return 0;
}
````
**Output**
```
The size of int: 4
The size of char: 1
The size of float: 4
The size of double: 8
```
Different data types also have different ranges up to which can vary from compiler to compiler. If you want to know more about ranges refer to this [Ranges of Datatypes in C](https://www.geeksforgeeks.org/c/ranges-of-data-types-in-c/).
> **Note:** The long, short, signed and unsigned are [datatype modifier](https://www.geeksforgeeks.org/c/data-type-modifiers-in-c/) that can be used with some primitive data types to change the size or length of the datatype.
### Related Article
> - [Literals](https://www.geeksforgeeks.org/c/literals-in-c-cpp-with-examples/)
> - [Type conversion](https://www.geeksforgeeks.org/c/type-conversion-c/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/c/data-types-in-c/)

## GATE CS

- Subject: Data Structures & C Programming
- Topic: Programming in C

> [!note] Related notes
>
> - [[Enum, Struct & Union in C]]
> - [[Functions in C]]
> - [[Introduction to C Programming]]
> - [[Operators in C]]
> - [[Pointers in C]]
> - [[Scope of a Variable]]
> - [[Type Casting in C]]
> - [[Variables in C]]
> - [[1D, 2D and 3D Arrays]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
