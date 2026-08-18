---
title: "Induction Variable and Strength Reduction"
subject: "Compiler Design"
topic: "Local Optimization"
source: "https://www.geeksforgeeks.org/compiler-design/induction-variable-and-strength-reduction/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Local Optimization"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/local-optimization
---


> [!abstract] Induction Variable and Strength Reduction
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Local Optimization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/induction-variable-and-strength-reduction/)

---

# Induction Variable and Strength Reduction

In programming, knowing a few key ideas may make a big difference in how well your code works and performs. These include the ideas of **Strength Reduction** and **Induction** **Variables**. These are basic principles, particularly in handling loops and code optimization for improved runtime. Now let's explore these ideas in more detail to see how they relate to programming.
## Induction Variable
An induction variable is a variable used in a [loop](https://www.geeksforgeeks.org/c/c-loops/) (for, while, do-while loop). It controls the iteration of the loop.
**Example:**
````cpp
for (int i = 0; i < 20; i++) //'i' is an induction variable
{
    cout << i;
}
````
In this example, **i** is an induction variable. Induction variables are first checked against the termination condition. If the condition is true, then the control goes inside the loop. The loop is executed and then the induction variable is incremented or decremented. This is done continuously until the termination condition becomes false.
Loop induction variables sometimes lead to increased [time complexity](https://www.geeksforgeeks.org/dsa/time-complexity-and-space-complexity/). The compiler also has limitations and can run the loop a limited number of times only. Loop induction variables can also be optimized. It enhances the performance of the code and reduces the time complexity.
## Strength Reduction
Strength reduction is one of the techniques used to optimize loop induction variables. In strength reduction, expensive operations like multiplication and division are replaced by cheaper operations like bit shifting, addition or subtraction.
Operations like multiplication and division are more time consuming than addition and subtraction. With the help of strength reduction, time complexity is reduced as expensive operations get replaced by cheaper ones. Strength reduction can be done by:
### 1. Replacing Multiplication with Addition
To reduce the complexity, multiplication operation can be replaced by multiple addition operations. Addition operation is less costly than multiplication operation.
````cpp
// before strength reduction
int main()
{
    int a = 2;
    int b = a * 3;
}
// after strength reduction
int main()
{
    int a = 2;
    int b = a + a + a; // replaced * with three + operations
}
````
### 2. Replacing multiplication with left shift operator (<<)
Multiplication operator can be replaced by left shift operator. If we are multiplying a variable with y (2x), we can left shift the variable 'x' bits.
> **In the below example, instead of multiplying a by 4, we can left shift by 2 bits (a\*22)**
````cpp
// before strength reduction
int main()
{
    int a = 2;
    int b = a * 4;
}
// after strength reduction
int main()
{
    int a = 2;
    int b = (a << 2); // left shift by 2
}
````
### 3. Replacing division by multiplication
Division operation is replaced by multiple multiplication operations to reduce the complexity of the code. Multiplication operator is less expensive than division operator.
````cpp
// before strength reduction
int main()
{
    int a = 8;
    int b = a / 4;
}
// after strength reduction
int main()
{
    int a = 8;
    int b
        = a * 0.5
          * 0.5; // replaced division with two * operations
}
````
### 4. Replacing division with right shift operator (>>)
Division operator can be replaced by right shift operator. If we are dividing a variable by y (2x), we can right shift the operator by 'y' bits.
> In the below example Instead of dividing a by 4, we can right shift by 2 bits (a/22)
````cpp
// before strength reduction
int main()
{
    int a = 8;
    int b = a / 4;
}
// after strength reduction
int main()
{
    int a = 8;
    int b = (a >> 2); // right shift by 2
}
````
### Advantages of Strength Reduction
- Improves performance
- Simplifies code
- Makes execution faster
### Differences between Strength Reduction and Induction Variables
#### Purpose
- **Induction Variables**: Induction variables focussed on controlling the iteration of a loop. They are responsible for managing the loop's progress, typically by incrementing or decrementing a variable until a termination condition is met.
- **Strength Reduction**: Strength reduction focuses on optimizing costly arithmetic operations (like, multiplication and division) within loops. It aims to replace these expensive operations with cheaper ones (e.g., bit shifting, addition, subtraction) to improve code performance.
#### Role within Loops
- **Induction Variables**: Induction variables directly influence the loop control flow. They determine how many times the loop will iterate and are critical for ensuring the loop's termination condition is met.
- **Strength Reduction**: Strength reduction is concerned with optimizing the operations performed within the loop but does not directly control the loop's iteration. It aims to make the code within the loop more efficient without changing the loop's fundamental structure.
#### Example
- **Induction Variables:** Example of an induction variable is a variable (e.g., 'i') used in a 'for' loop to control the number of iterations.
- **Strength Reduction**: Examples of strength reduction techniques include replacing multiplication with addition, using left shift operators, or replacing division with multiplication.
## Conclusion
Strength Reduction and Induction Variables is essential for optimizing code within loops. Induction Variables control loop iteration, while Strength Reduction optimizes arithmetic operations. These concepts, when applied, lead to more efficient and resource friendly code used for effective programming.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/induction-variable-and-strength-reduction/)

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
> - [[Frequency Reduction]]
> - [[Function Inlining]]
> - [[Loop Jamming]]
