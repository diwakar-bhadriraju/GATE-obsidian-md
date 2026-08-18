---
title: "Types of Schedules Based on Recoverability in DBMS"
subject: "Database Management System"
topic: "Transactions and Concurrency Control"
source: "https://www.geeksforgeeks.org/dbms/types-of-schedules-based-recoverability-in-dbms/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Transactions and Concurrency Control"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/transactions-and-concurrency-control
---


> [!abstract] Types of Schedules Based on Recoverability in DBMS
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Transactions and Concurrency Control`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/types-of-schedules-based-recoverability-in-dbms/)

---

# Types of Schedules Based on Recoverability in DBMS

In a Database Management System (DBMS), multiple transactions often run at the same time, and their execution order is called a schedule. It is important to ensure that these schedules do not cause data loss or inconsistencies, especially if a failure occurs.
- A recoverable schedule allows the system to safely roll back changes if a transaction fails.
- In such schedules, a transaction commits only after the transactions whose data it has read have committed.
- Some schedules may cause unwanted rollbacks, which can lead to cascading failures.
- To avoid these problems, schedules are classified based on recoverability.
![420851501](assets/420851501-f27444f059.webp)
### **1. Recoverable Schedule**
A [recoverable schedule](https://www.geeksforgeeks.org/dbms/recoverability-in-dbms/) ensures that the database can return to a consistent state after a transaction failure.
In this type of schedule:
1. A transaction cannot use (read) data updated by another transaction until that transaction commits.
2. If a transaction fails before committing, all its changes must be rolled back, and any other transactions that have used its uncommitted data must also be rolled back.
Recoverable Schedule prevents data inconsistencies and ensures that no transaction commits based on unverified changes, making recovery easier and safer.
**Example:**
```
S1: R1(x), W1(x), R2(x), R1(y), R2(y), W2(x), W1(y), C1, C2;
```
The given schedule follows the order of **Ti->Tj => C1->C2**. Transaction T1 is executed before T2 hence there is no chance of conflict occurring. R1(x) appears before W1(x) and transaction T1 is committed before T2 i.e. completion of the first transaction performed the first update on data item x, hence given schedule is recoverable. 
Let us see an example of an unrecoverable schedule to clear the concept more.
```
S2: R1(x), R2(x), R1(z), R3(x), R3(y), W1(x), W3(y), R2(y), W2(z), W2(y), C1, C2, C3;
```
**Ti->Tj => C2->C3** but W3(y) executed before W2(y) which leads to conflicts thus it must be committed before the T2 transaction. So given schedule is unrecoverable. if **Ti->Tj => C3->C2** is given in the schedule then it will become a recoverable schedule. 
**Example:**
![420851497](assets/420851497-763b5e480b.webp)
Dirty Read Problem
> **Note:** A committed transaction should never be rollback. It means that reading value from uncommitted transaction and commit it will enter the current transaction into inconsistent or unrecoverable state this is called **Dirty Read problem**. 
### **2. Cascadeless Schedule**
A [cascade-less schedule](https://www.geeksforgeeks.org/dbms/cascadeless-in-dbms/) ensures that if one transaction fails, it does not cause multiple other transactions to roll back.
A transaction is not allowed to use (read) uncommitted data from another transaction until that transaction is fully committed. This prevents [cascading rollbacks](https://www.geeksforgeeks.org/dbms/cascading-rollback/), where a failure in one transaction forces many others to undo their changes. If a transaction fails before committing, only its own changes are undone, but other transactions that have read its data do not need to roll back, making the recovery process simpler and more efficient.
**Example:**
```
S3: R1(x), R2(z), R3(x), R1(z), R2(y), R3(y), W1(x), C1, W2(z), W3(y), W2(y), C3, C2;
```
In this schedule W3(y) and W2(y) overwrite conflicts and there is no read, therefore given schedule is cascade less schedule. 
![420851498](assets/420851498-fa42d51399.webp)
Cascadeless Schedule
> **Special Case:** A committed transaction desired to abort. As given below all the transactions are reading committed data hence it's cascadeless schedule. 
### **3. Strict Schedule**
A schedule is strict if it is both recoverable and cascadeless.
A strict schedule ensures strong data consistency by following two key rules:
1. A transaction cannot use (read) uncommitted data from another transaction until that transaction commits.
2. A transaction cannot update (write) the same data modified by another transaction until the first one commits.
This means that if a transaction fails before committing, all its changes must be undone (rolled back), and any other transactions that used its uncommitted data must also be rolled back.
Strict schedule helps in maintaining a reliable and consistent database by preventing data conflicts and minimizing errors.
**Example:**
```
S4: R1(x), R2(x), R1(z), R3(x), R3(y), W1(x), C1, W3(y), C3, R2(y), W2(z), W2(y), C2;
```
In this schedule, no read-write or write-write conflict arises before committing hence its strict schedule: 
![420851499](assets/420851499-3e63064e2f.webp)
Strict Schedule
**Cascading Abort:** Cascading Abort can also be rollback. If transaction T1 aborts as T2 read data that is written by T1 it is not committed. Hence its cascading rollback. 
**Example:** 
![420851496](assets/420851496-8ee5319ee6.webp)
Cascading Abort
## Relation Between Strict, Cascadeless and Recoverable schedules
In [Database Management Systems (DBMS)](https://www.geeksforgeeks.org/dbms/introduction-of-dbms-database-management-system-set-1/), the schedules can be categorized based on their recoverability. Recoverability refers to the ability to recover the database to a consistent state after a transaction failure.  
- Strict schedules are all recoverable and cascade schedules.
- All cascade-less schedules are recoverable.
![420851500](assets/420851500-9f42aa5a0b.webp)
Venn Diagram of Schedule
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/types-of-schedules-based-recoverability-in-dbms/)

## GATE CS

- Subject: Database Management System
- Topic: Transactions and Concurrency Control

> [!note] Related notes
>
> - [[ACID Properties in DBMS]]
> - [[Cascadeless in DBMS]]
> - [[Categories of Two Phase Locking]]
> - [[Concurrency Control Techniques]]
> - [[Conflict Serializability]]
> - [[Database Recovery Techniques]]
> - [[Deadlock in DBMS]]
> - [[Graph Based Protocol]]
> - [[How to test if two schedules are View Equal or not]]
> - [[Implementation of Locking in DBMS]]
