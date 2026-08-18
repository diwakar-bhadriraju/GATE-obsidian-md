---
title: "Types of Functional dependencies in DBMS"
subject: "Database Management System"
topic: "Database Design"
source: "https://www.geeksforgeeks.org/dbms/types-of-functional-dependencies-in-dbms/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Database Design"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/database-design
---


> [!abstract] Types of Functional dependencies in DBMS
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Database Design`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/types-of-functional-dependencies-in-dbms/)

---

# Types of Functional dependencies in DBMS

A functional dependency occurs when one attribute uniquely determines another attribute within a relation. There are the following types of functional dependencies.
### 1. Trivial Functional Dependency
In Trivial Functional Dependency, a dependent is always a subset of the determinant. i.e., If X → Y and Y is the subset of X, then it is called a trivial functional dependency.
Symbolically: A→B is a trivial [functional dependency](https://www.geeksforgeeks.org/dbms/what-is-functional-dependency-in-dbms/) if B is a subset of A.
The following dependencies are also trivial: A→A & B→B
**Example 1** :
- ABC -> AB
- ABC -> A
- ABC -> ABC
**Example 2:**
| roll\_no | name | age |
| --- | --- | --- |
| 42 | abc | 17 |
| 43 | pqr | 18 |
| 44 | xyz | 18 |
Here, {roll\_no, name} → name is a trivial functional dependency, since the dependent name is a subset of determinant set {roll\_no, name}. Similarly, roll\_no → roll\_no is also an example of trivial functional dependency. 
### 2. Non-trivial Functional Dependency
In Non-trivial functional dependency, the dependent is strictly not a subset of the determinant. i.e. If X → Y and Y is not a subset of X, then it is called Non-trivial functional dependency.
**Example 1 :**
- Id -> Name
- Name -> DOB
**Example 2:**
| **roll\_no** | name | age |
| --- | --- | --- |
| 42 | abc | 17 |
| 43 | pqr | 18 |
| 44 | xyz | 18 |
Here, roll\_no → name is a non-trivial functional dependency, since the dependent name is not a subset of determinant roll\_no. Similarly, {roll\_no, name} → age is also a non-trivial functional dependency, since age is not a subset of {roll\_no, name} 
### **3. Semi Non Trivial Functional Dependencies**
A semi non-trivial functional dependency occurs when part of the dependent attribute (right-hand side) is included in the determinant (left-hand side), but not all of it. This is a middle ground between trivial and non-trivial functional dependencies. X -> Y is called semi non-trivial when X intersect Y is not NULL. 
**Example:**
Consider the following table:
| **Student\_ID** | **Course\_ID** | **Course\_Name** |
| --- | --- | --- |
| 101 | CSE101 | Computer Science |
| 102 | CSE102 | Data Structures |
| 103 | CSE101 | Computer Science |
#### Functional Dependency:
{StudentID,CourseID}→CourseID
This is semi non-trivial because:
- Part of the dependent attribute (`Course_ID`) is already included in the determinant (`{Student_ID, Course_ID}`).
- However, the dependency is not completely trivial because {StudentID}→CourseID is not implied directly.
### 4. Multivalued Functional Dependency
In Multivalued functional dependency, entities of the dependent set are not dependent on each other. i.e. If a → {b, c} and there exists no functional dependency between b and c, then it is called a multivalued functional dependency.
**Example:**
| bike\_model | color | accessory |
| --- | --- | --- |
| tu1001 | Black | Helmet |
| tu1001 | Black | Gloves |
| tu1001 | Red | Helmet |
| tu1001 | Red | Gloves |
In this table:
- X = bike\_model
- Y = color
- Z = accessory
For each bike model (`bike_model`):
1. There is a group of colors (color) and a group of accessories (accessory).
2. The colors do not depend on the accessory, and the accessories do not depend on the colors. They are independent of each other.
3. The sets of color and accessory are linked only to bike\_model.
That’s what makes it a [multivalued dependency.](https://www.geeksforgeeks.org/dbms/multivalued-dependency-mvd-in-dbms/)
In this case, these two columns (color and accessory) are said to be multivalued dependent on bike\_model.These dependencies can be represented like this:
```
bike_model →→ color
bike_model →→ accessory
```
### 5. Transitive Functional Dependency
In transitive functional dependency, dependent is indirectly dependent on determinant. i.e. If a → b & b → c, then according to axiom of transitivity, a → c. This is a transitive functional dependency.
**Example:**
| enrol\_no | name | dept | building\_no |
| --- | --- | --- | --- |
| 42 | abc | CO | 4 |
| 43 | pqr | EC | 2 |
| 44 | xyz | IT | 1 |
| 45 | abc | EC | 2 |
Here, enrol\_no → dept and dept → building\_no. Hence, according to the axiom of transitivity, enrol\_no → building\_no is a valid functional dependency. This is an indirect functional dependency, hence called Transitive functional dependency.
### **6. Fully Functional Dependency**
In [full functional dependency](https://www.geeksforgeeks.org/dbms/fully-functional-dependency-in-dbms/) an attribute or a set of attributes uniquely determines another attribute or set of attributes. If a relation R has attributes X, Y, Z with the dependencies X->Y and X->Z which states that those dependencies are fully functional.
### 7. Partial Functional Dependency
In [partial functional dependency](https://www.geeksforgeeks.org/dbms/partial-dependency-in-dbms/) a non key attribute depends on a part of the composite key, rather than the whole key. If a relation R has attributes X, Y, Z where X and Y are the composite key and Z is non key attribute. Then X->Z is a partial functional dependency in RDBMS.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/types-of-functional-dependencies-in-dbms/)

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
> - [[Introduction to Database Normalization]]
> - [[Lossless Join and Dependency Preserving Decomposition]]
> - [[Lossy and Lossless Decomposition]]
> - [[Minimum relations satisfying 1NF]]
