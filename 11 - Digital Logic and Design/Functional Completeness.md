---
title: "Functional Completeness in Digital Logic"
subject: "Digital Logic and Design"
topic: "Introduction of Boolean Algebra and Logic Gates"
source: "https://www.geeksforgeeks.org/digital-logic/functional-completeness-in-digital-logic/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Introduction of Boolean Algebra and Logic Gates"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/introduction-of-boolean-algebra-and-logic-gates
---


> [!abstract] Functional Completeness in Digital Logic
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Introduction of Boolean Algebra and Logic Gates`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/functional-completeness-in-digital-logic/)

---

# Functional Completeness in Digital Logic

A set of Boolean functions (or logic operations) is functionally complete (or universal) if every Boolean function can be implemented using only the functions in that set. For example:
- Set A = {+, ·, '} (OR, AND, NOT) is functionally complete.
- Set B = {+, '} (OR, NOT) is functionally complete.
- Set C = {·, '} (AND, NOT) is functionally complete.
## **Post's Functional Completeness Theorem**
A set of Boolean functions is functionally complete if and only if it is not completely contained in any one of the five closed classes: T₀, T₁, S, M, and L.
**The Five Closed Classes**
1. **T₀ (0-Preserving Functions):** Functions for which f(0,0,…,0) = 0.
2. **T₁ (1-Preserving Functions):** Functions for which f(1,1,…,1) = 1.
3. **S (Self-Dual Functions):** Functions whose output becomes the opposite when all inputs are complemented (0 becomes 1 and 1 becomes 0).
4. **M (Monotonic Functions):** Functions whose output never decreases when any input changes from 0 to 1 while all other inputs remain unchanged.
5. **L (Linear Functions):** Functions that can be written using only XOR (⊕) operations and constants.
**Theorem**
A set of Boolean functions is functionally complete if, for each of the five classes (T₀, T₁, S, M, and L), the set contains at least one function that does not belong to that class.
The minimal functionally complete operator sets are:
- Single-element sets: {NAND}, {NOR}
- Two-element sets: {OR, NOT}, {AND, NOT}, {Implication, FALSE}, {Converse Implication, FALSE}, {Implication, TRUE}, {Converse Implication, TRUE}, and other equivalent pairs.
- Three-element sets: {OR, XOR, NOT}, {OR, XNOR, TRUE}, {AND, XOR, NOT}, {AND, XNOR, TRUE}, and other equivalent triples.
## Advantages
- **Flexibility:** A functionally complete set can represent any boolean function.
- **Efficiency:** Complex circuits can be built using a small set of basic logic gates, reducing design complexity.
- **Universality:** It can be used to implement any digital logic circuit.
## Disadvantages
- **Complexity:** Functionally complete sets can be difficult for beginners to understand and use.
- **Less Efficient Implementations:** Using only one operator set may require more gates than using a mix of logic gates.
- **Non-Intuitiveness:** They are based on mathematical concepts, making them less intuitive to understand.
## **Solved Examples of Functional Completeness**
### **Example 1**
Check if function F(A, B, C) = A' + BC' is functionally complete.
**Solution:**
F(A,A,A)=A′ + AA′ = A′
F(B,B,B) = B′ + BB′ = B′
Substitute the above into the function:
F(A′,B,B′) = (A′)′ + B(B′)′ = A + B
Thus, we have obtained:
- Complement (NOT): A′
- OR: A + B
Since {OR, NOT} is a functionally complete operator set,
∴ F(A,B,C) = A′ + BC′ is functionally complete.
### **Example 2**
Check if function F(A, B) = A'B + AB' (EX-OR) is functionally complete.
**Solution:**
- F(A,1) = A′ → NOT is obtained.
- F(A,A) = 0 → Constant 0 is obtained.
- F(A,B′) = A′B′ + AB → XNOR is obtained.
NOT, 0, and XNOR are obtained, but no functionally complete operator set can be derived.
∴ F(A,B) = A′B + AB′ (XOR) is not functionally complete.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/functional-completeness-in-digital-logic/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Introduction of Boolean Algebra and Logic Gates

> [!note] Related notes
>
> - [[Boolean functions]]
> - [[Canonical and Standard Form]]
> - [[Consensus Theorem]]
> - [[Implicants in K-Map]]
> - [[K-Map]]
> - [[Logic Gates]]
> - [[Logical gates in logic design]]
> - [[Minimization of Boolean Functions]]
> - [[PDNF and PCNF]]
> - [[Prime implicants and Explicit implicants]]
