---
title: "PDNF and PCNF in Discrete Mathematics"
subject: "Digital Logic and Design"
topic: "Introduction of Boolean Algebra and Logic Gates"
source: "https://www.geeksforgeeks.org/engineering-mathematics/pdnf-and-pcnf-in-discrete-mathematics/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Introduction of Boolean Algebra and Logic Gates"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/introduction-of-boolean-algebra-and-logic-gates
---


> [!abstract] PDNF and PCNF in Discrete Mathematics
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Introduction of Boolean Algebra and Logic Gates`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/pdnf-and-pcnf-in-discrete-mathematics/)

---

# PDNF and PCNF in Discrete Mathematics

In Discrete Mathematics, PDNF and PCNF are standard ways of expressing a Boolean function. In these forms, each term contains all variables exactly once. PDNF represents the function using minterms corresponding to output 1, whereas PCNF uses maxterms corresponding to output 0.
## **PDNF (Principal Disjunctive Normal Form)**
PDNF is a logical expression written in the [Sum of Products](https://www.geeksforgeeks.org/digital-logic/what-is-sum-of-product-sop-form/) (SOP) form where every product term contains all variables exactly once, either in [normal form or complemented form](https://www.geeksforgeeks.org/engineering-mathematics/normal-and-principal-forms/). The terms are joined using the OR (+) operator.
> **Example:** (P . Q' . R) + (P' . Q . R) + (P . Q . R')
>
> Here, the ‘+’ sign represents the OR operation, and each term contains all variables P, Q, and R.
## **PCNF (Principal Conjunctive Normal Form)**
PCNF is a logical expression written in the [Product of Sums](https://www.geeksforgeeks.org/digital-logic/what-is-product-of-sum-pos-form/) (POS) form where every sum term contains all variables exactly once, either in normal form or complemented form. The terms are joined using the AND (.) operator.
> **Example:** (P + Q' + R) . (P' + Q + R) . (P + Q + R')
>
> Here, the ‘.’ sign represents the AND operation, and each term contains all variables P, Q, and R.
### **Properties**
1. Every PDNF or PCNF corresponds to a unique [Boolean Expression](https://www.geeksforgeeks.org/dsa/boolean-search/) and vice versa.
2. If X and Y are two Boolean expressions, then X is equivalent to Y if and only if PDNF(X) = PDNF(Y) or PCNF(X) = PCNF(Y).
3. For a Boolean Expression, if PCNF has m terms and PDNF has n terms, then the number of variables in such a Boolean expression =
$$
\log_{2} (m + n)
$$
    .
### Solved Examples
**Example 1:** Convert the following Boolean expression to PDNF: A . (B + C')
**Solution:**
> 1. Distribute A
>
> A . B + A . C'
>
> 2.Ensure each product term contains all variables
>
> (A . B . C') + (A . B . C) + (A . B' . C')
**Example 2:** Convert the following Boolean expression to PCNF: (A + B') . (B + C)
**Solution:**
> 1.Ensure each sum term contains all variables using Boolean identity
>
> (A+B′) = (A+B′+C) . (A+B′+C′)
>
> (B+C) = (A+B+C) . (A′+B+C)
>
> 2.Write the expression in PCNF
>
> (A+B′+C) . (A+B′+C′) . (A+B+C) . (A′+B+C)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/pdnf-and-pcnf-in-discrete-mathematics/)

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
> - [[Prime implicants and Explicit implicants]]
