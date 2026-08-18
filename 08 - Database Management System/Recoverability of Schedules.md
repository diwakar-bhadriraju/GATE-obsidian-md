---
title: "Recoverability in DBMS"
subject: "Database Management System"
topic: "Transactions and Concurrency Control"
source: "https://www.geeksforgeeks.org/dbms/recoverability-in-dbms/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Transactions and Concurrency Control"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/transactions-and-concurrency-control
---


> [!abstract] Recoverability in DBMS
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Transactions and Concurrency Control`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/recoverability-in-dbms/)

---

# Recoverability in DBMS

Recoverability ensures that after a failure, the database can restore a consistent state by keeping committed changes and undoing uncommitted ones. It uses logs to redo or undo actions, preventing data loss and maintaining integrity.
**There are several levels of recoverability that can be supported by a database system:**
- **No-Undo Logging**: Only saves committed transactions; can't undo uncommitted ones.
- **Undo Logging**: Can undo uncommitted transactions but may lose some committed updates.
- **Redo Logging**: Can redo committed transactions to ensure durability.
- **Undo-Redo Logging**: Supports both undo and redo, ensuring full recovery and consistency.
Overall, recoverability is a crucial property of database systems, as it ensures that data is consistent and durable even in the event of failures or errors. It is important for database administrators to understand the level of recoverability provided by their system and to configure it appropriately to meet their application's requirements.
![schedules_types](assets/schedules_types-8e63b04507.webp)
## **Recoverable Schedules**
A recoverable schedule ensures a transaction commits only after the transactions it depends on have committed. This avoids inconsistencies and helps the database recover correctly after failures.
**Example 1:**
Consider the following schedule involving two transactions T1 and T2.
| T1 | T2 |
| --- | --- |
| R(A) |  |
| W(A) |  |
|  | W(A) |
|  | R(A) |
| commit |  |
|  | commit |
This is a recoverable schedule since T1 commits before T2, that makes the value read by T2 correct.
**Example 2:**
> S1: R1(x), W1(x), R2(x), R1(y), R2(y),W2(x), W1(y), C1, C2;
![cascade_3](assets/cascade_3-000be86c59.webp)
- T2 reads uncommitted data from T1 (`R2(x)` depends on `W1(x)`), but T2 commits only after T1 commits.
- The schedule is recoverable.
> Read more about [Types of Schedule Based on Recoverability](https://www.geeksforgeeks.org/dbms/types-of-schedules-based-recoverability-in-dbms/).
## **Irrecoverable Schedules**
An irrecoverable schedule occurs when a transaction commits after performing a dirty read—i.e., reading data written by another uncommitted transaction—and the original transaction later fails or is rolled back. This leads to inconsistency, as the committed transaction has used invalid data.
For example, if T2 reads and commits a value written by T1, but T1 later fails, the system cannot undo T2 since it has already committed. This makes the schedule irrecoverable. To avoid this, a transaction should not commit before the transactions it depends on have committed.
| T1 Operation | T1 Buffer | T2 Operation | T2 Buffer | Database | Notes |
| --- | --- | --- | --- | --- | --- |
| R(A) | A = 5000 |  |  | A = 5000 | T1 reads original value |
| A = A − 100 | A = 4900 |  |  | A = 5000 | Update in T1 buffer only |
| W(A) | A = 4900 |  |  | A = 4900 | T1 writes uncommitted value to DB |
|  |  | R(A) | A = 4900 | A = 4900 | T2 reads **dirty** value from T1 |
|  |  | A = A + 500 | A = 5400 | A = 4900 | T2 updates its buffer |
|  |  | W(A) | A = 5400 | A = 5400 | T2 writes dirty value |
|  |  | **Commit** | — | A = 5400 | **T2 commits before T1 → Dangerous** |
| **Failure Occurs** | — | — | — | A = 5400 | T1 crashes before committing |
| **Rollback Needed** | — | — | — | — | But **T2 committed**, so rollback impossible |
## **Recoverable with Cascading Rollback**
A **recoverable schedule with cascading rollback** occurs when a **failure in one transaction (Ti)** causes other dependent transactions (Tj) to also **roll back**, but no committed transaction is affected. Since **Tj reads data written by Ti** and has **not yet committed**, it can be safely rolled back when Ti fails.
This preserves recoverability, as all dependencies commit in the correct order. Although multiple rollbacks may happen, the **database remains consistent**. Such a schedule follows the rule: **Tj commits only after Ti commits**.
| T1 Operation | T1 Buffer | T2 Operation | T2 Buffer | Database | Notes |
| --- | --- | --- | --- | --- | --- |
| R(A) | A = 5000 |  |  | A = 5000 | T1 reads original value |
| A = A − 100 | A = 4900 |  |  | A = 5000 | Uncommitted update in T1 buffer |
| W(A) | A = 4900 |  |  | A = 4900 | T1 writes **uncommitted** value |
|  |  | R(A) | A = 4900 | A = 4900 | T2 reads T1's **uncommitted (dirty) value** |
| **Failure Occurs** | — | — | — | A = 4900 | T1 fails before commit |
| **Rollback (T1)** | — |  |  | A = 5000 | DB restored to old value |
|  |  | **Rollback (T2)** | — | A = 5000 | Cascading rollback since T2 depended on T1 |
| R(A) | A = 5000 |  |  | A = 5000 | T1 restarts clean |
| A = A − 100 | A = 4900 |  |  | A = 5000 | T1 buffer update again |
| W(A) | A = 4900 |  |  | A = 4900 | T1 writes to DB |
| **Commit** | — |  |  | A = 4900 | T1 commits → value now safe |
|  |  | R(A) | A = 4900 | A = 4900 | T2 reads **committed** value this time |
|  |  | A = A + 500 | A = 5400 | A = 4900 | T2 updates buffer |
|  |  | W(A) | A = 5400 | A = 5400 | T2 writes |
|  |  | **Commit** | — | A = 5400 | Safe commit (after T1) |
## **Cascadeless Recoverable Rollback**
A cascadeless recoverable schedule is a type of transaction schedule where transactions are both recoverable and free from cascading rollbacks. In this schedule, a transaction (Tj) reads data written by another transaction (Ti) only after Ti has committed.
This ensures that if Ti fails, no other transaction depends on its uncommitted changes, avoiding the need for cascading rollbacks. The schedule maintains consistency and simplifies recovery by preventing dirty reads. The key rule is: Tj reads Ti’s data only after Ti commits, ensuring both recoverability and cascadelessness.
| T1 Operation | T1 Buffer | T2 Operation | T2 Buffer | Database | Notes |
| --- | --- | --- | --- | --- | --- |
| R(A) | A = 5000 |  |  | A = 5000 | T1 reads original value |
| A = A − 100 | A = 4900 |  |  | A = 5000 | T1 updates buffer only |
| W(A) | A = 4900 |  |  | A = 4900 | T1 writes to DB |
| **Commit** | — |  |  | A = 4900 | T1 commits → value now safe |
|  |  | R(A) | A = 4900 | A = 4900 | T2 reads **only committed** value (safe) |
|  |  | A = A + 500 | A = 5400 | A = 4900 | T2 updates buffer |
|  |  | W(A) | A = 5400 | A = 5400 | T2 writes to DB |
|  |  | **Commit** | — | A = 5400 | T2 commits safely |
### **Capabilities of Recoverability in DBMS**
1. **Atomicity**: Transactions in a DBMS are atomic, meaning they either complete entirely or are rolled back to their original state in case of a failure. This ensures that the database remains in a consistent state at all times.
2. **Durability**: Once a transaction is committed, its changes are permanently saved to the database. Even in the event of a failure, these changes are retained, ensuring the database can be restored to its last consistent state.
3. **Logging**: A DBMS maintains a transaction log that records all changes made to the database and the transactions responsible for those changes. In case of a failure, this log is used to recover the database to a consistent state.
4. **Checkpointing**: Checkpoints mark a specific point in time where the DBMS saves the current state of the database. This reduces recovery time after a failure, as only the transactions occurring after the last checkpoint need to be rolled back or replayed.
5. **Recovery Manager**: The recovery manager is a component of the DBMS responsible for restoring the database to a consistent state after a failure. It uses logs and checkpoints to identify and handle transactions that need to be undone or redone.
6. **Media Recovery**: Media recovery deals with recovering the database from storage failures, such as a hard drive crash. This involves restoring the database from backups and using transaction logs to bring it up to date.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/recoverability-in-dbms/)

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
