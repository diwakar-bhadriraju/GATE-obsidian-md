---
title: "Row Echelon Form"
subject: "Engineering Mathematics"
topic: "Linear Algebra"
source: "https://www.geeksforgeeks.org/machine-learning/row-echelon-form/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Linear Algebra"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/linear-algebra
---


> [!abstract] Row Echelon Form
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Linear Algebra`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/machine-learning/row-echelon-form/)

---

# Row Echelon Form

**Row Echelon Form (REF)** of a matrix simplifies solving systems of linear equations, understanding linear transformations, and working with matrix equations.
A matrix is in Row Echelon form if it has the following properties:
- **Zero Rows at the Bottom**: If there are any rows that are completely filled with zeros they should be at the bottom of the matrix.
- **Leading 1s**: In each non-zero row, the first non-zero entry (called a leading entry) can be any non-zero number. It does not have to be 1.
- **Staggered Leading 1s**: The leading entry in any row must be to the right of the leading entry in the row above it.
Below is an example of row-echelon form: 
$$
\begin{bmatrix} 1 & 2 & -1  & 4 \\ 0 & 1 &  0 & 3 \\ 0 & 0 &  1 & 2 \end{bmatrix}
$$
### Reduced Row Echelon Form
A matrix is in **Reduced Row Echelon Form (RREF)** if:
- **Zero Rows at the Bottom**: Any row that consists entirely of zeros must be at the bottom of the matrix.
- **Leading Entries**: The first non-zero entry in each non-zero row must be 1.
- **Staggered Leading Entries**: The leading 1 in each row must be to the right of the leading 1 in the row above it.
- **Column of Leading 1s**: Each leading 1 is the only non-zero entry in its column. This means that all other entries in the column containing a leading 1 must be zero.
Example of reduced row echelon form:
$$
\begin{bmatrix} 0 & 1 & 0  & 5 \\ 0 & 0 &  1 & 3 \\ 0 & 0 &  0 & 0 \end{bmatrix}
$$
### Gaussian Elimination
Gaussian Elimination is a way of converting a matrix into the reduced row echelon form. It can also be used as a way of finding a solution to a solution to the system of linear equations. The idea behind this is that we perform some mathematical operations on the row and continue until only one variable is left.
Below are some operations which we can perform:
- Interchange any two rows
- Add two rows together.
- Multiply one row by a non-zero constant (i.e. 1/3, -1/5, 2).
## Solving a System of Linear Equations
Consider the following linear equation:
$$
x - 2y + z = -1
$$
$$
2x + y - 3z = 8
$$
$$
4x - 7y + z = -2
$$
### S**tep 1: Write the Augmented Matrix**
$$
\begin{bmatrix} 1 & -2 &  1 & : & -1 \\ 2 &  1 &  3 & : & 8\\ 4 & -7 &  1 & : & -2 \end{bmatrix}
$$
### **Step 2: Convert to Row Echelon Form**
Now, we need to convert this into the row-echelon form. To convert this into row-echelon form, we need to perform Gaussian Elimination.
First we need to subtract 2\*r1 from the r2 and 4\*r1 from the r3 to get the 0 in the first place of r2 andr3.
$$
\begin{bmatrix} 1 & -2 &  1 & : & -1 \\ 0 &  5 &  -5 & : & 10\\ 0 &  1 &  -3 & : & 2 \end{bmatrix}
$$
Next we will interchange the rows r2 and r3 and after that subtract 5\*r2 from r3 to get the second 0 in the third row.
$$
\begin{bmatrix} 1 & -2 &  1 & : & -1 \\ 0 &  1 &  -3 & : & 2\\ 0 &  0 &  10 & : & 0 \end{bmatrix}
$$
### **Step 3: Back Substitution**
Now we can find the value **z** from r3, i.e 10 z =0 ⇾ z=0. With the help of the value of z =0 we can put it to r2, y = 2. Similarly we can put the value of y and z in r1 and we get a value of x=3
## **Rank of matrix**
The [rank of the matrix](https://www.geeksforgeeks.org/maths/rank-of-matrix/) is the number of non-zero rows in the row echelon form. To find the rank we need to perform the following steps:
- Find the row-echelon form of the given matrix
- Count the number of non-zero rows.
Let's take an example matrix:
$$
\begin{bmatrix} 4 & 0 & 1\\   2 & 0 & 2\\   3 & 0 & 3 \end{bmatrix}
$$
Now we reduce the above matrix to row-echelon form
$$
\begin{bmatrix} 1 & 0 & \frac{1}{4}\\   0 & 0 & 1\\   0 & 0 & 0 \end{bmatrix}
$$
Here only two row contains non-zero elements. Hence the rank of the matrix is 2.
## Implementation of Reduced Row-Echelon Form Using SymPy
To convert a matrix into reduced row-echelon form, we used the Sympy package in python first we need to install it.
To install it we use pip command:
```
! pip install sympy
```
````python3
import sympy
print(sympy.Matrix([[4,0,1],[2,0,2],[3,0,3]]).rref())
print("Rank of matrix:",sympy.Matrix([[4,0,1],[2,0,2],[3,0,3]]).rank())
````
**Output:**
```
(Matrix([ [1, 0, 0], [0, 0, 1], [0, 0, 0]]), (0, 2))  Rank of matrix : 2
```
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/machine-learning/row-echelon-form/)

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
> - [[Rank of a Matrix]]
