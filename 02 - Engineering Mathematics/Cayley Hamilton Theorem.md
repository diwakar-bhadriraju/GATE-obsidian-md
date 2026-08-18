---
title: "Cayley Hamilton Theorem"
subject: "Engineering Mathematics"
topic: "Linear Algebra"
source: "https://www.geeksforgeeks.org/maths/cayley-hamilton-theorem/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Linear Algebra"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/linear-algebra
---


> [!abstract] Cayley Hamilton Theorem
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Linear Algebra`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/cayley-hamilton-theorem/)

---

# Cayley Hamilton Theorem

The Cayley–Hamilton Theorem is a fundamental result in linear algebra that connects a matrix with its characteristic polynomial. Simply put, it states that every square matrix satisfies its own characteristic equation.
For an (n × n) matrix A, the characteristic polynomial P(λ) is given as:
> P(λ) = det(λIn − A)
where,
- λ is a variable
- In is the [identity matrix](https://www.geeksforgeeks.org/maths/identity-matrix/) of order n.
This polynomial is of degree n and can be written in general form as:
> p(λ) = λn + an−1 ​λn−1 + ⋯ + a1​λ + a0​
The roots of p(λ) are the **eigenvalues** of A.
### Theorem Statement
The Cayley–Hamilton Theorem says:
> p(A) = An + an−1 ​An−1 + ⋯ + a1 ​A + a0 ​In ​= 0
That is, if you substitute the matrix A into its own characteristic polynomial, the result is always the zero matrix.
The roots of this [polynomial](https://www.geeksforgeeks.org/maths/polynomials/) are the [eigenvalues](https://www.geeksforgeeks.org/engineering-mathematics/eigen-values/) of the matrix.
This theorem is useful because it allows any power of the matrix A (such as Ak for k>n) to be expressed as a linear combination of the lower powers of A(I, A, A2, ... An-1) .
The theorem is applied in various mathematical domains, assisting in matrix-related operations like inversion, exponentiation, and control theory.
### Steps to Apply the Cayley–Hamilton Theorem
Following steps are performed to apply Cayley Hamilton theorem to a matrix.
- **Find the characteristic polynomial:** For an n×n matrix A, form the matrix (λIn − A) and calculate its determinant to get the characteristic polynomial p(λ).
- **Substitute the matrix:** Replace the variable λ in the polynomial with the matrix A. For the constant term in the polynomial, use the identity matrix In.
- **Result is the zero matrix:** The theorem guarantees that p(A) = 0.
### General Form
This polynomial can be broken down into a simpler form, written as
> p(λ) = anλn + an−1λn−1 +…..+ a1λ1 + a0λ0.
The coeffiecient of highest degree variable(λn), and in this case, an is always 1.
Variables are in decreasing order of degree, like λn−1, … , λ1, λ0.
> p(A) = An + an-1 An-1 + ..... + a1A +a0In = 0
>  **OR**
> p(A) = 0, where A is an n×n square matrix
## Cayley Hamilton Theorem Example
In matrix (B)
$$
B = \begin{bmatrix} 2 & 1 \\ 3 & 2 \end{bmatrix}
$$
And the characteristic polynomial for (B) is
$$
\lambda^2 - 4\lambda + 1
$$
Now, we can use the Cayley-Hamilton Theorem by substituting (B) into the polynomial:
> p(B) = B2 - 4B + I
On calculating, we get
$$
B^2 = \begin{bmatrix} 2 & 1 \\ 3 & 2 \end{bmatrix} \times \begin{bmatrix} 2 & 1 \\ 3 &2 \end{bmatrix} = \begin{bmatrix} 7 & 4 \\ 12 & 7 \end{bmatrix}
$$
$$
4B = 4 \times \begin{bmatrix} 2 &1 \\ 3 & 2 \end{bmatrix} = \begin{bmatrix} 8 & 4 \\ 12 & 8 \end{bmatrix}
$$
$$
I = \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}
$$
Now, put these into the expression:
$$
p(B) = \begin{bmatrix} 7 & 4 \\ 12 & 7 \end{bmatrix} - \begin{bmatrix} 8 & 4 \\ 12 & 8 \end{bmatrix} + \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}
$$
Further subtracting:
$$
p(B) = \begin{bmatrix} -1 & 0 \\ 0 & -1 \end{bmatrix} + \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}
$$
Combining the matrices:
$$
p(B) = \begin{bmatrix} 0 & 0 \\ 0 & 0 \end{bmatrix}
$$
So, in this example, by substituting the matrix (B) into the characteristic polynomial
$$
\lambda^2 - 4\lambda + 1
$$
, we get p(B) = 0, confirming the Cayley-Hamilton Theorem for this specific matrix.
## Cayley Hamilton Theorem Formula
The Cayley-Hamilton Theorem formula is a useful tool for solving complex calculations quickly and accurately, especially in matrix algebra. It is also employed to find the inverse of a matrix. The formula is as follows:
**Characteristic polynomial for an n×n square matrix (A), written as:**
$$
p(\lambda) = \lambda^n + a_{n-1}\lambda^{n-1} + \ldots + a_1\lambda + a_0
$$
Then, substituting the matrix A into this polynomial, denoted as p(A), results in:
$$
p(A) = A^n + a_{n-1}A^{n-1} + \ldots + a_1A + a_0I_n = 0
$$
This implies that p(A) = 0
To find the inverse of the matrix, you can multiply this equation by the inverse of (A), denoted as A-1, giving:
$$
A^{n-1} + a_{n-1}A^{n-2} + \ldots + a_1I_n + a_0A^{-1} = 0
$$
Solving for A-1, it is expressed as:
$$
A^{-1} = -[A^{n-1} + a_{n-1}A^{n-2} + \ldots + a_1I_n]a_0
$$
In other words, the Cayley-Hamilton Theorem formula helps in understanding that when a matrix is appplied to its own characteristic polynomial, the result is always zero. This property is then leveraged to find the inverse of the matrix.
### Cayley Hamilton Theorem for 2×2 Matrix
When dealing with a 2 × 2 square matrix and applying the Cayley Hamilton Theorem, the first thing is to figure out the characteristic polynomial expression. The general form of this polynomial is written as λ2 + a1λ + a0, where a1 and a0 are coefficients. Since we're dealing with a 2 × 2 matrix (meaning n = 2, the polynomial simplifies to λ2 + a1λ + a0.
In the specific case of a 2 × 2 matrix, we can represent the characteristic polynomial as λ2 - S1λ + S0, where S is the sum of the diagonal elements and S0 is the determinant of the matrix.
Now, according to the Cayley Hamilton Theorem, if we replace λ with our 2 × 2 square matrix, say (B), the characteristic polynomial becomes B2 - S1B + S0I = 0. Here, (B) is the 2 × 2 square matrix, (B2) is the matrix multiplied by itself, S1 is the sum of the diagonal elements of (B), S0 is the determinant of (B), and (I) is the identity matrix.
In simpler terms, plugging our matrix (B) into this equation should give us the zero matrix, as per the Cayley Hamilton Theorem for 2 × 2 matrices.
**Example: Consider a 2 × 2 matrix**
$$
C = \begin{bmatrix} 3 & 2 \\ 1 & 4 \end{bmatrix}
$$
**Solution:**
> To find characteristic polynomial, the general form is λ2 - S1 λ + S0, where S1 is the sum of the diagonal elements, and S0 is the determinant.
>
> For matrix (C):
>
> S1 = 3 + 4 = 7
>
> S0 = (3 × 4) - (2 × 1) = 10
>
> The characteristic polynomial is λ2 - 7λ + 10
>
> Now, applying the Cayley Hamilton Theorem:
>
>
$$
C^2 - 7C + 10I = \begin{bmatrix} 3 & 2 \\ 1 & 4 \end{bmatrix}^2 - 7 \times \begin{bmatrix} 3 & 2 \\ 1 & 4 \end{bmatrix} + 10 \times \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}
$$
>
>
$$
C^2 = \begin{bmatrix} 3 & 2 \\ 1 & 4 \end{bmatrix} \times \begin{bmatrix} 3 & 2 \\ 1 & 4 \end{bmatrix} = \begin{bmatrix} 11 & 14 \\ 4 & 18 \end{bmatrix}
$$
>
>
$$
7C = 7 \times \begin{bmatrix} 3 & 2 \\ 1 & 4 \end{bmatrix} = \begin{bmatrix} 21 & 14 \\ 7 & 28 \end{bmatrix}
$$
>
>
$$
10I = 10 \times \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} = \begin{bmatrix} 10 & 0 \\ 0 & 10 \end{bmatrix}
$$
>
> Now, substitute these into the Cayley Hamilton Theorem equation:
>
>
$$
C^2 - 7C + 10I = \begin{bmatrix} 11 & 14 \\ 4 & 18 \end{bmatrix} - \begin{bmatrix} 21 & 14 \\ 7 & 28 \end{bmatrix} + \begin{bmatrix} 10 & 0 \\ 0 & 10 \end{bmatrix}
$$
>
> After performing the subtraction, you should find that the result is the zero matrix:
>
>
$$
\begin{bmatrix} 0 & 0 \\ 0 & 0 \end{bmatrix}
$$
>
> This confirms the Cayley Hamilton Theorem for the given 2 × 2 matrix example.
### Cayley Hamilton Theorem for 3×3 Matrix
For a 3 × 3 square matrix, the Cayley-Hamilton Theorem relates the matrix to its characteristic polynomial, which is expressed as p(λ) = λ3 - T2λ2 + T1λ - T0. In this formula, T2 is the sum of the main diagonal elements, T1 is the sum of the minors of the main diagonal elements, and T0 is the determinant of the 3 × 3 square matrix.
When we apply the Cayley Hamilton Theorem to a 3 × 3 matrix (C), the resulting formula is:
C3 - T2C2 + T1C - T0I = 0
Here, (C) represents the 3 × 3 square matrix, and (I) is the identity matrix. The theorem tells us that if we plug the matrix (C) into this equation, the result will be the zero matrix.
**Example:** **Consider a 3 × 3 matrix (C)**
$$
C = \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix}
$$
**Solution:**
> Now, we need to find the characteristic polynomial using the given formula:
>
> p(λ) = λ3 - T2 λ2 + T1 λ- T0
>
> where:
>
> - **T**2**is Sum of Main Diagonal Elements
> - **T**1**is Sum of Minors of Main Diagonal Elements
> - **T**0** is Determinant of 3 × 3 Square Matrix
>
> T2 = 1 + 5 + 9 = 15
>
> T1 = (1 × 5 × 9) + (2 × 6 × 7) + (3 × 4 × 8) - (3 × 5 \× 7) - (2 ×s 4 × 9) - (1 × 6 × 8) = -24
>
> T0 = det(C) = 1 × (5 × 9 - 6 × 8) - 2 × (4 × 9 - 6 × 7) + 3 × (4 × 8 - 5 × 7) = 0
>
> Now, the characteristic polynomial is:
>
> p(λ) = λ3 - 15λ2 - 24λ
>
> Applying the Cayley-Hamilton Theorem to the matrix (C):
>
> C3 - 15C2 - 24C = 0
>
> As
>
>
$$
C^3 - 15C^2 - 24C = \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix}^3 - 15 \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix}^2 - 24 \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix}
$$
>
> Now, perform the matrix operations:
>
> ⇒
>
>
$$
C^3 = \begin{bmatrix} 468 & 576 & 684 \\ 1062 & 1296 & 1530 \\ 1656 & 2016 & 2376 \end{bmatrix}
$$
>
> ⇒
>
>
$$
15 C^2 = 15 \times \begin{bmatrix} 30 & 36 & 42 \\ 66 & 81 & 96 \\ 102 & 126 & 150 \end{bmatrix}
$$
>
> ⇒
>
>
$$
24C = 24 \times \begin{bmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \\ 7 & 8 & 9 \end{bmatrix}
$$
>
> Now, subtract these matrices:
>
>
$$
\begin{bmatrix} 468 & 576 & 684 \\ 1062 & 1296 & 1530 \\ 1656 & 2016 & 2376 \end{bmatrix} - \begin{bmatrix} 450 & 540 & 630 \\ 990 & 1215 & 1440 \\ 1230 & 1512 & 1794 \end{bmatrix} - \begin{bmatrix} 24 & 48 & 72 \\ 96 & 120 & 144 \\ 168 & 192 & 216 \end{bmatrix}
$$
>
> Performing the subtraction, you should find that the result is the zero matrix:
>
>
$$
\begin{bmatrix} 0 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{bmatrix}
$$
>
> Cayley-Hamilton Theorem holds for the given 3 × 3 matrix (C).
## Proof of Cayley Hamilton Theorem
To prove the Cayley Hamilton Theorem, the easiest method is by substitution. Consider a matrix (A) given as:
$$
A = \begin{bmatrix} a & b \\ c & d \end{bmatrix}
$$
According to the Cayley Hamilton theorem, the expression
$$
p(A) = A^2 - (a + d)A + (ad - bc)I
$$
 should equal the zero matrix. The proof unfolds as follows:
$$
A^2 = \begin{bmatrix} a^2 + bc & ab + bd \\ ac + cd & bc + d^2 \end{bmatrix}
$$
$$
(a + d)A = \begin{bmatrix} a(a + d) & b(a + d) \\ c(a + d) & d(a + d) \end{bmatrix} = \begin{bmatrix} a^2 + ad & ab + bd \\ ac + cd & ad + d^2 \end{bmatrix}
$$
⇒
$$
(ad - bc)I = \begin{bmatrix} ad - bc & 0 \\ 0 & ad - bc \end{bmatrix}
$$
Now, combine these matrices in the expression
$$
A^2 - (a + d)A + (ad - bc)I
$$
$$
\begin{bmatrix} a^2 + bc & ab + bd \\ ac + cd & bc + d^2 \end{bmatrix} - \begin{bmatrix} a^2 + ad & ab + bd \\ ac + cd & ad + d^2 \end{bmatrix} + \begin{bmatrix} ad - bc & 0 \\ 0 & ad - bc \end{bmatrix}
$$
After performing the subtraction, the result is the zero matrix:
$$
\begin{bmatrix} 0 & 0 \\ 0 & 0 \end{bmatrix}
$$
This confirms the Cayley Hamilton Theorem for a 2 × 2 matrix. The proof can be extended similarly for higher-order square matrices.
## Applications of Cayley Hamilton Theorem
**Various uses of Cayley Hamilton Theorem are,**
- [**Finding Matrix Inverses**](https://www.geeksforgeeks.org/maths/inverse-of-matrix/)**:** The Cayley Hamilton Theorem is employed to simplify the process of calculating the inverse of square matrices.
- [**Matrix Exponentiation:**](https://www.geeksforgeeks.org/dsa/matrix-exponentiation/) It can be used to efficiently compute the values of matrices raised to large exponents.
- **Control Theory:** In control theory, the Cayley Hamilton Theorem plays a role in defining important concepts, such as checking the controllability of linear systems.
- **Proof of Jacobson's Theorem:** The Cayley Hamilton Theorem is instrumental in proving Jacobson's Theorem.
- **Nakayama's Lemma in Commutative Algebra:** In commutative algebra, a generalization of the Cayley Hamilton Theorem is used to prove Nakayama's Lemma, a significant result in the field.
### Related Articles
> - [Finding Inverse of a Square Matrix using Cayley Hamilton Theorem in MATLAB](https://www.geeksforgeeks.org/dsa/finding-inverse-of-a-square-matrix-using-cayley-hamilton-theorem-in-matlab/)
> - [Implementation of Cayley-Hamilton’s Theorem in MATLAB](https://www.geeksforgeeks.org/dsa/implementation-of-cayley-hamiltons-theorem-in-matlab/)
> - [Videos of Cayley-Hamilton’s Theorem](https://www.geeksforgeeks.org/videos/17-linear-algebra-cayley-hamilton-theorem/)
## Solved Examples
**Example 1: Let (F) be a 2 × 2 matrix given by**F =
$$
\begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix}
$$
**. Find (F**3**) using the Cayley Hamilton Theorem.**
**Solution:**
> Given Matrix:
>
> F =
>
>
$$
\begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix}
$$
>
> Characteristic polynomial of (F) is found by solving det(λI - F) = 0, where (I) is the identity matrix.
>
> For matrix (F),
>
> det(λI - F) = 
>
>
$$
{det}\left(\begin{bmatrix} \lambda - 1 & -2 \\ -3 & \lambda - 4 \end{bmatrix}\right)
$$
>
> (λ- 1)(λ - 4) - (-2)(-3) = λ2 - 5λ -2
>
> According to the Cayley Hamilton Theorem, F2 - 5F -2I = 0-----(1)
>
> Multiply both sides of equation by (F)
>
> F.(F2 - 5F - 2F) = F3 - 5F2 -2F = 0
>
> Now, solving for (F3)
>
> F3 = 5F2 + 2F
>
> Now substitute again F2=5F+2I from equation (1)
>
> ⇒ F3 = 5[5F + 2I] + 2F =25F + 10I + 2F
>
> ⇒ F3= 27F + 10I-----(2)
>
> 27F =
>
>
$$
27\begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} = \begin{bmatrix} 27 & 54 \\ 81 & 108 \end{bmatrix}
$$
>
> 10I=
>
>
$$
\begin{bmatrix} 10 & 0 \\ 0 & 10 \end{bmatrix}
$$
>
> Now substitute value of 27F and 10I in equation (2)
>
> F3= 27F + 10I
>
> F3 =
>
>
$$
\begin{bmatrix} 27+10 & 54+0 \\ 81+0 & 108+10 \end{bmatrix}
$$
>
> F3 =
>
>
$$
\begin{bmatrix} 37 & 54 \\ 81 & 118 \end{bmatrix}
$$
**Example 2: Consider a 3 × 3 matrix (D):** D = \begin{bmatrix} 2 & 1 & 0 \\ 0 & 2 & 1 \\ 0 & 0 & 2 \end{bmatrix}
- **Find the characteristic polynomial of matrix (D).**
- **Applying the Cayley Hamilton Theorem to show that D**3**- 6D**2**+ 12D - 8I = 0**
**Solution:**
> Characteristic polynomial of matrix (D)
>
> Characteristic polynomial is obtained by finding the determinant of (λI - D), where (I) is the identity matrix.
>
>
$$
\text{det}(\lambda I - D) = \text{det}\left(\begin{bmatrix} \lambda - 2 & -1 & 0 \\ 0 & \lambda - 2 & -1 \\ 0 & 0 & \lambda - 2 \end{bmatrix}\right)
$$
>
> = (λ - 2)3
>
> So, the characteristic polynomial is p(λ) = (λ - 2)3
>
> **Applying the Cayley Hamilton Theorem**
>
> Cayley Hamilton Theorem states that for a 3 × 3 matrix (D) with characteristic polynomial (λ - 2)3, substituting (D) into (λ - 2)3 - 3(λ - 2)2 + 3(λ - 2) - I = 0 should result in the zero matrix.
>
> Now, substitute (D) into the Cayley Hamilton Equation
>
> D3 - 6D2 + 12D - 8I =
>
>
$$
\begin{bmatrix} 2 & 1 & 0 \\ 0 & 2 & 1 \\ 0 & 0 & 2 \end{bmatrix}^3 - 6 \begin{bmatrix} 2 & 1 & 0 \\ 0 & 2 & 1 \\ 0 & 0 & 2 \end{bmatrix}^2 + 12 \begin{bmatrix} 2 & 1 & 0 \\ 0 & 2 & 1 \\ 0 & 0 & 2 \end{bmatrix} - 8 \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix}
$$
>
> First, find (D2) and (D3)
>
>
$$
D^2 = \begin{bmatrix} 2 & 1 & 0 \\ 0 & 2 & 1 \\ 0 & 0 & 2 \end{bmatrix} \times \begin{bmatrix} 2 & 1 & 0 \\ 0 & 2 & 1 \\ 0 & 0 & 2 \end{bmatrix} = \begin{bmatrix} 4 & 4 & 2 \\ 0 & 4 & 4 \\ 0 & 0 & 4 \end{bmatrix}\\D^3 = D \times D^2 = \begin{bmatrix} 2 & 1 & 0 \\ 0 & 2 & 1 \\ 0 & 0 & 2 \end{bmatrix} \times \begin{bmatrix} 4 & 4 & 2 \\ 0 & 4 & 4 \\ 0 & 0 & 4 \end{bmatrix} = \begin{bmatrix} 8 & 12 & 8 \\ 0 & 8 & 12 \\ 0 & 0 & 8 \end{bmatrix}
$$
>
> Now, substitute these into D3 - 6D2 + 12D - 8I
>
>
$$
\begin{bmatrix} 8 & 12 & 8 \\ 0 & 8 & 12 \\ 0 & 0 & 8 \end{bmatrix} - 6 \begin{bmatrix} 4 & 4 & 2 \\ 0 & 4 & 4 \\ 0 & 0 & 4 \end{bmatrix} + 12 \begin{bmatrix} 2 & 1 & 0 \\ 0 & 2 & 1 \\ 0 & 0 & 2 \end{bmatrix} - 8 \begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix}\\\begin{bmatrix} 0 & 0 & 0 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{bmatrix}
$$
>
> This confirms the Cayley Hamilton Theorem for the given matrix (D).
## Practice Questions on Cayley Hamilton Theorem
**Problem 1:** **Let matrix**
$$
\bold{J = \begin{bmatrix} 2 & 1 \\ 0 & 2 \end{bmatrix}}
$$
- **Determine the characteristic polynomial of matrix (J).**
- **Use the Cayley Hamilton Theorem to verify that J**2**- 4J + 4I = 0**
**Problem 2: Consider a 3 × 3 matrix (K):**
$$
\bold{K = \begin{bmatrix} 5 & 1 & 0 \\ 0 & 5 & 1 \\ 0 & 0 & 5 \end{bmatrix}}
$$
- **Find the characteristic polynomial of matrix (K).**
- **Apply the Cayley Hamilton Theorem to show that K**3**- 15K**2**+ 75K - 125I = 0**
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/cayley-hamilton-theorem/)

## GATE CS

- Subject: Engineering Mathematics
- Topic: Linear Algebra

> [!note] Related notes
>
> - [[Determinants]]
> - [[Different Operations on matrices]]
> - [[Eigenvalues and Eigenvectors]]
> - [[Introduction to Matrix]]
> - [[LU Decomposition]]
> - [[Matrix Diagonalization]]
> - [[Null Space and Nullity of a Matrix]]
> - [[Properties of Determinants]]
> - [[Rank of a Matrix]]
> - [[Row Echelon Form]]
