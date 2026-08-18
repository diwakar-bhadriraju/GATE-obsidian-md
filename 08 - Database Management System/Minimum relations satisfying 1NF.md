---
title: "Minimum Relations Satisfying First Normal Form (1NF)"
subject: "Database Management System"
topic: "Database Design"
source: "https://www.geeksforgeeks.org/dbms/minimum-relations-satisfying-first-normal-form-1nf/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Database Design"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/database-design
---


> [!abstract] Minimum Relations Satisfying First Normal Form (1NF)
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Database Design`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/minimum-relations-satisfying-first-normal-form-1nf/)

---

# Minimum Relations Satisfying First Normal Form (1NF)

A relation that does not contain any composite or multivalued attribute is said to be in its First Normal Form (1NF). In simple terms, when all attributes in a table are atomic (single-valued), the relation satisfies 1NF.
Key Characteristics of 1NF
1. Each column contains atomic (single) values: no repeating groups or arrays.
2. Each record is unique: a primary key exists.
3. Each attribute (column) stores values of the same data type.
## How to Design a Database
Before we reach the stage of normalization, a proper database design is essential. The process generally involves the following steps:
1. **Requirement Gathering:** Discuss with the stakeholders to identify what data needs to be stored and what relationships exist between data items.
2. **Functional Dependency Analysis:** Identify dependencies among attributes to understand which attribute determines another.
3. **Entity-Relationship (ER) Diagram:** Represent entities, their attributes and relationships using an ER diagram.
4. **Conversion to Relational Model:** Transform the ER diagram into a relational model (tables, keys, relationships).
5. **Apply Normalization Rules:** Start with 1NF and proceed towards higher forms (2NF, 3NF, BCNF, etc.) to remove redundancy and anomalies.
## Understanding 1NF Through Database Design Rules
When designing tables, relationships and participation between entities play a vital role in deciding how many relations (tables) will be created to satisfy 1NF. Below are the general rules that guide the formation of relations:
| Participation | Relationship Type | Resulting Tables |
| --- | --- | --- |
| Total–Total | Any (1:1, 1:N, M:N) | Merge both entities and relationship into one table |
| Total–Partial | M:N or 1:N | Merge the relationship on the total participation side |
| Total–Partial | 1:1 | Merge both entities and the relationship into one table |
| Partial–Partial | M:N | Create three tables – one for each entity and one for the relationship |
| Partial–Partial | 1:N | Merge the relationship on the N-side using foreign key referencing the 1-side |
| Partial–Partial | 1:1 | Merge one entity and the relationship into one table, keep another entity as a separate table |
## Example Scenario
Let’s take a 1:N relationship between two entities:
- E1(A, B, C) -> Primary Key: A
- E2(D, E, F) -> Primary Key: D
- E1 has partial participation
- E2 has total participation
### E1:
| A | B | C |
| --- | --- | --- |
| a1 | b1 | c1 |
| a2 | b2 | c2 |
| a3 | b3 | c3 |
### E2:
| D | E | F |
| --- | --- | --- |
| d1 | e1 | f1 |
| d2 | e2 | f2 |
| d3 | e3 | f3 |
### Relationship (R):
Since E1 -> E2 is a 1:N relationship and E2 has total participation, we can define:
| A | D |
| --- | --- |
| a1 | d1 |
| a1 | d2 |
| a2 | d3 |
## Ways of Merging Two Entities into a Single Table
### Way 1 - Merge Both Entities and Relationship
Not correct., If we merge E1, E2 and R together, the primary key becomes (A, D). But since E1 has partial participation, there will be NULLs for D - violating the rule of no NULLs in a primary key.
| A | B | C | D | E | F |
| --- | --- | --- | --- | --- | --- |
| a1 | b1 | c1 | d1 | e1 | f1 |
| a1 | b1 | c1 | d2 | e2 | f2 |
| a2 | b2 | c2 | d3 | e3 | f3 |
| a3 | b3 | c3 | NULL | NULL | NULL |
> **Note:** Hence, Way-1 violates 1NF because of NULL in primary key.
### Way 2 - Merge Relationship on 1-Side
Also incorrect. Here, the primary key again becomes (A, D) with NULLs.
| A | B | C | D |
| --- | --- | --- | --- |
| a1 | b1 | c1 | d1 |
| a1 | b1 | c1 | d2 |
| a2 | b2 | c2 | d3 |
| a3 | b3 | c3 | NULL |
> **Note:** Again, NULLs violate the rule.
### Way 3 - Merge Relationship on N-Side
This is correct. The table on the N-side (E2) has total participation, so we merge the relationship there.
| D | E | F | A |
| --- | --- | --- | --- |
| d1 | e1 | f1 | a1 |
| d2 | e2 | f2 | a1 |
| d3 | e3 | f3 | a2 |
**Here:**
- Each column has atomic values.
- There are no repeating groups.
- Each record is uniquely identified.
> Hence, this relation satisfies 1NF.
## Special Case: 1:1 Relationship:
- In a 1:1 relationship, both sides have at most one matching tuple.
- Hence, merging entities and the relationship into a single table will not create composite keys with NULLs.
- Therefore, it is valid to merge them into one relation.
## Why Total Participation Allows Merging
- When both sides have total participation, even if a composite key exists, it will never contain NULLs, because every entity must participate in the relationship.
- Thus, merging entities and the relationship together into one table still satisfies 1NF.
> **Note:** You can follow the same procedure as stated above to establish all the results.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/minimum-relations-satisfying-first-normal-form-1nf/)

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
> - [[Multivalued Dependency]]
