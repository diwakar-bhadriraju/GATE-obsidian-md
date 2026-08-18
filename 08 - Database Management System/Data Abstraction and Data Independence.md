---
title: "Data Abstraction and Data Independence"
subject: "Database Management System"
topic: "Introduction"
source: "https://www.geeksforgeeks.org/dbms/data-abstraction-and-data-independence/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Introduction"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/introduction
---


> [!abstract] Data Abstraction and Data Independence
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Introduction`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/data-abstraction-and-data-independence/)

---

# Data Abstraction and Data Independence

A Database Management System (DBMS) is designed to efficiently store, organize and retrieve large volumes of data. However, because of the complexity of databases, it is essential to simplify how users interact with the system. To achieve this,
- DBMS uses a concept called data abstraction, which hides unnecessary details and presents only relevant information to different users.
- This simplification also enables data independence, ensuring that changes in one level of the database do not affect other levels.
## Data Abstraction
The main goal of data abstraction is to simplify database management and achieve data independence. It allows users to work with data without worrying about how it is stored or maintained internally, reducing complexity and improving efficiency. There are mainly three levels of data abstraction in a DBMS:
![frame_3175](assets/frame_3175-f91169f8b5.webp)
Data Abstraction
1. Physical or Internal Level
2. Logical or Conceptual Level
3. View or External Level
### 1. Physical or Internal Level
- This is the lowest level of abstraction that deals with how data is physically stored in memory.
- It defines file organization techniques (like hashing or B+ trees) and access methods (such as sequential or random access).
- Details such as block size, memory allocation and storage paths are managed at this level.
- These physical details are hidden from the end users.
> **Example:** When storing employee details, the user doesn’t need to know how many memory blocks are used or where the data is stored on disk.
### 2. Logical or Conceptual Level
- This level describes what data is stored in the database and the relationships among those data.
- It represents the entire database using simple logical structures like tables, attributes and relationships.
- The logical level provides physical data independence, meaning that changes at the physical level do not affect this level.
- Database administrators primarily work at this level to define schemas and relationships.
> **Example:** At this level, employee details are represented as tables with fields such as Emp\_ID, Emp\_Name and Manager\_ID.
### 3. View or External Level
- This is the highest level of abstraction, where users interact directly with the database.
- It provides different views of the same data for different users, ensuring security and simplicity.
- Users access data through Graphical User Interfaces (GUI) or Command-Line Interfaces (CLI) without dealing with the underlying complexity.
> **Example:** A user may view only the `Emp_Name` and `Department` columns, while other details remain hidden.
## Data Independence
Data Independence is the property that allows changes in the database schema at one level without requiring changes at the next higher level. It helps separate data from the programs that use it, thereby improving flexibility and minimizing maintenance effort.
![Data-Abstraction-and-Data-Independence](assets/Data-Abstraction-and-Data-Independence-ae787f4357.webp)
Data Independence
### Example of Data Independence
Consider a database storing customer information:
- **Physical level:** Stores data in files and manages memory blocks.
- **Logical level:** Represents customers as a table with attributes like `Customer_ID`, `Name` and `Phone`.
- **View level:** A user may see only `Name` and `Phone` fields.
> **Note:** If the storage method changes (physical level) or a new column `Email` is added (logical level), the user view remains unaffected - demonstrating data independence.
There are two types of data independence:
1. Physical Data Independence
2. Logical Data Independence
### 1. Physical Data Independence
- It refers to the ability to change the physical storage of data without affecting the logical schema.
- Changes like altering indexes, switching file organization methods or upgrading storage devices do not affect the conceptual structure of the database.
**Examples:**
- Changing from sequential file organization to hashing.
- Using a new storage device or modifying access paths.
> **Benefit:** It allows performance optimizations at the physical level without modifying higher-level structures.
### 2. Logical Data Independence
- It refers to the ability to modify the logical schema (tables, attributes, relationships) without affecting the user views or application programs.
- Users can continue to access data without changes in their queries even if new fields are added or relationships modified in the conceptual schema.
**Examples:**
- Adding or deleting attributes in a table.
- Changing the relationship between entities.
> **Benefit:** **,** It allows the database to evolve without disturbing existing applications.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/data-abstraction-and-data-independence/)

## GATE CS

- Subject: Database Management System
- Topic: Introduction

> [!note] Related notes
>
> - [[Advantages of DBMS over File system]]
> - [[Challenges of Database Security in DBMS]]
> - [[DBMS 2-Level, 3-Level Architecture]]
> - [[DBMS 3-Tier Architecture]]
> - [[Introduction to Database Management System]]
> - [[Need for DBMS]]
> - [[ACID Properties in DBMS]]
> - [[Anomalies in Relational Model]]
> - [[Canonical Cover]]
> - [[Cascadeless in DBMS]]
