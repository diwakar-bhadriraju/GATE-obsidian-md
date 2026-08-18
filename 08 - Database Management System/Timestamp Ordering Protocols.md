---
title: "Timestamp based Concurrency Control"
subject: "Database Management System"
topic: "Transactions and Concurrency Control"
source: "https://www.geeksforgeeks.org/dbms/timestamp-based-concurrency-control/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Transactions and Concurrency Control"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/transactions-and-concurrency-control
---


> [!abstract] Timestamp based Concurrency Control
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Transactions and Concurrency Control`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/timestamp-based-concurrency-control/)

---

# Timestamp based Concurrency Control

Timestamp-based concurrency control is a technique used in database management systems (DBMS) to ensure serializability of transactions without using locks. It uses timestamps to determine the order of transaction execution and ensures that conflicting operations follow a consistent order.
Each transaction T is assigned a unique timestamp TS(T) when it enters the system. This timestamp determines the transaction’s place in the execution order.
## Timestamp Ordering Protocol
The Timestamp Ordering Protocol enforces that older transactions (with smaller timestamps) are given higher priority. This prevents conflicts and ensures the execution is serializable and deadlock-free.
**For example:**
- If Transaction T1 enters the system first, it gets a timestamp TS(T1) = 007 (assumption).
- If Transaction T2 enters after T1, it gets a timestamp TS(T2) = 009 (assumption).
This means T1 is "older" than T2 and T1 should execute before T2 to maintain consistency.
## Features of Timestamp Ordering Protocol:
### **1. Transaction Priority**:
- Older transactions (those with smaller timestamps) are given higher priority.
- For example, if transaction T1 has a timestamp of 007 times and transaction T2 has a timestamp of 009 times, T1 will execute first as it entered the system earlier.
### **2. Early Conflict Management**:
Unlike lock-based protocols, which manage conflicts during execution, timestamp-based protocols start managing conflicts as soon as a transaction is created.
### **3. Ensuring Serializability**:
The protocol ensures that the schedule of transactions is serializable. This means the transactions can be executed in an order that is logically equivalent to their timestamp order.
## How Timestamp Ordering Works
Each **data item X** in the database keeps two timestamps:
- **W\_TS(X):** Timestamp of the last transaction that wrote to X
- **R\_TS(X):** Timestamp of the last transaction that read from X
## Basic Timestamp Ordering
The Basic TO Protocol works by comparing the timestamp of the current transaction with the timestamps on the data items it wants to **read/write:**
![Timestamp based Protocol](assets/22-6-bd3dfb7305.png)
Precedence Graph for TS ordering
- Suppose, if an old transaction Ti has timestamp TS(Ti), a new transaction Tj is assigned timestamp TS(Tj) such that TS(Ti) < TS(Tj).
- The protocol manages concurrent execution such that the timestamps determine the serializability order.
- The timestamp ordering protocol ensures that any conflicting read and write operations are executed in timestamp order.
- Whenever some Transaction **T** tries to issue a R\_item(X) or a W\_item(X), the Basic TO algorithm compares the timestamp of **T** with R\_TS(X) & W\_TS(X) to ensure that the Timestamp order is not violated.
**Two Basic TO protocols are discussed below:**
1. Whenever a Transaction **T** issues a **R\_item(X)** operation, check the following conditions: 
- If **W\_TS(X) > TS(T)** → **Abort T** (conflict: a newer write already occurred)
- **Else → Allow read** and set **R\_TS(X) = max(R\_TS(X), TS(T))**
2. Whenever a Transaction **T** issues a **W\_item(X)** operation, check the following conditions: 
- If **R\_TS(X) > TS(T)** or **W\_TS(X) > TS(T)** → **Abort** T (conflict: older transaction overwriting newer read/write)
- **Else → Allow write** and set **W\_TS(X) = TS(T)**
When conflicts are detected, the younger transaction is aborted and rolled back.
## Strict Timestamp Ordering Protocol
The Strict Timestamp Ordering Protocol is an enhanced version that avoids cascading rollbacks by delaying operations until it's safe to execute them.
### Key Features
- **Strict Execution Order**: Transactions must execute in the exact order of their timestamps. Operations are delayed if executing them would violate the timestamp order, ensuring a strict schedule.
- **No Cascading Rollbacks**: To avoid cascading aborts, a transaction must delay its operations until all conflicting operations of older transactions are either committed or aborted.
- **Consistency and Serializability**: The protocol ensures conflict-serializable schedules by following strict ordering rules based on transaction timestamps.
### Rules for Read Operation R\_item(X):
T can read X only if:
- W\_TS(X) ≤ TS(T) and
- The transaction that last wrote X has committed
### Rules for Write Operation W\_item(X):
T can write X only if:
- R\_TS(X) ≤ TS(T) and W\_TS(X) ≤ TS(T) and
- All previous readers/writers of X have committed
If these conditions aren't met, the operation is delayed (not aborted immediately).
| Advantages | Disadvantages |
| --- | --- |
| **Conflict-Serializable**: Maintains a correct execution order | **Cascading Rollbacks** (in Basic TO protocol) |
| **Deadlock-Free**: No locks, so no circular waits | **Starvation**: Newer transactions may be delayed |
| **Simple Conflict Resolution**: Uses timestamps only | **High Overhead**: Constantly updating R\_TS/W\_TS |
| **No Locking Needed**: Avoids lock management complexity | **Lower Throughput** under high concurrency |
| **Predictable Execution**: Operations follow a known order | **Delayed Execution** in Strict TO for consistency |
### Related PYQs
> 1. [GATE | GATE CS 2010 | Question 20](https://www.geeksforgeeks.org/questions/which-of-the-following-concurrency-control-protocols-ensure-both/)
> 2. [GATE | GATE-CS-2017 (Set 1) | Question 46](https://www.geeksforgeeks.org/questions/in-a-database-system-unique-time-stamps-are-assigned/)
> 3. [GATE | GATE-IT-2004 | Question 21](https://www.geeksforgeeks.org/questions/which-level-of-locking-provides-the-highest-degree-of/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/timestamp-based-concurrency-control/)

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
