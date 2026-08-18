---
title: "Non-Restoring Division For Unsigned Integer"
subject: "Digital Logic and Design"
topic: "Number Representation and Computer Arithmetic"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/non-restoring-division-unsigned-integer/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Number Representation and Computer Arithmetic"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/number-representation-and-computer-arithmetic
---


> [!abstract] Non-Restoring Division For Unsigned Integer
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Number Representation and Computer Arithmetic`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/non-restoring-division-unsigned-integer/)

---

# Non-Restoring Division For Unsigned Integer

The non-restoring division algorithm is a faster method to divide binary numbers. Unlike traditional division, it avoids repeatedly adding back the divisor, making it more efficient for computers to perform.
- It uses repeated subtraction and addition to find the quotient bits.
- If subtraction gives a negative result, the algorithm just adds in the next step instead of fixing it.
## **Flow Chart of Non-Restoring Division For Unsigned Integer**
![start-](assets/start--fd7f3e4cc2.webp)
## Steps Involved in the Non-Restoring Division Algorithm
Step-1: First, the registers are initialized with corresponding values (Q = Dividend, M = Divisor, A = 0, n = number of bits in dividend)
Step-2: Shift left the contents of (A, Q) as a combined register
Step-3: Check the sign bit of register A
- If the sign bit is 0, perform A = A − M
- If the sign bit is 1, perform A = A + M
Step-4: Check the sign bit of register A again
Step-5: If the sign bit is 0, set Q[0] = 1; otherwise, set Q[0] = 0 (Q[0] is the least significant bit of register Q)
Step-6: Decrement the value of n by 1
Step-7: If n is not equal to zero, go to Step-2; otherwise, proceed to the next step
Step-8: If the sign bit of A is 1, perform A = A + M
Step-9: Register Q contains the quotient and register A contains the remainder
## Example
Let’s divide the binary number 1011 (which is 11 in decimal) by 0011 (which is 3 in decimal) using the Non-Restoring Division Algorithm.
**Initialization:**
- Dividend (Q) = 1011
- Divisor (M) = 0011
- Accumulator (A) = 0000
- Number of bits (n) = 4
### **Step-by-Step Solution**
**1. Initial Setup:**
- Q = 1011
- M = 0011
- A = 0000
- n = 4
**2. First Iteration:**
- Shift Left AQ: A = 0000, Q = 1011 becomes A = 0000, Q = 0110
- **Perform Operation:**  A = A - M = 0000 - 0011 = 1101 (2's complement of 0011)
- Sign Bit of A: 1
- Update Q[0]: 0
- Decrement N: N = 3
**3. Second Iteration:**
- Shift Left AQ: A = 1101, Q = 0110 becomes A = 1010, Q = 1100
- Perform Operation (Since previous A < 0) : A = A + M = 1010 + 0011 = 1101
- Sign Bit of A: 1
- Update Q[0]: 0
- Decrement N: N = 2
**4. Third Iteration:**
- Shift Left AQ: A = 1101, Q = 1100 becomes A = 1011, Q = 1000
- Perform Operation: A = A - M = 1011 - 0011 = 1000 (2's complement of 0011)
- Sign Bit of A: 1
- Update Q[0]: 0
- Decrement N: N = 1
**5. Fourth Iteration:**
- Shift Left AQ: A = 1000, Q = 1000 becomes A = 0001, Q = 0000
- Perform Operation: A = A + M = 0001 + 0011 = 0010
- Sign Bit of A: 0
- Update Q[0]: 1
- Decrement N: N = 0
**6. Final Adjustment:**
If the sign bit of A is 1 (A < 0), perform A = A + M; otherwise, no adjustment is required.
- Quotient (Q) = 0011 (3 in decimal)
- Remainder (A) = 0010 (2 in decimal)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/non-restoring-division-unsigned-integer/)

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
> - [[Number System and base conversions]]
> - [[Program for Binary To Decimal Conversion]]
> - [[Program for Decimal to Binary Conversion]]
