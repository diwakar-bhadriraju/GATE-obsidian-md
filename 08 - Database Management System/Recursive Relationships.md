---
title: "Recursive Relationships in ER diagrams"
subject: "Database Management System"
topic: "ER-Model"
source: "https://www.geeksforgeeks.org/dbms/recursive-relationships-in-er-diagrams/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/ER-Model"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/er-model
---


> [!abstract] Recursive Relationships in ER diagrams
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `ER-Model`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/recursive-relationships-in-er-diagrams/)

---

# Recursive Relationships in ER diagrams

A relationship between two entities of the same entity set is called a recursive relationship or repeated relationship. Here, the same entity set participates more than once in a relationship type with a different role for each instance.
- To represent a recursive relationship in an ER diagram, we use a self-join, which is a join between a table and itself.
- The self-join involves creating two instances of the same entity and connecting them with a relationship, one is considered as the child and the other as the parent.
- Often used to represent hierarchies or networks, where an entity can be connected to other entities of the same type.
![2](assets/2-2a5777a7dd.webp)
Recursive Relationship
> **Example:** In an organizational chart, an employee can have a relationship with other employees who are also in a managerial position. Similarly, in a social network, a user can have a relationship with other users who are their friends.
## Cardinality in Recursive Relationship
We use cardinality constraints to specify the number of instances of the entity that can participate in the relationship. For example, in an organizational chart, an employee can have many subordinates, but each subordinate can only have one manager. This is represented as a one-to-many (1:N) relationship between the employee entity and itself. Let us suppose that we have an employee table, where:
- A manager supervises a subordinate.
- Every employee can have a supervisor except the CEO
- There can be at most one boss for each employee.
- One employee may be the boss of more than one employee.
![1](assets/1-c68f6eb5d6.webp)
Employee table Recursive Relationship
Here REPORTS\_TO is a recursive relationship on the Employee entity type where each Employee plays two roles: Supervisor & Subordinate. Here, "Supervisor" and "Subordinate" are referred to as role names. The degree of the REPORTS\_TO relationship is 1 (i.e., a unary relationship)
- The minimum cardinality of the Supervisor role is 0 because the lowest-level employee (e.g., a subordinate) may not manage anyone.
- The maximum cardinality of the Supervisor role is N, as an employee can manage many subordinates.
### For the Subordinate role:
- The minimum cardinality is 0, as the CEO, for example, is not a subordinate to anyone.
- The maximum cardinality is 1, as a subordinate can have only one manager.
> **Note:** In this case, neither of the participants has total participation since the minimum cardinality for both roles is 0. Therefore, the relationship is represented with a single line (not a double line) in the ER diagram
## Implementing a Recursive Relationship
To implement a recursive relationship, a foreign key of the employee’s manager number would be held in each employee record. A sample table would look something like this:- 
> Emp\_entity( Emp\_no,Emp\_Fname, Emp\_Lname, Emp\_DOB, Emp\_NI\_Number, Manager\_no);
>
> Manager no - (this is the employee no of the employee's manager)
### Example:
> CREATE TABLE employee (
>  id INT PRIMARY KEY,
>  name VARCHAR(50),
>  manager\_id INT,
>  FOREIGN KEY (manager\_id) REFERENCES employee(id)
> );
Here, the employee table has a foreign key column called manager\_id that references the id column of the same employee table. This allows you to create a recursive relationship where an employee can have a manager who is also an employee.
### Sample Employee Table Structure:
| Emp\_no | Emp\_Fname | Emp\_Lname | Emp\_DOB | Emp\_NI\_Number | Manager\_no |
| --- | --- | --- | --- | --- | --- |
| 1 | John | Doe | 1980-01-01 | 123456789 | NULL |
| 2 | Jane | Smith | 1990-05-15 | 987654321 | 1 |
| 3 | Bob | Johnson | 1985-03-22 | 112233445 | 1 |
**In this table:**
- Manager\_no refers to the Emp\_no of the employee’s manager.
- The CEO (employee 1 in this example) does not have a manager, hence their Manager\_no is NULL.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/recursive-relationships-in-er-diagrams/)

## GATE CS

- Subject: Database Management System
- Topic: ER-Model

> [!note] Related notes
>
> - [[Enhanced ER Model]]
> - [[Introduction to ER Model]]
> - [[Mapping from ER Model to Relational Model]]
> - [[Minimization of ER Diagram]]
> - [[ACID Properties in DBMS]]
> - [[Advantages of DBMS over File system]]
> - [[Anomalies in Relational Model]]
> - [[Canonical Cover]]
> - [[Cascadeless in DBMS]]
> - [[Categories of Two Phase Locking]]
