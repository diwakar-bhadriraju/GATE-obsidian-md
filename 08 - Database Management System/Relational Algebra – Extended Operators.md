---
title: "Extended Operators in Relational Algebra"
subject: "Database Management System"
topic: "Relational Model"
source: "https://www.geeksforgeeks.org/dbms/extended-operators-in-relational-algebra/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Relational Model"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/relational-model
---


> [!abstract] Extended Operators in Relational Algebra
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Relational Model`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/extended-operators-in-relational-algebra/)

---

# Extended Operators in Relational Algebra

Extended operators in relational algebra are operators that go beyond the basic set of relational algebra operations. They are also known as derived operators because they can be constructed from combinations of the fundamental operators.
There are mainly three types of extended operators in Relational Algebra, Join, Intersection (∩) and Divide (÷)
![extended_relational_algebra](assets/extended_relational_algebra-aa31bde8a1.webp)
We will be explaining these types using the following tables:
**Table R:**
| A | B |
| --- | --- |
| 1 | x |
| 2 | y |
| 3 | z |
**Table S:**
| B | C |
| --- | --- |
| x | 10 |
| y | 20 |
| w | 30 |
## Join
Join operators in [DBMS](https://www.geeksforgeeks.org/dbms/dbms/) are used to combine data from two or more tables based on a related column between them. These operators allow efficient data retrieval, making it easier to perform complex queries. The most common types of Join operators are Inner Join and Outer Join.
### 1. Inner Join
[Inner join](https://www.geeksforgeeks.org/sql/sql-inner-join/) returns rows when there is a match in both tables. If there is no match, the row is excluded from the result. It is the most frequently used join in relational databases and ensures that only matching records from both tables are included.
Inner joins can be categorized into more specific types based on how the join condition is defined:
**1.1 Conditional Join(⋈**θ**):** [Conditional Join](https://www.geeksforgeeks.org/dbms/conditional-join/) or Theta Join is used when you want to join two or more relation based on some conditions. It supports various comparison operators, such as <, >, <=, >=, = and ≠.
**Example:** Join tables R and S based on a condition θ. For example, join where R.B = S.B and R.A > 1.
> **R** **⋈** **R. B = S .B** **∧ R . A** **> 1** **S**
**Output Table:**
| A | R.B | S.B | C |
| --- | --- | --- | --- |
| 2 | y | y | 20 |
> **Note:** The selection operator only selects the required tuples but does not display them. For display, the data projection operator is used.
**1.2 Equi Join:** [Equi Join](https://www.geeksforgeeks.org/sql/sql-equi-join-and-non-equi-join/) is a special case of conditional join where only equality condition holds between a pair of attributes. As values of two attributes will be equal in result of equijoin, only one attribute will be appeared in result.
**Example:** Join tables R and S where R.B = S.B.
> **R ⋈**R.B=S.B** **S**
**Output Table:**
| A | R.B | S.B | C |
| --- | --- | --- | --- |
| 1 | x | x | 10 |
| 2 | y | y | 20 |
**1.3 Natural Join(⋈):** A [Natural Join](https://www.geeksforgeeks.org/sql/sql-natural-join/) automatically combines two tables based on matching column names and data type, eliminating duplicate columns and providing a seamless result set. While applying natural join on two relations, there is no need to write equality condition explicitly. Natural Join will also return the similar attributes only once as their value will be same in resulting relation.
**Example:** Join tables R and S on the common attribute B and eliminate duplicate columns.
> **R ⋈ S**
**Output Table:**
| A | B | C |
| --- | --- | --- |
| 1 | x | 10 |
| 2 | y | 20 |
Natural Join is by default inner join because the tuples which does not satisfy the conditions of join does not appear in result set.
### 2. Outer Join
The [Outer Join](https://www.geeksforgeeks.org/sql/sql-outer-join/) returns all records from one table and the matched records from the other table. If no match is found, the result will include NULL values for the non-matching columns. Outer joins can be further classified into [Left Outer Join, Right Outer Join and Full Outer Join](https://www.geeksforgeeks.org/sql/sql-join-set-1-inner-left-right-and-full-joins/), based on which table’s records are prioritized in case of non-matching rows.
**2.1 Left Outer Join(⟕):** A Left Outer Join in DBMS returns all records from the left table and the matching records from the right table. If there is no match in the right table, it still includes all rows from the left table with NULL values for the columns of the right table.
![left-join](assets/left-join-cc26bbfbbe.gif)
Left Outer Join
**Example:** Join tables R and S on R.B = S.B and include all rows from R even if there is no match in S.
> **R** ⟕**S**
**Output Table:**
| **A** | **R.B** | **S.B** | **C** |
| --- | --- | --- | --- |
| 1 | x | x | 10 |
| 2 | y | y | 20 |
| 3 | z | NULL | NULL |
**2.2 Right Outer Join(⟖):** A Right Outer Join retrieves all records from the right table and the matching records from the left table. If there is no match in the left table, the result will still include all rows from the right table, with NULL values for the left table's columns. This join is particularly useful when you want to ensure all data from the right table is included, even if no corresponding records exist in the left table.
![Right_Join](assets/Right_Join-19763aac70.gif)
Right Outer Join
**Example:** Join tables R and S on R.B = S.B and include all rows from S even if there is no match in R.
> **R ⟖ S**
**Output Table:**
| **A** | **R.B** | **S.B** | **C** |
| --- | --- | --- | --- |
| **1** | x | x | 10 |
| 2 | y | y | 20 |
| NULL | NULL | w | 30 |
**2.3 Full Outer Join(⟗):** A Full Outer Join returns all records when there is a match in either the left or right table. If there is no match, it includes all rows from both tables with NULL values for the missing side. This join is useful when you need to ensure that no data is lost from either table, making it ideal for combining datasets where all information should be preserved, regardless of whether a match exists.
![Full-Join](assets/Full-Join-24801394ba.gif)
Full Outer Join
**Example:** Join tables R and S on R.B = S.B and include all rows from both tables, filling in NULLs where there is no match.
> **R ⟗ S**
**Output Table:**
| A | R.B | S.B | C |
| --- | --- | --- | --- |
| 1 | x | x | 10 |
| 2 | y | y | 20 |
| 3 | z | NULL | NULL |
| NULL | NULL | w | 30 |
> Read related article [Inner Join v/s Outer Join](https://www.geeksforgeeks.org/dbms/inner-join-vs-outer-join/)
## Intersection (∩)
Intersection is an operator that returns the common records from two relations. It retrieves rows that appear in both tables, ensuring that only the matching data from both sets is included in the result. Intersection on two relations can only be computed if both relations are **union compatible.**
It means two relation should have same number of attributes and corresponding attributes in two relations have same domain. In simple words, both table should have same schema.
**Example:** Assume R and S are as follows for intersection:
**Table R:**
| A | B |
| --- | --- |
| 1 | x |
| 2 | y |
| 3 | z |
**Table S:**
| A | B |
| --- | --- |
| 1 | x |
| 2 | y |
Both R and S have the same schema (A and B). The intersection of R and S returns rows that are present in both R and S.
> **R ∩ S**
**Output Table:**
| **A** | **B** |
| --- | --- |
| 1 | x |
| 2 | y |
## Division (÷)
The Division operator is used to find records in one relation that are associated with all records in another relation. It is commonly used when we want to identify entities that satisfy certain conditions across multiple related data sets.
The Division operator (R ÷ S) can be applied if:
- The attributes of B are a proper subset of the attributes of R.
- The result will include all attributes of A except those that are in S.
- It returns the tuples from R that are associated with every tuple in S.
**Example:** Assume R and S are as follows for division,
**Table R:**
| A | B |
| --- | --- |
| 1 | x |
| 1 | y |
| 2 | x |
| 2 | y |
| 3 | z |
**Table S:**
| B |
| --- |
| x |
| y |
The division R ÷ S returns values of A that are associated with all values of B in S.
> **R ÷ S**
**Output Table:**
| **A** |
| --- |
| 1 |
| 2 |
## Related PYQs
> [GATE | GATE CS 2012 | Question 41](https://www.geeksforgeeks.org/questions/suppose-a-b-and-cd-are-two-relation-schemas/)
>
> [GATE | GATE CS 2012 | Question 50](https://www.geeksforgeeks.org/questions/consider-the-following-relations-a-b-c-how-many/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/extended-operators-in-relational-algebra/)

## GATE CS

- Subject: Database Management System
- Topic: Relational Model

> [!note] Related notes
>
> - [[Anomalies in Relational Model]]
> - [[How to solve Relational Algebra problems for GATE]]
> - [[Introduction to Relational Model]]
> - [[Keys in Relational Model]]
> - [[Relational Algebra – Overview]]
> - [[Relational Model Introduction and Codd Rules]]
> - [[Tuple Relational Calculus]]
> - [[ACID Properties in DBMS]]
> - [[Advantages of DBMS over File system]]
> - [[Canonical Cover]]
