---
title: "LU Decomposition"
subject: "Engineering Mathematics"
topic: "Linear Algebra"
source: "https://www.geeksforgeeks.org/engineering-mathematics/l-u-decomposition-system-linear-equations/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Linear Algebra"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/linear-algebra
---


> [!abstract] LU Decomposition
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Linear Algebra`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/l-u-decomposition-system-linear-equations/)

---

# LU Decomposition

LU decomposition or factorization of a matrix is the factorization of a given square matrix into two triangular matrices, one upper triangular matrix and one lower triangular matrix, such that the product of these two matrices gives the original matrix. It is a fundamental technique in linear algebra used to solve systems of linear equations, invert matrices, and compute determinants. Computers usually solve square [systems of linear equations](https://www.geeksforgeeks.org/engineering-mathematics/system-linear-equations/) using LU decomposition.
> LU decomposition breaks a matrix into two simpler matrices: one with numbers below the diagonal (L) and one above the diagonal (U). This makes solving equations, finding inverses and calculating determinants easier.
![LU_Decomposition](assets/LU_Decomposition-0eaa92aaca.webp)
LU Decomposition expresses a given square matrix A as the product of two matrices:
- **L: A lower triangular matrix with ones on the diagonal.**
- **U: An upper triangular matrix.**
Mathematically, A can be written as
> **A = L** × **U**
**Example:** Given matrix :
$$
A = \begin{pmatrix} 4 & 3 \\ 6 & 3 \end{pmatrix}
$$
> Start with Gaussian elimination:
>
> Subtract
>
>
$$
\frac{6}{4}​
$$
>
>  times the first row from the second row.
>
>
>
$$
U = \begin{pmatrix} 4 & 3 \\ 0 & \frac{3}{2} \end{pmatrix}
$$
>
>
> Find L :
>
>
$$
L = \begin{pmatrix} 1 & 0 \\ 1.5 & 1 \end{pmatrix}
$$
>
>
> Verify:
>
>
$$
A = L \times U = \begin{pmatrix} 1 & 0 \\ 1.5 & 1 \end{pmatrix} \times \begin{pmatrix} 4 & 3 \\ 0 & \frac{3}{2} \end{pmatrix} = \begin{pmatrix} 4 & 3 \\ 6 & 3 \end{pmatrix}
$$
>
> Thus, LU decomposition gives:
>
>
$$
L = \begin{pmatrix} 1 & 0 \\ 1.5 & 1 \end{pmatrix}, \quad U = \begin{pmatrix} 4 & 3 \\ 0 & -1.5 \end{pmatrix}
$$
**LU Decomposition Method**
To factor any square matrix into two triangular matrices, i.e., one is a lower triangular matrix and the other is an upper triangular matrix, we can use the following steps.
#### Steps for LU Decomposition:
**Start with a square matrix A**: Given a square matrix A of size n ×n, the goal is to factor it into the product of two matrices: A = L×U, where:
- L is a lower triangular matrix with 1s on the diagonal.
- U is an upper triangular matrix.
**Gaussian Elimination**: Apply [Gaussian elimination](https://www.geeksforgeeks.org/dsa/gaussian-elimination/) to convert matrix A into upper triangular form U. This step involves row operations to eliminate elements below the diagonal, resulting in an upper triangular matrix.
**Track the Row Operations:** As you perform row operations, keep track of the multipliers used to eliminate the elements below the diagonal. These multipliers form the entries of the lower triangular matrix L.
- The entries of L will be the factors used during the elimination steps.
- The diagonal of L will consist of 1s.
**Extract the Matrices L and U:**
- After the elimination process, the resulting upper triangular matrix is U.
- The lower triangular matrix L consists of the multipliers you tracked during the Gaussian elimination.
**Check the Result:**Verify that the product of L and U yields the original matrix A: A = L × U. This confirms the correctness of the LU Decomposition.
## **Example of LU Decomposition**
Solve the following system of equations using the LU Decomposition method:
>
$$
x_1 + x_2 + x_3 = 1 \\4x_1 + 3x_2 – x_3 = 6\\3x_1 + 5x_2 + 3x_3 = 4
$$
**Solution:**
Here, we have A =
$$
\begin{bmatrix} 1 & 1 & 1 \\ 4 & 3 & -1 \\ 3 & 5 & 3 \end{bmatrix} , X = \begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix}
$$
 and
$$
C = \begin{bmatrix} 1 \\ 6 \\ 4 \end{bmatrix}
$$
such that A X = C. Now, we first consider
$$
\begin{bmatrix} 1 & 1 & 1 \\ 4 & 3 & -1 \\ 3 & 5 & 3 \end{bmatrix}
$$
and convert it to row echelon form using the Gauss-Jordan Elimination Method. So, by doing
$$
R_2 \to R_2 – 4R_1
$$
$$
R_3 \to R_3 – 3R_1
$$
we get
$$
\begin{bmatrix} 1 & 1 & 1 \\ 0 & -1 & -5 \\ 0 & 2 & 0 \end{bmatrix}
$$
Now, by doing
$$
R_3 \to R_3 – (-2)R_2
$$
We get
$$
\sim \begin{bmatrix} 1 & 1 & 1 \\ 0 & -1 & -5 \\ 0 & 0 & -10 \end{bmatrix}
$$
(Remember to always keep the' – ' sign in between, replace the ' + ' sign with two ' – ' signs)
Hence, we get L =
$$
\begin{bmatrix} 1 & 0 & 0 \\ 4 & 1 & 0 \\ 3 & -2 & 1 \end{bmatrix}
$$
 and U =
$$
\begin{bmatrix} 1 & 1 & 1 \\ 0 & -1 & -5 \\ 0 & 0 & -10 \end{bmatrix}
$$
Notice that in the L matrix,
$$
l_{21} = 4
$$
 is from (1),
$$
l_{31} = 3
$$
 is from (2), and
$$
l_{32} = -2
$$
 is from (3)
Now, we assume Z
$$
= \begin{bmatrix} z_1 \\ z_2 \\ z_3 \end{bmatrix}
$$
and solve L Z = C,
$$
\begin{bmatrix} 1 & 0 & 0 \\ 4 & 1 & 0 \\ 3 & -2 & 1 \end{bmatrix} \begin{bmatrix} z_1 \\ z_2 \\ z_3 \end{bmatrix}
$$
$$
= \begin{bmatrix} 1 \\ 6 \\ 4 \end{bmatrix}
$$
So, we have
$$
z_1 = 1 ,
$$
$$
4z_1 + z_2 = 6 ,
$$
$$
3z_1 - 2z_2 + z_3 = 4 .
$$
Solving, we get
$$
z_1 = 1
$$
,
$$
z_2 = 2
$$
 and
$$
z_3 = 5
$$
Now, we solve U X = Z
$$
\begin{bmatrix} 1 & 1 & 1 \\ 0 & -1 & -5 \\ 0 & 0 & -10 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix}
$$
$$
= \begin{bmatrix} 1 \\ 2 \\ 5 \end{bmatrix}
$$
Therefore, we get
$$
x_1 + x_2 + x_3 = 1 ,
$$
$$
-x_2 - 5x_3 = 2
$$
$$
-10x_3 = 5 .
$$
Thus, the solution to the given system of linear equations is
$$
x_1 = 1
$$
$$
x_2 = 0.5
$$
$$
x_3 = -0.5
$$
and hence the matrix X =
$$
\begin{bmatrix} 1 \\ 0.5 \\ -0.5 \end{bmatrix}
$$
## Applications of LU decomposition
- **Structural Engineering:** Used to analyze forces in bridges and buildings, ensuring efficient and safe designs.
- **Computer Graphics:** Helps in transforming 3D objects, like rotating and scaling models, for smoother rendering.
- **Robotics:** Assists in solving kinematic equations, enabling real-time movement adjustments for robots.
- **Weather Prediction:** Speeds up the solving of climate models and weather simulations for accurate forecasting.
- **Electrical Engineering:** Used in circuit analysis to solve systems of equations for designing and optimizing electrical circuits.
- **Economics and Finance:** Helps solve economic models for resource allocation and market predictions efficiently.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/l-u-decomposition-system-linear-equations/)

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
> - [[Matrix Diagonalization]]
> - [[Null Space and Nullity of a Matrix]]
> - [[Properties of Determinants]]
> - [[Rank of a Matrix]]
> - [[Row Echelon Form]]
