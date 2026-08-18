---
title: "Recurrence Relations Notes for GATE Exam [2024]"
subject: "Algorithms"
topic: "Recurrence Relations"
source: "https://www.geeksforgeeks.org/dsa/recurrence-relations-notes-for-gate-exam/#what-is-recurrence-relations"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Algorithms/Recurrence Relations"
tags:
  - gate/cs
  - subject/algorithms
  - topic/recurrence-relations
---


> [!abstract] Recurrence Relations Notes for GATE Exam [2024]
> 
> **Subject:** `Algorithms` &nbsp;|&nbsp; **Topic:** `Recurrence Relations`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/recurrence-relations-notes-for-gate-exam/#what-is-recurrence-relations)

---

# Recurrence Relations Notes for GATE Exam [2024]

Recurrence relations are the mathematical backbone of algorithmic analysis, providing a systematic way to express the time complexity of recursive algorithms. As GATE Exam 2024 approaches, a profound understanding of recurrence relations becomes imperative for tackling questions that demand a deep comprehension of algorithmic efficiency. These notes aim to present a concise and illuminating guide to recurrence relations, covering key concepts and techniques that are likely to be assessed in the GATE examination.
Table of Content
- [What is Recurrence Relations?](#what-is-recurrence-relations)
- [What is Linear Recurrence Relation?](#what-is-linear-recurrence-relation)
- [How to Solve Recurrence Relations?](#how-to-solve-recurrence-relations)
- [1. Substitution Method:](#1-substitution-method)
- [2. Recurrence Tree Method:](#2-recurrence-tree-method)
- [3. Master Method:](#3-master-method)
- [Different types of recurrence relations and their solutions:](#different-types-of-recurrence-relations-and-their-solutions)
- [Previously Asked GATE Questions on Recurrence Relations:](#previously-asked-gate-questions-on-recurrence-relations)
## **What is Recurrence Relations?**
A **recurrence relation** is a mathematical expression that defines a sequence in terms of its previous terms. In the context of algorithmic analysis, it is often used to model the time complexity of recursive algorithms.
## **What is Linear Recurrence Relation?**
In a **linear recurrence relation**, each term in the sequence is a linear combination of previous terms.
General form:
>
$$
a_n = c_1 a_{n-1} +  c_2 a_{n-2} + ... + c_k a_{n-k} + F(n)
$$
where, c1, c2, ..., ck are constants and F(n) is a function.
## [How to Solve Recurrence Relations?](https://www.geeksforgeeks.org/dsa/how-to-analyse-complexity-of-recurrence-relation/)
The analysis of the complexity of a recurrence relation involves finding the asymptotic upper bound on the running time of a recursive algorithm. This is usually done by finding a closed-form expression for the number of operations performed by the algorithm as a function of the input size, and then determining the order of growth of the expression as the input size becomes large.
Various methods to analyze the complexity of a recurrence relation are:
## 1. Substitution Method:
We make a guess for the solution and then we use mathematical induction to prove the guess is correct or incorrect. 
> For example consider the recurrence T(n) = 2T(n/2) + n
>
> We guess the solution as T(n) = O(nLogn). Now we use induction to prove our guess.
>
> We need to prove that T(n) <= cnLogn. We can assume that it is true for values smaller than n.
>
> T(n) = 2T(n/2) + n
>      <= 2cn/2Log(n/2) + n
>        =  cnLogn – cnLog2 + n
>        =  cnLogn – cn + n
>     <= cnLogn
## **2. Recurrence Tree Method:**
In this method, we draw a recurrence tree and calculate the time taken by every level of the tree. Finally, we sum the work done at all levels. To draw the recurrence tree, we start from the given recurrence and keep drawing till we find a pattern among levels. The pattern is typically arithmetic or geometric series. 
> For example, consider the recurrence relation 
>
> T(n) = T(n/4) + T(n/2) + cn2
>
>             cn2
> /      \
>   T(n/4)     T(n/2)
>
> If we further break down the expression T(n/4) and T(n/2), 
> we get the following recursion tree.
>
>                     cn2
>               /             \      
>     c(n2)/16          c(n2)/4
>    /         \            /         \
> T(n/16)  T(n/8)  T(n/8)    T(n/4) 
>
> Breaking down further gives us following
>
>                        cn2 
>                 /                \     
>        c(n2)/16              c(n2)/4
>     /          \                 /          \
> c(n2)/256  c(n2)/64  c(n2)/64   c(n2)/16
>  /    \            /    \      /    \        /    \  
>
> To know the value of T(n), we need to calculate the sum of tree 
> nodes level by level. If we sum the above tree level by level, 
>
> we get the following series T(n)  = c(n^2 + 5(n^2)/16 + 25(n^2)/256) + ….
> The above series is a geometrical progression with a ratio of 5/16.
>
> To get an upper bound, we can sum the infinite series. We get the sum as (n2)/(1 – 5/16) which is O(n2)
## **3. Master Method:**
Master Method is a direct way to get the solution. The master method works only for the following type of recurrences or for recurrences that can be transformed into the following type. 
> T(n) = aT(n/b) + f(n) where a >= 1 and b > 1
There are the following three cases: 
- If f(n) = O(nc) where c < Logba then T(n) = Θ(nLogba)
- If f(n) = Θ(nc) where c = Logba then T(n) = Θ(ncLog n)
- If f(n) = Ω(nc) where c > Logba then T(n) = Θ(f(n))
### **How does this work?**
The master method is mainly derived from the recurrence tree method. If we draw the recurrence tree of T(n) = aT(n/b) + f(n), we can see that the work done at the root is f(n), and work done at all leaves is Θ(nc) where c is Logba. And the height of the recurrence tree is Logbn 
![Master Theorem](assets/AlgoAnalysis-8f0986a7bb.png)
In the recurrence tree method, we calculate the total work done. If the work done at leaves is polynomially more, then leaves are the dominant part, and our result becomes the work done at leaves (Case 1). If work done at leaves and root is asymptotically the same, then our result becomes height multiplied by work done at any level (Case 2). If work done at the root is asymptotically more, then our result becomes work done at the root (Case 3). 
**Examples of some standard algorithms whose time complexity can be evaluated using the Master Method**
- [Merge Sort](https://www.geeksforgeeks.org/dsa/merge-sort/): T(n) = 2T(n/2) + Θ(n). It falls in case 2 as c is 1 and Logba] is also 1. So the solution is Θ(n Logn)
- [Binary Search](https://www.geeksforgeeks.org/dsa/binary-search/): T(n) = T(n/2) + Θ(1). It also falls in case 2 as c is 0 and Logba is also 0. So the solution is Θ(Logn)
**Notes:**
- It is not necessary that a recurrence of the form T(n) = aT(n/b) + f(n) can be solved using Master Theorem. The given three cases have some gaps between them. For example, the recurrence T(n) = 2T(n/2) + n/Logn cannot be solved using master method.
- Case 2 can be extended for f(n) = Θ(ncLogkn) 
  If f(n) = Θ(ncLogkn) for some constant k >= 0 and c = Logba, then T(n) = Θ(ncLogk+1n)
# [Advanced master theorem for divide and conquer recurrences](https://www.geeksforgeeks.org/dsa/advanced-master-theorem-for-divide-and-conquer-recurrences/):
The Master Theorem is a tool used to solve recurrence relations that arise in the analysis of divide-and-conquer algorithms. The Master Theorem provides a systematic way of solving recurrence relations of the form:
T(n) = aT(n/b) + f(n)
1. where a, b, and f(n) are positive functions and n is the size of the problem. The Master Theorem provides conditions for the solution of the recurrence to be in the form of O(n^k) for some constant k, and it gives a formula for determining the value of k.
2. The advanced version of the Master Theorem provides a more general form of the theorem that can handle recurrence relations that are more complex than the basic form. The advanced version of the Master Theorem can handle recurrences with multiple terms and more complex functions.
3. It is important to note that the Master Theorem is not applicable to all recurrence relations, and it may not always provide an exact solution to a given recurrence. However, it is a useful tool for analyzing the time complexity of divide-and-conquer algorithms and provides a good starting point for solving more complex recurrences.
[Master Theorem](https://www.geeksforgeeks.org/dsa/how-to-analyse-complexity-of-recurrence-relation/) is used to determine running time of algorithms (divide and conquer algorithms) in terms of asymptotic notations. 
Consider a problem that is solved using recursion. 
>  **function f**(input x size n)
> **if**(n < k)
> solve x directly and return
> **else**
> divide x into **a** subproblems of size n/b
> call f recursively to solve each subproblem
> Combine the results of all sub-problems
The above algorithm divides the problem into **a** subproblems, each of size n/b and solve them recursively to compute the problem and the extra work done for problem is given by f(n), i.e., the time to create the subproblems and combine their results in the above procedure. 
> So, according to master theorem the runtime of the above algorithm can be expressed as: 
>  **T(n) = aT(n/b) + f(n)**
>
> where n = size of the problem 
> a = number of subproblems in the recursion and a >= 1 
> n/b = size of each subproblem 
> f(n) = cost of work done outside the recursive calls like dividing into subproblems and cost of combining them to get the solution. 
Not all recurrence relations can be solved with the use of the master theorem i.e. if 
- T(n) is not monotone, ex: T(n) = sin n
- f(n) is not a polynomial, ex: T(n) = 2T(n/2) + 2n
This theorem is an advance version of master theorem that can be used to determine running time of divide and conquer algorithms if the recurrence is of the following form :- 
![Formula to calculate runtime of divide and conquer algorithms](assets/ma-1-c26528c464.png)
where n = size of the problem 
a = number of subproblems in the recursion and a >= 1 
n/b = size of each subproblem 
b > 1, k >= 0 and p is a real number. 
Then, 
1. if a > bk, then T(n) = θ(nlogba)
2. if a = bk, then 
   (a) if p > -1, then T(n) = θ(nlogba logp+1n) 
   (b) if p = -1, then T(n) = θ(nlogba loglogn) 
   (c) if p < -1, then T(n) = θ(nlogba)
3. if a < bk, then 
   (a) if p >= 0, then T(n) = θ(nk logpn) 
   (b) if p < 0, then T(n) = θ(nk)
**Time Complexity Analysis –** 
- **Example-1: Binary Search –** T(n) = T(n/2) + O(1) 
  a = 1, b = 2, k = 0 and p = 0 
  bk = 1. So, a = bk and p > -1 [Case 2.(a)] 
  T(n) = θ(nlogba logp+1n) 
  T(n) = θ(logn)
- **Example-2: Merge Sort –** T(n) = 2T(n/2) + O(n) 
  a = 2, b = 2, k = 1, p = 0 
  bk = 2. So, a = bk and p > -1 [Case 2.(a)] 
  T(n) = θ(nlogba logp+1n) 
  T(n) = θ(nlogn)
- **Example-3:** T(n) = 3T(n/2) + n2 
  a = 3, b = 2, k = 2, p = 0 
  bk = 4. So, a < bk and p = 0 [Case 3.(a)] 
  T(n) = θ(nk logpn) 
  T(n) = θ(n2)
- **Example-4:** T(n) = 3T(n/2) + log2n 
  a = 3, b = 2, k = 0, p = 2 
  bk = 1. So, a > bk [Case 1] 
  T(n) = θ(nlogba ) 
  T(n) = θ(nlog23)
- **Example-5:** T(n) = 2T(n/2) + nlog2n 
  a = 2, b = 2, k = 1, p = 2 
  bk = 2. So, a = bk [Case 2.(a)] 
  T(n) = θ(nlogbalogp+1n ) 
  T(n) = θ(nlog22log3n) 
  T(n) = θ(nlog3n)
- **Example-6:** T(n) = 2nT(n/2) + nn 
  This recurrence can’t be solved using above method since function is not of form T(n) = aT(n/b) + θ(nk logpn)
## [Different types of recurrence relations and their solutions](https://www.geeksforgeeks.org/dsa/different-types-recurrence-relations-solutions/):
### **Type 1: Divide and conquer recurrence relations**
Following are some of the examples of recurrence relations based on divide and conquer.
> T(n) = 2T(n/2) + cn
> T(n) = 2T(n/2) + √n
These types of recurrence relations can be easily solved using [**Master Method**](https://www.geeksforgeeks.org/dsa/how-to-analyse-complexity-of-recurrence-relation/).
For recurrence relation T(n) = 2T(n/2) + cn, the values of a = 2, b = 2 and k =1. Here logb(a) = log2(2) = 1 = k. Therefore, the complexity will be Θ(nlog2(n)).
Similarly for recurrence relation T(n) = 2T(n/2) + √n, the values of a = 2, b = 2 and k =1/2. Here logb(a) = log2(2) = 1 > k. Therefore, the complexity will be Θ(n).
### **Type 2: Linear recurrence relations**
Following are some of the examples of recurrence relations based on linear recurrence relation.
> T(n) = T(n-1) + n for n>0 and T(0) = 1
These types of recurrence relations can be easily solved using [substitution method](https://www.geeksforgeeks.org/dsa/how-to-analyse-complexity-of-recurrence-relation/).
For example,
> T(n) = T(n-1) + n
>  = T(n-2) + (n-1) + n
>  = T(n-k) + (n-(k-1))….. (n-1) + n
Substituting k = n, we get
> T(n) = T(0) + 1 + 2+….. +n = n(n+1)/2 = O(n^2)
**Type 3: Value substitution before solving –**
Sometimes, recurrence relations can’t be directly solved using techniques like substitution, recurrence tree or master method. Therefore, we need to convert the recurrence relation into appropriate form before solving. For example,
> T(n) = T(√n) + 1
To solve this type of recurrence, substitute n = 2^m as:
> T(2^m) = T(2^m /2) + 1
> Let T(2^m) = S(m),
> S(m) = S(m/2) + 1
Solving by master method, we get
> S(m) = Θ(logm)
> As n = 2^m or m = log2(n),
> T(n) = T(2^m) = S(m) = Θ(logm) = Θ(loglogn)
## Previously Asked GATE Questions on Recurrence Relations:
**Que – 1. What is the time complexity of Tower of Hanoi problem?**
(A) T(n) = O(sqrt(n))
(D) T(n) = O(n^2)
(C) T(n) = O(2^n)
(D) None
> **Solution:** For Tower of Hanoi, T(n) = 2T(n-1) + c for n>1 and T(1) = 1. Solving this,
>
> T(n) = 2T(n-1) + c
>  = 2(2T(n-2)+ c) + c = 2^2\*T(n-2) + (c + 2c)
>  = 2^k\*T(n-k) + (c + 2c + .. kc)
> Substituting k = (n-1), we get
> T(n) = 2^(n-1)\*T(1) + (c + 2c + (n-1)c) = O(2^n)
**Que – 2. Consider the following recurrence:**
**T(n) = 2 \* T(ceil (sqrt(n) ) ) + 1, T(1) = 1**
Which one of the following is true?
(A) T(n) = (loglogn)
(B) T(n) = (logn)
(C) T(n) = (sqrt(n))
(D) T(n) = (n)
> **Solution:** To solve this type of recurrence, substitute n = 2^m as:
>
> T(2^m) = 2T(2^m /2) + 1
> Let T(2^m) = S(m),
> S(m) = 2S(m/2) + 1
> Solving by master method, we get
> S(m) = Θ(m)
> As n = 2^m or m = log2n,
> T(n) = T(2^m) = S(m) = Θ(m) = Θ(logn)
**Que – 3. What is the value of following recurrence.**
T(n) = T(n/4) + T(n/2) + cn2
T(1) = c
T(0) = 0
Where c is a positive constant
**(A)** O(n3)
**(B)** O(n2)
**(C)** O(n2 Logn)
**(D)** O(nLogn)
> **Answer:** **(B)**
**Que – 4. What is the value of following recurrence.**
T(n) = 5T(n/5) + 
$$
\sqrt{n}
$$
,
T(1) = 1,
T(0) = 0
**(A)** Theta (n)
**(B)** Theta (n^2)
**(C)** Theta (sqrt(n))
**(D)** Theta (nLogn)
> **Answer:** **(A)**
**Que – 5. Suppose T(n) = 2T(n/2) + n, T(0) = T(1) = 1**
Which one of the following is false. ( GATE CS 2005)
a) T(n) = O(n^2)
b) T(n) = θ(nLogn)
c) T(n) = **Ω**(n^2)
d) T(n) = O(nLogn)
**(A)** A
**(B)** B
**(C)** C
**(D)** D
> **Answer:** **(C)**
**Que – 6. The running time of an algorithm is represented by the following recurrence relation:**
**if n <= 3 then T(n) = n**
 **else T(n) = T(n/3) + cn**
Which one of the following represents the time complexity of the algorithm?
(A) θ(n)
(B) θ(n log n)
(C) θ(n^2)
(D) θ(n^2log n)
> **Answer:** **(A)**
**Que – 7. The running time of the following algorithm**
Procedure A(n)
 If n <= 2 return(1) else return A(
$$
\sqrt{n}
$$
);
is best described by
**(A)** O(n)
**(B)** O(log n)
**(C)** O(1og log n)
**(D)** O(1)
> **Answer:** **(C)**
**Que – 8. The time complexity of the following C function is (assume n > 0 (GATE CS 2004)**
int recursive (mt n)
{
if (n == 1)
 return (1);
else
 return (recursive (n-1) + recursive (n-1));
}
**(A)** 0(n)
**(B)** 0(nlogn)
**(C)** 0(n^2)
**(D)** 0(2^n)
> **Answer:** **(D)**
**Que – 9. Which one of the following correctly determines the solution of the recurrence relation with T(1) = 1? (GATE-CS-2014-(Set-2))**
T(n) = 2T(n/2) + Logn
**(A)** Θ(n)
**(B)** Θ(nLogn)
**(C)** Θ(n\*n)
**(D)** Θ(log n)
> **Answer:** **(A)**
**Que – 10.** **Consider the recurrence relation a**1**= 8, a**n**= 6n**2**+ 2n + a**n-1**. Let a**99**= k x 10**4**. The value of K is \_\_\_\_\_. (**GATE-CS-2016 (Set 1)**)**
Note : This question was asked as Numerical Answer Type.
**(A)** 190
**(B)** 296
**(C)** 198
**(D)** 200
> **Answer:** **(C)**
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/recurrence-relations-notes-for-gate-exam/#what-is-recurrence-relations)

## GATE CS

- Subject: Algorithms
- Topic: Recurrence Relations

> [!note] Related notes
>
> - [[Applications of Depth First Search]]
> - [[Asymptotic Notations]]
> - [[Binary Search]]
> - [[Breadth First Traversal or BFS for a Graph]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
> - [[Dijkstra’s Algorithm for Adjacency List Representation]]
> - [[Efficient Huffman Coding for Sorted Input]]
> - [[Fractional Knapsack Problem]]
> - [[Introduction of Algorithms]]
> - [[Introduction to Divide and Conquer]]
