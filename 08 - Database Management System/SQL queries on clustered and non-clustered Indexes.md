---
title: "SQL Queries on Clustered and Non-Clustered Indexes"
subject: "Database Management System"
topic: "Structured Query Languages (SQL)"
source: "https://www.geeksforgeeks.org/sql/sql-queries-on-clustered-and-non-clustered-indexes/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Structured Query Languages (SQL)"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/structured-query-languages-sql
---


> [!abstract] SQL Queries on Clustered and Non-Clustered Indexes
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Structured Query Languages (SQL)`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/sql/sql-queries-on-clustered-and-non-clustered-indexes/)

---

# SQL Queries on Clustered and Non-Clustered Indexes

Indexes in SQL play a pivotal role in enhancing database performance by enabling efficient data retrieval without scanning the entire table. The two primary types of indexes Clustered Index and Non-Clustered Index serve distinct purposes in optimizing query performance.
## Indexes in SQL
[Indexing](https://www.geeksforgeeks.org/sql/sql-indexes/) in SQL is similar to the index page in a book, they allow the database to quickly locate data without scanning the entire table. Without indexing, [SQL Server](https://www.geeksforgeeks.org/sql/create-schema-in-sql-server/) performs a full table scan, which can be time-consuming for large datasets. By creating indexes, SQL Server optimizes query execution, reducing retrieval time. In the same way, a table's index allows us to locate the exact data without scanning the whole table.
- Faster SELECT queries.
- Efficient data access for UPDATE, DELETE, and JOIN operations.
- Minimizes disk I/O operations.
### Types of Indexes in SQL
- Clustered index
- Non-clustered index
## 1. Clustered Index
Type of indexing that establishes a physical sorting order of rows. The data rows are stored directly in the order of the indexed column(s). Each table can have only one clustered index because it dictates the data’s physical storage. A clustered index is like a Dictionary in which the sorting order is alphabetical and there is no separate index page. 
Suppose we have a table Student\_info which contains ROLL\_NO as a [primary key](https://www.geeksforgeeks.org/sql/primary-key-constraint-in-sql/), then the clustered index which is self-created on that primary key will sort the Student\_info table as per ROLL\_NO.
**Example:** Creating a Clustered Index
> CREATE TABLE Student\_info
> (
> ROLL\_NO int(10) primary key,
> NAME varchar(20),
> DEPARTMENT varchar(20),
> );
> INSERT INTO Student\_info values(1410110405, 'H Agarwal', 'CSE');
> INSERT INTO Student\_info values(1410110404, 'S Samadder', 'CSE');
> INSERT INTO Student\_info values(1410110403, 'MD Irfan', 'CSE');
>
> SELECT \* FROM Student\_info;
**Output:**
| ROLL\_NO | NAME | DEPARTMENT |
| --- | --- | --- |
| 1410110403 | MD Irfan | CSE |
| 1410110404 | S Samadder | CSE |
| 1410110405 | H Agarwal | CSE |
**Explanation:**
- The ROLL\_NO column is the [primary key](https://www.geeksforgeeks.org/sql/primary-key-constraint-in-sql/), making it the Clustered Index by default.
- Rows are stored in ascending order of ROLL\_NO.
### Dropping and Creating a Custom Clustered Index
If we want to create a Clustered index on another column, first we have to remove the primary key, and then we can remove the previous index. Note that defining a column as a [primary key](https://www.geeksforgeeks.org/dbms/primary-key-in-dbms/) makes that column the Clustered Index of that table. To create a clustered index on a different column:
1. Remove the existing primary key (if any).
2. Drop the previous clustered index**.**
**Syntax:**
> DROP INDEX table\_name.index\_name;
>
> CREATE CLUSTERED INDEX IX\_table\_name\_column\_name
> ON table\_name (column\_name ASC);
**Example:**
> CREATE CLUSTERED INDEX IX\_Student\_info\_NAME
> ON Student\_info (NAME ASC);
## 2. Non-Clustered Index
An index structure separate from the data stored in a table that reorders one or more selected columns. The non-clustered index is created to improve the performance of frequently used queries not covered by a clustered index. It's like a textbook, the index page is created separately at the beginning of that book.
**Example:** Creating a Non-Clustered Index - We start by creating the Student\_info table and inserting some sample data.
> CREATE TABLE Student\_info
> (
> ROLL\_NO int(10),
> NAME varchar(20),
> DEPARTMENT varchar(20),
> );
>
> INSERT INTO Student\_info values(1410110405, 'H Agarwal', 'CSE');
> INSERT INTO Student\_info values(1410110404, 'S Samadder', 'CSE');
> INSERT INTO Student\_info values(1410110403, 'MD Irfan', 'CSE');
>
> SELECT \* FROM Student\_info;
**Output:**
| ROLL\_NO | NAME | DEPARTMENT |
| --- | --- | --- |
| 1410110405 | H Agarwal | CSE |
| 1410110404 | S Samadder | CSE |
| 1410110403 | MD Irfan | CSE |
**Syntax:**
> create NonClustered index IX\_table\_name\_column\_name on table\_name (column\_name ASC)
We will create a Non-Clustered Index on the NAME column to improve query performance when searching by name. Here is the SQL Query for the same
**Query:**
> create NonClustered index IX\_Student\_info\_NAME on Student\_info (NAME ASC)
**Output:**
| NAME | ROW\_ADDRESS |
| --- | --- |
| H Agarwal | 1 |
| MD Irfan | 3 |
| S Samadder | 2 |
## Difference between Clustered and Non-clustered Index
| Aspect | Clustered Index | Non-Clustered Index |
| --- | --- | --- |
| Data Storage Order | Determines the physical order of data in the table. | Does not affect the physical order of data. |
| Number of Indexes | Only one per table. | Multiple indexes can be created on a table. |
| Index Structure | The index is the table; data rows are stored in the index order. | The index is a separate structure with pointers to data rows. |
| Performance | Optimized for range queries and ordered data retrieval. | Useful for quick lookups and searches on non-primary key columns. |
| Primary Key Default | If no clustered index is specified, the primary key usually becomes the clustered index. | Can be created on any column, not necessarily a primary key. |
| Flexibility | Less flexible due to the single ordering constraint. | More flexible as multiple non-clustered indexes can be created. |
| Use Case | Ideal for tables where data is frequently retrieved in a sorted order or requires range queries. | Ideal for optimizing search queries on columns that are not the primary key or clustered index. |
## Optimizing Queries with Clustered and Non-Clustered Indexes
Below are detailed examples of [SQL queries](https://www.geeksforgeeks.org/sql/sql-concepts-and-queries/) and the advantages of using Clustered Indexes and Non-Clustered Indexes, along with practical scenarios to illustrate their impact on query performance.
### 1. SELECT Queries with WHERE Clause
**Clustered Index:** When executing a SELECT query with a [WHERE](https://www.geeksforgeeks.org/sql/sql-where-clause/) clause on a table with a Clustered Index, the database engine uses the index to directly locate rows matching the condition, minimizing disk I/O.
**Example:**
> -- Create a table with a clustered index on ROLL\_NO
> CREATE TABLE Student\_info (
>  ROLL\_NO INT PRIMARY KEY,
>  NAME VARCHAR(20),
>  DEPARTMENT VARCHAR(20)
> );
>
> INSERT INTO Student\_info VALUES
> (1410110405, 'H Agarwal', 'CSE'),
> (1410110404, 'S Samadder', 'CSE'),
> (1410110403, 'MD Irfan', 'CSE');
>
> -- Query using the clustered index
> SELECT \*
> FROM Student\_info
> WHERE ROLL\_NO = 1410110404;
**Output:**
| ROLL\_NO | NAME | DEPARTMENT |
| --- | --- | --- |
| 1410110404 | S Samadder | CSE |
**Non-Clustered Index:** If a Non-Clustered Index is created on the NAME column, the query optimizer uses the index to locate matching rows efficiently.
**Example:**
> -- Create a non-clustered index on NAME
> CREATE NONCLUSTERED INDEX IX\_Student\_info\_NAME
> ON Student\_info (NAME ASC);
>
> -- Query using the non-clustered index
> SELECT \*
> FROM Student\_info
> WHERE NAME = 'H Agarwal';
**Output:**
| ROLL\_NO | NAME | DEPARTMENT |
| --- | --- | --- |
| 1410110405 | H Agarwal | CSE |
### 2. UPDATE Queries
**Clustered Index:** When updating a row in a table with a Clustered Index, the database can quickly locate the row to modify based on the indexed column.
**Example:**
> -- Update the DEPARTMENT of a specific ROLL\_NO
> UPDATE Student\_info
> SET DEPARTMENT = 'ECE'
> WHERE ROLL\_NO = 1410110403;
**Output:**
| ROLL\_NO | NAME | DEPARTMENT |
| --- | --- | --- |
| 1410110403 | MD Irfan | ECE |
**Non-Clustered Index:** If the [UPDATE](https://www.geeksforgeeks.org/sql/sql-update-statement/) query references columns that are not part of the clustered index, SQL Server may need to perform additional disk writes to update the non-clustered index as well.
**Example:**
> -- Update NAME for a specific ROLL\_NO
> UPDATE Student\_info
> SET NAME = 'Harsh Agarwal'
> WHERE ROLL\_NO = 1410110405;
**Output:**
| ROLL\_NO | NAME | DEPARTMENT |
| --- | --- | --- |
| 1410110405 | Harsh Agarwal | CSE |
| 1410110404 | S Samadder | CSE |
| 1410110403 | MD Irfan | CSE |
### 3. JOIN Queries
**Clustered Index:** When performing a [JOIN operation](https://www.geeksforgeeks.org/sql/sql-join-set-1-inner-left-right-and-full-joins/) between two large tables, SQL Server can use the clustered index on the join column(s) to efficiently match the rows from both tables. This can significantly reduce the time required to complete the query.
**Example:**
> -- Create another table for join
> CREATE TABLE Course\_enrollments (
>  ROLL\_NO INT,
>  COURSE\_NAME VARCHAR(20)
> );
>
> INSERT INTO Course\_enrollments VALUES
> (1410110405, 'Data Structures'),
> (1410110404, 'Algorithms'),
> (1410110403, 'Databases');
>
> -- Join query
> SELECT s.ROLL\_NO, s.NAME, e.COURSE\_NAME
> FROM Student\_info s
> JOIN Course\_enrollments e
> ON s.ROLL\_NO = e.ROLL\_NO;
**Output:**
| ROLL\_NO | NAME | COURSE\_NAME |
| --- | --- | --- |
| 1410110405 | H Agarwal | Data Structures |
| 1410110404 | S Samadder | Algorithms |
| 1410110403 | MD Irfan | Databases |
**Non-Clustered Index**: If the [JOIN](https://www.geeksforgeeks.org/sql/sql-join-set-1-inner-left-right-and-full-joins/) operation references columns that are not part of the clustered index, SQL Server can use a non-clustered index to find the matching rows. However, this may require additional disk reads and slow down the query.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/sql/sql-queries-on-clustered-and-non-clustered-indexes/)

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
> - [[Nested Queries in SQL]]
> - [[Parts of SQL]]
> - [[SQL Indexes]]
