---
title: "Matrix Diagonalization"
subject: "Engineering Mathematics"
topic: "Linear Algebra"
source: "https://www.geeksforgeeks.org/dsa/matrix-diagonalization/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Linear Algebra"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/linear-algebra
---


> [!abstract] Matrix Diagonalization
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Linear Algebra`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/matrix-diagonalization/)

---

# Matrix Diagonalization

Matrix diagonalization is the process of reducing a square matrix into its diagonal form using a similarity transformation. This process is useful because diagonal matrices are easier to work with, especially when raising them to integer powers.
Not all matrices are diagonalizable. A matrix is diagonalizable if it has no defective eigenvalues, meaning each eigenvalue's geometric multiplicity is equal to its algebraic multiplicity.
![Diaognalize-the-Matrix-1](assets/Diaognalize-the-Matrix-1-ca17a89a3c.webp)
Matrix Diagonalization
### Matrix Similarity Transformation
Let A and B be two matrices of order n. Matrix B is considered similar to A if there exists an [invertible matrix](https://www.geeksforgeeks.org/maths/invertible-matrix/) P such that:
B = P-1 A P
This transformation is known as Matrix Similarity Transformation. Similar matrices have the same rank, trace, determinant, and eigenvalues. Additionally, the eigenvalues of similar matrices maintain their [algebraic and geometric multiplicities](https://www.geeksforgeeks.org/engineering-mathematics/algebraic-and-geometric-multiplicity/).
## Diagonalization of a Matrix
Diagonalization of a matrix refers to the process of transforming any matrix A into its diagonal form D. According to the similarity transformation, if A is diagonalizable, then:
$$
D=P^{-1} A P
$$
where D is a [diagonal matrix](https://www.geeksforgeeks.org/maths/diagonal-matrix/) and P is a modal matrix.
A modal matrix is an n × n matrix consisting of the [eigenvectors](https://www.geeksforgeeks.org/engineering-mathematics/eigen-values/) of A. It is essential in the process of diagonalization and similarity transformation.
> In simpler words, it is the process of taking a [square matrix](https://www.geeksforgeeks.org/maths/square-matrix/) and converting it into a special type of matrix called a [diagonal matrix](https://www.geeksforgeeks.org/maths/diagonal-matrix/).
### **Steps** to Diagonalize a Matrix
> **Step 1:** Initialize the diagonal matrix D as:
>
>
$$
D=\left[\begin{array}{ccc} \lambda_{1} & 0 & 0 \\ 0 & \lambda_{2} & 0 \\ 0 & 0 & \lambda_{3} \end{array}\right]
$$
>
> where **λ**1,** **λ**2**, λ**3** **->** eigen values
>
> **Step 2:** Find the eigen values using the equation given below.
>
>
$$
\operatorname{det}(A-\lambda I)=0
$$
>
>  
> where, **A ->** given 3x3 [square matrix](https://www.geeksforgeeks.org/maths/square-matrix/).
> **I ->** identity matrix of size 3x3.
> **λ ->** eigen value.
>
> **Step 3:** Compute the corresponding eigen vectors using the equation given below.
> At **λ**=i
>
>
$$
[A - \lambda I] X_i = 0
$$
>
>
> where, **λ**i -> eigen value.
> **X**i** -> corresponding eigen vector.
>
> **Step 4:** Create the modal matrix P.
>
>
$$
P=\left[X_{0} X_{1} . . X_{n}\right]
$$
>
> Here, all the eigenvectors till Xi have filled column-wise in matrix P. 
>
> **Step 5:** Find P-1 and then use the equation given below to find [diagonal matrix](https://www.geeksforgeeks.org/maths/diagonal-matrix/) D.
>
>
$$
D=P^{-1} A P
$$
### **Example Problem**
**Problem Statement:** Assume a 3x3 square matrix A having the following values:
$$
A=\left[\begin{array}{ccc} 1 & 0 & -1 \\ 1 & 2 & 1 \\ 2 & 2 & 3 \end{array}\right]
$$
Find the diagonal matrix D of A using the [diagonalization of the matrix](https://www.geeksforgeeks.org/maths/diagonal-matrix/). [ D = P-1AP ]
**Solution:**
**Step 1:** Initializing D as:
$$
D=\left[\begin{array}{ccc} \lambda_{1} & 0 & 0 \\ 0 & \lambda_{2} & 0 \\ 0 & 0 & \lambda_{3} \end{array}\right]
$$
**Step 2:** Find the eigen values. (or possible values of λ)
$$
\operatorname{det}(A-\lambda I)=0
$$
$$
\begin{array}{l} \Longrightarrow \operatorname{det}(A-\lambda I)=\operatorname{det}\left(\left[\begin{array}{ccc} 1-\lambda & 0 & -1 \\ 1 & 2-\lambda & 1 \\ 2 & 2 & 3-\lambda \end{array}\right]\right)=0 \\ \Longrightarrow\left(\lambda^{3}-6 \lambda^{2}+11 \lambda-6\right)=0 & \\ \Longrightarrow(\lambda-1)(\lambda-2)(\lambda-3)=0 \end{array}
$$
$$
⟹\lambda=1,2,3
$$
**Step 3:** Find the eigen vectors X1, X2, X3 corresponding to the eigen values λ = 1,2,3. 
At λ=1
$$
(A - (1) I) X_{1}=0
$$
$$
\Longrightarrow \begin{bmatrix}  1-1 & 0 & -1 \\   1 & 2-1 & 1 \\   2 & 2 & 3-1   \end{bmatrix}   \begin{bmatrix} x_{1} \\ x_{2} \\ x_{3} \end{bmatrix}   = \begin{bmatrix} 0 \\ 0 \\ 0 \end{bmatrix}
$$
$$
\Longrightarrow \begin{bmatrix}   0 & 0 & -1 \\   1 & 1 & 1 \\   2 & 2 & 2   \end{bmatrix}   \begin{bmatrix} x_{1} \\ x_{2} \\ x_{3} \end{bmatrix}   = \begin{bmatrix} 0 \\ 0 \\ 0 \end{bmatrix}
$$
On solving, we get the following equations:
$$
x_{3}=0(x_{1})
$$
$$
x_{1}+x_{2}=0 \Longrightarrow x_{2}=-x_{1}
$$
$$
\therefore X_{1}= \begin{bmatrix} x_{1} \\ -x_{1} \\ 0(x_{1}) \end{bmatrix}
$$
$$
\Longrightarrow X_{1}= \begin{bmatrix} 1 \\ -1 \\ 0 \end{bmatrix}
$$
Similarly, for λ=2:
$$
X_{2}= \begin{bmatrix} -2 \\ 1 \\ 2 \end{bmatrix}
$$
And for λ=3 :
$$
X_{3}= \begin{bmatrix} 1 \\ -1 \\ -2 \end{bmatrix}
$$
**Step 5:** Creation of modal matrix P. (here, X1, X2, X3 are column vectors)
$$
P=\left[X_{1} X_{2} X_{3}\right]=\left[\begin{array}{ccc} 1 & -2 & 1 \\ -1 & 1 & -1 \\ 0 & 2 & -2 \end{array}\right]
$$
**Step 6:** Finding P-1 and then putting values in diagonalization of a matrix equation **[D= P**-1** **AP]**
We do Step 6 to find out which eigenvalue will replace λ1, λ2, and λ3 in the initial diagonal matrix created in Step 1.
$$
\begin{array}{l} \begin{array}{l} \quad P=\left[\begin{array}{ccc} 1 & -2 & 1 \\ -1 & 1 & -1 \\ 0 & 2 & -2 \end{array}\right] \\\\ \operatorname{det}(P)=[0+(4)+(-2)] \\ =2 \end{array}\\\\ \text { Since } \operatorname{det}(P) \neq 0 \Longrightarrow \text { Matrix } P \text { is invertible. } \end{array}
$$
We know that 
$$
P^{-1}=\frac{\operatorname{adj}(P)}{\operatorname{det}(P)}
$$
On solving, we get  
$$
P^{-1}=\frac{1}{2}\left[\begin{array}{ccc} 0 & -2 & 1 \\ -2 & -2 & 0 \\ -2 & -2 & -1 \end{array}\right]
$$
Putting in the Diagonalization of Matrix equation, we get 
$$
\begin{array}{l} \quad D=P^{-1} A P \\\\ D=\frac{1}{2}\left[\begin{array}{ccc} 0 & -2 & 1 \\ -2 & -2 & 0 \\ -2 & -2 & -1 \end{array}\right]\left[\begin{array}{ccc} 1 & 0 & -1 \\ 1 & 2 & 1 \\ 2 & 2 & 3 \end{array}\right]\left[\begin{array}{ccc} 1 & -2 & 1 \\ -1 & 1 & -1 \\ 0 & 2 & -2 \end{array}\right] \\\\ D=\left[\begin{array}{lll} 1 & 0 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 3 \end{array}\right] \end{array}
$$
## `MATLAB Implementation for Diagonalization of a Square Matrix`
Matlab
````matlab
% MATLAB Implementation for
% Diagonalization of a Square Matrix:
clear all
clc
disp("MATLAB Implementation for Diagonalization
 of a Square Matrix | GeeksforGeeks")
A = input("Enter a matrix A : ");
[P , D] = eig(A);
D1 = inv(P)*(A)*(P);
disp("Diagonal form 'D' of Input Matrix 'A' is:")
disp(D1)
````
**Output:**
For the Matrix: 
$$
A = \begin{bmatrix} 1 &  3\\ 3 &  9\\ \end{bmatrix}
$$
![](assets/output1-11d2a6239d.jpg)
For the Matrix:  
$$
A = \begin{bmatrix} 1 & 0 & -1 \\ 1 & 2 & 1 \\ 2 &  2&  3\\ \end{bmatrix}
$$
![](assets/output2-e39cef830b.jpg)
## **The Diagonalization is Not Unique**
If a matrix A is diagonalizable, there is no unique way to diagonalize it.
1. The order of eigenvalues in the diagonal matrix D can be changed.
2. A column in P can be replaced with a scalar multiple of itself, as it remains an eigenvector for the same eigenvalue.
3. If an eigenvalue is repeated, different bases for its eigenspace can be chosen.
### **Example**
in the previous example, we could have defined:
$$
D = \begin{bmatrix} \lambda_2 & 0 & 0 \\ 0 & \lambda_1 & 0 \\ 0 & 0 & \lambda_3 \end{bmatrix} = \begin{bmatrix} 3 & 0 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 1 \end{bmatrix}
$$
and
$$
P = \begin{bmatrix} x_2 & x_1 & x_3 \end{bmatrix} = \begin{bmatrix} 1 & 0 & -1 \\ 1 & 2 & 1 \\ 2 & 2 & 3 \end{bmatrix}
$$
Another possibility would have been to choose:
$$
x_2 = \begin{bmatrix} -1 \\ -1 \\ -2 \end{bmatrix}
$$
and
$$
P = \begin{bmatrix} x_2 & x_1 & x_3 \end{bmatrix} = \begin{bmatrix} -1 & 0 & -1 \\ -1 & 2 & 1 \\ -2 & 2 & 3 \end{bmatrix}
$$
This shows that diagonalization is not unique since we can change eigenvectors by scalar multiples or reorder them while maintaining the same eigenvalues.
## **Inverse Matrix**
Once a matrix has been diagonalized, computing its inverse (if it exists) becomes straightforward.
In fact, we have:
$$
A^{-1} = (PDP^{-1})^{-1} =P D^{-1} P^{-1}
$$
where:
$$
D^{-1} = \text{diag} \left(\frac{1}{\lambda_1}, \frac{1}{\lambda_2}, \dots, \frac{1}{\lambda_n} \right)
$$
provided none of the eigenvalues **λ** are zero.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/matrix-diagonalization/)

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
> - [[Null Space and Nullity of a Matrix]]
> - [[Properties of Determinants]]
> - [[Rank of a Matrix]]
> - [[Row Echelon Form]]
