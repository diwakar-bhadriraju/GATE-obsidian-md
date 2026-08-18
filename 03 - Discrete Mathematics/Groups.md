---
title: "Group in Maths: Group Theory"
subject: "Discrete Mathematics"
topic: "Algebraic and Set-Theoretic Structures"
source: "https://www.geeksforgeeks.org/engineering-mathematics/groups-discrete-mathematics/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Algebraic and Set-Theoretic Structures"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/algebraic-and-set-theoretic-structures
---


> [!abstract] Group in Maths: Group Theory
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Algebraic and Set-Theoretic Structures`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/groups-discrete-mathematics/)

---

# Group in Maths: Group Theory

A group is a basic concept from abstract algebra. It describes a set of elements together with an operation that combines any two elements to form another element in the same set, following certain rules.
A group is a set(G) equipped with a single binary operation( \* ) that satisfies the following four properties:
**1. Closure:** For every pair of elements a and b in G, the result of the operation a \* b is also in G.
> a ∗ b ∈ G ,∀ a, b ∈ G
**2. Associativity:** For every three elements a, b, and c in G, the equation (a \* b) \* c = a \* (b \* c) holds.
> (a ∗ b) ∗ c = a ∗ (b ∗ c) ,∀ a, b, c ∈ G
**3. Identity Element:** There exists an element e in G (called the identity element) such that the given equation holds.
> e ∗ a =a ∗ e = a , ∃ e ∈ G such that ∀ a ∈ G
**4. Inverses:** For every in G, there exists an element a−1  in G (called the inverse of a ) such that
>  a ∗ a−1 =  a−1 ∗ a = e , ∀ a ∈ G, ∃ a-1 ∈ G 
![2056958165](assets/2056958165-ef1d70a2b5.webp)
## Examples of Group
Some of the important examples of groups are discussed below:
### **Integers under Addition (Z, +)**
- **Set:**  Z, the set of all integers {…, −3, −2, −1, 0, 1, 2, 3,…}.
- **Operation:**  Addition (+).
- **Identity Element:**  0 (since n + 0 = n for any integer n).
- **Inverse Element:**  For any integer n, the inverse is −n (since n + (−n) = 0).
### **Non-Zero Real Numbers under Multiplication (R, ⋅)**
- **Set:** R, the set of all non-zero real numbers.
- **Operation:**  Multiplication (⋅).
- **Identity Element:**  1 (since n ⋅ 1 = n for any non-zero real number n).
- **Inverse Element:**  For any non-zero real number n, the inverse is 1/n​ (since n \* 1/n = n).
### **Cyclic Group Z**n**
- **Set:**  The set of integers (modulo n), {0, 1, 2, …, n−1}.
- **Operation:**  Addition modulo n.
- **Identity Element:**  0 (since (a+0) mod  n = a for any integer a).
- **Inverse Element:**  For any integer a, the inverse is n−a (since (a+ (n−a)) mod  n = 0 , only when a ≠ 0)
## Algebraic Structure
An algebraic structure is a set of elements equipped with one or more operations that combine elements of the set in a specific way.
A non-empty set S is called an algebraic structure with a binary operation (∗) if it follows the closure axiom.
**Closure Axiom:**  For a, b in S, if (a\*b) belongs to S, then S is closed for operation \*.
Let's consider an example for better understanding.
- S = {1,- 1} is an algebraic structure under multiplication.
- Set of Integers; Z = {...,−3,−2,−1,0,1,2,3,...} with addition as well as multiplication.
- Set of non-zero real numbers (R, ∗) with multiplication.
## Algebraic Structure Related to Group
Other algebraic structures related to groups are:
- Abelian Group
- Semi Group
- Monoid
### Abelian Group or Commutative group
For a non-empty set S, (S, \*) is called a Abelian group if it follows the following axiom:
- **Closure:**  (a\*b) belongs to S for all a, b ∈ S.
- **Associativity:**  a\*(b\*c) = (a\*b)\*c where a ,b ,c belongs to S.
- **Identity Element:**  There exists e ∈ S such that a\*e = e\*a = a where a ∈ S
- **Inverses:**  For a ∈ S there exists a  -1  ∈ S such that a\*a  -1  = a  -1  \*a = e
- **Commutative:**  a\*b = b\*a for all a, b ∈ S
For finding a set that lies in which category one must always check axioms one by one starting from closure property and so on.
> Every Abelian group is a group, monoid, semigroup, and algebraic structure.
### Semi Group
A non-empty set S, (S,\*) is called a semigroup if it follows the following axiom:
- **Closure:**  (a\*b) belongs to S for all a, b ∈ S.
- **Associativity:**  a\*(b\*c) = (a\*b)\*c where a, b ,c∈ S.
> A semi-group is always an algebraic structure.
**Example:**  (Set of integers, +), and (Matrix ,\*) are examples of semigroup.
### Monoid
A non-empty set S, (S,\*) is called a monoid if it follows the following axiom:
- **Closure:**  (a\*b) belongs to S for all a, b ∈ S.
- **Associativity:**  a\*(b\*c) = (a\*b)\*c ? a, b, c ∈ S.
- **Identity Element:**  There exists e ∈ S such that a\*e = e\*a = a , a ∈ S
> A monoid is always a semi-group and algebraic structure.
## **Examples of Various Algebraic Structures**
(Set of integers, \*) is Monoid as 1 is an integer which is also an identity element. (Set of natural numbers, +) is not Monoid as there doesn’t exist any identity element. But this is Semigroup. But (Set of whole numbers, +) is Monoid with 0 as identity element.
Here is a Table with different nonempty set and operation:
| Set, Operation | Algebraic Structure | Semi Group | Monoid | Group | Abelian Group |
| --- | --- | --- | --- | --- | --- |
| N, + | Y | Y | - | - | - |
| N, - | - | - | - | - | - |
| N, × | Y | Y | Y | - | - |
| N, ÷ | - | - | - | - | - |
| Z, + | Y | Y | Y | Y | Y |
| Z, - | Y | - | - | - | - |
| Z, × | Y | Y | Y | - | - |
| Z, ÷ | - | - | - | - | - |
| R, + | Y | Y | Y | Y | Y |
| R, - | Y | - | - | - | - |
| R, × | Y | Y | Y | - | - |
| R, ÷ | - | - | - | - | - |
| E, + | Y | Y | Y | Y | Y |
| E, × | Y | Y | - | - | - |
| O, + | - | - | - | - | - |
| O, × | Y | Y | Y | - | - |
| M, + | Y | Y | Y | Y | Y |
| M, × | Y | Y | Y | - | - |
Where,
- N: Set of Natural Number
- Z: Set of Integer
- R: Set of Real Number
- E: Set of Even Number
- O: Set of Odd Number
- M: Set of Matrix
- +, -, ×, ÷ are the operations
| Structure | Must Satisfy Properties |
| --- | --- |
| Algebraic Structure | Closure |
| Semi Group | Closure, Associative |
| Monoid | Closure, Associative, Identity |
| Group | Closure, Associative, Identity, Inverse |
| Abelian Group | Closure, Associative, Identity, Inverse, Commutative |
## Solved Examples
**Problem 1**: Prove that in a group G, if (ab)² = a²b² for all a, b ∈ G, then G is abelian.
> Given: (ab)² = a²b² for all a, b ∈ G
>
> Expand (ab)²: ab.ab = a²b²
>
> Multiply both sides by a⁻¹ on the left: a⁻¹(abab) = a⁻¹(a²b²)
>
> Simplify: bab = ab²
>
> Multiply both sides by b⁻¹ on the right: (bab)b⁻¹ = (ab²)b⁻¹
>
> Simplify: ba = ab
>
> Therefore, G is abelian.
**Problem 2:** Let G be a group of order 15. Prove that G is cyclic.
> By Lagrange's theorem, the possible orders of elements in G are 1, 3, 5, and 15.
>
> If there exists an element of order 15, then G is cyclic.
>
> If not, then G has elements of order 3 and 5 (since it can't be all identity elements).
>
> Let a be an element of order 3 and b be an element of order 5.
>
> Consider the subgroup H = <a, b>. Its order must divide 15.
>
> |H| ≠ 3 or 5 because it contains elements of both orders.
>
> |H| ≠ 1 because it's not just the identity.
>
> Therefore, |H| = 15, which means H = G.
>
> By the fundamental theorem of finite abelian groups, G ≅ Z₃ ⊕ Z₅ ≅ Z₁₅.
>
> Thus, G is cyclic.
**Problem 3:** Let G be a group and H be a subgroup of G. Prove that if [G:H] = 2, then H is normal in G.
> [G:H] = 2 means there are only two cosets of H in G.
>
> These cosets are H itself and some aH where a ∉ H.
>
> For any g ∈ G, gH must equal either H or aH.
>
> If gH = H, then g ∈ H, so gHg⁻¹ = H.
>
> If gH = aH, then g = ah for some h ∈ H.
>
> In this case, gHg⁻¹ = ahH(ah)⁻¹ = aHa⁻¹
>
> But aHa⁻¹ must be either H or aH.
>
> If aHa⁻¹ = aH, then Ha⁻¹ = H, which means a ∈ H, contradicting our choice of a.
>
> Therefore, aHa⁻¹ = H.
>
> Thus, for all g ∈ G, gHg⁻¹ = H, so H is normal in G.
**Problem 4:** Let G be a group and let a, b ∈ G. Prove that if ab = ba, then (ab)ⁿ = aⁿbⁿ for all n ∈ Z.
> We'll use induction on n.
>
> Base case: For n = 0, (ab)⁰ = e = a⁰b⁰
>
> For n = 1, (ab)¹ = ab = a¹b¹
>
> Inductive hypothesis: Assume (ab)ᵏ = aᵏbᵏ for some k ≥ 1
>
> Inductive step: Consider (ab)ᵏ⁺¹
>
> (ab)ᵏ⁺¹ = (ab)ᵏ(ab) = (aᵏbᵏ)(ab) = aᵏ(bᵏa)b = aᵏ(abᵏ)b = aᵏ⁺¹bᵏ⁺¹
>
> By induction, (ab)ⁿ = aⁿbⁿ for all n ≥ 0
>
> For negative integers, note that (ab)⁻ⁿ = ((ab)ⁿ)⁻¹ = (aⁿbⁿ)⁻¹ = b⁻ⁿa⁻ⁿ = a⁻ⁿb⁻ⁿ
>
> Therefore, (ab)ⁿ = aⁿbⁿ for all n ∈ Z.
**Problem 5:** Let G be a group of order pq, where p and q are distinct primes. Prove that G is cyclic if and only if gcd(p-1, q-1) = 1.
> First, prove that if G is cyclic, then gcd(p-1, q-1) = 1:
>
> If G is cyclic, it has an element of order pq.
>
> By the structure theorem of cyclic groups, G ≅ Zₚq
>
> The number of elements of order pq in Zₚq is φ(pq) = (p-1)(q-1)
>
> This number must equal the number of generators of G, which is φ(pq)
>
> For this to be true, we must have gcd(p-1, q-1) = 1
>
> Now, prove that if gcd(p-1, q-1) = 1, then G is cyclic:
>
> By Sylow's theorems, G has a unique subgroup P of order p and a unique subgroup Q of order q
>
> Let a generate P and b generate Q
>
> Consider the order of ab:
>
> (ab)ᵖq = aᵖqbᵖq = (aᵖ)q(bq)ᵖ = e
>
> So the order of ab divides pq
>
> If ord(ab) = p or q, then ab ∈ P or ab ∈ Q, which is impossible
>
> Therefore, ord(ab) = pq, and G is cyclic
>
> Thus, G is cyclic if and only if gcd(p-1, q-1) = 1.
### **Related Articles**
> - [Set Theory](https://www.geeksforgeeks.org/maths/set-theory/)
> - [Set Theory Symbols](https://www.geeksforgeeks.org/maths/set-theory-symbols/)
> - [Set Theory Formulas](https://www.geeksforgeeks.org/maths/set-theory-formulas/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/groups-discrete-mathematics/)

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
> - [[Hasse Diagrams]]
> - [[Introduction to Set Theory]]
> - [[Inverse Functions]]
> - [[Modular Addition]]
> - [[Multiplication Modulo]]
