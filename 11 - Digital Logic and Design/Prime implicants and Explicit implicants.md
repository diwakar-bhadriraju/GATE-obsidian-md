---
title: "Prime Implicant chart for minimizing Cyclic Boolean functions"
subject: "Digital Logic and Design"
topic: "Introduction of Boolean Algebra and Logic Gates"
source: "https://www.geeksforgeeks.org/digital-logic/prime-implicant-chart-for-minimizing-cyclic-boolean-functions/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Introduction of Boolean Algebra and Logic Gates"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/introduction-of-boolean-algebra-and-logic-gates
---


> [!abstract] Prime Implicant chart for minimizing Cyclic Boolean functions
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Introduction of Boolean Algebra and Logic Gates`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/prime-implicant-chart-for-minimizing-cyclic-boolean-functions/)

---

# Prime Implicant chart for minimizing Cyclic Boolean functions

Prerequisite - [K-Map (Karnaugh Map)](https://www.geeksforgeeks.org/digital-logic/introduction-of-k-map-karnaugh-map/), [Implicants in K-Map](https://www.geeksforgeeks.org/engineering-mathematics/various-implicants-in-k-map/) 
A functions is said to be a **Cyclic Boolean Function** if there is no *Essential* prime Implicant in its respective K-Map. 
**Properties of Cyclic functions:** 
- Every prime Implicant is of same size.
- Every minterm is covered by at least two prime Implicants (which means no essential prime Implicants).
- Having no essential prime Implicants means that there exist *more than one minimized Solution / Expression* for such functions, which will further be realized using digital circuits.
- For a cyclic function we can have two minimal forms with no overlapping of prime Implicants.
**Example:** 
Find the minimal expression for the following function. 
```
f(w, x, y, z) = \Sigma(0, 2, 4, 5, 10, 11, 13, 15)
```
![](assets/1111-3-35dd1522a7.jpg)
As we can see in the above K-Map that there exist no essential prime Implicants. Here we can use prime Implicant chart to solve it easily. 
**Steps to solve above function using prime Implicant chart:** 
- **Step-1:** 
  Draw prime Implicant chart as below.The horizontal entries denote the given minterms which are mapped against all prime Implicants (vertically).The square boxes are crossed ('x') whenever a prime Implicant covers a particular minterm in K-Map. 
  For example 'WXZ' prime Implicant is covering 13 and 15 therefore the corresponding squares are crossed(denoted by 'x'). 
  **Note** that, A, B, C, D .., are variables used to denote all the prime Implicants.
![](assets/img28-425fc898bc.png)
- **Step-2:** 
  Arbitrarily choose any prime Implicant; check (
$$
\checkmark
$$
  ) the prime Implicant and the corresponding covered minterms as well. Now delete the row of the prime Implicant and corresponding columns of its minterms. 
  In our example prime Implicant A is chosen which is covering minterms 2 and 10. Therefore. delete the row of A and the columns of 2 and 10. The arbitrarily chosen Prime Implicant (in our example A) must be present in the final minimal expression.
![](assets/img36-c51d021615.png)![](assets/img42-2f8d7f0872.png)
- **Step-3:** 
  Find all such prime Implicant which are being covered by other prime Implicant completely and remove their corresponding rows (since these are non essential prime Implicants.). 
  In our example H is covering {0, 4} and B is covering {0} it means H is covering all the minterms that are covered by B, so delete B. Similarly D is covering C completely, so delete C.
![](assets/img52-270369f839.png)![](assets/img62-b9703d8feb.png)
- **Step-4:** 
  Now follow the standard procedure of prime Implicant chart mentioned in the sub steps given below: 
  1. Find the minterm which is covered by only one prime Implicant.
  2. Check (
$$
\checkmark
$$
     ) that minterm, its corresponding prime Implicant and all other minterms which are covered by that corresponding prime Implicant.
  3. If all the minterms are checked (
$$
\checkmark
$$
     ) stop the procedure, otherwise goto sub-step-1.
**Example-2**: find the minimal expression for the following cyclic function. 
```
f(x, y, z) = \Sigma(0, 1, 2, 5, 6, 7)
```
![](assets/img111-4a916e19c6.png)
**Step-1:** 
Draw prime Implicant chart. 
![](assets/img121-c546b99367.png)
**Step-2:** 
A is chosen arbitrarily.Now the row of A and the columns of the corresponding minterms (0 and 2) are deleted. 
![](assets/img131-daf272474e.png)![](assets/img141-4dde14d327.png)
**Step-3:** 
Since B and F are completely covered by C and E respectively hence deleting prime Implicants B and F . 
![](assets/img151-c291dad8aa.png)
**Step-4:** 
Now follow the standard procedure of prime Implicant chart mentioned in Example-1. 
Minterm 1 is covered by prime Implicant C only therefore check (
$$
\checkmark
$$
) C along with all the minterms which are covered by it (1 and 5). 
Minterm 6 is covered by prime Implicant E only therefore check (
$$
\checkmark
$$
) E along with all the minterms which are covered by it (6 and 7). 
![](assets/img161-b141df1bab.png)
Now since all the min terms (1, 5, 6, 7) are checked(
$$
\checkmark
$$
) therefore stop the procedure. 
```
Final Minimal Expression: A + C + E
```
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/prime-implicant-chart-for-minimizing-cyclic-boolean-functions/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Introduction of Boolean Algebra and Logic Gates

> [!note] Related notes
>
> - [[Boolean functions]]
> - [[Canonical and Standard Form]]
> - [[Consensus Theorem]]
> - [[Functional Completeness]]
> - [[Implicants in K-Map]]
> - [[K-Map]]
> - [[Logic Gates]]
> - [[Logical gates in logic design]]
> - [[Minimization of Boolean Functions]]
> - [[PDNF and PCNF]]
