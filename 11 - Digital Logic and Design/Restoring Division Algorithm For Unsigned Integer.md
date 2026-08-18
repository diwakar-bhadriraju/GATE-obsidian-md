---
title: "Restoring Division Algorithm For Unsigned Integer"
subject: "Digital Logic and Design"
topic: "Number Representation and Computer Arithmetic"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/restoring-division-algorithm-unsigned-integer/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Number Representation and Computer Arithmetic"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/number-representation-and-computer-arithmetic
---


> [!abstract] Restoring Division Algorithm For Unsigned Integer
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Number Representation and Computer Arithmetic`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/restoring-division-algorithm-unsigned-integer/)

---

# Restoring Division Algorithm For Unsigned Integer

The Restoring Division Algorithm is a method for dividing two unsigned integers in binary form, producing a quotient and remainder through iterative shifting and subtraction.
- It uses registers for the quotient (Q), remainder (A), and divisor (M).
- If subtraction gives a negative result, the remainder is restored to its previous value, and the quotient bit is set to zero, hence the term "restoring."
![union_set](assets/union_set-a10aaa7e63.webp)
Initially, register Q contains the dividend and register A is set to 0. After completion, Q contains the quotient and A contains the remainder. Here, an n-bit dividend is loaded in Q and the divisor is loaded in M. The Value of Register is initially kept 0, and this is the register whose value is restored during iteration, due to which it is named Restoring.
![union_t](assets/union_t-c1a24e4bbd.webp)
### **Steps for Restoring Division Algorithm**
- **Step-1:** First the registers are initialized with corresponding values (Q = Dividend, M = Divisor, A = 0, n = number of bits in dividend)
- **Step-2:** Then the content of register A and Q is shifted left as if they are a single unit
- **Step-3:** Then content of register M is subtracted from A and result is stored in A
- **Step-4:** Then the most significant bit of the A is checked if it is 0 the least significant bit of Q is set to 1 otherwise if it is 1 the least significant bit of Q is set to 0 and value of register A is restored i.e the value of A before the subtraction with M
- **Step-5:** The value of counter n is decremented
- **Step-6:** If the value of n becomes zero we exit the loop otherwise we repeat from step 2
- **Step-7:** Finally, the register Q contain the quotient and A contain remainder
## Unsigned Integer
Unsigned integers store only non-negative numbers. Signed integers use the first bit for the sign (0 = positive, 1 = negative), while unsigned use all bits for value. In 8-bit form, unsigned integers range from 0 to 255. They are used in computing when only positive values or a larger range is required.
## **Slow Algorithm and Fast Algorithm**
Slow division algorithms include restoring, non-restoring, and SRT algorithms. Fast algorithms include Newton–Raphson and Goldschmidt methods. In this article, will be performing restoring algorithm for unsigned integer. Restoring term is due to fact that value of register A is restored after each iteration.
## **Example Restoring Division Algorithm**
> Perform Division Restoring Algorithm Dividend = 11 Divisor = 3
| n | M | A | Q | Operation |
| --- | --- | --- | --- | --- |
| 4 | 00011 | 00000 | 1011 | initialize |
|  | 00011 | 00001 | 011\_ | shift left AQ |
|  | 00011 | 11110 | 011\_ | A=A-M |
|  | 00011 | 00001 | 0110 | Q[0]=0 And restore A |
| 3 | 00011 | 00010 | 110\_ | shift left AQ |
|  | 00011 | 11111 | 110\_ | A=A-M |
|  | 00011 | 00010 | 1100 | Q[0]=0 |
| 2 | 00011 | 00101 | 100\_ | shift left AQ |
|  | 00011 | 00010 | 100\_ | A=A-M |
|  | 00011 | 00010 | 1001 | Q[0]=1 |
| 1 | 00011 | 00101 | 001\_ | shift left AQ |
|  | 00011 | 00010 | 001\_ | A=A-M |
|  | 00011 | 00010 | 0011 | Q[0]=1 |
Remember to restore the value of A most significant bit of A is 1. As that register Finally, register Q contains the quotient (3) and register A contains the remainder (2).
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/restoring-division-algorithm-unsigned-integer/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Number Representation and Computer Arithmetic

> [!note] Related notes
>
> - [[Booth’s Algorithm]]
> - [[Code Converters – BCD(8421) to from Excess-3]]
> - [[Code Converters – Binary to from Gray Code]]
> - [[Computer Arithmetic Set – 1]]
> - [[Computer Arithmetic Set – 2]]
> - [[Floating Point Representation]]
> - [[Last Minute Notes – Digital Electronics]]
> - [[Non-Restoring Division For Unsigned Integer]]
> - [[Number System and base conversions]]
> - [[Program for Binary To Decimal Conversion]]
