---
title: "How to Solve Relational Algebra Problems for GATE"
subject: "Database Management System"
topic: "Relational Model"
source: "https://www.geeksforgeeks.org/dbms/how-to-solve-relational-algebra-problems-for-gate/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Relational Model"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/relational-model
---


> [!abstract] How to Solve Relational Algebra Problems for GATE
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Relational Model`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/how-to-solve-relational-algebra-problems-for-gate/)

---

# How to Solve Relational Algebra Problems for GATE

Relational Algebra is fundamental or necessary for GATE computer science preparation. It is also an important section of the Database Management System (DBMS). Relational algebra provides a theoretical representation for querying and manipulating data in a relational database. Relational algebra has various operations like selection, projection, joins, union, and more.
In this article, Let's discuss common types of questions in relational algebra that are asked in GATE. Before reading this article, you should have an idea about basic operators and extended operators in relational algebra. 
## Types of Relational Algebra Problems
### **Type-1: Given a relational algebra expression, find the result.**
Suppose you have a relation Order(Prod\_Id, Agent\_Id, Order\_Month) and you have to find out what will the following algebra expression return. 
```
πOrder1.Prod_Id (σ Order1.Prod_Id=Order2.Prod_Id                                           and Order1.Agent_Id <> Order2.Agent_Id                                           and Order1.Order_Month=Order2.Order_Month (Order2,Order1))
```
Process the expression starting from the innermost brackets. 
In this example, we have renamed order to Order1 and Order2 (Both represent the same relation order). Then we have applied the conditional join between Order1 and Order2. It will return those rows where Product\_Id and Order\_Month of Order1 and Order2 are the same but Agent\_Id of Order1 and Order2 is different. It implies the rows where the same product is ordered by two different agents in the same month. Then we are projecting the Prod\_Id. 
So the final output will return the Prod\_Id of products that are ordered by different agents in the same month. We can do this by taking sample data. Let Order relation consists of the following data. 
**Table -** Order 
| Prod\_Id | Agent\_Id | Order\_Month |
| --- | --- | --- |
| P001 | A001 | JAN |
| P002 | A002 | FEB |
| P002 | A001 | FEB |
| P001 | A002 | FEB |
When we apply the following expression, the rows which are highlighted in blue will be selected. 
```
σOrder1.Prod_Id=Order2.Prod_Id                    and Order1.Agent_Id <> Order2.Agent_Id                    and Order1.Order_Month=Order2.Order_Month (Order2,Order1))
```
| Order1.Prod\_Id | Order1.Agent\_Id | Order1.Order\_Month | Order2.Prod\_Id | Order2.Agent\_Id | Order2.Order\_Month |
| --- | --- | --- | --- | --- | --- |
| P001 | A001 | JAN | P001 | A001 | JAN |
| P002 | A002 | FEB | P001 | A001 | JAN |
| P002 | A001 | FEB | P001 | A001 | JAN |
| P001 | A002 | FEB | P001 | A001 | JAN |
| P001 | A001 | JAN | P002 | A002 | FEB |
| P002 | A002 | FEB | P002 | A002 | FEB |
| P002 | A001 | FEB | P002 | A002 | FEB |
| P001 | A002 | FEB | P002 | A002 | FEB |
| P001 | A001 | JAN | P002 | A001 | FEB |
| P002 | A002 | FEB | P002 | A001 | FEB |
| P002 | A001 | FEB | P002 | A001 | FEB |
| P001 | A002 | FEB | P002 | A001 | FEB |
| P001 | A001 | JAN | P001 | A002 | FEB |
| P002 | A002 | FEB | P001 | A002 | FEB |
| P002 | A001 | FEB | P001 | A002 | FEB |
| P001 | A002 | FEB | P001 | A002 | FEB |
After projecting Order1.Prod\_Id, the output will be **P002** which is Prod\_Id of products that are ordered by at least two different agents in the same month. 
**Note -** If we want to find Prod\_Id which are ordered by at least three different agents in same month, it can be done as: 
```
πOrder1.Prod_Id (σOrder1.Prod_Id=Order2.Prod_Id                                  and Order1.Prod_Id=Order3.Prod_Id                                  and  Order1.Agent_Id <> Order2.Agent_Id                                  and Order1.Agent_Id <> Order3.Agent_Id                                  and Order2.Agent_Id <> Order3.Agent_Id                                  and Order1.Order_Month=Order2.Order_Month                                  and Order1.Order_Month=Order3.Order_Month((Order1,Order2),Order3) )
```
### **Type-2: Given two relations, what will be the maximum and minimum number of tuples after natural join?**
Consider the following relation R(A,B,C) and S(B,D,E) with underlined primary key. The relation R contains 200 tuples and the relation S contains 100 tuples. What is the maximum number of tuples possible in the natural Join R and S? 
To solve this type of question, first, we will see on which attribute natural join will take place. Natural join selects those rows which have equal values for common attribute. In this case, the expression would be like: 
```
σR.B=S.B (R X S)
```
In relation R, attribute B is the primary key. So Relation R will have 200 distinct values of B. On the other hand, Relation S has BD as the primary key. So attribute B can have 100 distinct values or 1 value for all rows. 
**Case-1:** S.B has 100 distinct values and each of these values match to R.B 
![Relational Algebra Problem](assets/11111111-39811f3613.png)
In this case, every value of B in S will match to a value of B in R. So natural join will have 100 tuples. 
**Case-2:** S.B has 1 values and this values match to R.B 
![Relational Algebra Problem](assets/22222222-12ed420ae4.png)
In this case, every value of B in S will match to a value of B in R. So natural join will have 100 tuples. 
**Case-3:** S.B has 100 distinct values and none of these values matches to R.B 
![Relational Algebra Problem](assets/33333333-f216f42231.png)
In this case, no value of B in S will match to a value of B in R. So natural join will have 0 tuple. 
**Case-4:** S.B has 1 value and it does not match with R.B 
![Relational Algebra Problem](assets/4444444-250c70b932.png)
In this case, no value of B in S will match to a value of B in R. So natural join will have 0 tuples. 
So the maximum number of tuples will be 100 and min will be 0. 
**Note -** If it is explicitly mentioned that S.B is a foreign key to R.B, then Case-3 and Case-4 discussed above are not possible because the value of S.B will be from the values of R.B. So, the minimum and maximum number of tuples in natural join will be 100. 
Consider the following three relations in a relational database.
### **Example:** Employee(eId, Name), Brand(bId, bName), Own(eId, bId)
Which of the following relational algebra expressions return the set of eIds who own all the brands? (GATE 2022)
**Option:**
1. πeld (Own) / πbId (Brand)
2. πeld(Own)(σbId (Brand))
3. πeld (Own)(σ (Brand,Own), Employee)
4. πeld (Own) ( πbId (Brand))
**Ans:** Option**1** is correct.
**Concept:**
The "Division operator" in relational algebra return all the entities that are associated with entities of different relation.
**The result of the query in option 1:**
It will display all the eId of relation "Own" which are associated with all the bId of relation "Brand".
## Conclusion
In conclusion, solving Relational Algebra problems for GATE requires a good understanding of core operations (like selection, projection, and join), derived operations (like intersection and division), and the ability to logically plan query steps. You must be understand the problem so you can breaking down problems into simpler tasks, applying the operations in an efficient sequence. Practicing with past GATE questions is game changer step to improve speed and accuracy. At the last, if you want to solve the question then you understand the problem, apply the operations and arrange the query in efficient sequence.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/how-to-solve-relational-algebra-problems-for-gate/)

## GATE CS

- Subject: Database Management System
- Topic: Relational Model

> [!note] Related notes
>
> - [[Anomalies in Relational Model]]
> - [[Introduction to Relational Model]]
> - [[Keys in Relational Model]]
> - [[Relational Algebra – Extended Operators]]
> - [[Relational Algebra – Overview]]
> - [[Relational Model Introduction and Codd Rules]]
> - [[Tuple Relational Calculus]]
> - [[ACID Properties in DBMS]]
> - [[Advantages of DBMS over File system]]
> - [[Canonical Cover]]
