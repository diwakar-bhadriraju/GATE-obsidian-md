---
title: "Introduction of K-Map (Karnaugh Map)"
subject: "Digital Logic and Design"
topic: "Introduction of Boolean Algebra and Logic Gates"
source: "https://www.geeksforgeeks.org/digital-logic/introduction-of-k-map-karnaugh-map/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Introduction of Boolean Algebra and Logic Gates"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/introduction-of-boolean-algebra-and-logic-gates
---


> [!abstract] Introduction of K-Map (Karnaugh Map)
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Introduction of Boolean Algebra and Logic Gates`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/introduction-of-k-map-karnaugh-map/)

---

# Introduction of K-Map (Karnaugh Map)

Karnaugh Map (K-Map) is a graphical method used to simplify Boolean expressions without using lengthy Boolean algebra. It helps reduce the number of logic gates by grouping adjacent cells in a truth table, making digital circuits simpler and more efficient.
- K-map can be used for SOP and POS forms.
- It organizes truth table values into a grid for easy simplification.
Depending on the required representation, a K-Map is filled with 1s (for SOP) or 0s (for POS), and adjacent cells are grouped to obtain a simplified Boolean expression.
## **Steps to Solve Expression using K-map**
1. Select the K-map according to the number of variables.
2. Identify minterms or maxterms as given in the problem.
3. For SOP, place 1s in the cells corresponding to the minterms (0s elsewhere).
4. For POS, place 0s in the K-map cells corresponding to the maxterms (1s elsewhere).
5. Group adjacent cells in powers of two (1, 2, 4, 8, 16, ...) while covering the maximum possible cells.
6. From the groups made in step 5 find the product terms and sum them up for SOP form.
## **SOP FORM(Sum of Product Form)**
SOP (Sum of Products) is a method of representing Boolean expressions in which variables are combined using the AND operation to form product terms, and these product terms are combined using the OR operation.
### K-map for 2 variables
A 2-variable K-Map consists of four cells. Each cell represents one combination of the two input variables.
![K-map for 2 variables](assets/_variable-K-map-for-SOP-and-POS-ba721b2d82.webp)
K-Map for 2 variables
### **K-map of 3 variables**
A 3-variable K-Map consists of 8 cells, with each cell representing one minterm of the Boolean expression.
![llll](assets/llll-1f1af517f5.webp)
K-map SOP form for 3 variables
**Example:**
F(A, B, C) = Σ(1, 3, 6, 7)
![SOP](assets/K-Map-Karnaugh-Map-cd7a4bbd58.png)
- From the red group, we obtain the product term: A’C
- From the green group, we obtain the product term: AB
Combining the product terms, we get the simplified Boolean expression:
F = A'C + AB
### **K-map for 4 variables**
A 4-variable K-Map consists of 16 cells, with each cell representing one minterm of the Boolean expression.
![jij](assets/jij-568d4fd901.webp)
K-map 4 variable SOP form
**Example:**
F(A, B, C, D) = Σ(0, 1, 2, 3, 12, 13, 14, 15)
![k_map](assets/k_map-04933d681a.webp)
k map 4 variables
- From the red group, we obtain the product term: AB
- From the green group, we obtain the product term: A'B'
Combining the product terms, we get the simplified Boolean expression:
F = AB + A'B'
## **POS FORM (Product of Sum Form)**
POS (Product of Sums) is a method of simplifying and representing Boolean expressions. It uses the OR operation to form sum terms and the AND operation to combine them.
### K-map for 2 variables
A 2-variable K-Map consists of four cells. Each cell represents one maxterm of the Boolean expression.
![K-map of 2 variables](assets/_variable-K-map-for-SOP-and-POS-2-36cff19a6a.webp)
K-map of 2 variables
### **K-map of 3 variables**
A 3-variable K-Map consists of 8 cells, with each cell representing one maxterm of the Boolean expression.
![bjbj](assets/bjbj-0fe4533f56.webp)
K-map 3 variable POS form
**Example:**
F(A, B, C) = Π(0, 3, 6, 7)
![POS](assets/Screenshot281-bc097bf159.png)
- From the red group, we obtain the variables: AB
- Complementing these variables gives: A' B'
Form the sum term:
(A' + B') 
- From the brown group, we obtain the variables: BC
- Complementing these variables gives: B'C'
Form the sum term:
(B’+C’) 
- From the yellow group, we obtain the variables: A' B' C’
- Complementing these variables gives: A B C
Form the sum term: 
(A + B + C) 
Combining the sum terms, we obtain the simplified Boolean expression:
F = (A' + B')(B' + C')(A + B + C)
### **K-map of  4 variables**
A 4-variable K-map consists of 16 cells arranged in a 4 × 4 grid. Each cell represents one minterm or maxterm, making it easier to simplify Boolean expressions.
![sds](assets/sds-3ceeb94e04.webp)
K-map 4 variable POS form
**Example:**
F(A,B,C,D) = Π(3,5,7,8,10,11,12,13)
![](assets/KMapKarnaughMap3correct01-300x300-624c674477.png)
- From the green group, we obtain the variables: C’DB
- Complementing these variables gives: CD’B’
Form the sum term:
(C+D’+B’) 
- From the red group, we obtain the variables: C D A’
- Complementing these variables gives: C’D’A
Form the sum term:
(C’+D’+A) 
- From the blue group, we obtain the variables: A C’ D’
- Complementing these variables gives: A’CD
Form the sum term: 
(A’+C+D)
- From the brown group, we obtain the variables: A B’ C
- Complementing these variables gives: A’BC’
Form the sum term: 
(A’+B+C’) 
Combining all the sum terms, we obtain the simplified Boolean expression:
F = (C+D'+B')(C'+D'+A)(A'+C+D)(A'+B+C')
## Advantages
- **Makes Logic Simpler:** It makes complicated Boolean expressions simpler.
- **Minimizes Logic Gates:** Simplifying the logic helps us to use fewer logic gates, making circuits more efficient.
- **Reduce Errors:** The visual representation of k-map helps to avoid errors while simplifying.
- **Time-Saving:** It's quicker than traditional methods for simplifying logic.
## Disadvantages
- **Limited to Fewer Variables:** K-maps are best suited for 2 to 4 variables and above it, process becomes hard and complicated to manage.
- **Not suitable for all functions:** In some cases, its hard to group terms correctly, leading to errors and making simplification difficult.
- **Space Limitations:** As the number of variables increases, the K-map grid becomes too large to handle easily.
- **Requires Careful Grouping:** Sometimes incorrect grouping of terms can cause mistakes in logic simplification.
**Also attempt** [**Quiz on K-MAP**](https://www.geeksforgeeks.org/quizzes/digital-logic-number-representation-gq/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/introduction-of-k-map-karnaugh-map/)

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
> - [[Logic Gates]]
> - [[Logical gates in logic design]]
> - [[Minimization of Boolean Functions]]
> - [[PDNF and PCNF]]
> - [[Prime implicants and Explicit implicants]]
