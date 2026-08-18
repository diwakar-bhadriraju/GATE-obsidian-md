---
title: "Properties of Boolean Algebra"
subject: "Digital Logic and Design"
topic: "Introduction of Boolean Algebra and Logic Gates"
source: "https://www.geeksforgeeks.org/maths/properties-of-boolean-algebra/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Introduction of Boolean Algebra and Logic Gates"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/introduction-of-boolean-algebra-and-logic-gates
---


> [!abstract] Properties of Boolean Algebra
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Introduction of Boolean Algebra and Logic Gates`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/properties-of-boolean-algebra/)

---

# Properties of Boolean Algebra

Boolean Algebra is a branch of mathematics that deals with binary values, 0 and 1, and is widely used in digital electronics and computer systems to simplify logical expressions.
> **Note:** In Boolean Algebra, the symbol **+** represents the [OR](https://www.geeksforgeeks.org/digital-logic/or-gate/) operation (Boolean addition), and the symbol **·** represents the [AND](https://www.geeksforgeeks.org/digital-logic/and-gate/) operation (Boolean multiplication).
The properties (laws) are the basic rules used to simplify Boolean expressions.
![properties-of-boolean-Algebra](assets/properties-of-boolean-Algebra-83ebf22da9.webp)
### **Annulment law**
A variable ANDed with 0 gives 0, while a variable ORed with 1 gives 1, i.e., 
> A.0 = 0 
>
> A + 1 = 1 
### **Identity law**
In this law variable remains unchanged it is ORed with '0' or ANDed with '1', i.e., 
> A.1 = A 
>
> A + 0 = A 
### **Idempotent law**
A variable remains unchanged when it is ORed or ANDed with itself, i.e., 
> A + A = A 
>
> A.A = A 
### **Complement law**
In this Law if a complement is added to a variable it gives one, if a variable is multiplied with its complement it results in '0', i.e., 
> A + A' = 1 
>
> A.A' = 0 
### **Double Negation Law**
A variable with two negations, its symbol gets cancelled out and original variable is obtained, i.e., 
> ((A)')'=A 
### **Commutative law**
A variable order does not matter in this law, i.e., 
> A + B = B + A 
>
> A.B = B.A 
### **Associative law**
The order of operation does not matter if the priority of variables are the same like '\*' and '/', i.e., 
> A+(B+C) = (A+B)+C 
>
> A.(B.C) = (A.B).C 
### **Distributive law**
This law governs the opening up of brackets, i.e., 
> A.(B+C) = (A.B)+(A.C)
>
> (A+B)(A+C) = A + BC 
### **Absorption law**
The absorption law consists of two dual statements:
> X.(X+Y) = X
>
> X+XY = X
### **De Morgan law**
In [De Morgan law](https://www.geeksforgeeks.org/maths/de-morgans-law/), the operation of an AND or OR logic circuit is unchanged if all inputs are inverted, the operator is changed from AND to OR, and the output is inverted, i.e., 
(A.B)' = A' + B' 
(A+B)' = A'.B'
> Consensus theorem
>
> AB + A'C + BC = AB + A'C
**➣Practice:** [Solved Examples](https://www.geeksforgeeks.org/maths/properties-of-boolean-algebra-practice-questions/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/properties-of-boolean-algebra/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Introduction of Boolean Algebra and Logic Gates

> [!note] Related notes
>
> - [[Boolean functions]]
> - [[Canonical and Standard Form]]
> - [[Consensus Theorem]]
> - [[Functional Completeness]]
> - [[Implicants in K-Map]]
> - [[K-Map]]
> - [[Logic Gates]]
> - [[Logical gates in logic design]]
> - [[Minimization of Boolean Functions]]
> - [[PDNF and PCNF]]
