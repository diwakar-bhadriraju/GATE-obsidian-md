---
title: "Attribute Closure in DBMS"
subject: "Database Management System"
topic: "Database Design"
source: "https://www.geeksforgeeks.org/dbms/functional-dependency-and-attribute-closure/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Database Design"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/database-design
---


> [!abstract] Attribute Closure in DBMS
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Database Design`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/functional-dependency-and-attribute-closure/)

---

# Attribute Closure in DBMS

Functional dependency and attribute closure are essential for maintaining data integrity and building effective, organized, and normalized databases. The attribute closure of an attribute set can be defined as a set of attributes that can be functionally determined from it.
- Helps to identify all possible attributes that can be derived from a set of given attributes.
- It can be computationally expensive, especially for large datasets.
- Helps in database design by showing how attributes and tables are related, which can improve query performance.
- It becomes complex to manage as the number of attributes and tables increases.
## Find the Attribute Closure of an Attribute Set
- Add elements of the [attribute](https://www.geeksforgeeks.org/dbms/attributes-in-dbms/) set to the result set.
- Recursively add elements to the result set that can be functionally determined from the elements of the result set.
| STUD\_NO | STUD\_NAME | STUD\_PHONE | STUD\_STATE | STUD\_COUNTRY | STUD\_AGE |
| --- | --- | --- | --- | --- | --- |
| 1 | JOHN | 2025550147 | California | USA | 20 |
| 2 | EMMA | 3035550192 | Texas | USA | 19 |
| 3 | LIAM | 4165550138 | Ontario | Canada | 18 |
| 4 | SOPHIA | 2075550175 | London | UK | 21 |
Using FD set of table 1, [attribute closure](https://www.geeksforgeeks.org/videos/14-attribute-closure/) can be determined as: 
> (STUD\_NO)+= {STUD\_NO, STUD\_NAME, STUD\_PHONE, STUD\_STATE, STUD\_COUNTRY, STUD\_AGE}
> (STUD\_STATE)+ = {STUD\_STATE, STUD\_COUNTRY}
## Find Candidate Keys and Super Keys Using Attribute Closure
- If attribute closure of an attribute set contains all attributes of relation, the attribute set will be [super key](https://www.geeksforgeeks.org/dbms/types-of-keys-in-relational-model-candidate-super-primary-alternate-and-foreign/) of the relation.
- If no subset of this attribute set can functionally determine all attributes of the relation, the set will be candidate key as well. For Example, using FD set of table 1
> (STUD\_NO, STUD\_NAME)+ = {STUD\_NO, STUD\_NAME, STUD\_PHONE, STUD\_STATE, STUD\_COUNTRY, STUD\_AGE} 
>
> (STUD\_NO)+= {STUD\_NO, STUD\_NAME, STUD\_PHONE, STUD\_STATE, STUD\_COUNTRY, STUD\_AGE} 
>
> (STUD\_NO, STUD\_NAME) will be super key but not candidate key because its subset (STUD\_NO)+ is equal to all attributes of the relation. So, STUD\_NO will be a candidate key. 
## Prime and Non-Prime Attributes
Attributes which are parts of any [candidate key](https://www.geeksforgeeks.org/dbms/candidate-key-in-dbms/) of relation are called as prime attribute, others are non-prime attributes. For Example, STUD\_NO in STUDENT relation is prime attribute, others are non-prime attribute. 
> Read more about - [Finding Attribute Closure and Candidate Keys using Functional Dependencies](https://www.geeksforgeeks.org/dbms/finding-attribute-closure-and-candidate-keys-using-functional-dependencies/)
## GATE Questions
**Q.1:** Consider the relation scheme R = {E, F, G, H, I, J, K, L, M, N} and the set of functional dependencies {{E, F} -> {G}, {F} -> {I, J}, {E, H} -> {K, L}, K -> {M}, L -> {N} on R. What is the key for R? (GATE-CS-2014) 
A. {E, F} 
B. {E, F, H} 
C. {E, F, H, K, L} 
D. {E} 
**Solution:**
> Finding attribute closure of all given options, we get: 
> {E,F}+ = {EFGIJ} 
> {E,F,H}+= {EFHGIJKLMN} 
> {E,F,H,K,L}+ = {EFHGIJKLMN} 
> {E}+= {E} 
> {EFH}+ and {EFHKL}+ results in set of all attributes, but EFH is minimal. So it will be candidate key. So correct option is (B). 
**Q.2:** How to check whether an FD can be derived from a given FD set?
**Solution:**
> To check whether an FD A->B can be derived from an FD set F, 
>  
>
> 1. Find (A)+ using FD set F.
> 2. If B is subset of (A)+, then A->B is true else not true.
**Q.3:** In a schema with attributes A, B, C, D and E following set of functional dependencies are given 
{A -> B, A -> C, CD -> E, B -> D, E -> A} 
Which of the following functional dependencies is NOT implied by the above set? (GATE IT 2005) 
A. CD -> AC 
B. BD -> CD 
C. BC -> CD 
D. AC -> BC 
**Solution:**
> Using FD set given in question, 
> (CD)+ = {CDEAB} which means CD -> AC also holds true. 
> (BD)+ = {BD} which means BD -> CD can't hold true. So this FD is no implied in FD set. So (B) is the required option. 
> Others can be checked in the same way. 
**Q.4:** Consider a relation scheme R = (A, B, C, D, E, H) on which the following functional dependencies hold: {A–>B, BC–> D, E–>C, D–>A}. What are the candidate keys of R? [GATE 2005] 
(a) AE, BE 
(b) AE, BE, DE 
(c) AEH, BEH, BCH 
(d) AEH, BEH, DEH 
**Solution:**
> (AE)+ = {ABECD} which is not set of all attributes. So AE is not a candidate key. Hence option A and B are wrong. 
> (AEH)+= {ABCDEH} 
> (BEH)+ = {BEHCDA} 
> (BCH)+= {BCHDA} which is not set of all attributes. So BCH is not a candidate key. Hence option C is wrong. 
> So correct answer is D.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/functional-dependency-and-attribute-closure/)

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
> - [[Introduction to Database Normalization]]
> - [[Lossless Join and Dependency Preserving Decomposition]]
> - [[Lossy and Lossless Decomposition]]
> - [[Minimum relations satisfying 1NF]]
> - [[Multivalued Dependency]]
