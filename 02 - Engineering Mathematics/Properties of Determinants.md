---
title: "Properties of Determinants"
subject: "Engineering Mathematics"
topic: "Linear Algebra"
source: "https://www.geeksforgeeks.org/engineering-mathematics/properties-of-determinants-of-matrices/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Linear Algebra"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/linear-algebra
---


> [!abstract] Properties of Determinants
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Linear Algebra`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/properties-of-determinants-of-matrices/)

---

# Properties of Determinants

A determinant is a function with entries of a square matrix. For a matrix M = [aij], the determinant of the matrix is denoted as |M| or det M.
![properties_of_determinants](assets/properties_of_determinants-6147e7f643.webp)
These various properties of the [determinant](https://www.geeksforgeeks.org/maths/what-is-determinant-of-a-matrix/) are based on the elements, rows, and columns of the determinant and are discussed below:
## 1. Triangle Property
This property of the determinant states that if the elements above or below the main diagonal are zero, then the value of the determinant is equal to the product of the diagonal elements.
For any square matrix A such that,
A =
$$
\begin{pmatrix}a & 0 & 0\\ d & e & 0\\g & h & i\\\end{pmatrix}
$$
|A| =
$$
\begin{vmatrix}a & 0 & 0\\ d & e & 0\\g & h & i\\\end{vmatrix}
$$
Then, according to the Triangle Property of Determinant
> **|A| = a** × **e** × **i**
**Example:**
> A =
>
>
$$
\begin{pmatrix}1 & 0 & 0\\ 2 & 3 & 0\\4 & 5 & 6\\\end{pmatrix}
$$
>
> |A| =
>
>
$$
\begin{vmatrix}1 & 0 & 0\\ 2 & 3 & 0\\4 & 5 & 6\\\end{vmatrix}
$$
>
> |A| = 1[(3).(6) -(0)(5)] - 0 + 0
>
> = 1[18 - 0] = 18
>
> |A| = 1 × 3 × 6 = 18
>
> Therefore, |A| = a × e × i
## 2. Determinant of Cofactor Matrix
The determinant of the cofactor matrix of a matrix A is equal to the determinant of A raised to the power of (n-1), where n is the order of the matrix.
For any [square matrix](https://www.geeksforgeeks.org/maths/square-matrix/) A of order n, the property is given by,
> |C| = |A| n-1
Where,
- |C| - determinant of cofactor matrix
- |A| - determinant of matrix A
- n - order of matrix
**Example:**
> A =
>
>
$$
\begin{pmatrix}1 & 2 \\ 3 & 4\\\end{pmatrix}
$$
>
> n = 2
>
> |A| = (1)(4) − (2)(3) = 4 − 6 = −2
>
> - C11 = |4| = 4
> - C12 = - |3| = −3
> - C21 = −|2| = −2
> - C22 = |1| = 1
>
> C =
>
>
$$
\begin{pmatrix}4 & -3 \\ -2 & 1\\\end{pmatrix}
$$
>
> |C| = (4)(1) - (-3)(-2) = 4 - 6 = -2
>
> Therefore |A| = |C|2-1
## 3. Factor Property
For any square matrix A of variable 'x', if on putting x = a, the value of the determinant is zero, then (x - a) is a factor of the determinant.
**Example:**
> A =
>
>
$$
\begin{pmatrix}x & 0 \\ 3 & x-2\\\end{pmatrix}
$$
>
> |A| = (x)(x-2) − 0 = x( x - 2)
>
> At x = 2 : 2(x - 2) - 0 = x(x - 2)
>
> (x - a) = (x - 2)
>
> Therefore (x - 2) is a factor of determinant polynomial of x(x - 2)
## 4. Property of Invariance
Suppose we have a square matrix A of order 3
A =
$$
\begin{pmatrix}a & b & c\\ d & e & f\\g & h & i\\\end{pmatrix}
$$
Then adding a scalar multiple of any row or column to any row or column does not change the value of the determinant, i.e.
> **R**i**→ R**i**+ (q)R**j**
> **OR**
> **C**i**→ C**i**+ (q)C**j**
where q represents the scalar constant, then the value of the determinant of the new matrix form does not change.
- |A| =
$$
\begin{vmatrix}a & b & c\\ d & e & f\\g & h & i\\\end{vmatrix}
$$
- |B| =
$$
\begin{vmatrix}a + qc & b & c\\ d + qf& e & f\\g + qi& h & i\\\end{vmatrix}
$$
Then the determinants of matrix A and matrix B are equal, i.e.
> **|A| = |B|**
**Example:**
> |A| =
>
>
$$
\begin{vmatrix}1 & 2\\ 5 & 2\\\end{vmatrix}
$$
>
> = (1)(2) - (2)(5) = 2 - 10 = -8
>
> |B| =
>
>
$$
\begin{vmatrix}1 -3(5) & 2 - 3(2)\\ 5 & 2 \\\end{vmatrix}
$$
>
> = (1-15)(2) - (2-6)(5) = -28 + 20 = -8
>
> Therefore |A| = |B|.
## **5. Scalar Multiple Property**
If any row or column of a determinant is multiplied by any scalar value, that is, a non-zero constant, the entire determinant gets multiplied by the same scalar; that is,
**Case 1** - If any one row or column is multiplied by a constant k, the determinant value gets multiplied by k. Constants may be any real number.
> **det(Δ') = k det(Δ)**
**Case 2 -** If all rows (or columns) of an n×n determinant are multiplied by k, then
> det⁡(Δ′) = kndet⁡(Δ)
**Example:**
>
$$
\begin{vmatrix}2 & 1\\ 2 & 4\\ \end{vmatrix}
$$
>
> Its determinant is |A| = 8 - 2 = 6
>
> Let us multiply all the elements in the above matrix by 2, say |A|'
>
> |A|' =
>
>
$$
\begin{vmatrix}4 & 2 \\4 & 8 \end{vmatrix}
$$
>
> |A|' = 32 - 8 = 24
>
> Since both rows are multiplied by 2,
>
> |A|' = 22 × |A| = 4 x 6 = 24
## 6. Transpose of Determinant (Reflection Property)
[Transpose of a Matrix](https://www.geeksforgeeks.org/maths/transpose-of-a-matrix/) refers to the operations of interchanging rows and columns of the determinant. The rows become columns and columns become rows in order. It is denoted by |AT| for any determinant |A|.
The property says the determinant remains unchanged on its transpose, that is,
> **|A**T**| = |A|**.
**Example:**
> |A| =
>
>
$$
\begin{vmatrix}1 & 2\\ 3 & 2\\ \end{vmatrix}
$$
>
> = (1)(2) - (2)(3) = 2 - 6 = -4
>
> |AT| =
>
>
$$
\begin{vmatrix}1 & 3\\ 2 & 2\\ \end{vmatrix}
$$
>
> = (1)(2) - (3)(2) = 2 - 6 = -4
>
> Therefore |A| = |AT|.
## **7. Switching Property**
If we interchange any two rows/columns of the determinant, the magnitude (i.e., the sign) changes, but the determinant value remains the same.
Now,
> **Value of Determinant = (-1)**number of exchanges**
For a matrix **Δ**, one row/column exchanged to get **Δ**', two rows\columns exchanged to get **Δ**'', then,
> **det(Δ") = -det(Δ') = det (Δ)**
**Example:**
> **Δ =**
>
>
$$
\begin{pmatrix} 1 & 2 & -4\\ -3 & 0 & 7\\0 & 5 & 1\end{pmatrix}
$$
>
> det (Δ) = 1(-35) - 2(-3) - 4(-15) = -35 + 6 + 60 = 31
>
> det (Δ) = 31
>
> If we interchange C1 and C3, denoted by C1 ↔ C3
>
> Δ' =
>
>
$$
\begin{pmatrix} -4 & 2 & 1\\ 7 & 0 & -3\\1 & 5 & 0\end{pmatrix}
$$
>
> det(Δ') = -4(0 + 15) - 2(3) + 1(35) = -60 -6 + 35 = -31
>
> det (Δ) = -det(Δ')
>
> If we again interchange R1 and R2, denoted by R1 ↔ R2 
>
> Δ'' =
>
>
$$
\begin{pmatrix} 7 & 0 & -3\\ -4 & 2 & 1\\1 & 5 & 0\end{pmatrix}
$$
>
> det(Δ'') = 7(0 - 5) - 0 -3(-20 - 2) = -35 + 66 = 31
>
> det(Δ'') = det(Δ)
>
> Therefore det(Δ") = -det(Δ') = det (Δ)
## **8. Repetition Property**
If any pair of rows or columns of a determinant is identical or proportioned by the same amount, then the determinant is zero.
**Example:**
> A =
>
>
$$
\begin{pmatrix}1 & 3 \\ 1 & 3  \\\end{pmatrix}
$$
>
> = (1)(3) - (3)(1) = 0
## **9. All Zero Property**
If all elements of any column or row are zero, then the determinant is zero
For any matrix,
> A =
>
>
$$
\begin{pmatrix}0 & 0 & 0\\ d & e & g\\g & h & i\\\end{pmatrix}
$$
>
> **⇒ |A| = 0**
**Example**:
> A =
>
>
$$
\begin{pmatrix}1 & 2 \\ 0 & 0  \\\end{pmatrix}
$$
>
> = (1)(0) - (2)(0) = 0
## **10. Sum Property**
If all the elements of a row or column in a determinant are expressed as a summation of two or more numbers, then the determinant can be broken down as a sum of corresponding smaller determinants**.**
> We have,
>
>
$$
\Delta = \begin{vmatrix} a + 5m & d & g\\ b + 7n & e & h\\ c + 3p & f & i \end{vmatrix}
$$
>
> Then,
>
>
$$
\Delta = \begin{vmatrix} a & d & g\\ b & e & h\\ c & f & i \end{vmatrix} + \begin{vmatrix} 5m & d & g\\ 7n & e & h\\ 3p & f & i \end{vmatrix}
$$
**Example:**
> A
>
>
$$
= \begin{pmatrix} 2+3 & 1\\ 5+8 & 3\\ \end{pmatrix}
$$
>
> |A| = (5)(3) - (1)(13) = 15 - 13 = 2
>
>
$$
B = \begin{pmatrix} 2 & 1\\ 5 & 3\\ \end{pmatrix} + \begin{pmatrix} 3 & 1\\ 8 & 3\\\end{pmatrix}
$$
>
> |B| = (6 - 5) + (9 - 8) = 1 + 1 = 2
>
> |A| = |B|
### **Related Articles**
> - [Transpose of a Matrix](https://www.geeksforgeeks.org/maths/transpose-of-a-matrix/)
> - [Inverse of a Matrix Formula](https://www.geeksforgeeks.org/maths/determinant-of-3x3-matrix/)
> - [Determinant of 2x2 Matrix](https://www.geeksforgeeks.org/maths/determinant-of-2x2-matrix/)
> - [Determinant of 3 × 3 Matrix](https://www.geeksforgeeks.org/maths/determinant-of-3x3-matrix/)
## Solved Examples of Properties of Determinants
**Example 1:** Verify det(Δ') = k det(Δ) in,
Δ =
$$
\begin{vmatrix} 5 & 2 & 3\\ 2 & 4 & 5\\ 1 & 8 & 7 \end{vmatrix}
$$
 **k = 3/2**
**Solution:**
> Δ =
>
>
$$
\begin{vmatrix} 5 & 2 & 3\\ 2 & 4 & 5\\ 1 & 8 & 7 \end{vmatrix}
$$
>
>
> det(Δ) = 5[(4×7) - (8×5)] - 2[(2×7) - (5×1)] + 3[(2×8) - (4×1)]
> det(Δ) = -60 - 18 + 36
> det(Δ) = -42
>
> Now, on multiplying by k = 3/2, first column,
>
> Δ' =
>
>
$$
\begin{vmatrix} 5 & 2 & 3\\ 2 & 4 & 5\\ 1 & 8 & 7 \end{vmatrix}
$$
>
>
> Δ' =
>
>
$$
\begin{vmatrix} 15/2 & 2 & 3\\ 3 & 4 & 5\\ 3/2 & 8 & 7 \end{vmatrix}
$$
>
>
> det (Δ') = -63
>
> Therefore,
> det(Δ') = 3/2  det(Δ)
>
> **⇒ det(Δ') = k det(Δ)**
**Example 2:** Find the Determinant of
[A] =
$$
\begin{pmatrix}9 & 8 & 7\\ 0 & 0 & 0\\1 & 8 & 5\\\end{pmatrix}
$$
**Solution:**
> |A| =
>
>
$$
\begin{vmatrix}9 & 8 & 7\\ 0 & 0 & 0\\1 & 8 & 5\\\end{vmatrix}
$$
>
>
> det(Δ) = 0 (since R2 ⇢0)
**Example 3:** Find the Determinant of
[A] **=**
$$
\begin{pmatrix}2 & 0 & 0 & 0\\ 3 & 1 & 0 & 0\\5 & 6 & 8 & 0\\7 & 1 & 5 & 9\end{pmatrix}
$$
**Solution:**
> |A| =
>
>
$$
\begin{vmatrix}2 & 0 & 0 & 0\\ 3 & 1 & 0 & 0\\5 & 6 & 8 & 0\\7 & 1 & 5 & 9\end{vmatrix}
$$
>
>
> det(Δ) = 2 × 1 × 8 × 9
> det(Δ) = 144
### **Related Articles:**
> - [Determinants Class 12 Notes](https://www.geeksforgeeks.org/maths/cbse-class-12-maths-notes/#:~:text=)
> - [Determinants Class 12 NCERT Solutions](https://www.geeksforgeeks.org/maths/ncert-solutions-for-class-12-maths/#:~:text=)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/properties-of-determinants-of-matrices/)

## GATE CS

- Subject: Engineering Mathematics
- Topic: Linear Algebra

> [!note] Related notes
>
> - [[Cayley Hamilton Theorem]]
> - [[Determinants]]
> - [[Different Operations on matrices]]
> - [[Eigenvalues and Eigenvectors]]
> - [[Introduction to Matrix]]
> - [[LU Decomposition]]
> - [[Matrix Diagonalization]]
> - [[Null Space and Nullity of a Matrix]]
> - [[Rank of a Matrix]]
> - [[Row Echelon Form]]
