---
title: "Operators in C"
subject: "Data Structures & C Programming"
topic: "Programming in C"
source: "https://www.geeksforgeeks.org/c/operators-in-c/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Data Structures & C Programming/Programming in C"
tags:
  - gate/cs
  - subject/data-structures-c-programming
  - topic/programming-in-c
---


> [!abstract] Operators in C
> 
> **Subject:** `Data Structures & C Programming` &nbsp;|&nbsp; **Topic:** `Programming in C`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/c/operators-in-c/)

---

# Operators in C

Operators in C are special symbols used to perform operations on variables, constants, and expressions. They form the foundation of programming logic by enabling arithmetic calculations, comparisons, logical decisions, memory access, and bit-level manipulations.
- C supports arithmetic, relational, logical, bitwise, assignment, and special operators.
- Operators can be unary, binary, or ternary based on the number of operands.
````c
#include <stdio.h>
int main() {
    // Expression for getting sum
    int sum = 10 + 20;
    printf("%d", sum);
    return 0;
}
````
**Output**
```
30
```
## Types of Operators in C
C language provides a wide range of built in operators that can be classified into 6 types based on their functionality:
### 1. Arithmetic Operators
The [arithmetic operators](https://www.geeksforgeeks.org/c/arithmetic-operators-in-c/) are used to perform mathematical calculations such as addition, subtraction, multiplication, division, and modulus on numeric values.
- Work with integer and floating-point data types.
- Include unary operators like increment (++) and decrement (--)
````c
#include <stdio.h>
int main() {
    int a = 25, b = 5;
    // using operators and printing results
    printf("a + b = %d\n", a + b);
    printf("a - b = %d\n", a - b);
    printf("a * b = %d\n", a * b);
    printf("a / b = %d\n", a / b);
    printf("a %% b = %d\n", a % b);
    printf("+a = %d\n", +a);
    printf("-a = %d\n", -a);
    printf("a++ = %d\n", a++);
    printf("a-- = %d\n", a--);
    return 0;
}
````
**Output**
```sql
a + b = 30
a - b = 20
a * b = 125
a / b = 5
a % b = 0
+a = 25
-a = -25
a++ = 25
a-- = 26
```
### 2.Relational Operators
The [relational operators](https://www.geeksforgeeks.org/c/relational-operators-in-c/) compare two values and determine the relationship between them. The result of a relational operation is either true (1) or false (0).
- Return boolean-like results (0 or 1).
- Used in decision-making statements.
````c
#include <stdio.h>
int main() {
    int a = 25, b = 5;
    // using operators and printing results
    printf("a < b  : %d\n", a < b);
    printf("a > b  : %d\n", a > b);
    printf("a <= b: %d\n", a <= b);
    printf("a >= b: %d\n", a >= b);
    printf("a == b: %d\n", a == b);
    printf("a != b : %d\n", a != b);
    return 0;
}
````
**Output**
```
a < b  : 0
a > b  : 1
a <= b: 0
a >= b: 1
a == b: 0
a != b : 1
```
Here, 0 means false and 1 means true.
### 3.Logical Operator
[Logical Operators](https://www.geeksforgeeks.org/c/logical-operators-in-c/) are used to combine multiple conditions or reverse a condition's result. They evaluate expressions and return either true or false.
- Return logical results (true or false).
- Support AND (&&), OR (||), and NOT (!) operations.
| Symbol | **Operator** | Description | Syntax |
| --- | --- | --- | --- |
| **&&** | **Logical AND** | Returns true if both the operands are true. | **a && b** |
| **||** | **Logical OR** | Returns true if both or any of the operand is true. | **a || b** |
| **!** | **Logical NOT** | Returns true if the operand is false. | **!a** |
````c
#include <stdio.h>
int main() {
    int a = 25, b = 5;
    // using operators and printing results
    printf("a && b : %d\n", a && b);
    printf("a || b : %d\n", a || b);
    printf("!a: %d\n", !a);
    return 0;
}
````
**Output**
```
a && b : 1
a || b : 1
!a: 0
```
### 4.Bitwise Operators
The [Bitwise operators](https://www.geeksforgeeks.org/c/bitwise-operators-in-c-cpp/) perform operations directly on the binary representation of integers. They are widely used in low-level programming and performance-critical applications.
- Useful for flags, masks, and hardware programming.
- Generally faster than equivalent arithmetic operations.
> **Note:** Mathematical operations such as addition, subtraction, multiplication, etc. can be performed at the bit level for faster processing.
| Symbol | **Operator** | Description | Syntax |
| --- | --- | --- | --- |
| **&** | **Bitwise AND** | Performs bit-by-bit AND operation and returns the result. | **a & b** |
| **|** | **Bitwise OR** | Performs bit-by-bit OR operation and returns the result. | **a | b** |
| **^** | **Bitwise XOR** | Performs bit-by-bit XOR operation and returns the result. | **a ^ b** |
| **~** | **Bitwise First Complement** | Flips all the set and unset bits on the number. | **~a** |
| **<<** | **Bitwise Leftshift** | Shifts bits to the left by a given number of positions; multiplies the number by 2 for each shift. | **a << b** |
| **>>** | **Bitwise Rightshift** | Shifts bits to the right by a given number of positions; divides the number by 2 for each shift. | **a >> b** |
````c
#include <stdio.h>
int main() {
    int a = 25, b = 5;
    // using operators and printing results
    printf("a & b: %d\n", a & b);
    printf("a | b: %d\n", a | b);
    printf("a ^ b: %d\n", a ^ b);
    printf("~a: %d\n", ~a);
    printf("a >> b: %d\n", a >> b);
    printf("a << b: %d\n", a << b);
    return 0;
}
````
**Output**
```
a & b: 1
a | b: 29
a ^ b: 28
~a: -26
a >> b: 0
a << b: 800
```
### 5. Assignment Operators
[Assignment operators](https://www.geeksforgeeks.org/c/assignment-operators-in-c-c/) are used to assign values to variables. Compound assignment operators combine assignment with another operation, making code shorter and more readable.
- Simplify expressions using compound operators.
- Improve code readability.
| Symbol | **Operator** | Description | Syntax |
| --- | --- | --- | --- |
| **=** | **Simple Assignment** | Assign the value of the right operand to the left operand. | **a = b** |
| **+=** | **Plus and assign** | Add the right operand and left operand and assign this value to the left operand. | **a += b** |
| **-=** | **Minus and assign** | Subtract the right operand and left operand and assign this value to the left operand. | **a -= b** |
| **\*=** | **Multiply and assign** | Multiply the right operand and left operand and assign this value to the left operand. | **a \*= b** |
| **/=** | **Divide and assign** | Divide the left operand with the right operand and assign this value to the left operand. | **a /= b** |
| **%=** | **Modulus and assign** | Assign the remainder in the division of left operand with the right operand to the left operand. | **a %= b** |
| **&=** | **AND and assign** | Performs bitwise AND and assigns this value to the left operand. | **a &= b** |
| **|=** | **OR and assign** | Performs bitwise OR and assigns this value to the left operand. | **a |= b** |
| **^=** | **XOR and assign** | Performs bitwise XOR and assigns this value to the left operand. | **a ^= b** |
| **>>=** | **Rightshift and assign** | Performs bitwise Rightshift and assign this value to the left operand. | **a >>= b** |
| **<<=** | **Leftshift and assign** | Performs bitwise Leftshift and assign this value to the left operand. | **a <<= b** |
````c
#include <stdio.h>
int main() {
    int a = 25, b = 5;
    // using operators and printing results
    printf("a = b: %d\n", a = b);
    printf("a += b: %d\n", a += b);
    printf("a -= b: %d\n", a -= b);
    printf("a *= b: %d\n", a *= b);
    printf("a /= b: %d\n", a /= b);
    printf("a %%= b: %d\n", a %= b);
    printf("a &= b: %d\n", a &= b);
    printf("a |= b: %d\n", a |= b);
    printf("a ^= b: %d\n", a ^= b);
    printf("a >>= b: %d\n", a >>= b);
    printf("a <<= b: %d\n", a <<= b);
    return 0;
}
````
**Output**
```
a = b: 5
a += b: 10
a -= b: 5
a *= b: 25
a /= b: 5
a %= b: 0
a &= b: 0
a |= b: 5
a ^= b: 0
a >>= b: 0
a <<= b: 0
```
## **Other Operators**
Apart from the above operators, there are some other operators available in C used to perform some specific tasks. Some of them are discussed here: 
### 1. sizeof Operator
[sizeof](https://www.geeksforgeeks.org/c/sizeof-operator-c/) is much used in the C programming language. It is a compile-time unary operator which can be used to compute the size of its operand.
**Syntax**
> sizeof (operand)
### 2. Comma Operator ( , )
The [comma operator](https://www.geeksforgeeks.org/c/comma-in-c/) (represented by the token) is a binary operator that evaluates its first operand and discards the result, it then evaluates the second operand and returns this value (and type).
**Syntax**
> operand1 , operand2
### 3. Conditional Operator ( ? : )
The [**conditional operator**](https://www.geeksforgeeks.org/c/conditional-or-ternary-operator-in-c/) is the only ternary operator in C. It is a conditional operator that we can use in place of if..else statements.
**Syntax**
> expression1 ? Expression2 : Expression3;
Here, Expression1 is the condition to be evaluated. If the condition(Expression1) is True then we will execute and return the result of Expression2 otherwise if the condition(Expression1) is false then we will execute and return the result of Expression3.
### 4. dot (.) and arrow (->) Operators
Member operators are used to reference individual members of classes, structures, and unions.
- The [**dot operator**](https://www.geeksforgeeks.org/c/dot-operator-in-c/) is applied to the actual object.
- The [**arrow operator**](https://www.geeksforgeeks.org/c/arrow-operator-in-c-c-with-examples/) is used with a pointer to an object.
**Syntax**
> structure\_variable . member;
> structure\_pointer -> member;
### 5. Cast Operators
[**Casting operators**](https://www.geeksforgeeks.org/cpp/casting-operators-in-cpp/) convert one data type to another. For example, (int)2.2000 would return 2. A cast is a special operator that forces one data type to be converted into another. 
**Syntax**
> (new\_type) operand;
### 6. addressof (&) and Dereference (\*) Operators
[Addressof operator &](https://www.geeksforgeeks.org/cpp/address-operator-in-c/) returns the address of a variable and the [dereference operator \*](https://www.geeksforgeeks.org/cpp/dereference-pointer-in-c/) is used to access the value stored at that address.
Example of Other C Operators
````c
#include <stdio.h>
int main()
{
    // integer variable
    int num = 10;
    int* add_of_num = &num;
    printf("sizeof(num) = %d bytes\n", sizeof(num));
    printf("&num = %p\n", &num);
    printf("*add_of_num = %d\n", *add_of_num);
    printf("(10 < 5) ? 10 : 20 = %d\n", (10 < 5) ? 10 : 20);
    printf("(float)num = %f\n", (float)num);
    return 0;
}
````
**Output**
```
sizeof(num) = 4 bytes
&num = 0x7ffdb58c037c
*add_of_num = 10
(10 < 5) ? 10 : 20 = 20
(float)num = 10.000000
```
> **Related article:** [Operator Precedence and Associativity](https://www.geeksforgeeks.org/c/operator-precedence-and-associativity-in-c/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/c/operators-in-c/)

## GATE CS

- Subject: Data Structures & C Programming
- Topic: Programming in C

> [!note] Related notes
>
> - [[Data Types in C]]
> - [[Enum, Struct & Union in C]]
> - [[Functions in C]]
> - [[Introduction to C Programming]]
> - [[Pointers in C]]
> - [[Scope of a Variable]]
> - [[Type Casting in C]]
> - [[Variables in C]]
> - [[1D, 2D and 3D Arrays]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
