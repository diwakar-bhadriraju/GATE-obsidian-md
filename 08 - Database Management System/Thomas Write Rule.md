---
title: "Thomas Write Rule in DBMS"
subject: "Database Management System"
topic: "Transactions and Concurrency Control"
source: "https://www.geeksforgeeks.org/dbms/thomas-write-rule-in-dbms/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Transactions and Concurrency Control"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/transactions-and-concurrency-control
---


> [!abstract] Thomas Write Rule in DBMS
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Transactions and Concurrency Control`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/thomas-write-rule-in-dbms/)

---

# Thomas Write Rule in DBMS

The Thomas Write Rule (TWR) is an extension of the Basic Timestamp Ordering (TO) Protocol used for concurrency control in Database Management Systems (DBMS).
- **Developed by:** R. H. Thomas (1979)
- **Type:** Timestamp-based concurrency control
- **Goal:** Reduce unnecessary rollbacks while maintaining view serializability
> **Note:** It allows higher concurrency by ignoring obsolete writes instead of aborting transactions, as long as doing so doesn’t affect the final database state.
## Basic Idea
In the Basic Timestamp Ordering (TO) protocol, if a transaction tries to write an outdated value, it is aborted. However, in the Thomas Write Rule, instead of aborting, the outdated write is ignored, allowing the transaction to continue.
> **Note:** This helps avoid unnecessary aborts and increases system throughput.
### Notations:
| Symbol | Meaning |
| --- | --- |
| TS(T) | Timestamp of transaction T |
| R\_TS(X) | Timestamp of the last read on data item X |
| W\_TS(X) | Timestamp of the last write on data item X |
## Write Operation Conditions in TWR
### 1. Abort the Transaction:
- If R\_TS(X) > TS(T)
- A newer transaction has already read X, so writing now would violate serializability.
- Action: Abort and rollback T.
### 2. Ignore Outdated Writes (Allow Execution Without Writing):
- If W\_TS(X) > TS(T)
- A newer write has already updated X. Writing now is obsolete.
- Action: Ignore the write; continue the transaction.
### 3. Execute Write Operation (Normal Execution):
- If neither condition above is true
- Action: Execute W\_item(X) and update W\_TS(X) = TS(T)
## Example - Ignoring an Outdated Write
The main improvement in Thomas Write Rule is that it ignores obsolete (outdated) writes instead of rejecting transactions. This happens when a newer transaction has already updated a value, making the older transaction's write operation unnecessary. Let'sconsider two transactions:
- TS(T1) = 30, TS(T2) = 20
- T1 arrives after T2
### Schedule Execution:
| Step | Operation | Description |
| --- | --- | --- |
| 1 | T2: W2(X) | T2 writes X (sets W\_TS(X) = TS(T2)) |
| 2 | T1: W1(X) | T1 tries to write X (TS(T1) > W\_TS(X)) |
| 3 | T1's write is ignored | Since T2 has already written X, T1’s write is obsolete and ignored instead of rollback |
- In Basic Timestamp Ordering, T1 would abort because its write is considered outdated.
- In Thomas Write Rule, outdated writes are ignored instead of rollback, allowing T1 to continue execution.
Consider the partial schedule given below - Obsolete Writes are hence ignored in this rule which is in accordance with the 2nd protocol.
![Example of Outdated Write](assets/Thomas-Write-Rule-660-24f5ec9d43.webp)
Example of Outdated Write
> **Note:** It seems to be more logical as users skip an unnecessary procedure of restarting the entire transaction. This protocol is just a modification to the Basic TO protocol.
## Example - View-Serializable but Not Conflict-Serializable
| T1 | T2 |
| --- | --- |
| R(A) |  |
| W(A) |  |
| Commit |  |
|  | W(A) |
|  | Commit |
- TWR allows such schedules because it ignores outdated writes.
- The schedule is view-serializable but not conflict-serializable.
- Hence, Thomas Write Rule guarantees view serializability, not conflict serializability.
## Comparison between Basic TO and Thomas Write Rule
| Aspect | Basic Timestamp Ordering (TO) | Thomas Write Rule (TWR) |
| --- | --- | --- |
| Basis | Strict timestamp checking for reads/writes | Modified TO that ignores outdated writes |
| Outdated Writes | Transaction aborted | Write ignored |
| Type of Serializability | Conflict serializable | View serializable (not always conflict serializable) |
| Concurrency Level | Low (more rollbacks) | Higher (fewer rollbacks) |
| System Throughput | Low | High |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/thomas-write-rule-in-dbms/)

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
