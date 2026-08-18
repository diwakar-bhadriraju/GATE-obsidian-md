---
title: "Modular Addition"
subject: "Discrete Mathematics"
topic: "Algebraic and Set-Theoretic Structures"
source: "https://www.geeksforgeeks.org/engineering-mathematics/modular-addition/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Algebraic and Set-Theoretic Structures"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/algebraic-and-set-theoretic-structures
---


> [!abstract] Modular Addition
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Algebraic and Set-Theoretic Structures`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/modular-addition/)

---

# Modular Addition

Modular addition is a basic math concept used in computers and number systems. It is commonly used in areas like cryptography (data security), coding, and digital signal processing. In modular addition, you add two numbers normally, but if the result reaches a certain fixed number (called the modulus), it starts again from zero just like how a clock resets after 12 hours.
## Modular Addition
Modular addition involves adding two numbers and then taking the remainder when the sum is divided by a modulus.
Computers use finite data types (like 8-bit, 16-bit, 32-bit integers), so modular behavior naturally occurs when values exceed the maximum representable number (e.g., 255 in 8-bit).
Understanding modular addition helps avoid overflow bugs and makes it easier to implement efficient and secure algorithms.
> For integers a and b and a positive integer n(the modulus), the modular addition of a and b is given by: (a + b) mod n
Where:
- a and b are integers (operands),
- n is the modulus (a fixed positive integer),
- The result is the remainde**r** when a+b is divided by n.
### Modular Addition Example
For a = 7, b = 5, and n = 6:
(7 + 5) mod 6 = 12 mod 6 = 0, since 6 divides 12 completely so no remainder left.
### Properties of Modular Addition
Modular addition has several important properties that make it useful in various applications:
> **Commutative Property:** (a + b) mod n = (b + a) mod n
**Example:**
(7 + 5) mod 6
= 12 mod 6
= 0
(5 + 7) mod 6
= 12 mod 6
= 0
> **Associative Property:** (a + (b + c)) mod n = ((a + b) + c) mod n
**Example:**
(7 + (5 + 4) mod 6
= (7 + 9) mod 6
= 16 mod 6
= 4
> **Identity Element** : The identity element for modular addition is 0: (a + 0) mod n = a mod n
**Example:**
(7 + 0) mod 6
= 7 mod 6
= 1
> **Inverse Element** : For each integer a in modular arithmetic, there exists an inverse element - a such that: (a + (-a)) mod n = 0
**Example:**
For a = 5 and n = 6:
(5 + (-5)) mod 6
= 0
### **Applications In Real World**
**Cryptography :**
- Modular arithmetic (including addition) is central to algorithms like [RSA](https://www.geeksforgeeks.org/computer-networks/rsa-algorithm-cryptography/), [Diffie-Hellman](https://www.geeksforgeeks.org/computer-networks/diffie-hellman-key-exchange-and-perfect-forward-secrecy/), [AES](https://www.geeksforgeeks.org/computer-networks/advanced-encryption-standard-aes/), and [Elliptic Curve Cryptography.](https://www.geeksforgeeks.org/ethical-hacking/blockchain-elliptic-curve-cryptography/)
- It ensures operations stay within a fixed number range, which helps preserve security features like key wrapping and encryption cycles.
**Hash Functions :**
- Modular addition is used to combine data pieces efficiently while keeping results within a manageable range.
**Digital Signal Processing (DSP) :**
- In [DSP](https://www.geeksforgeeks.org/electronics-engineering/what-is-digital-signal-processing/), signals are often processed in modular formats to limit overflow and control data flow in systems like audio and image processing.
**Computer Graphics and Gaming :**
- Used in cyclic animations, game state updates, and circular buffers.
**Coding Theory :**
- Modular arithmetic ensures that encoded messages can be transmitted and decoded efficiently and correctly over noisy channels.
### Also Check:
> - [Modular Arithmetic](https://www.geeksforgeeks.org/engineering-mathematics/modular-arithmetic/)
> - [Modular Arithmetic for Competitive Programming](https://www.geeksforgeeks.org/competitive-programming/modular-arithmetic-for-competitive-programming/)
> - [Modular Multiplication](https://www.geeksforgeeks.org/dsa/modular-multiplication/)
> - [Modular Exponentiation](https://www.geeksforgeeks.org/dsa/modular-exponentiation-power-in-modular-arithmetic/)
### Solved Examples
**Example 1: (1234 + 5678) mod 97**
> Step 1: Add the numbers
>
> 1234 + 5678 = 6912
>
> Step 2: Divide by the modulus and find the remainder
>
> 6912 ÷ 97 = 71 remainder 25
>
> Therefore, (1234 + 5678) mod 97 = 25
**Example 2: (2^50 + 3^40) mod 101**
> Step 1: Calculate 2^50 mod 101 and 3^40 mod 101 separately using Euler's theorem or repeated squaring.
>
> 2^50 mod 101 = 100
>
> 3^40 mod 101 = 1
>
> Step 2: Add the results
>
> (100 + 1) mod 101 = 0
>
> Therefore, (2^50 + 3^40) mod 101 = 0
**Example 3: (123456789 + 987654321) mod 1000000007**
> Step 1: Add the numbers
>
> 123456789 + 987654321 = 1111111110
>
> Step 2: Take the modulus
>
> 1111111110 mod 1000000007 = 111111103
>
> Therefore, (123456789 + 987654321) mod 1000000007 = 111111103
**Example 4: (factorial(20) + fibonacci(30)) mod 1009**
> Step 1: Calculate factorial(20) and fibonacci(30)
>
> factorial(20) = 2432902008176640000
>
> fibonacci(30) = 832040
>
> Step 2: Add these numbers
>
> 2432902008176640000 + 832040 = 2432902008177472040
>
> Step 3: Take the modulus
>
> 2432902008177472040 mod 1009 = 24
>
> Therefore, (factorial(20) + fibonacci(30)) mod 1009 = 24
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/modular-addition/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Algebraic and Set-Theoretic Structures

> [!note] Related notes
>
> - [[Cartesian Product of Two Sets]]
> - [[Classes of Functions]]
> - [[Closure of Relations]]
> - [[Composition of Functions]]
> - [[Equivalence Relations]]
> - [[Groups]]
> - [[Hasse Diagrams]]
> - [[Introduction to Set Theory]]
> - [[Inverse Functions]]
> - [[Multiplication Modulo]]
