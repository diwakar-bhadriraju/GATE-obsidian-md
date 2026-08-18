---
title: "Runtime Environments in Compiler Design"
subject: "Compiler Design"
topic: "Runtime Environment"
source: "https://www.geeksforgeeks.org/compiler-design/runtime-environments-in-compiler-design/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Runtime Environment"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/runtime-environment
---


> [!abstract] Runtime Environments in Compiler Design
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Runtime Environment`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/runtime-environments-in-compiler-design/)

---

# Runtime Environments in Compiler Design

A runtime environment refers to the system that supports the execution of a compiled program. It connects the static program written in the source code with the dynamic actions performed during execution. The runtime environment manages memory, procedure calls, parameter passing, and other services required while the program runs.
- Programs contain identifiers such as variables and procedures that must be mapped to actual memory locations during execution.
- The runtime environment maintains the state of the target machine and provides necessary services such as memory allocation, control flow management, and access to libraries.
## **Activation Tree**
An activation tree represents the sequence of procedure (function) calls during program execution. Each execution of a procedure is called an activation. Activations may be non-overlapping, nested, or recursive, depending on how functions call each other.
### Properties
- Each node represents an activation of a procedure.
- The root represents the activation of the main function.
- A node for procedure x is the parent of node for procedure y if control flows from x to y.
**Example -** Consider the following program of Quicksort
```
void main() {    int n;    readarray();    quicksort(1, n);}void quicksort(int m, int n) {    if (m >= n) return;   // base condition added    int i = partition(m, n);    quicksort(m, i - 1);    quicksort(i + 1, n);}
```
The activation tree for this program will be: ![1](assets/1-35-a2d516998c.png)First main function as the root then main calls readarray and quicksort. Quicksort in turn calls partition and quicksort again. The flow of control in a program corresponds to a pre-order depth-first traversal of the activation tree which starts at the root.
## Control Stack and Activation Records
Control stack or runtime stack is used to keep track of the active procedure activations i.e the procedures whose execution have not been completed. When a procedure is called, an activation record (stack frame) is pushed onto the stack. When the procedure finishes, the activation record is removed from the stack. 
An activation record stores information required for a single procedure execution, including:
- Local variables
- Temporary values used during expression evaluation
- Machine status information before the procedure call
- Access link for accessing non-local variables
- Control link pointing to the caller’s activation record
- Return value
- Actual parameters passed to the procedure
![2](assets/2-20-e448010722.png)
![3](assets/3-17-fa003d4374.png)
Control stack for the above quicksort example:
![4](assets/4-12-05cc0c6b78.png)
## Subdivision of Runtime Memory
Runtime memory is divided into different regions to store program data during execution.
- **Target code:** compiled program instructions (fixed at compile time)
- **Static data:** global and static variables
- **Stack:** automatic variables and activation records
- **Heap:** dynamically allocated memory
![5](assets/5-8-d7dcf5a59a.png)
## Storage Allocation Techniques
### **Static Storage Allocation**
Memory locations for variables are determined at compile time. Each variable is bound to the same memory location during all procedure activations.
- Memory is allocated once before execution begins
- Values of local variables can remain across procedure calls
- Does not support recursion
- Size of data must be known at compile time
Ex: FORTRAN was designed to permit static storage allocation. 
### **Stack Storage Allocation**
Memory is managed using a stack structure where activation records are pushed and popped as procedures are called and completed.
- Each procedure activation receives fresh storage and Support recursion
- Efficient management of local variables and parameters
### **Heap Storage Allocation**
Memory can be allocated and deallocated at any time during program execution.
- Used for dynamic data structures such as linked lists and trees
- Supports recursion and dynamic memory usage
## Parameter Passing
Parameter passing is the mechanism used to transfer data between the calling procedure and the called procedure.
- **Formal Parameter:**  Variables that take the information passed by the caller procedure are called formal parameters. These variables are declared in the definition of the called function.
- **Actual Parameter:**  Variables whose values and functions are passed to the called function are called actual parameters. These variables are specified in the function call as arguments.
### **Basic terminology**
- **R-value:**  The value of an expression is called its r-value. The value contained in a single variable also becomes an r-value if its appear on the right side of the assignment operator. R-value can always be assigned to some other variable.
- **L-value:**  The location of the memory(address) where the expression is stored is known as the l-value of that expression. It always appears on the left side if the assignment operator.
## Parameter Passing Methods
### Call by Value
The value of the actual parameter is copied into the formal parameter. Changes inside the function do not affect the original variable.
````cpp
#include <iostream>
using namespace std;
void swap(int a, int b)  // call by value
{
    int temp = a;
    a = b;
    b = temp;
}
int main()
{
    int a = 10, b = 20;
    swap(a, b);
    cout << a << " " << b << endl;
    return 0;
}
````
### Call by Reference
The address of the actual parameter is passed to the function. Any modification inside the function affects the original variable.
````cpp
#include <iostream>
using namespace std;
void swap(int &a, int &b) // call by reference
{
    int temp = a;
    a = b;
    b = temp;
}
int main()
{
    int a = 10, b = 20;
    swap(a, b);
    cout << a << " " << b << endl;
    return 0;
}
````
### Call by Copy-Restore
Values are copied to the formal parameters during the call and copied back to the actual parameters when the function returns.
````cpp
#include <iostream>
using namespace std;
void swap(int &a, int &b)
{
    /* A hybrid between call-by-value and call-by-reference
       is copy-restore linkage (also known as copy in and
       copy out ,or value-result) */
    int copy_a, copy_b;
    copy_a = a; // copy in phase
    copy_b = b;
    int temp = copy_a; // function proper
    copy_a = copy_b;
    copy_b = temp;
    a = copy_a; // copy out phase
    b = copy_b;
}
int main()
{
    int a = 10, b = 20;
    swap(a, b);
    cout << a << " " << b << endl;
    return 0;
}
// code added by raunakraj232
````
### Call by Name
Actual parameters are substituted for formal parameters in the function body and evaluated only when needed. This mechanism is mainly theoretical and not supported in most modern languages. This concept is mainly theoretical and is not directly supported in modern programming languages like C++. Therefore, no direct implementation is provided.
We can simulate Call by Name behavior using macros (approximation).
- Macro directly substitutes x and y
- No parameter passing -> behaves like call by name
````cpp
#include <iostream>
using namespace std;
#define SWAP(x, y) \
do { \
    int temp = x; \
    x = y; \
    y = temp; \
} while(0)
int main()
{
    int a = 10, b = 20;
    SWAP(a, b);
    cout << "a = " << a << " b = " << b << endl;
    return 0;
}
````
### Advantages
- Improves portability by providing an abstraction layer between the compiled program and the operating system.
- Manages system resources such as memory and CPU efficiently.
- Supports dynamic memory allocation during program execution.
- Can automatically free unused memory through garbage collection.
- Provides mechanisms for handling exceptions and runtime errors.
### Disadvantages
- Introduces performance overhead due to additional runtime processing.
- Some runtime environments may depend on specific platforms.
- Debugging can become more complex because of the abstraction layer.
- Compatibility issues may arise with certain operating systems or hardware.
- Different versions of runtime environments can create versioning problems.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/runtime-environments-in-compiler-design/)

## GATE CS

- Subject: Compiler Design
- Topic: Runtime Environment

> [!note] Related notes
>
> - [[Pass by Copy-restore]]
> - [[Pass by Name]]
> - [[Ambiguous Grammar]]
> - [[Backtracking]]
> - [[Bottom Up or Shift Reduce Parsers]]
> - [[Classification of Context Free Grammars]]
> - [[Classification of top down parsers]]
> - [[Code Motion]]
> - [[Code Optimization]]
> - [[Common Sub Expression Elimination]]
