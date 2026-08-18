---
title: "Pointers in C"
subject: "Data Structures & C Programming"
topic: "Programming in C"
source: "https://www.geeksforgeeks.org/c/c-pointers/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Data Structures & C Programming/Programming in C"
tags:
  - gate/cs
  - subject/data-structures-c-programming
  - topic/programming-in-c
---


> [!abstract] Pointers in C
> 
> **Subject:** `Data Structures & C Programming` &nbsp;|&nbsp; **Topic:** `Programming in C`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/c/c-pointers/)

---

# Pointers in C

A pointer is a variable that stores the memory address of another variable. Instead of holding a direct value, it holds the address where the value is stored in memory. It is the backbone of low-level memory manipulation in C.
- A pointer is declared using its data type followed by an asterisk (\*) and the pointer name, indicating the type of data it can store the address of.
- A pointer variable stores the memory address of another variable, while the dereference operator (\*) is used to access the value stored at that address.
- The \* symbol has two purposes in C: it is used to declare a pointer and to dereference a pointer to access the value it points to.
````c
#include <stdio.h>
int main()
{
    // Normal Variable
    int var = 10;
    // Pointer Variable ptr that stores address of var
    int *ptr = &var;
    // Directly accessing ptr will give us an address
    printf("%p", ptr);
    return 0;
}
````
**Output**
```
0x7fffffffe9cc
```
This hexadecimal integer (starting with 0x) is the memory address.
![](assets/pointer-in-c-7e0bb3d48f.png)
Let us understand different steps of the above program.
### Syntax
> data\_type \*pointer\_name;
## **Initialize the Pointer**
A pointer is initialized by assigning it the address of a variable using the [address operator (&)](https://www.geeksforgeeks.org/cpp/address-operator-in-c/)
- Initializing a pointer ensures it points to a valid memory location before use.
- You can also initialize a pointer to NULL if it doesn’t point to any variable yet: int \*ptr = NULL;
### Syntax
> pointer\_name = &variable;
## Dereference a Pointer
We have to first [dereference](https://www.geeksforgeeks.org/cpp/dereference-pointer-in-c/) the pointer to access the value present at the memory address. This is done with the help of dereferencing operator(\*) (same operator used in declaration).
````c
#include <stdio.h>
int main() {
    int var = 10;
    // Store address of var variable
    int* ptr = &var;
    // Dereferencing ptr to access the value
    printf("%d", *ptr);
    return 0;
}
````
**Output**
```
10
```
> **Note**: Earlier, we used %d for printing pointers, but C provides a separate [format specifier](https://www.geeksforgeeks.org/c/format-specifiers-in-c/) **%p** for printing pointers.
## Size of Pointers
The size of a pointer in C depends on the architecture (bit system) of the machine, not the data type it points to.
- On a 32-bit system, all pointers typically occupy 4 bytes.
- On a 64-bit system, all pointers typically occupy 8 bytes.
The size remains constant regardless of the data type (`int*`, `char*`, `float*`, etc.). We can verify this using the [sizeof operator](https://www.geeksforgeeks.org/c/sizeof-operator-c/).
````c
#include <stdio.h>
int main() {
    int *ptr1;
    char *ptr2;
    // Finding size using sizeof()
    printf("%zu\n", sizeof(ptr1));
    printf("%zu", sizeof(ptr2));
    return 0;
}
````
**Output**
```
8
8
```
The reason for the same size is that the pointers store the memory addresses, no matter what type they are. As the space required to store the addresses of the different memory locations is the same, the memory required by one pointer type will be equal to the memory required by other pointer types.
> **Note:** The actual size of the pointer may vary depending on the **compiler and system architecture**, but it is always **uniform across all data types** on the same system.
## Special Types of Pointers
There are 4 special types of pointers that used or referred to in different contexts:
### 1. NULL Pointer
A [NULL Pointers](https://www.geeksforgeeks.org/cpp/null-pointer-in-cpp/) is a pointer that does not point to any valid memory location. It is created by assigning the value NULL to a pointer variable.
- A pointer of any data type can be initialized or assigned with NULL to indicate that it is not pointing to any object.
- Checking whether a pointer is NULL helps prevent invalid memory access and ensures the pointer references a valid memory location before use.
````c
#include <stdio.h>
int main() {
    // Null pointer
    int *ptr = NULL;
    return 0;
}
````
### 2. Void Pointer
The [void pointers](https://www.geeksforgeeks.org/c/void-pointer-c-cpp/) is a pointer of type void that does not have an associated data type. It is also known as a generic pointer because it can store the address of any data type.
- A void pointer can point to variables of any data type but must be typecast before dereferencing.
- It is commonly used in generic functions and memory management routines where the data type is not known in advance.
````c
#include <stdio.h>
int main() {
    // Void pointer
    void *ptr;
    return 0;
}
````
### 3. Wild Pointer
The [wild pointer](https://www.geeksforgeeks.org/dsa/what-are-wild-pointers-how-can-we-avoid/) is a pointer that has been declared but not initialized with a valid memory address. Using a wild pointer results in undefined behavior.
- Dereferencing a wild pointer can cause program crashes, memory corruption, or unexpected results.
- Always initialize pointers with a valid address or NULL before using them to avoid errors.
````c
#include <stdio.h>
int main() {
    // Wild Pointer
    int *ptr;
    return 0;
}
````
### 4. Dangling Pointer
A [dangling pointer](https://www.geeksforgeeks.org/c/dangling-void-null-wild-pointers/) is a pointer that refers to a memory location that has already been deallocated or freed. Accessing such a pointer leads to undefined behavior.
- Dereferencing a dangling pointer can cause program crashes, incorrect results, or memory access errors.
- Dangling pointers commonly occur when dynamically allocated memory is freed but the pointer is not updated or set to NULL.
````c
#include <stdio.h>
#include <stdlib.h>
int main() {
    int* ptr = (int*)malloc(sizeof(int));
    // After below free call, ptr becomes a dangling pointer
    free(ptr);
    printf("Memory freed\n");
    // removing Dangling Pointer
    ptr = NULL;
    return 0;
}
````
**Output**
```
Memory freed
```
## C Pointer Arithmetic
The [pointer arithmetic](https://www.geeksforgeeks.org/c/pointer-arithmetics-in-c-with-examples/) refers to the arithmetic operations that can be performed on a pointer. It is slightly different from the ones that we generally use for mathematical calculations as only a limited set of operations can be performed on pointers. These operations include:
- Increment/Decrement
- Addition/Subtraction of Integer
- Subtracting Two Pointers of Same Type
- Comparing/Assigning Two Pointers of Same Type
- Comparing/Assigning with NULL
## Constant Pointers
In constant pointers, the memory address stored inside the pointer is constant and cannot be modified once it is defined. It will always point to the same memory address.
````c
#include <stdio.h>
int main() {
    int a = 90;
    int b = 50;
    // Creating a constant pointer
    int* const ptr = &a;
    // Trying to reassign it to b
    ptr = &b;
    return 0;
}
````
**Output**
```
solution.c: In function ‘main’:solution.c:11:9: error: assignment of read-only variable ‘ptr’   11 |     ptr = &b;      |         ^
```
As we try here to assign `ptr` a new address, the compiler throws an error because a constant pointer cannot change the memory location it was originally assigned.
We can also create a pointer to constant or even constant pointer to constant. Refer to this article to know more - [Constant pointer, Pointers to Constant and Constant Pointers to Constant](https://www.geeksforgeeks.org/cpp/difference-between-constant-pointer-pointers-to-constant-and-constant-pointers-to-constants/)
## Pointer to Function
A [function pointer](https://www.geeksforgeeks.org/c/function-pointer-in-c/) is a pointer that stores the address of a function instead of a variable. It allows functions to be called indirectly and passed as arguments to other functions.
- Function pointers enable dynamic function calls and are commonly used to implement callback functions.
- They are widely used in event-driven programming, function tables, and flexible program design.
````c
#include <stdio.h>
int add(int a, int b) {
    return a + b;
}
int main() {
    // Declare a function pointer that matches
  	// the signature of add() function
    int (*fptr)(int, int);
    // Assign address of add()
    fptr = &add;
    // Call the function via ptr
    printf("%d", fptr(10, 5));
    return 0;
}
````
**Output**
```
15
```
## **Multilevel Pointers**
A [multi-level pointers](https://www.geeksforgeeks.org/c/chain-of-pointers-in-c-with-examples/) is a pointer that stores the address of another pointer instead of directly pointing to a data value. The most common type is a double pointer (\*\*), which points to another pointer.
- Multi-level pointers can have multiple levels (such as \*\*, \*\*\*, \*\*\*\*) depending on the application.
- They are commonly used for dynamic memory allocation, passing pointers to functions, and managing complex data structures.
````c
#include <stdio.h>
int main() {
    int var = 10;
    // Pointer to int
    int *ptr1 = &var;
    // Pointer to pointer (double pointer)
    int **ptr2 = &ptr1;
    // Accessing values using all three
    printf("var: %d\n", var);
    printf("*ptr1: %d\n", *ptr1);
    printf("**ptr2: %d", **ptr2);
    return 0;
}
````
**Output**
```
var: 10
*ptr1: 10
**ptr2: 10
```
## Advantages of Pointers
Following are the major advantages of pointers in C:
- Pointers are used for dynamic memory allocation and deallocation.
- An Array or a structure can be accessed efficiently with pointers
- Pointers are useful for accessing memory locations.
- Pointers are used to form complex data structures such as linked lists, graphs, trees, etc.
## Issues with Pointers
Pointers are vulnerable to errors and have following disadvantages:
- Memory corruption can occur if an incorrect value is provided to pointers.
- Pointers are a little bit complex to understand.
- Pointers are majorly responsible for [memory leaks in C](https://www.geeksforgeeks.org/c/what-is-memory-leak-how-can-we-avoid/).
- Uninitialized pointers might cause a [segmentation fault.](https://www.geeksforgeeks.org/c/segmentation-fault-sigsegv-vs-bus-error-sigbus/)
### Related Article
> [Pointers Vs Arrays](https://www.geeksforgeeks.org/c/pointer-vs-array-in-c/).
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/c/c-pointers/)

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
> - [[Scope of a Variable]]
> - [[Type Casting in C]]
> - [[Variables in C]]
> - [[1D, 2D and 3D Arrays]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
