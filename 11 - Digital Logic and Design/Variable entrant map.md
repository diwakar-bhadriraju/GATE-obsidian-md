---
title: "Variable Entrant Map (VEM) in Digital Logic"
subject: "Digital Logic and Design"
topic: "Introduction of Boolean Algebra and Logic Gates"
source: "https://www.geeksforgeeks.org/digital-logic/variable-entrant-map-vem-in-digital-logic/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Introduction of Boolean Algebra and Logic Gates"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/introduction-of-boolean-algebra-and-logic-gates
---


> [!abstract] Variable Entrant Map (VEM) in Digital Logic
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Introduction of Boolean Algebra and Logic Gates`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/variable-entrant-map-vem-in-digital-logic/)

---

# Variable Entrant Map (VEM) in Digital Logic

Variable Entrant Map (VEM) is an extension of the Karnaugh Map (K-Map) used to simplify boolean expressions with a large number of variables. Instead of increasing the size of the K-Map, one or more variables are represented inside the cells, allowing larger boolean functions to be minimized efficiently.
- Produces simpler and more efficient logic circuits.
- Useful for minimizing large combinational logic functions.
![c_ab](assets/c_ab-32955a9688.webp)
## **Minimization Procedure for VEM**
1. Replace all variable entries with 0, while treating the original and complemented forms as separate variables. Keep the minterms, 0's, and don't care conditions unchanged, then obtain the SOP expression.
2. Select one variable and replace all its occurrences with 1. Replace its complement with 0, treat all existing 1's as don't cares, and obtain the SOP expression.
3. Multiply the obtained SOP expression by the selected variable.
4. Repeat Step 2 and Step 3 for every remaining variable in the VEM.
5. Combine all the obtained product terms using the OR operation to get the final SOP expression.
Let's apply the above procedure on a sample VEM (X is used to represent don't care):
![](assets/VEM_kmap2_new-300x300-8425b8660a.jpg)
**Step 1:**
Replace all variable entries with 0, treating D and D′ as separate variables. Keep the minterms, 0's, and don't care conditions unchanged, then obtain the SOP expression.
![](assets/VEM_kmap3_new-300x300-4171b8e7c4.jpg)
> SOP obtained: A'C
**Step 2:**
(a) Replace all occurrences of D with 1 and D′ with 0. Convert all existing 1's to don't care (X), while keeping 0's and existing don't care conditions unchanged.
![](assets/VEM_kmap4_new-300x300-819c984ebe.jpg)
(b) Multiply the obtained SOP with the concerned variable.
> SOP obtained: AC'D
**Step 3:**
Repeat Step 2 for D′ (the complement of D).
(a) Replace all occurrences of D′ with 1 and D with 0. Convert all existing 1's to don't care (X), while leaving all 0's and existing don't care conditions unchanged.
![](assets/VEM_kmap5_new-300x300-c90dfaa462.jpg)
(b) Multiply the obtained SOP with the concerned variable.
> SOP obtained: CD'
**Step 4:**
Combine all the obtained SOP expressions using the logical OR operation. Therefore, the final SOP expression for the given VEM is:
> A'C + AC'D + CD'
## **Solved Example of Variable Entrant Map (VEM)**
Consider the following 3-variable Boolean function:
F(A, B, C) = (0, 1, 2, 5)
![VEM_example1-1-240x300](assets/VEM_example1-1-240x300-c66939e4d2.jpg)
Expressing F in terms of C, we obtain:
![VEM_example2-2-300x263](assets/VEM_example2-2-300x263-2e7511ffcb.jpg)
The corresponding Variable Entrant Map (VEM) is shown below:
![VEM_kmap1-1-300x300](assets/VEM_kmap1-1-300x300-8e982091c7.jpg)
## **Advantages**
- **Handles More Variables:** A VEM can represent more than n variables using an n-variable K-Map.
- **Simplifies Complex Functions:** It reduces the complexity of minimizing Boolean expressions with many variables.
- **Useful in Multiplexer Design:** VEM is commonly used for designing and simplifying multiplexer-based circuits.
- **Supports Digital Circuit Design:** It is useful in the design of decoders, Programmable Logic Arrays (PLAs), and other combinational circuits.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/variable-entrant-map-vem-in-digital-logic/)

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
