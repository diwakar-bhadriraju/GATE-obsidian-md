---
title: "SQL Indexes"
subject: "Database Management System"
topic: "Structured Query Languages (SQL)"
source: "https://www.geeksforgeeks.org/sql/sql-indexes/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Structured Query Languages (SQL)"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/structured-query-languages-sql
---


> [!abstract] SQL Indexes
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Structured Query Languages (SQL)`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/sql/sql-indexes/)

---

# SQL Indexes

Indexes in SQL are special database structures that improve query performance by allowing faster access to data instead of scanning the entire table. They help retrieve records efficiently and enhance overall database performance.
> **Note:** Primary Key and Unique constraints automatically create indexes.
## Creating an Index
There are three main ways to create an index in SQL, each serving different purposes based on how data is accessed and organized in a table. Indexes help improve query performance by allowing faster data retrieval.
### Single Column Indexes
A single-column index is created on just one column. It’s the most basic type of index and helps speed up queries when you frequently search, filter or sort by that column.
**Syntax:**
```
CREATE INDEX index_name ON table_name (column);
```
**Example:** First, we [create](https://www.geeksforgeeks.org/sql/sql-create-table/) a demo SQL database and table, on which we implement the Indexes.
![Screenshot-2025-11-22-150923](assets/Screenshot-2025-11-22-150923-317e889e6b.png)
**Query:**
```
CREATE INDEX idx_product_id ON Sales (product_id);
```
### Multi Column Indexes
A multi-column index is created on two or more columns. It improves performance when queries filter or join based on multiple columns together.
**Syntax:**
```
CREATE INDEX index_name ON table_name (column1, column2,.....);
```
**Query:**
```
CREATE INDEX idx_product_quantity ON Sales (product_id, quantity);
```
### Unique Indexes
A unique index ensures that all values in a column (or combination of columns) are unique preventing duplicates and maintaining data integrity.
**Syntax:**
```
CREATE UNIQUE INDEX index_name ON table_name (column_name);
```
**Query:**
```
CREATE UNIQUE INDEX idx_unique_employee_id ON Sales (customer_id);
```
If we try inserting a duplicate:
```
INSERT INTO Sales (sale_id, product_id, quantity, customer_id)VALUES (6, 105, 4, 201);
```
It will throw an error because customer\_id = 201 already exists.
## Confirming & Viewing Indexes
We can view all the indexes in a database to understand which ones are in use and confirm their structure. In SQL, the following query helps us see the indexes for a given table:
**Syntax:**
```
SHOW INDEXES FROM table_name;
```
**Query:**
```
SHOW INDEXES FROM Sales;
```
**Output:**
![Screenshot-2025-11-22-150743](assets/Screenshot-2025-11-22-150743-142293a29c.png)
## Removing an Index
Indexes take up storage and add overhead on write operations (INSERT, UPDATE, DELETE). If an index is no longer needed, it can be removed.
**Syntax:**
```
DROP INDEX index_name ON table_name;
```
**Query:**
```
DROP INDEX idx_product_quantity ON Sales;
```
## Altering an Index
If an index requires adjustments, such as reorganizing or rebuilding, it can be altered without affecting the data. This is useful for optimizing index performance as tables grow larger.
**Syntax:**
```
ALTER INDEX IndexName ON TableName REBUILD;
```
**Query:**
```
ALTER INDEX idx_product_id ON Sales REBUILD;
```
## Renaming an Index
In some cases, renaming an index might be necessary for clarity or consistency. While SQL does not directly support renaming indexes, we can use a combination of commands to achieve this.
**Syntax:**
```
EXEC sp_rename 'old_index_name', 'new_index_name', 'INDEX';
```
**Query:**
```
EXEC sp_rename 'idx_product_quantity', 'idx_prod_qty', 'INDEX';
```
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/sql/sql-indexes/)

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
> - [[SQL queries on clustered and non-clustered Indexes]]
