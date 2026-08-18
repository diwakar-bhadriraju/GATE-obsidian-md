---
title: "Implementation of Locking in DBMS"
subject: "Database Management System"
topic: "Transactions and Concurrency Control"
source: "https://www.geeksforgeeks.org/dbms/implementation-of-locking-in-dbms/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Transactions and Concurrency Control"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/transactions-and-concurrency-control
---


> [!abstract] Implementation of Locking in DBMS
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Transactions and Concurrency Control`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/implementation-of-locking-in-dbms/)

---

# Implementation of Locking in DBMS

Locking protocols are used in [database management systems](https://www.geeksforgeeks.org/dbms/introduction-of-dbms-database-management-system-set-1/) as a means of concurrency control. Multiple transactions may request a lock on a data item simultaneously. Hence, we require a mechanism to manage the locking requests made by transactions. Such a mechanism is called a **Lock Manager**. It relies on the process of message passing where [transactions](https://www.geeksforgeeks.org/sql/sql-transactions/) and lock manager exchange messages to handle the locking and unlocking of data items.
## **Data Structure in Lock Manager**
The data structure required for the implementation of locking is called a [Lock table](https://www.geeksforgeeks.org/sql/sql-lock-table/).
1. It is a [hash table](https://www.geeksforgeeks.org/dsa/hashing-data-structure/) where the names of data items are used as a hashing index.
2. Each locked data item has a linked list associated with it.
3. Every node in the linked list represents the transaction requested for lock, the mode of lock requested (mutual/exclusive), and the current status of the request (granted/waiting).
4. Every new lock request for the data item will be added to the end of the linked list as a new node.
5. Collisions in the hash table are handled by the technique of [separate chaining.](https://www.geeksforgeeks.org/dsa/separate-chaining-collision-handling-technique-in-hashing/)
Consider the following example of a lock table:
![Implementation of Locking in DBMS](assets/imgonline-com-ua-resize-Aczylhdnj2ODAIm--1234baab56.webp)
Implementation of Locking in DBMS
**Explanation:** In the above figure, the locked data items present in the lock table are 5, 47, 167, and 15. The transactions which have requested for lock have been represented by a linked list shown below them using a downward arrow. Each node in the linked list has the name of the transaction which has requested the data item like T33, T1, T27, etc. The color of the node represents the status i.e. whether the lock has been granted or waiting. Note that a collision has occurred for data items 5 and 47. It has been resolved by separate chaining where each data item belongs to a linked list. The data item is acting as a header for a linked list containing the locking request.
## **Working as Lock Manager**
- Initially, the lock table is empty as no data item is locked.
- Whenever the lock manager receives a lock request from a transaction Ti on a particular data item Qi following cases may arise:
  - If Qi is not already locked, a linked list will be created and a lock will be granted to the requesting transaction Ti.
  - If the data item is already locked, a new node will be added at the end of its linked list containing the information about the request made by Ti.
- If the lock mode requested by Ti is compatible with the lock mode of the transaction currently having the lock, Ti will acquire the lock too and the status will be changed to ‘granted’. Else, the status of Ti’s safety will be ‘waiting’.
- If a transaction Ti wants to unlock the data item it is currently holding, it will send an unlock request to the lock manager. The lock manager will delete Ti’s node from this linked list. The lock will be granted to the next transaction in the list.
- Sometimes transaction Ti may have to be aborted. In such a case all the waiting requests made by Ti will be deleted from the linked lists present in the lock table. Once abortion is complete, locks held by Ti will also be released.
## Advantages of Locking
- **Data Consistency:** Locking can help ensure data consistency by preventing multiple users from modifying the same data simultaneously. By controlling access to shared resources, locking can help prevent data conflicts and ensure that the database remains in a consistent state.
- **Isolation:** Locking can ensure that transactions are executed in isolation from other transactions, preventing interference between transactions and reducing the risk of [data inconsistencies.](https://www.geeksforgeeks.org/dbms/difference-between-data-redundancy-and-data-inconsistency/)
- **Granularity:** Locking can be implemented at different levels of granularity, allowing for more precise control over shared resources. For example, row-level locking can be used to lock individual rows in a table, while table-level locking can be used to lock entire tables.
- **Availability:** Locking can help ensure the availability of shared resources by preventing users from monopolizing resources or causing resource [starvation](https://www.geeksforgeeks.org/dbms/starvation-in-dbms/).
## Disadvantages of Locking
- **Overhead:** Locking requires additional overhead, such as acquiring and releasing locks on shared resources. This overhead can lead to slower performance and increased resource consumption, particularly in systems with high levels of [concurrency.](https://www.geeksforgeeks.org/dbms/concurrency-control-in-dbms/)
- **Deadlocks:** [Deadlocks](https://www.geeksforgeeks.org/operating-systems/deadlock-system-model/) can occur when two or more transactions are waiting for each other to release resources, causing a circular dependency that can prevent any of the transactions from completing. Deadlocks can be difficult to detect and resolve and can result in reduced throughput and increased latency.
- **Reduced Concurrency:** Locking can limit the number of users or applications accessing the database simultaneously. This can lead to reduced concurrency and slower performance in systems with high levels of concurrency.
- **Complexity:** Implementing locking can be complex, particularly in distributed systems or in systems with complex transactional logic. This complexity can lead to increased development and maintenance costs.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/implementation-of-locking-in-dbms/)

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
> - [[Introduction to Concurrency Control]]
