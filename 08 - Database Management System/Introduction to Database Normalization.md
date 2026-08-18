---
title: "Introduction to Database Normalization"
subject: "Database Management System"
topic: "Database Design"
source: "https://www.geeksforgeeks.org/dbms/introduction-of-database-normalization/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Database Design"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/database-design
---


> [!abstract] Introduction to Database Normalization
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Database Design`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/introduction-of-database-normalization/)

---

# Introduction to Database Normalization

Normalization is an important process in database design that helps improve the database's efficiency, consistency, and accuracy. It makes it easier to manage and maintain the data and ensures that the database is adaptable to changing business needs.
- It is the process of organizing the attributes of the database to reduce or eliminate data redundancy (having the same data in different places), which otherwise unnecessarily increases the size of the database.
- Data redundancy leads to inconsistency problems during insert, delete, and update operations, making data management difficult.
- Normalization involves splitting a table into multiple tables, which must be linked each time a query requires data from the split tables.
- **Before Normalization:** The table is prone to redundancy and anomalies (insertion, update, and deletion).
- **After Normalization:** The data is divided into logical tables to ensure consistency, avoid redundancy and remove anomalies making the database efficient and reliable.
## Need of Normalization
The primary objective for normalizing the relations is to eliminate the below [anomalies](https://www.geeksforgeeks.org/dbms/anomalies-in-relational-model/). Failure to reduce anomalies results in data redundancy, which may threaten data integrity and cause additional issues as the database increases.
- **Insertion Anomalies:** Insertion anomalies occur when it is not possible to insert data into a database because the required fields are missing or because the data is incomplete. For example, if a database requires that every record has a primary key, but no value is provided for a particular record, it cannot be inserted into the database.
- **Deletion anomalies:** Deletion anomalies occur when deleting a record from a database and can result in the unintentional loss of data. For example, if a database contains information about customers and orders, deleting a customer record may also delete all the orders associated with that customer.
- **Update anomalies:**Updation of anomalies occur when modifying data in a database and can result in inconsistencies or errors. For example, if a database contains information about employees and their salaries, updating an employee’s salary in one record but not in all related records could lead to incorrect calculations and reporting.
## Features of Database Normalization
- **Elimination of Data Redundancy:** One of the main features of normalization is to eliminate the data redundancy that can occur in a database. Data redundancy refers to the repetition of data in different parts of the database. Normalization helps in reducing or eliminating this redundancy, which can improve the efficiency and consistency of the database.
- **Ensuring Data Consistency:** Normalization helps in ensuring that the data in the database is consistent and accurate. By eliminating redundancy, normalization helps in preventing inconsistencies and contradictions that can arise due to different versions of the same data.
- **Simplification of Data Management:** Normalization simplifies the process of managing data in a database. By breaking down a complex data structure into simpler tables, normalization makes it easier to manage the data, update it, and retrieve it.
- **Improved Database Design:** Normalization helps in improving the overall design of the database. By organizing the data in a structured and systematic way, normalization makes it easier to design and maintain the database. It also makes the database more flexible and adaptable to changing business needs.
- **Standardization:** Normalization helps in standardizing the data in the database. By organizing the data into tables and defining relationships between them, normalization helps in ensuring that the data is stored in a consistent and uniform manner.
## Normal Forms in DBMS
| Normal Forms | Description of Normal Forms |
| --- | --- |
| **First Normal Form (1NF)** | A relation is in [first normal form](https://www.geeksforgeeks.org/dbms/first-normal-form-1nf/) if every attribute in that relation is single-valued attribute. |
| **Second Normal Form (2NF)** | A relation that is in First Normal Form and every non-primary-key attribute is fully functionally dependent on the primary key, then the relation is in [Second Normal Form (2NF).](https://www.geeksforgeeks.org/dbms/second-normal-form-2nf/) |
| **Third Normal Form (3NF)** | A relation is in the [third normal form](https://www.geeksforgeeks.org/dbms/third-normal-form-3nf/), if there is no transitive dependency for non-prime attributes as well as it is in the second normal form. A relation is in 3NF if at least one of the following conditions holds in every non-trivial function dependency X –> Y.   - X is a super key. - Y is a prime attribute (each element of Y is part of some candidate key). |
| **Boyce-Codd Normal Form (BCNF)** | For BCNF the relation should satisfy the below conditions   - The relation should be in the 3rd [Normal Form](https://www.geeksforgeeks.org/dbms/normal-forms-in-dbms/). - X should be a super-key for every functional dependency (FD) X−>Y in a given relation. |
| **Fourth Normal Form (4NF)** | A relation R is in [4NF](https://www.geeksforgeeks.org/dbms/introduction-of-4th-and-5th-normal-form-in-dbms/) if and only if the following conditions are satisfied:    - It should be in the [Boyce-Codd Normal Form (BCNF)](https://www.geeksforgeeks.org/dbms/boyce-codd-normal-form-bcnf/). - The table should not have any Multi-valued Dependency. |
| **Fifth Normal Form (5NF)** | A relation R is in [5NF](https://www.geeksforgeeks.org/dbms/what-is-fifth-normal-form-5nf-in-dbms/) if and only if it satisfies the following conditions:   - R should be already in 4NF. - It cannot be further non loss decomposed (join dependency) |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/introduction-of-database-normalization/)

## GATE CS

- Subject: Database Management System
- Topic: Database Design

> [!note] Related notes
>
> - [[Canonical Cover]]
> - [[DBMS How to find the highest normal form of a relation]]
> - [[Dependency Preserving Decomposition]]
> - [[Equivalence of Functional Dependencies]]
> - [[Finding Attribute Closure and Candidate Keys using Functional Dependencies]]
> - [[Functional Dependency and Attribute Closure]]
> - [[Lossless Join and Dependency Preserving Decomposition]]
> - [[Lossy and Lossless Decomposition]]
> - [[Minimum relations satisfying 1NF]]
> - [[Multivalued Dependency]]
