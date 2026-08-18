---
title: "Modular Multiplication"
subject: "Discrete Mathematics"
topic: "Algebraic and Set-Theoretic Structures"
source: "https://www.geeksforgeeks.org/dsa/modular-multiplication/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Algebraic and Set-Theoretic Structures"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/algebraic-and-set-theoretic-structures
---


> [!abstract] Modular Multiplication
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Algebraic and Set-Theoretic Structures`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/modular-multiplication/)

---

# Modular Multiplication

Given three integers `a`, `b`, and `M`, where `M` is the modulus. Compute the result of the modular multiplication of `a` and `b` under modulo `M.(`**(a×b) mod M**)
**Examples:**
> **Input:** a = 5, b = 3, M = 11
> **Output:** 4
> **Explanation:** a × b = 5 × 3 = 15, 15 % 11 = 4, so the result is 4.
>
> **Input:** a = 12, b = 15, M = 7
> **Output:** 5
> **Explanation:** a × b = 12 × 15 = 180, 180 % 7 = 5, so the result is 5.
Table of Content
- [Basic Principles of Modular Multiplication](#basic-principles-of-modular-multiplication)
- [Calculating Modular Multiplication](#calculating-modular-multiplication)
- [Interesting Properties of Modular Multiplication](#interesting-properties-of-modular-multiplication)
### Basic Principles of Modular Multiplication
Modular arithmetic, or clock arithmetic, is a system of arithmetic for integers, where numbers "wrap around" upon reaching a certain value. **Modular multiplication** is a specific operation within modular arithmetic.
**The Modulo Operation**
This modulo operation yields the remainder when the product of a and b is divided by M. The result is always an integer between 0 and M−1.
For example, 7 mod 3 results in 1 because when 7 is divided by 3, the remainder is 1. This operation is at the core of [modular arithmetic](https://www.geeksforgeeks.org/engineering-mathematics/modular-arithmetic/).
**Properties of Modular Multiplication**
Modular multiplication shares several properties with regular multiplication, which makes it a useful tool in various mathematical and computational contexts.
- Commutativity: **(a × b) mod M = (b × a) mod M**. The order of multiplication does not affect the result.
- Associative: **((a × b) ×c) mod M = (a× (b × c)) mod M**. The way in which numbers are grouped during multiplication does not affect the outcome.
- Distributivity: **(a × (b+c)) mod M = ((a×b) mod M +(a × c) mod M) mod M**. This property links multiplication and addition in modular arithmetic.
### Calculating Modular Multiplication
To calculate modular multiplication, follow these steps:
> 1. Multiply the two integers a and b.
> 2. Divide the product by the modulus M.
> 3. The remainder of this division is the result of the modular multiplication.
````cpp
#include <iostream>
using namespace std;
int modmul(int a, int b, int M) {
    return ((a % M) * (b % M)) % M;
}
int main() {
    int a = 5;
    int b = 3;
    int M = 11;
    cout << modmul(a, b, M);
}
````
````java
import java.io.*;
class GFG {
    public static int modmul(int a, int b, int M) {
        return ((((a % M) * (b % M)) % M));
    }
// Driver Code
    public static void main(String[] args) {
        int a = 5;
        int b = 3;
        int M = 11;
        System.out.println(modmul(a, b, M));
    }
}
````
````python3
def modmul(a, b, M):
    return (a % M) * (b % M) % M
if __name__ == "__main__":
    a = 5
    b = 3
    M = 11
    print(modmul(a, b, M))
````
````csharp
using System;
class GFG {
    public static int modmul(int a, int b, int M) {
        return (((a % M) * (b % M)) % M);
    }
    static void Main() {
        int a = 5;
        int b = 3;
        int M = 11;
        Console.WriteLine(modmul(a, b, M));
    }
}
````
````javascript
function modMul(a, b, M) {
    return Number(((a % M) * (b % M)) % (M));
}
// Driver Code
const a = 5;
const b = 3;
const M = 11;
console.log(modMul(a, b, M));
````
**Output**
```
4
```
Time Complexity: O(1)
Space Complexity: O(1)
### Interesting Properties of Modular Multiplication
> (a x b) mod M = ((a mod M) x (b mod M)) mod M 
> (a x b x c) mod M = ((a mod M) x (b mod M) x (c mod M)) mod M 
The same property holds for more than three numbers.
**Proof of Modular Multiplication Property**
**Proof:** If we prove for two numbers, then we can easily generalize it. Let us see proof for two numbers. 
> Let a % M = r1
> and b % M = r2
>
> Then a and b can be written as (using quotient
> theorem). Here q1 is quotient when we divide
> a by M and r1 is remainder. Similar meanings
> are there for q2 and r2
> a = M x q1 + r1
> b = M x q2 + r2
>
> LHS = (a x b) % M
>  = ((M x q1 + r1 ) x (M x q2 + r2) ) % M
>  = (M x M x q1 x q2 + M x q1 x r2 + M x q2 x r1 + r1 x r2 ) % M
>  = (M x (M x q1 x q2 + q1 x r2 + q2 x r1) + r1 x r2 ) % M
>
> We can eliminate the multiples of M when
> we take the mod M.
> LHS = (r1 x r2) % M
>
> RHS = (a % M x b % M) % M
>  = (r1 x r2) % M
>
> Hence, LHS = RHS
**Applications of Modular Multiplication**
Modular multiplication has several applications in various domains:
1. **Cryptography**: It is crucial in algorithms like RSA, where modular arithmetic ensures that encryption and decryption processes are secure and efficient.
2. **Hash Functions**: In computer science, modular multiplication is often used in hashing algorithms, which are used to map data of arbitrary size to fixed-size values.
3. **Digital Signal Processing**: Modular arithmetic is used in algorithms that process signals, images, and other forms of digital data.
4. **Gaming and Simulations**: Modular arithmetic is used to create cyclic behaviors, such as rotating objects or managing time cycles in simulations and video games.
**Modular Multiplication - FAQs**
**What is the modulus in modular multiplication?**
> The modulus is the number at which values "wrap around" in modular arithmetic. It defines the range within which the result must lie. For example, in (a×b) mod M, M is the modulus.
**Why is modular multiplication important in cryptography?**
> Modular multiplication is crucial in cryptographic algorithms, particularly RSA, where large numbers are involved. It ensures that values stay within manageable ranges while maintaining security, especially during encryption and decryption.
**How is modular multiplication different from regular multiplication?**
> While regular multiplication can result in very large numbers, modular multiplication confines the result within a specific range (0 to M−1) by using the modulus operation. This keeps the values within practical bounds for applications like cryptography and computer science.
**What are some real-life examples of modular arithmetic?**
> Modular arithmetic is used in situations like clock calculations, where numbers "reset" after reaching a limit (12 hours on a clock), and in systems where periodicity or repetition occurs, such as in encryption, hashing, and simulations.
**Can modular multiplication be applied to negative numbers?**
> Yes, modular multiplication can be applied to negative numbers. The result will still lie within the range defined by the modulus, though the process may involve adding the modulus to ensure the result is non-negative.
**Related article**
[Modular multiplicative inverse](https://www.geeksforgeeks.org/dsa/multiplicative-inverse-under-modulo-m/)[Modular arithmetic](https://www.geeksforgeeks.org/engineering-mathematics/modular-arithmetic/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/modular-multiplication/)

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
> - [[Modular Addition]]
