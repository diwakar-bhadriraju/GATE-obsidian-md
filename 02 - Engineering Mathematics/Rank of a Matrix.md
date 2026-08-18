---
title: "Rank of a Matrix"
subject: "Engineering Mathematics"
topic: "Linear Algebra"
source: "https://www.geeksforgeeks.org/maths/rank-of-matrix/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Linear Algebra"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/linear-algebra
---


> [!abstract] Rank of a Matrix
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Linear Algebra`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/rank-of-matrix/)

---

# Rank of a Matrix

The Rank of a Matrix is the maximum number of [linearly independent](https://www.geeksforgeeks.org/maths/linear-independence/) rows or columns in a matrix. It essentially determines the dimensionality of the vector space formed by the rows or columns of the matrix, i.e. the unique information the matrix contains.
It helps determine:
- If a system of linear equations has solutions.
- How many rows or columns contain unique information in the matrix.
![inverse_and_rank_of_a_matrix](assets/inverse_and_rank_of_a_matrix-365f763de6.webp)
The rank of a matrix is denoted using ρ(A), where A is any matrix. Thus, the number of rows of a matrix is a limit on the rank of the matrix, which means the rank of the matrix cannot exceed the total number of rows in a matrix.
**For example**, if a matrix is of the order 3×3, then the maximum rank of a matrix can be 3.
## Nullity of Matrix
Every column either contributes to the rank (it's linearly independent) or falls into the null space (it's a combination of others).
The number of vectors in the null space is called the nullity of the matrix.
> Total columns in a matrix = Rank + Nullity
This relation is known as the [Rank Nullity](https://www.geeksforgeeks.org/maths/rank-and-nullity/) theorem.
## Finding Rank of a Matrix
3 methods can be used to get the rank of any given matrix. These methods are as follows:
- Minor Method
- Using Elementary Operations
  - Row Echelon Form
  - Normal Form
### 1. Minor Method
To find the rank of a matrix using the [minor method](https://www.geeksforgeeks.org/dsa/minors-and-cofactors/), the following steps are followed:
- Calculate the determinant of the matrix (say A).
- If det(A) ≠ 0, then the rank of matrix A = order of matrix A.
- If det(A) = 0, then the rank of the matrix is equal to the order of the maximum possible nonzero minor of the matrix.
**Example:** Find the rank of a matrix
$$
\begin{bmatrix}1 & 2 & 3\\4 & 5 & 6 \\ 7 & 8 & 7\end{bmatrix}
$$
using the minor method.
> Given
>
>
$$
A = \begin{bmatrix}1 & 2 & 3\\4 & 5 & 6 \\ 7 & 8 & 7\end{bmatrix}
$$
>
> - Step 1: Calculate the determinant of A
>
> det(A) = 1 (35 - 48) - 2 (28 - 42) + 3 (32 - 35)
> det(A) = -13 + 28 - 9 = 6
>
> - As det(A) ≠ 0,
>   ρ(A) = order of A = 3
### 2. Elementary Operations
Elementary operations are reversible transformations that preserve rank. They come in three types
- Row/Column Swap (Ri ↔ Rj​)
- Row/Column Scaling (Ri → kRi, k≠0)
- Row/Column Replacement (Ri ​→ Ri ​+ kRj​)
We use these [elementary row operations](https://www.geeksforgeeks.org/maths/elementary-operations-on-matrices/) to find Rank by converting the matrix into either:
**(a) Row/Column Echelon Form**
The following steps are followed to calculate the rank of a matrix using the Echelon form:
- Locate the leftmost non-zero column (this is the pivot column) of the matrix.
- If needed, swap rows to bring a non-zero entry to the top of this column.
- Use row replacement to make all entries below the pivot zero.
- Move to the next row and next column (diagonally down-right).
- Repeat these steps until no more pivots can be formed.
- Count the non-zero rows → that’s the rank.
**Example 1:** Find the rank of a matrix
$$
\begin{bmatrix}1 & 2 & 3\\4 & 5 & 6 \\ 7 & 8 & 9\end{bmatrix}
$$
using the Elementary Operations.
> Given
>
>
$$
A = \begin{bmatrix}1 & 2 & 3\\4 & 5 & 6 \\ 7 & 8 & 9\end{bmatrix}
$$
>
> - Convert A to echelon form
>
> Apply R2 = R2 - 4R1
> Apply R3 = R3 - 7R1
>
>
$$
A = \begin{bmatrix}1 & 2 & 3\\0 & -3 & -6 \\ 0 & -6 & -12\end{bmatrix}
$$
>
> Apply R3 = R3 - 2R2
>
>
$$
A = \begin{bmatrix}1 & 2 & 3\\0 & -3 & -6 \\ 0 & 0 & 0\end{bmatrix}
$$
>
> As matrix A is now in lower triangular form, it is in Echelon Form.
>
> - Number of non-zero rows in A = 2.
>   Thus ρ(A) = 2
**Example 2:** Find the rank of a matrix
$$
\begin{bmatrix}1 & 2 & 3\\2 & 4 & 6 \\ 1 & 1 & 1\end{bmatrix}
$$
using the Elementary Operations.
> Given
>
>
$$
\begin{bmatrix}1 & 2 & 3\\2 & 4 & 6 \\ 1 & 1 & 1\end{bmatrix}
$$
>
> - Convert A to echelon form
>
> Apply R2 = R2 - 2R1
> Apply R3 = R3 - R1
>
>
$$
A = \begin{bmatrix}1 & 2 & 3\\0 & 0 & 0 \\ 0 & -1 & -2\end{bmatrix}
$$
>
> Swap R3 and R2
>
>
$$
A = \begin{bmatrix}1 & 2 & 3\\0 & -1 & -2 \\ 0 & 0 & 0\end{bmatrix}
$$
>
> As matrix A is in Echelon Form.
>
> - Number of non-zero rows in A = 2.
>   Thus ρ(A) = 2
**Example 3:** Find the rank of a matrix
$$
\begin{bmatrix}2 & 4 & -2\\4 & 9 & -3 \\ -2 & -3 & 7\end{bmatrix}
$$
using the Elementary Operations.
> Given A =
>
>
$$
\begin{bmatrix}2 & 4 & -2\\4 & 9 & -3 \\ -2 & -3 & 7\end{bmatrix}
$$
>
> - Convert A to echelon form
>
> Apply R2 = R2 - 2R1
> Apply R3 = R3 - R1
>
> A =
>
>
$$
\begin{bmatrix}2 & 4 & -2\\0 & 1 & 1 \\ 0 & 1 & 5\end{bmatrix}
$$
>
> R3 = R3 - R2
>
>
$$
A = \begin{bmatrix}2 & 4 & -2\\0 & 1 & 1 \\ 0 & 0 & 4\end{bmatrix}
$$
>
> As matrix A is in Echelon Form.
>
> - Number of non-zero rows in A = 3.
>   Thus ρ(A) = 3
**(b) Normal Form**
A matrix is said to be in normal form if it can be reduced to the form
$$
\begin{bmatrix}   I_r & 0\\  0 & 0\\   \end{bmatrix}
$$
. Here, Ir represents the identity matrix of order r.
If a matrix can be converted to its normal form, then the rank of the matrix is said to be r.
**Example:** Find the rank of a matrix
$$
\bold{\begin{bmatrix}1 & 2 & 1 & 2\\1 & 3 & 2 & 2 \\ 2 & 4 & 3 & 4 \\3 & 7 & 4 & 6\end{bmatrix}}
$$
using the normal form method.
**Solution:**
> Given
>
>
$$
A = \begin{bmatrix}1 & 2 & 1 & 2\\1 & 3 & 2 & 2 \\ 2 & 4 & 3 & 4 \\3 & 7 & 4 & 6\end{bmatrix}
$$
>
> Apply R2 = R2 - R1  , R3 = R3 - 2R1 and R4 = R4 - 3R1
>
>
$$
A = \begin{bmatrix}1 & 2 & 1 & 2\\0 & 1 & 1 & 0 \\ 0 & 0 & 1 & 0 \\0 & 1 & 1 & 0\end{bmatrix}
$$
>
> Apply R1 = R1 - 2R2 and R4 = R4 - R2
>
>
$$
A = \begin{bmatrix}1 & 0 & -1 & 2\\0 & 1 & 1 & 0 \\ 0 & 0 & 1 & 0 \\0 & 0 & 0 & 0\end{bmatrix}
$$
>
> Apply R1 = R1 + R3 and R2 = R2 - R3
>
>
$$
A = \begin{bmatrix}1 & 0 & 0 & 2\\0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\0 & 0 & 0 & 0\end{bmatrix}
$$
>
> Apply C4 → C4 - 2C1
>
>
$$
A = \begin{bmatrix}1 & 0 & 0 & 0\\0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\0 & 0 & 0 & 0\end{bmatrix}
$$
>
> Thus A can be written as
>
>
$$
\begin{bmatrix}   I_3 & 0\\  0 & 0\\   \end{bmatrix}
$$
>
> .
>
> Thus, ρ(A) = 3
## Properties of Rank of a Matrix
The properties of the rank of a matrix are as follows:
- Rank ≤ min(m, n) for an m×n matrix
- The rank of a matrix is equal to the number of non-zero rows if it is in Echelon Form.
- Rank(A) = Rank(AT), Rank of a matrix and it's [transpose](https://www.geeksforgeeks.org/maths/transpose-of-a-matrix/) are equal.
- The rank of the identity matrix is equal to the order of the identity matrix.
- [Rank of matrix] < [Order of matrix], if it is a singular matrix.
- [Rank of matrix] < [minimum {m, n}], if it is a rectangular matrix of order m x n.
- The rank of a [zero matrix](https://www.geeksforgeeks.org/maths/zero-matrix/) or a null matrix is zero.
## Solved Examples
**Example 1:** Find the rank of a matrix
$$
\begin{bmatrix}-1 & -2 & -3\\-4 & -5 & -6 \\ -7 & -8 & -7\end{bmatrix}
$$
using the minor method.
**Solution:**
> Given
>
>
$$
A = \begin{bmatrix}-1 & -2 & -3\\-4 & -5 & -6 \\ -7 & -8 & -7\end{bmatrix}
$$
>
> Step 1: Calculate the determinant of A
> det(A) = -1 (35 - 48) + 2 (28 - 42) - 3 (32 - 35)
> det(A) = 13 - 28 - 9 = -24
> As det(A) ≠ 0, ρ(A) = order of A = 3
**Example 2:** Find the rank of a matrix
$$
\bold{\begin{bmatrix}2 & 4 & 6\\8 & 10 & 12 \\ 14 & 16 & 0\end{bmatrix}}
$$
using the minor method.
**Solution:**
> Given
>
>
$$
A = \begin{bmatrix}2 & 4 & 6\\8 & 10 & 12 \\ 14 & 16 & 0\end{bmatrix}
$$
>
> Step 1: Calculate the determinant of A
> det(A) = 2(0-192) - 4(0-168) + 6(128-140)
> det(A) = -384 + 672 - 72 = 216
> As det(A) ≠ 0, ρ(A) = order of A = 3
**Example 3:** Find the rank of a matrix
$$
\bold{\begin{bmatrix}-1 & -2 & -3\\-4 & -5 & -6 \\ -7 & -8 & -9\end{bmatrix}}
$$
using the Echelon form method.
**Solution:**
> Given
>
>
$$
A = \begin{bmatrix}-1 & -2 & -3\\-4 & -5 & -6 \\ -7 & -8 & -9\end{bmatrix}
$$
>
> Step 1: Convert A to echelon form
> Apply R2 = R2 - 4R1
> Apply R3 = R3 - 7R1
>
>
$$
A = \begin{bmatrix}-1 & -2 & -3\\0 & 3 & 6 \\ 0 & 6 & 12\end{bmatrix}
$$
>
> Apply R3 = R3 - 2R2
>
>
$$
A = \begin{bmatrix}-1 & -2 & -3\\0 & 3 & 6 \\ 0 & 0 & 0\end{bmatrix}
$$
>
> As matrix A is now in lower triangular form, it is in Echelon Form.
>
> Step 2: Number of non-zero rows in A = 2.
> Thus ρ(A) = 2
**Example 4:** Find the rank of a matrix
$$
\bold{\begin{bmatrix}2 & 4 & 6\\8 & 10 & 12 \\ 14 & 16 & 18\end{bmatrix}}
$$
using the Echelon form method.
**Solution:**
> Given
>
>
$$
A = \begin{bmatrix}2 & 4 & 6\\8 & 10 & 12 \\ 14 & 16 & 18\end{bmatrix}
$$
>
> Step 1: Convert A to echelon form
> Apply R2 = R2 - 4R1
> Apply R3 = R3 - 7R1
>
>
$$
A = \begin{bmatrix}2 & 4 & 6\\0 & -6 & -12 \\ 0 & -12 & -24\end{bmatrix}
$$
>
> Apply R3 = R3 - 2R2
>
>
$$
A = \begin{bmatrix}2 & 4 & 6\\0 & -6 & -12 \\ 0 & 0 & 0\end{bmatrix}
$$
>
> As matrix A is now in lower triangular form, it is in Echelon Form.
>
> Step 2: Number of non-zero rows in A = 2.
> Thus ρ(A) = 2
**Example 5:** Find the rank of a matrix
$$
\bold{\begin{bmatrix}2 & 4 & 2 & 4\\2 & 6 & 4 & 4 \\ 4 & 8 & 6 & 8 \\6 & 14 & 8 & 12\end{bmatrix}}
$$
using the normal form method.
**Solution:**
> Given
>
>
$$
A = \begin{bmatrix}2 & 4 & 2 & 4\\2 & 6 & 4 & 4 \\ 4 & 8 & 6 & 8 \\6 & 14 & 8 & 12\end{bmatrix}
$$
>
> Apply R2 = R2 - R1 , R3 = R3 - 2R1 and R4 = R4 - 3R1
>
>
$$
A = \begin{bmatrix}2 & 4 & 2 & 4\\0 & 2 & 2 & 0 \\ 0 & 0 & 2 & 0 \\0 & 2 & 2 & 0\end{bmatrix}
$$
>
> Apply R1 = R1 - 2R2 and R4 = R4 - R2
>
>
$$
A = \begin{bmatrix}2 & 0 & -2 & 4\\0 & 2 & 2 & 0 \\ 0 & 0 & 2 & 0 \\0 & 0 & 0 & 0\end{bmatrix}
$$
>
> Apply R1 = R1 + R3 and R2 = R2 - R3
>
>
$$
A = \begin{bmatrix}2 & 0 & 0 & 4\\0 & 2 & 0 & 0 \\ 0 & 0 & 2 & 0 \\0 & 0 & 0 & 0\end{bmatrix}
$$
>
> Apply C4 → C4 - 2C1
>
>
$$
A = \begin{bmatrix}2 & 0 & 0 & 0\\0 & 2 & 0 & 0 \\ 0 & 0 & 2 & 0 \\0 & 0 & 0 & 0\end{bmatrix}
$$
>
> Apply R1 = R1/2, R2 = R2/2, R3 = R3/2
>
>
$$
A = \begin{bmatrix}1 & 0 & 0 & 0\\0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\0 & 0 & 0 & 0\end{bmatrix}
$$
>
> Thus A can be written as
>
>
$$
\begin{bmatrix}   I_3 & 0\\  0 & 0\\   \end{bmatrix}
$$
>
>
> Thus, ρ(A) = 3
### Related Articles
> - [Matrices](https://www.geeksforgeeks.org/engineering-mathematics/matrices/)
> - [Types of Matrices](https://www.geeksforgeeks.org/maths/types-of-matrices/)
> - [Transpose of a Matrix](https://www.geeksforgeeks.org/maths/transpose-of-a-matrix/)
> - [Inverse of Matrix](https://www.geeksforgeeks.org/maths/inverse-of-matrix/)
> - [Triangular Matrix](https://www.geeksforgeeks.org/maths/triangular-matrix/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/rank-of-matrix/)

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
> - [[Properties of Determinants]]
> - [[Row Echelon Form]]
