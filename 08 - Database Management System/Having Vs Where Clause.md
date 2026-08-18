---
title: "Having vs Where Clause in SQL"
subject: "Database Management System"
topic: "Structured Query Languages (SQL)"
source: "https://www.geeksforgeeks.org/sql/having-vs-where-clause-in-sql/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Structured Query Languages (SQL)"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/structured-query-languages-sql
---


> [!abstract] Having vs Where Clause in SQL
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Structured Query Languages (SQL)`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/sql/having-vs-where-clause-in-sql/)

---

# Having vs Where Clause in SQL

In SQL, **filtering data** is important for extracting meaningful insights from **large datasets**. While both the **WHERE** and **HAVING** clauses allow us to filter data, they serve **distinct purposes** and operate at different stages of the **query execution process**. Understanding the difference between these clauses is key to writing efficient **SQL queries**.
In this article, we will explain the fundamental difference between the **WHERE** and **HAVING** clauses, provides **practical examples**, and discuss when to use each clause. By the end of this article, we will have a clear understanding of how to use **WHERE** and **HAVING** for more effective data filtering in SQL.
## Difference Between HAVING and WHERE Clause in SQL
Here’s a table highlighting the key differences between the **WHERE** and **HAVING** clauses in SQL:
| **Criteria** | **WHERE Clause** | **HAVING Clause** |
| --- | --- | --- |
| **Purpose** | Filters rows before aggregation. | Filters rows after aggregation. |
| **Used With** | Works with individual rows. | Works with grouped or aggregated data. |
| **Applicable To** | Columns in the table (individual records). | Aggregated results (e.g., `SUM()`, `COUNT()`). |
| **Stage of Query Execution** | Filters data before `GROUP BY`. | Filters data after `GROUP BY`. |
| **Aggregate Functions** | Cannot be used with aggregate functions. | Can be used with aggregate functions. |
| **Efficiency** | Generally more efficient, as it filters data earlier. | Can be less efficient, as it filters after aggregation. |
| **Example Usage** | `WHERE column_name = value` | `HAVING aggregate_function(column_name) > value` |
| **Order in Query** | Appears before `GROUP BY`. | Appears after `GROUP BY`. |
## What is the WHERE Clause in SQL?
The [WHERE clause](https://www.geeksforgeeks.org/sql/sql-where-clause/) is used to **filter records** before any **grouping** or **aggregation** is done. It operates on **individual rows** and applies conditions to the raw data. We can use **WHERE** to filter out rows that don’t meet our criteria, such as filtering out **customers with sales below a certain amount,** or employees from a specific department.
**Syntax:**
> SELECT column1, column2
> FROM table\_name
> WHERE condition;
## What is the HAVING Clause in SQL?
The [HAVING clause](https://www.geeksforgeeks.org/sql/sql-having-clause-with-examples/), on the other hand, is used to filter records **after** the data has been **grouped** or **aggregated**. It works on aggregated data and is often used in **conjunction** with the [`GROUP BY` clause](https://www.geeksforgeeks.org/sql/sql-group-by/) to filter out groups based on **aggregate functions** like **`SUM()`**,** **`AVG()`**, **`COUNT()`**, etc.
#### Syntax:
> SELECT column1, aggregate\_function(column2)
> FROM table\_name
> GROUP BY column1
> HAVING condition;
## Example 1: Using WHERE Clause for Row-Level Filtering
Consider the following table **`Marks`**, which contains **student names**, their respective **courses**, and the scores they achieved. This example demonstrates how the **`WHERE`** **clause** can filter data at the **individual row level**, before any **grouping** or **aggregation** takes place.
![Using-Where-Clause](assets/Using-Where-Clause-89b9aa2e6c.png)
Using Where Clause
To select students with a score greater than or equal to 40, we can use the **WHERE** clause. This query filters rows before any [aggregation](https://www.geeksforgeeks.org/mongodb/aggregation-commands/), selecting only students with scores **greater than** or **equal to 40**.
**Query:**
```
SELECT Student, ScoreFROM MarksWHERE Score >= 40;
```
**Output**
| Student | Score |
| --- | --- |
| a | 40 |
| a | 50 |
| b | 60 |
| d | 70 |
| e | 80 |
## Example 2: Using HAVING Clause for Aggregated Data Filtering
Now, suppose you want to calculate the **total score of each student** and only show students whose **total score is greater than 70**. We can use the **HAVING** clause:
**Query:**
```
SELECT Student, SUM(Score) AS TotalFROM MarksGROUP BY StudentHAVING Total > 70;
```
**Output**
| Student | Total |
| --- | --- |
| a | 90 |
| e | 80 |
**Explanation:**
Here, we are using **HAVING** to filter groups of students after summing their scores. This is because **HAVING** works on aggregated data, whereas **WHERE** cannot be used for filtering after aggregation.
## Conclusion
The **WHERE** and **HAVING** clauses in SQL are both used for filtering data, but they work at different stages in the query execution process. **WHERE** filters individual rows before aggregation, while **HAVING** filters groups after aggregation. Understanding when to use each clause is essential for writing effective and efficient [SQL queries](https://www.geeksforgeeks.org/sql/sql-concepts-and-queries/). By using **WHERE** and **HAVING** appropriately, we can refine our data retrieval process and gain more precise insights from our [database](https://www.geeksforgeeks.org/dbms/what-is-database/).
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/sql/having-vs-where-clause-in-sql/)

## GATE CS

- Subject: Database Management System
- Topic: Structured Query Languages (SQL)

> [!note] Related notes
>
> - [[Database Objects]]
> - [[Indexing in Databases]]
> - [[Inner VS Outer Join]]
> - [[Introduction to Structured Query Language]]
> - [[Join operation Vs nested query]]
> - [[Joins in SQL]]
> - [[Nested Queries in SQL]]
> - [[Parts of SQL]]
> - [[SQL Indexes]]
> - [[SQL queries on clustered and non-clustered Indexes]]
