---
title: "1's Complement Representation vs 2's Complement Representation"
subject: "Digital Logic and Design"
topic: "Number Representation and Computer Arithmetic"
source: "https://www.geeksforgeeks.org/digital-logic/difference-between-1s-complement-representation-and-2s-complement-representation-technique/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Number Representation and Computer Arithmetic"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/number-representation-and-computer-arithmetic
---


> [!abstract] 1's Complement Representation vs 2's Complement Representation
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Number Representation and Computer Arithmetic`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/difference-between-1s-complement-representation-and-2s-complement-representation-technique/)

---

# 1's Complement Representation vs 2's Complement Representation

1's Complement and 2's Complement are two methods to represent signed (positive and negative) integers in binary form. Both methods allow computers to perform arithmetic operations with both positive and negative numbers.
- **1's Complement:** Negative numbers are formed by inverting all bits of the positive number, but dual zero representations complicate arithmetic.
- **2's Complement:** Negative numbers are formed by inverting bits and adding 1, giving a single zero and streamlined arithmetic.
![1_s_complement](assets/1_s_complement-cee7573abd.webp)
## What is 1's Complement?
The **1's complement** of a binary number is obtained by **flipping all the bits**, i.e., converting every `0` to `1` and every `1` to `0`.
```
Let numbers be stored using 4 bits1’s complement of 0111 (7) is 10001’s complement of 1100 (12) is 0011
```
### Advantages of 1's Complement
- Easy to compute by flipping bits.
- Suitable for basic arithmetic operations with a simpler hardware design.
### Disadvantages of 1's Complement
- 1's complement has two representations of zero (0000 and 1111), which can cause complications in calculations.
- Addition requires an end-around carry, which can complicate arithmetic operations.
- Not as efficient in representing negative numbers compared to 2's complement.
## What is 2's Complement?
2's complement is another binary number representation technique used widely in modern computers. To obtain the 2's complement of a binary number, you invert all the bits (similar to 1's complement) and add 1 to the least significant bit.
In practice, computers do not compute the 2’s complement explicitly; arithmetic circuits handle negative numbers automatically using binary addition.
**2's complement** of a binary number is 1 added to the 1's complement of the binary number. Examples:
```
Let numbers be stored using 4 bits2’s complement of 0111 (7) is 10012’s complement of 1100 (12) is 0100
```
### Advantages of 2's Complement
- Only one representation of zero, which simplifies arithmetic operations.
- No need for an end-around carry when adding numbers; subtraction can be done by adding the negative.
- Negative numbers have the most significant bit as 1, providing a clear distinction.
### Disadvantages of 2's Complement
- Has an asymmetric range with one extra negative number, but this does not affect precision or arithmetic operations.
These representations are used for signed numbers.
The main difference between 1’s complement and 2’s complement is that 1’s complement has two representations of zero:
- 00000000 (+0)
- 11111111 (−0)
In 2’s complement, there is only one representation of zero:
- 00000000 (0)
This happens because adding 1 to 11111111 results in 100000000 (for 8-bit), and the overflow bit is discarded, leaving 00000000. Therefore, 2’s complement avoids duplicate zero representation and is widely used.
Another difference is in addition:
- In 1’s complement, after binary addition, any carry out of the most significant bit is added back (end-around carry).
- In 2’s complement, no end-around carry is required.
**Range of numbers:**
- 1’s complement (n bits):
$$
-(2^{n-1} - 1) \text{ to } (2^{n-1} - 1)
$$
- 2’s complement (n bits):
$$
-2^{n-1} \text{ to } (2^{n-1} - 1)
$$
## **1's Complement Representation vs 2's Complement Representation**
| 1's Complement | 2's Complement |
| --- | --- |
| Invert all bits | Invert all bits + add 1 |
| Two zeros (+0 and -0) | One zero (0) |
| Needs end-around carry | No carry needed |
| Range: −(2n-1−1) to (2n-1−1) | Range: -(2n-1) to (2n-1-1) |
| Rarely used | Standard in modern systems |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/difference-between-1s-complement-representation-and-2s-complement-representation-technique/)

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
