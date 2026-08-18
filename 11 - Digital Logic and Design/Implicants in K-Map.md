---
title: "Various Implicants in K-Map"
subject: "Digital Logic and Design"
topic: "Introduction of Boolean Algebra and Logic Gates"
source: "https://www.geeksforgeeks.org/engineering-mathematics/various-implicants-in-k-map/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Introduction of Boolean Algebra and Logic Gates"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/introduction-of-boolean-algebra-and-logic-gates
---


> [!abstract] Various Implicants in K-Map
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Introduction of Boolean Algebra and Logic Gates`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/various-implicants-in-k-map/)

---

# Various Implicants in K-Map

An implicant can be defined as a product/minterm term in Sum of Products ([SOP](https://www.geeksforgeeks.org/digital-logic/what-is-sum-of-product-sop-form/)) or sum/maxterm term in Product of Sums (POS) of a [Boolean function](https://www.geeksforgeeks.org/digital-logic/boolean-functions/). For example, consider a Boolean function, F = AB + ABC + BC. Implicants are AB, ABC, and BC. 
There are various implicant in K-Map listed below :
- Prime Implicant (PI)
- Essential Prime Implicant (EPI)
- Redundant Prime Implicant (RPI)
- Selective Prime Implicant (SPI)
POS and SOP are the types of [boolean expression](https://www.geeksforgeeks.org/dsa/boolean-search/) formed according to the given K-Map. [POS](https://www.geeksforgeeks.org/digital-logic/what-is-product-of-sum-pos-form/) stands for Product of Sum created by using maxterms and [SOP](https://www.geeksforgeeks.org/digital-logic/what-is-sum-of-product-sop-form/) stands for Sum of Product created by using minterms.
## **Prime Implicants**
A group of squares or rectangles made up of a bunch of adjacent [minterms](https://www.geeksforgeeks.org/digital-logic/what-is-minterm/) which is allowed by the definition of K-Map are called **prime implicants(PI)** i.e. all possible groups formed in [K-Map.](https://www.geeksforgeeks.org/digital-logic/introduction-of-k-map-karnaugh-map/)
### Example of Prime Implicants
Here we have an example of prime implicant for better understanding given below :
![Prime Implicants](assets/pi-17a67ead1a.png)
## **Essential Prime Implicants**
These are those subcubes(groups) that cover at least one minterm that can't be covered by any other prime implicant. **Essential prime implicants(EPI)** are those prime [implicants](https://www.geeksforgeeks.org/digital-logic/prime-implicants-and-explicit-implicants/) that always appear in the final solution. 
### Example of Essential Prime Implicants
![Essential Prime Implicants](assets/x1-3d86651df2.png)
## **Redundant Prime Implicants**
The prime implicants for which each of its minterm is covered by some essential prime implicant are **redundant prime implicants(RPI)**. This prime implicant never appears in the final solution. 
### Example of Redundant Prime Implicants
Here, we have an example with one redundant prime implicant.
![Redundant Prime Implicants](assets/x2-0768b2ad9b.png)
## **Selective Prime Implicants**
The prime implicants for which are neither essential nor redundant prime implicants are called **selective prime implicants(SPI)**. These are also known as non-essential prime implicants. They may appear in some solution or may not appear in some solution. 
### Example of Selective Prime Implicants
![Selective Prime Implicants](assets/x3-144ba9fbbd.png)
## Solved Examples of Various Implicants in K-Map
Here we have examples of prime implicant for better understanding given below :
### **Example 1**
Given F = ∑(1, 5, 6, 7, 11, 12, 13, 15), find number of implicant, PI, EPI, RPI and SPI. 
![pi-5](assets/pi-5-61254bcd41.png)
> **Expression : BD + A'C'D + A'BC+ ACD+ABC'**
>
> No. of Prime Implicants(PI) = 5 {1,2,3,4,5}
> No. of Essential Prime Implicants(EPI) = 4 {1,2,3,4}
> No. of Redundant Prime Implicants(RPI) = 1 {5}
> No. of Selective Prime Implicants(SPI) = 0
### **Example 2**
Given F = ∑(0, 1, 5, 8, 12, 13), find number of implicant, PI, EPI, RPI and SPI. 
![pi-6-1](assets/pi-6-1-ad534e3051.png)
> **Expression : A'B'C'+ C'DB + C'D'A**
>
> No. of Prime Implicants(PI) = 6 {1,2,3,4,5,6}
> No. of Essential Prime Implicants(EPI) = 0
> No. of Redundant Prime Implicants(RPI) = 0
> No. of Selective Prime Implicants(SPI) = 6 {1,2,3,4,5,6}
### **Example 3**
Given F = ∑(0, 1, 5, 7, 15, 14, 10), find number of implicant, PI, EPI, RPI and SPI.  
![pi-7](assets/pi-7-f7cb2ed92a.png)
> No. of Prime Implicants(PI) = 6 {1,2,3,4,5,6}
> No. of Essential Prime Implicants(EPI) = 2 {1,4}
> No. of Redundant Prime Implicants(RPI) = 2
> No. of Selective Prime Implicants(SPI) = 4 {2,3,5,6}
**Read More:**
- [Introduction of K-Map (Karnaugh Map)](https://www.geeksforgeeks.org/digital-logic/introduction-of-k-map-karnaugh-map/)
- [5 variable K-Map in Digital Logic - GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/introduction-of-k-map-karnaugh-map/)
## Practices Problems
**1. Finding Prime Implicants**
- Simplify the following Boolean function using a K-Map and identify all prime implicants:
f(A, B, C, D) = ∑(0, 1, 2, 5, 8, 9, 10, 14)
**2. Minimization with Don't Care Conditions**
- Given the Boolean function with don't care conditions, use a K-Map to minimize it:
f(A, B, C) = ∑(0, 1, 2, 5, 7) + d(3, 6)
**3. Finding Essential Prime Implicants**
- For the following function, find the essential prime implicants using a K-Map:
f(A, B, C, D) = ∑(1, 3, 7, 11, 15) + d(0, 2, 5)
**4. Four-Variable K-Map Minimization**
- Simplify the given Boolean function using a 4-variable K-Map:
f(A, B, C, D) = ∑(1, 3, 7, 11, 15, 19, 23, 27, 31)
**5. Implicants and Essential Prime Implicants**
- Determine all implicants and essential prime implicants for the function:
f(A, B, C) = ∑(0, 1, 2, 3, 5, 7)
**6. Three-Variable K-Map Simplification**
- Use a 3-variable K-Map to simplify the Boolean function:
f(A, B, C) = ∑(1, 3, 4, 6, 7)
**7. Five-Variable K-Map Minimization**
- Simplify the following Boolean function using a 5-variable K-Map:
f(A, B, C, D, E) = ∑(1, 3, 7, 15, 31)
**8. Minimizing Boolean Expressions with Don't Cares**
- Given the function and don't care conditions, use a K-Map to minimize:
f(A, B, C, D) =∑(2, 3, 5, 7, 11, 13) + d(0, 1, 9, 15)
**9. Identification of Prime and Essential Prime Implicants**
- For the following Boolean function, identify all prime implicants and essential prime implicants:
f(A, B, C, D) = ∑(4, 5, 6, 7, 12, 13, 14, 15)
**10. Simplification Using K-Map with Multiple Variables**
- Simplify the Boolean function using a K-Map and identify any essential prime implicants:
f(A, B, C, D, E) = ∑(0, 1, 2, 5, 8, 9, 10, 14, 16, 17, 18, 21)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/various-implicants-in-k-map/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Introduction of Boolean Algebra and Logic Gates

> [!note] Related notes
>
> - [[Boolean functions]]
> - [[Canonical and Standard Form]]
> - [[Consensus Theorem]]
> - [[Functional Completeness]]
> - [[K-Map]]
> - [[Logic Gates]]
> - [[Logical gates in logic design]]
> - [[Minimization of Boolean Functions]]
> - [[PDNF and PCNF]]
> - [[Prime implicants and Explicit implicants]]
