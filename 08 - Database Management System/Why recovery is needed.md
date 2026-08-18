---
title: "Why recovery is needed in DBMS"
subject: "Database Management System"
topic: "Transactions and Concurrency Control"
source: "https://www.geeksforgeeks.org/dbms/why-recovery-is-needed-in-dbms/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Transactions and Concurrency Control"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/transactions-and-concurrency-control
---


> [!abstract] Why recovery is needed in DBMS
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Transactions and Concurrency Control`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/why-recovery-is-needed-in-dbms/)

---

# Why recovery is needed in DBMS

Basically, whenever a [transaction](https://www.geeksforgeeks.org/dbms/transaction-states-in-dbms/) is submitted to a DBMS for execution, the operating system is responsible for making sure or to be confirmed that all the operations which need to be performed in the transaction have been completed successfully and their effect is either recorded in the [database](https://www.geeksforgeeks.org/dbms/what-is-database/) or the transaction doesn't affect the database or any other transactions.
The [DBMS](https://www.geeksforgeeks.org/dbms/introduction-of-dbms-database-management-system-set-1/) must not permit some operation of the transaction T to be applied to the database while other operations of T are not. This basically may happen if a transaction fails after executing some of its operations but before executing all of them.
## **Types of Failures**
Failures are basically the inability of the database to perform a transaction or any kind of loss to the database. There are basically the following types of failures that may occur and lead to the failure of the transaction such as:
- **Transaction Failure:** It is a type of failure that occurs when a transaction is not able to complete or it is no longer acceptable.
- **System Failure/Crash:** A hardware, software, or network error occurs comes under this category this type of failure basically occurs during the execution of the transaction. Hardware failures are basically considered Hardware failures.
- **System Error:** Some operation that is performed during the transaction is the reason for this type of error to occur, such as integer or divide by zero. This type of failure is also known as the transaction which may also occur because of erroneous parameter values or because of a logical programming error. In addition to this user may also interrupt the execution during execution which may lead to failure in the transaction.
- **Local Error:** This basically happens when we are doing the transaction but certain conditions may occur that may lead to the cancellation of the transaction. This type of error is basically coming under Local error. A simple example of this is that data for the transaction may not be found. When we want to debit money from an insufficient balance account it leads to the cancellation of our request or transaction. And this exception should be programmed in the transaction itself so that it wouldn't be considered as a failure.
- **Concurrency Control Enforcement:** The [concurrency control method](https://www.geeksforgeeks.org/dbms/concurrency-control-techniques/) may decide to abort the transaction, to start again because it basically violates serializability or we can say that several processes are in a deadlock.
- **Disk Failure:** This type of failure basically occurs when some disk loses its data because of a read or write malfunction or because of a disk read/write head crash. This may happen during a read /write operation of the transaction.
- **Catastrophe:** These are also known as physical problems it basically refers to the endless list of problems that include power failure or air-conditioning failure, fire, theft sabotage overwriting disk or tapes by mistake, and mounting of the wrong tape by the operator.
- **Network Failure:** A network failure occurs when there is a disruption in the communication channel between the [client and the database server](https://www.geeksforgeeks.org/computer-networks/difference-between-client-server-and-distributed-dbms/). This can happen due to a variety of reasons, such as hardware failure, software error, or a natural disaster.
- **Deadlock:** A deadlock occurs when two or more transactions are waiting for each other to release the locks on the resources they need to proceed. This can cause a transaction to get stuck, and eventually, the system may need to abort one or more of the transactions to resolve the deadlock.
- **Software Bugs:** Bugs in the DBMS software can cause unexpected behavior or errors during the execution of a transaction. This can lead to data corruption or loss if not handled properly.
- **Power Outage:** A power outage can cause the system to shut down unexpectedly, leading to data loss or corruption if the transactions in progress are not properly handled by the recovery mechanism.
- **Data Corruption:** Data corruption can occur due to a variety of reasons, such as hardware failure, software bugs, or network errors. If the corruption is not detected and corrected, it can cause data inconsistencies and affect the overall integrity of the database.
Recovery is an essential feature in [Database Management Systems (DBMS)](https://www.geeksforgeeks.org/dbms/introduction-of-dbms-database-management-system-set-1/) because it ensures that data can be restored to a consistent and correct state in case of failures or errors.
## Why Recovery is Required in Database?
Here are some of the reasons why recovery is needed in DBMS.
- **System failures:** The DBMS can experience various types of failures, such as hardware failures, software bugs, or power outages, which can lead to data corruption or loss. Recovery mechanisms can help restore the database to a consistent state after such failures.
- **Transaction failures:** Transactions can fail due to various reasons, such as network failures, deadlock, or errors in application logic. Recovery mechanisms can help roll back or undo the effects of such failed transactions to ensure data consistency.
- **Human errors:** Human errors such as accidental deletion, updating or overwriting data, or incorrect data entry can cause data inconsistencies. Recovery mechanisms can help recover the lost or corrupted data and restore it to the correct state.
- **Security breaches:** Security breaches such as hacking or unauthorized access can compromise the [integrity of data](https://www.geeksforgeeks.org/software-testing/data-integrity-testing-in-software-testing/). Recovery mechanisms can help restore the database to a consistent state and prevent further data breaches.
- **Hardware upgrades:** When a DBMS is upgraded to a new hardware system, the migration process can potentially lead to data loss or corruption. Recovery mechanisms can help ensure that the data is successfully migrated and the integrity of the database is maintained.
- **Natural disasters:** Natural disasters such as earthquakes, floods, or fires can damage the hardware on which the database is stored, leading to data loss. Recovery mechanisms can help restore the data from backups and minimize the impact of the disaster.
- **Compliance regulations:** Many industries have regulations that require businesses to retain data for a certain period of time. Recovery mechanisms can help ensure that the data is available for compliance purposes even if it was deleted or lost accidentally.
- **Data corruption:** Data corruption can occur due to various reasons such as hardware failure, software bugs, or viruses. Recovery mechanisms can help restore the database to a consistent state and recover any lost or corrupted data.
Recovery is needed in DBMS to ensure data consistency, integrity, and availability in the face of various types of failures and errors.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/why-recovery-is-needed-in-dbms/)

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
