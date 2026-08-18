---
title: "Eigenvalues and Eigenvectors"
subject: "Engineering Mathematics"
topic: "Linear Algebra"
source: "https://www.geeksforgeeks.org/engineering-mathematics/eigen-values/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Linear Algebra"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/linear-algebra
---


> [!abstract] Eigenvalues and Eigenvectors
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Linear Algebra`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/eigen-values/)

---

# Eigenvalues and Eigenvectors

Eigenvalues and eigenvectors are fundamental concepts in linear algebra, used in various applications such as matrix diagonalization, stability analysis, and data analysis (e.g., [Principal Component Analysis](https://www.geeksforgeeks.org/data-analysis/principal-component-analysis-pca/)). They are associated with a square matrix and provide insights into its properties.
## Eigenvalues
Eigenvalues are scalar values linked to a matrix or [linear transformation](https://www.geeksforgeeks.org/data-science/linear-mapping/). They indicate how much an eigenvector gets stretched or compressed during the transformation. The eigenvector's direction remains unchanged unless the eigenvalue is negative, in which case the direction is simply reversed.
The equation for eigenvalue is given by,
>
$$
Av = \lambda v
$$
>
>
> where,
>
> - A is the matrix,
> - v is associated eigenvector and
> - \lambda is scalar eigenvalue.
## Eigenvectors
Eigenvectors are non-zero vectors that, when multiplied by a matrix, change only in magnitude, not direction. Eigenvalues are found first. For an n × n matrix A, eigenvectors are n × 1 column vectors (right eigenvectors).
Alternatively, the left eigenvector can be found using the equation
$$
vA = λv
$$
, where v is a row matrix of size 1 × n.
### Eigenvector Equation
The Eigenvector equation is the equation that is used to find the eigenvector of any square matrix. The eigenvector equation is
>
$$
Av = λv
$$
>
> - A is the given square matrix,
> - v is the eigenvector of matrix A and
> -
$$
\lambda
$$
>
>    is any scaler multiple.
Here the left hand side is a matrix vector multiplication and right side is a scalar multiplication. So let's rewrite the right-hand side as matrix vector multiplication.
Right hand side represents scaling any vector by a factor of lambda which can be written as
$$
\lambda
$$
I =
$$
\begin{bmatrix} \lambda & 0 & 0 \\ 0 & \lambda & 0 \\ 0 & 0 & \lambda \end{bmatrix}
$$
$$
A \overrightarrow{v} = (Iλ)\overrightarrow{v}
$$
$$
A \overrightarrow{v}  - Iλ\overrightarrow{v}  = 0
$$
$$
(A - Iλ)\overrightarrow{v}  = 0
$$
Product of a matrix to a non-zero vector is zero only if the transformation associated with that matrix squishes space into lower dimension. That implies the determinant of that matrix is zero.
i.e. det(A - ƛI) = 0
## Finding an Eigenvector
The eigenvector of the following square matrix can be easily calculated using the steps below,
**Step 1:** Find the eigenvalues of the matrix A, using the equation det |(A – λI| =0, where “I” is the identity matrix of order similar to matrix A
**Step 2:** The value obtained in Step 2 are named as,
$$
λ _1, λ_2, λ_3….
$$
**Step 3:** Find the eigenvector (X) associated with the eigenvalue  λ1 using the equation,
$$
(A – λ_1I) X = 0
$$
**Step 4:** Repeat step 3 to find the eigenvector associated with other remaining eigenvalues
$$
λ_2, λ_3….
$$
Following these steps gives the eigenvector related to the given square matrix.
### Types of Eigenvector
The eigenvectors calculated for the square matrix are of two types which are,
- Right Eigenvector
- Left Eigenvector
**Right Eigenvector:** The eigenvector which is multiplied by the given square matrix from the right-hand side is called the right eigenvector. It is calculated by using the following equation,
>
$$
AV_R = \lambda V_R
$$
Where,
- A is given square matrix of order n×n,
- λ is one of the eigenvalues and
- VR is the column vector matrix
The value of VR is,
$$
\bold{V_{R} = \begin{bmatrix} v_{1}\\ v_{2}\\ v_{3}\\ .\\ .\\ v_{n}\\ \end{bmatrix}}
$$
**Left Eigenvector:** The eigenvector which is multiplied by the given square matrix from the left-hand side is called the left eigenvector. It is calculated by using the following equation,
>
$$
V_LA  = V_L\lambda
$$
>
> - A is given square matrix of order n×n,
> - λ is one of the eigenvalues and
> - V\_L is the row vector matrix.
The value of VL is,
$$
V_L = [v_1, v_2, v_3,..., v_n]
$$
## Eigenvectors of a Square Matrix
We can easily find the eigenvector of square matrices of order n × n. Now, let's find the following square matrices:
- Eigenvectors of a 2 × 2 matrix
- Eigenvectors of a 3 × 3 matrix.
### **Eigenvector of a 2 × 2 matrix**
The Eigenvector of the 2 × 2 matrix can be calculated by,
- Find the eigenvalues of the matrix using the formula
$$
det(A - \lambda I) = 0
$$
  , where A is the matrix and I is the identity matrix.
- Substitute the eigenvalue(s) into the equation
$$
(A - \lambda I)v = 0
$$
   to find the corresponding eigenvector(s).
An example of the same is,
**Example:** Find the eigenvalues and the eigenvector for the matrix A =
$$
\begin{bmatrix} 1 & 2\\ 5& 4 \end{bmatrix}
$$
**Solution:**
If eigenvalues are represented using  λ and the eigenvector is represented as v =
$$
\begin{bmatrix} a\\b \end{bmatrix}
$$
Then the eigenvector is calculated by using the equation,
$$
|A- λI| = 0
$$
>
$$
\begin{bmatrix}1 & 2\\ 5& 4\end{bmatrix} -λ\begin{bmatrix}1 & 0\\ 0 & 1\end{bmatrix} = \begin{bmatrix}0 & 0\\ 0& 0\end{bmatrix}
$$
>
>
$$
\begin{bmatrix} 1 - λ& 2\\ 5& 4 - λ \end{bmatrix}
$$
>
>  = 0
>
> (1-λ) ⨉ (4-λ) - (2 ⨉ 5) = 0
> ⇒ 4 - λ - 4λ + λ2 - 10 = 0
> ⇒ λ2 - 5λ - 6 = 0
> ⇒ λ2 - (6λ - λ) - 6 = 0
> ⇒ λ2 - 6λ + λ - 6 = 0
> ⇒ (λ-6)(λ+1) = 0
> λ = 6 and λ = -1
Thus, the eigenvalues are 6 and -1.
- **For λ = 6**
> (A-λI)v = 0
>
> ⇒
>
>
$$
\begin{bmatrix}1 - 6& 2\\ 5& 4 - 6\end{bmatrix}.\begin{bmatrix}a\\ b\end{bmatrix}
$$
>
>  = 0
>
> ⇒
>
>
$$
\begin{bmatrix}-5& 2\\ 5& -2\end{bmatrix}.\begin{bmatrix}a\\ b\end{bmatrix}
$$
>
>  = 0
> ⇒ 5a - 2b = 0
>
> Simplifying the above equation we get, 5a=2b
>
> The required eigenvector is,
>
>
$$
\begin{bmatrix}a\\b\end{bmatrix} = \begin{bmatrix}2\\5\end{bmatrix}
$$
- **For λ = -1**
> ⇒
>
>
$$
\begin{bmatrix}1 - (-1)& 2\\ 5& 4 - (-1)\end{bmatrix}.\begin{bmatrix}a\\ b\end{bmatrix}
$$
>
>  = 0
>
> ⇒
>
>
$$
\begin{bmatrix}2& 2\\ 5& 5\end{bmatrix}.\begin{bmatrix}a\\ b\end{bmatrix}
$$
>
>  = 0
> ⇒ 2a + 2b = 0, ⇒ 5a + 5b = 0
>
> simplifying the above equation we get,  a = -b
>
> The required eigenvector is,
>
>
$$
\begin{bmatrix}a\\b\end{bmatrix} = \begin{bmatrix} 1\\-1\end{bmatrix}
$$
Then the eigenvectors of the given 2 × 2 matrix are
$$
\begin{bmatrix}a\\b\end{bmatrix} = \begin{bmatrix}2\\5\end{bmatrix}, \begin{bmatrix}a\\b\end{bmatrix} = \begin{bmatrix}1\\-1\end{bmatrix}
$$
These are two possible eigen vectors but many of the corresponding multiples of these eigen vectors can also be considered as other possible eigen vectors.
### Eigenvector of a 3 × 3 Matrix
An example of eigenvector of 3x3 matrix is,
**Example:** Find the eigenvalues and the eigenvector for the matrix A =
$$
\begin{bmatrix} 2 & 2 & 2 \\ 2 & 2 & 2\\2 & 2 & 2 \end{bmatrix}
$$
**Solution:**
If eigenvalues are represented using  λ and the eigenvector is represented as v =
$$
\begin{bmatrix} a\\b\\c \end{bmatrix}
$$
Then the eigenvector is calculated by using the equation,
> |A- λI| = 0
>
>
$$
\begin{bmatrix}2 & 2 & 2\\ 2 & 2 & 2\\ 2 & 2 & 2\end{bmatrix} -λ\begin{bmatrix}1 & 0 & 0\\ 0 & 1 & 0\\0 & 0 & 1\end{bmatrix} = \begin{bmatrix}0 & 0 & 0\\ 0 & 0 & 0\\ 0 & 0 & 0\end{bmatrix}
$$
>
>
$$
\begin{bmatrix} 2 - λ & 2 & 2 \\ 2 & 2 - λ & 2 \\ 2 & 2 & 2- λ\end{bmatrix}
$$
>
>  = 0
>
> Simplifying the above determinant we get
> ⇒ (2-λ)(λ2) + 2λ2 + 2λ2 = 0 ⇒ (-λ3) + 6λ2 = 0
> ⇒ λ2(6 - λ) = 0
> ⇒ λ = 0, λ = 6, λ = 0
**For λ = 0**
> (A - λI) v = 0
> ⇒
>
>
$$
\begin{bmatrix}2 - 0& 2& 2\\ 2& 2 - 0&2\\2 & 2 & 2-0\end{bmatrix}.\begin{bmatrix}a\\ b\\c\end{bmatrix}
$$
>
>  = 0
>
> ⇒
>
>
$$
\begin{bmatrix}2& 2& 2\\ 2& 2 &2\\2 & 2 & 2\end{bmatrix}.\begin{bmatrix}a\\ b\\c\end{bmatrix}
$$
>
>  = 0
>
> Simplifying the above equation we get
> 2a + 2b + 2c = 0
> ⇒ a + b + c = 0
>
> Let b = k1 and c = k2
> ⇒ a + k1 + k2 = 0
> ⇒ a = -(k1 + k2)
>
> Thus, the eigenvector is,
>
>
$$
\begin{bmatrix}a\\ b\\c\end{bmatrix} = \begin{bmatrix}-(k_{1}+k_{2})\\ k_{1}\\k_{2}\end{bmatrix}
$$
>
> taking k1 = 1 and k2 = 0, the eigenvector is,
>
>
$$
\begin{bmatrix}a\\ b\\c\end{bmatrix} = \begin{bmatrix}-1\\ 1\\0\end{bmatrix}
$$
>
> taking k1 = 0 and k2= 1, the eigenvector is,
>
>
$$
\begin{bmatrix}a\\ b\\c\end{bmatrix} = \begin{bmatrix}-1\\ 0\\1\end{bmatrix}
$$
**For λ = 6**
> (A - λI) v = 0
> ⇒
>
>
$$
\begin{bmatrix}2 - 6& 2& 2\\ 2& 2 -6&2\\2 & 2 & 2-6\end{bmatrix}.\begin{bmatrix}a\\ b\\c\end{bmatrix}
$$
>
>  = 0
>
> ⇒
>
>
$$
\begin{bmatrix}-4& 2& 2\\ 2& -4 &2\\2 & 2 & -4\end{bmatrix}.\begin{bmatrix}a\\ b\\c\end{bmatrix}
$$
>
>  = 0
>
> Simplifying the above equation we get,
> -4a +2b +2c = 0 ⇒ 2 (-2a + b + c) = 0
> ⇒ 2a = b + c
>
> Let b = k1  and c = k2  and taking k1 = k2 = 1 we get,
>
>
$$
\begin{bmatrix}a\\ b\\c\end{bmatrix} = \begin{bmatrix}1\\ 1\\1\end{bmatrix}
$$
>
> Thus, the eigenvector is,
>
>
$$
\begin{bmatrix}a\\ b\\c\end{bmatrix} = \begin{bmatrix}1\\ 1\\1\end{bmatrix}
$$
## Eigenspace
The eigenspace of a matrix A corresponding to an eigenvalue λ is the set of all vectors v that satisfy the equation: (A − λI)v = 0.
This means the eigenspace is the null space of (A − λI). It contains all eigenvectors associated with the eigenvalue λ, along with the zero vector. The basis vectors of the eigenspace are always linearly independent.
### Steps to Find the Eigenspace of a Matrix
> **Step 1:** Find the eigenvalues of the square matrix A by solving: det(A − λI) = 0
>
> **Step 2:** For each eigenvalue λ, substitute it into: (A − λI)v = 0 and solve the system to find the corresponding eigenvectors.
>
> **Step 3:** The complete set of solutions obtained for that eigenvalue, together with the zero vector, forms the eigenspace corresponding to that eigenvalue.
>
> **Step 4:** Repeat the same process for all remaining eigenvalues to determine their respective eigenspaces.
From the above example of given 3 × 3 matrix A, the eigenspace so formed is 
$$
\begin{bmatrix}-1\\ 1\\0\end{bmatrix},\begin{bmatrix}-1\\ 0\\1\end{bmatrix},\begin{bmatrix}1\\ 1\\1\end{bmatrix}
$$
## Diagonalize Matrix Using Eigenvalues and Eigenvectors
Eigenvalues and Eigenvectors are used to find diagonal matrices. A [diagonal matrix](https://www.geeksforgeeks.org/maths/diagonal-matrix/) is a matrix which can be written as,
> A = XDX-1 
Where,
- A is the original matrix.
- X is the matrix formed by eigenvectors.
- D is a diagonal matrix where the diagonal elements are the eigenvalues of A.
- X-1 is the inverse of the matrix X.
**Example:** Diagonalize the matrix A =
$$
\begin{bmatrix} 2 & 2 & 2 \\ 2 & 2 & 2\\2 & 2 & 2 \end{bmatrix}
$$
**Solution:**
> We have already solved for the eigenvalues and the eigenvectors of the A  **=**
>
>
$$
\begin{bmatrix} 2 & 2 & 2 \\ 2 & 2 & 2\\2 & 2 & 2 \end{bmatrix}
$$
>
> The eigenvalues of the A are λ = 6, λ = 0 and λ = 0
> The eigenvectors of A are
>
>
$$
\begin{bmatrix}1\\ 1\\1\end{bmatrix},\begin{bmatrix}-1\\ 1\\0\end{bmatrix},\begin{bmatrix}-1\\ 0\\1\end{bmatrix}
$$
>
>
> Thus,
>  D =
>
>
$$
\begin{bmatrix}6 & 0 & 0\\0 & 0 & 0\\0 & 0 & 0\end{bmatrix}
$$
>
> X =
>
>
$$
\begin{bmatrix} 1 & 1 & 1\\1 & -1 & 0\\1 & 0 & -1\end{bmatrix}
$$
## Applications
**Google PageRank Algorithm**
- Web pages form a graph; eigenvector corresponding to eigenvalue 1 of the link matrix gives each page’s importance score.
**Markov Processes & Steady-State Analysis**
- Used in simulations, natural language processing, recommendation systems, and stochastic modeling.
- The eigenvector for eigenvalue 1 gives long-term stable probabilities.
**Principal Component Analysis (PCA)**
- Reduces dimensionality of data, removes noise, and extracts key patterns.
- Common in image recognition, machine learning, and data compression.
**Latent Semantic Analysis (LSA) in NLP**
- Eigen-decomposition (via SVD) finds semantic relationships between words and documents.
- Improves search, document clustering, and recommendation engines.
**Spectral Graph Theory in Network Analysis**
- Eigenvalues of the graph Laplacian help detect communities, find graph partitions, and measure connectivity in social networks or computer networks.
**Computer Vision (Eigenfaces)**
- Eigenvectors from face image datasets form a “basis” for recognizing and comparing faces.
**Control System Stability in Robotics & AI**
- Eigenvalues of system matrices determine stability and convergence of autonomous systems and learning algorithms.
**Signal Processing & Data Transmission**
- Eigen-decomposition optimizes communication channels, feature extraction in audio/speech, and noise filtering.
**➢Practice:** [Solved Examples](https://www.geeksforgeeks.org/maths/practice-questions-on-eigenvalues-and-eigenvectors/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/eigen-values/)

## GATE CS

- Subject: Engineering Mathematics
- Topic: Linear Algebra

> [!note] Related notes
>
> - [[Cayley Hamilton Theorem]]
> - [[Determinants]]
> - [[Different Operations on matrices]]
> - [[Introduction to Matrix]]
> - [[LU Decomposition]]
> - [[Matrix Diagonalization]]
> - [[Null Space and Nullity of a Matrix]]
> - [[Properties of Determinants]]
> - [[Rank of a Matrix]]
> - [[Row Echelon Form]]
