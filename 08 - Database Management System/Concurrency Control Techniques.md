---
title: "Concurrency Control Techniques"
subject: "Database Management System"
topic: "Transactions and Concurrency Control"
source: "https://www.geeksforgeeks.org/dbms/concurrency-control-techniques/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Transactions and Concurrency Control"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/transactions-and-concurrency-control
---


> [!abstract] Concurrency Control Techniques
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Transactions and Concurrency Control`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/concurrency-control-techniques/)

---

# Concurrency Control Techniques

Concurrency control is a fundamental concept in database systems that ensures correct execution of simultaneous transactions without violating data integrity. Below are some characteristics of concurrency control:
- It enforces isolation among transactions.
- It preserve database consistency through consistency preserving execution of transactions.
- It resolve read-write and write-read conflicts.
Concurrency control techniques in DBMS ensure that multiple transactions can execute simultaneously without conflicting with each other. These techniques maintain data consistency and prevent issues like lost updates, dirty reads, or deadlocks. Various concurrency control techniques are:
> 1. Two-phase locking Protocol
> 2. Time stamp ordering Protocol
> 3. Multi version concurrency control
> 4. Validation concurrency control
Concurrency control in DBMS ensures safe and consistent transaction execution when multiple users access data simultaneously. Techniques like locking, timestamps, and optimistic control prevent issues like deadlocks, dirty reads, and lost updates.
These are briefly explained below.
### 1. Two-Phase Locking Protocol
Locking is an operation which secures: permission to read, OR permission to write a data item. Two phase locking is a process used to gain ownership of shared resources without creating the possibility of deadlock. The 3 activities taking place in the two phase update algorithm are:
> 1. Lock Acquisition
> 2. Modification of Data
> 3. Release Lock
Two-phase locking prevents deadlocks by ensuring a process releases all held locks if it can't acquire all needed resources without waiting. This avoids situations where processes wait on each other, preventing deadlock.
A transaction in the Two Phase Locking Protocol can assume one of the 2 phases:
- **Growing Phase:** In this phase a transaction can only acquire locks but cannot release any lock. The point when a transaction acquires all the locks it needs is called the Lock Point.
- **Shrinking Phase:** In this phase a transaction can only release locks but cannot acquire any.
### 2. Time Stamp Ordering Protocol
A timestamp is a tag showing when a transaction or data item was last used. It can be assigned using the system clock or a logical counter. Each data item has two timestamps: one for the last read and one for the last write.
- **W-timestamp(X):** This means the latest time when the data item X has been written into.
- **R-timestamp(X):** This means the latest time when the data item X has been read from. These 2 timestamps are updated each time a successful read/write operation is performed on the data item X.
### **3. Multi-version Concurrency Control**
Multiversion 2-Phase Locking (MV2PL) improves concurrency by keeping multiple versions of data. Each write creates a new version with a timestamp. Reads access the version matching the transaction's timestamp.
### 4. Validation Concurrency Control
The optimistic approach assumes that conflicts between transactions are rare. So, it allows transactions to execute freely without using locks or timestamps. Each transaction goes through three phases:
**1. Read Phase:** The transaction reads data and performs all operations using a private copy. Any updates are stored in a temporary area, not visible to other transactions.
**2. Validation Phase:** Before committing, the transaction is checked to ensure that applying its changes won't violate database consistency.
- If the check **passes**, it proceeds to the next phase.
- If the check **fails**, the transaction is rolled back and restarted.
**3. Write Phase:** The validated changes are now written permanently to the database.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/concurrency-control-techniques/)

## GATE CS

- Subject: Database Management System
- Topic: Transactions and Concurrency Control

> [!note] Related notes
>
> - [[ACID Properties in DBMS]]
> - [[Cascadeless in DBMS]]
> - [[Categories of Two Phase Locking]]
> - [[Conflict Serializability]]
> - [[Database Recovery Techniques]]
> - [[Deadlock in DBMS]]
> - [[Graph Based Protocol]]
> - [[How to test if two schedules are View Equal or not]]
> - [[Implementation of Locking in DBMS]]
> - [[Introduction to Concurrency Control]]
