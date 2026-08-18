---
title: "SQL Nested Queries"
subject: "Database Management System"
topic: "Structured Query Languages (SQL)"
source: "https://www.geeksforgeeks.org/sql/nested-queries-in-sql/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Structured Query Languages (SQL)"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/structured-query-languages-sql
---


> [!abstract] SQL Nested Queries
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Structured Query Languages (SQL)`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/sql/nested-queries-in-sql/)

---

# SQL Nested Queries

A nested query (or subquery) is a SQL query written inside another query to solve complex data problems. The inner query executes first and passes its result to the main query. Used for filtering, updating and retrieving data from related tables.
We will use the following sample tables to demonstrate nested queries:
### 1. STUDENT Table
The STUDENT table stores information about students, including their unique ID, name, address, phone number and age.
![Student_details](assets/Student_details-f4e3ca299b.png)
Student Table
### 2. COURSE Table
The COURSE table stores course details, including a unique course ID and course name.
![course_table](assets/course_table-7d4da0e5c0.png)
Course Table
### 3. STUDENT\_COURSE Table
This table maps students to the courses they have enrolled in, with columns for student ID (S\_ID) and course ID (C\_ID):
![student_course_table](assets/student_course_table-f4538b226c.png)
STUDENT\_COURSE Table
## Types of Nested Queries in SQL
There are two primary types of nested queries in SQL:
### Independent Nested Queries
In an independent nested query, the execution of the inner query is independent of the outer query. The inner query runs first and its result is used directly by the outer query. Operators like IN, NOT IN, ANY and ALL are commonly used with independent nested query.
### Example 1: Using IN
In this example, we will find the S\_IDs of students who are enrolled in the courses ‘DSA’ or ‘DBMS’. We can break the query into two parts:
**Step 1:** Find the C\_IDs of the courses:
This query retrieves the IDs of the courses named 'DSA' or 'DBMS' from the COURSE table.
```
SELECT C_ID FROM COURSE WHERE C_NAME IN ('DSA', 'DBMS');
```
**Output:**
![C_ID](assets/C_ID-d8e63594e9.png)
Output
**Step 2:** Use the result of Step 1 to find the corresponding S\_IDs:
The inner query finds the course IDs and the outer query retrieves the student IDs associated with those courses from the STUDENT\_COURSE table.
```
SELECT S_ID FROM STUDENT_COURSE WHERE C_ID IN (  SELECT C_ID FROM COURSE WHERE C_NAME IN ('DSA', 'DBMS'));
```
**Output**
![S_id](assets/S_id-28360cc186.png)
Output
### 2. Correlated Nested Queries
A correlated nested query depends on the outer query and is executed once for each row processed by it. The inner query references columns from the outer query and is often used with the `EXISTS` keyword.
**Example 2: Using EXISTS**
In this Example, we will find the names of students who are enrolled in the course with C\_ID = 'C1':
```
SELECT S_NAME FROM STUDENT SWHERE EXISTS (  SELECT 1 FROM STUDENT_COURSE SC  WHERE S.S_ID = SC.S_ID AND SC.C_ID = 'C1');
```
**Output**
![S_name](assets/S_name-84c29611e9.png)
Output
**Explanation:** For each student, the inner query checks if they are enrolled in C1. If yes, that student’s name is returned.
## Common SQL Operators for Nested Queries
SQL provides several operators that can be used with nested queries to filter, compare and perform conditional checks.
### 1. IN Operator
The `IN` operator checks whether a column value matches any value returned by a subquery, eliminating the need for multiple `OR` conditions.
**Example:** Retrieve student names who enrolled in ‘DSA’ or ‘DBMS’:
```
SELECT S_NAME FROM STUDENTWHERE S_ID IN (  SELECT S_ID FROM STUDENT_COURSE  WHERE C_ID IN (    SELECT C_ID FROM COURSE WHERE C_NAME IN ('DSA', 'DBMS')  ));
```
**Output**
![s_name-1](assets/s_name-1-d50c5de884.png)
Output
### 2. NOT IN Operator
The `NOT IN` operator excludes rows whose values match those returned by a subquery, helping filter out unwanted records.
**Example:** Retrieve student IDs not enrolled in ‘DSA’ or ‘DBMS’:
```
SELECT S_ID FROM STUDENTWHERE S_ID NOT IN (  SELECT S_ID FROM STUDENT_COURSE  WHERE C_ID IN (    SELECT C_ID FROM COURSE WHERE C_NAME IN ('DSA', 'DBMS')  ));
```
**Output:**
![S_ID](assets/S_ID-2e3c654836.png)
Output
### 3. ANY Operator
The ANY operator compares a value with the results of a subquery and returns TRUE if the condition is satisfied for at least one value. It is commonly used with comparison operators such as =, >, <, >=, <= and <>.
**Example:** Retrieve student names whose age is greater than at least one student from
```
SELECT S_NAMEFROM Student_Details sWHERE EXISTS (  SELECT 1  FROM Student_Details d  WHERE d.S_ADDRESS = 'LONDON'    AND s.S_AGE > d.S_AGE);
```
**Output**
![Daniel](assets/Daniel-44e24df642.png)
Output
### 4. ALL Operator
It compares a value with all values returned by the subquery. The condition is satisfied only if it is true for every value.
**Example:** Retrieve student names whose age is greater than all students from London
```
SELECT S_NAME FROM Student_DetailsWHERE S_AGE > (  SELECT MAX(S_AGE)  FROM Student_Details  WHERE S_ADDRESS = 'London');
```
**Output:**
![Daniel](assets/Daniel-913410e323.png)
Output
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/sql/nested-queries-in-sql/)

## GATE CS

- Subject: Database Management System
- Topic: Structured Query Languages (SQL)

> [!note] Related notes
>
> - [[Database Objects]]
> - [[Having Vs Where Clause]]
> - [[Indexing in Databases]]
> - [[Inner VS Outer Join]]
> - [[Introduction to Structured Query Language]]
> - [[Join operation Vs nested query]]
> - [[Joins in SQL]]
> - [[Parts of SQL]]
> - [[SQL Indexes]]
> - [[SQL queries on clustered and non-clustered Indexes]]
