---
title: "SQL Views"
subject: "Database Management System"
topic: "Structured Query Languages (SQL)"
source: "https://www.geeksforgeeks.org/sql/sql-views/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Structured Query Languages (SQL)"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/structured-query-languages-sql
---


> [!abstract] SQL Views
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Structured Query Languages (SQL)`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/sql/sql-views/)

---

# SQL Views

A SQL View is a virtual table created from the result of a SELECT query. It does not store data physically but displays data stored in underlying tables. Views help simplify complex queries, enhance security and present data in a cleaner, customized format.
**Example:** First, we will [create](https://www.geeksforgeeks.org/sql/sql-create-table/) a demo SQL database and table, on which we will use the TRUNCATE TABLE command.
![student_details](assets/student_details-08d91b4a8e.png)
**Query:**
```
CREATE VIEW StudentView ASSELECT NAME, ADDRESSFROM StudentDetails;SELECT * FROM StudentView;
```
**Output:**
![Output](assets/Output-6095166285.png)
## CREATE VIEWS in SQL
We can create a view using CREATE VIEW statement. A View can be created from a single table or multiple tables.
**Syntax:**
```
CREATE VIEW view_name ASSELECT column1, column2.....FROM table_nameWHERE condition;
```
- **view\_name**: Name for the View
- **table\_name**: Name of the table
- **condition**: Condition to select rows
### Example 1: Creating a Simple View from a Single Table
First, create a sample table. Then create a view using the CREATE VIEW statement.
![students](assets/students-2510aad791.png)
In this example, we create a View named DetailsViewfrom the table StudentDetails.
**Query:**
```
CREATE VIEW DetailsView ASSELECT NAME, ADDRESSFROM StudentDetailsWHERE S_ID < 5;
```
Use the below query to retrieve the data from this view
```
SELECT * FROM DetailsView;
```
**Output:**
![Liam](assets/Liam-6404241b40.png)
### Example 2: Creating a View From Multiple Tables
In this example, we create a View MarksView that combines data from bothtables StudentDetails and StudentMarks. To create a View from multiple tables we can simply include multiple tables in the [SELECT](https://www.geeksforgeeks.org/sql/sql-select-query/) statement.
![Student_marks](assets/Student_marks-bf29462f3f.png)
**Query:**
```
CREATE VIEW MarksView ASSELECT StudentDetails.NAME, StudentDetails.ADDRESS, StudentMarks.MARKSFROM StudentDetails, StudentMarksWHERE StudentDetails.NAME = StudentMarks.NAME;
```
To display data of View MarksView:
```
SELECT * FROM MarksView;
```
**Output:**
![Marks_view](assets/Marks_view-f476a683d6.png)
## Managing Views
Here are some common operations used to manage views in SQL:
### 1. Listing all Views in a Database
We can list all the views in a database using the SHOW FULL TABLES statement or by querying the information\_schema tables.
```
USE "database_name";SHOW FULL TABLES WHERE table_type LIKE "%VIEW";
```
**Using information\_schema**
```
SELECT table_nameFROM information_schema.viewsWHERE table_schema = 'database_name';ORSELECT table_schema, table_name, view_definitionFROM information_schema.viewsWHERE table_schema = 'database_name';
```
### 2. Deleting a View
SQL allows us to delete an existing View. We can [delete](https://www.geeksforgeeks.org/sql/sql-delete-statement/) or drop View using the DROP statement.
Syntax:
```
DROP VIEW view_name;
```
**Example:** In this example, we are deleting the View MarksView.
```
DROP VIEW MarksView;
```
### 3. Updating a View Definition
If we want to update the existing data within the view, use the [UPDATE](https://www.geeksforgeeks.org/sql/sql-update-statement/)statement.
```
UPDATE view_nameSET column1 = value1, column2 = value2...., columnN = valueNWHERE [condition];
```
If you want to update the view definition without affecting the data, use the CREATE OR REPLACE VIEW statement. For example, let’s add the `Age` column to the `MarksView`:
```
CREATE OR REPLACE VIEW view_name ASSELECT column1, column2, ...FROM table_nameWHERE condition;
```
**Note:** Not all views can be updated using the UPDATE statement.
### Rules to Update Views in SQL
Certain conditions need to be satisfied to update a view. If any of these conditions are **not** met, the view can not be updated.
1. The SELECT statement which is used to create the view should not include GROUP BY clause or [ORDER BY](https://www.geeksforgeeks.org/sql/sql-order-by/) clause.
2. The SELECT statement should not have the [DISTINCT](https://www.geeksforgeeks.org/mysql/mysql-distinct-clause/) keyword.
3. The View should have all NOT NULL values.
4. The view should not be created using nested queries or complex queries.
5. The view should be created from a single table. If the view is created using multiple tables then we will not be allowed to update the view.
## Advanced Techniques with Views
Here are some advanced ways to work with SQL views:
### 1. Updating Data Through Views
We can use the CREATE OR REPLACE VIEW statement to add or replace fields from a view If we want to update the view MarksView and add the field AGE to this View from StudentDetails Table, we can do this by:
**Example:**
```
UPDATE MarkViewSET ADDRESS = 'Perth'WHERE NAME = 'Liam';
```
If we fetch all the data from MarksView now as:
```
SELECT * FROM MarksView;
```
**Output:**
![Screenshot-2026-06-29-162355](assets/Screenshot-2026-06-29-162355-0872032f41.png)
### **2.** Inserting Data into Views
We can insert a row in a View in the same way as we do in a table. We can use the [INSERT INTO](https://www.geeksforgeeks.org/sql/sql-insert-statement/) statement of SQL to insert a row in a View. In the below example, we will insert a new row in the View Mawhich we have created above in the example of "creating views from a single table".
**Example:**
```
INSERT INTO MarkView(NAME, ADDRESS)VALUES("John","German");
```
If we fetch all the data from DetailsView now as,
```
SELECT * FROM MarkView;
```
**Output:**
![Screenshot-2026-06-29-162524](assets/Screenshot-2026-06-29-162524-67583ec9c5.png)
Markvoiew
### 3. Deleting a row from a View
Deleting rows from a view works the same as deleting from a table. Using the DELETE command removes the row from the base table and the change automatically appears in the view. In this example, we delete the last row fromMarkView added earlier.
**Query:**
```
DELETE FROM MarkViewWHERE NAME="John";
```
If we fetch all the data from MarkView now as,
```
SELECT * FROM MarkView;
```
**Output:**
![Screenshot-2026-06-29-162355](assets/Screenshot-2026-06-29-162355-90ad3ba0db.png)
### 4. WITH CHECK OPTION Clause
The WITH CHECK OPTION clause ensures that any INSERT or UPDATE on an updatable view must satisfy the view’s WHERE condition. If the condition is violated, SQL returns an error. In this example, a view is created with WITH CHECK OPTION to restrict changes that fall outside the defined criteria.
**Query:**
```
CREATE VIEW SampleView ASSELECT S_ID, NAMEFROM  StudentDetailsWHERE NAME IS NOT NULLWITH CHECK OPTION;
```
```
UPDATE SampleView SET NAME = 'Mark' WHERE S_ID = 2;
```
**Output:**
![Mark](assets/Mark-a1ea0ea70e.png)
> The update succeeds only if the modified row still satisfies the view condition (`NAME IS NOT NULL`).
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/sql/sql-views/)

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
