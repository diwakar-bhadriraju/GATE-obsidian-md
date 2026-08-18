---
title: "Types of Schedules in DBMS"
subject: "Database Management System"
topic: "Transactions and Concurrency Control"
source: "https://www.geeksforgeeks.org/dbms/types-of-schedules-in-dbms/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Transactions and Concurrency Control"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/transactions-and-concurrency-control
---


> [!abstract] Types of Schedules in DBMS
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Transactions and Concurrency Control`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/types-of-schedules-in-dbms/)

---

# Types of Schedules in DBMS

Scheduling is the process of determining the order in which transactions are executed. When multiple transactions run concurrently, scheduling ensures that operations are executed in a way that prevents conflicts or overlaps between them.
![Types-of-Schedules](assets/Types-of-Schedules-7530ac33fd.webp)
Types of Schedules in DBMS
## 1. Serial Schedule
Schedules in which transactions execute one after another without interleaving., i.e., no transaction starts until a running transaction has ended are called serial schedules.
- Only one transaction runs at a time.
- No concurrency issues.
- Simple and always consistent.
**Example:** Consider the following schedule involving two transactions T1  and T2 .
![serial-schedule-examlpe](assets/serial-schedule-examlpe-63968ca34b.webp)
Serial Schedule
In the above table R(A) and W(A) denotes that a read and write operation is performed on some data item 'A' respectively, denoting a serial schedule since the transactions perform serially in the order **T**1** **—> T**2 .**
## 2. Non-Serial Schedule
Transactions execute in an interleaved manner in Non-Serial Schedule.
- Allows concurrency.
- Must be checked for correctness.
- May or may not be serializable.
Non-serial schedules are of two types:
### Serializable Scheduling (Concurrency Control)
A non-serial schedule that behaves like a serial schedule.
### Why Serializable Schedules?
- Maintain consistency.
- Avoid anomalies.
- Improve performance by allowing concurrency.
There are two types of serializable schedules:
**i. Conflict Serializable**: A schedule is [conflict serializable](https://www.geeksforgeeks.org/dbms/conflict-serializability-in-dbms/) if it can be converted into a serial schedule by swapping non-conflicting operations.
Two operations conflict when:
- They belong to different transactions.
- They operate on the same data item.
- At least one operation is a write.
**ii. View Serializable**: A Schedule is called [view serializable](https://www.geeksforgeeks.org/dbms/condition-of-schedules-to-be-view-equivalent/) if:
- Transactions read the same initial values.
- Transactions read values written by the same transactions.
- The final write is by the same transaction as the serial schedule.
> **Note**: Conflict-serializable schedules are a subset of view-serializable schedules. (Conflict-serializable ⊂ View-serializable.)
### Non-Serializable Scheduling
Schedules that do not preserve serial equivalence and may lead to inconsistencies if not handled carefully.
They are classified into the following types:
**i. Recoverable Schedule**: [Recoverable schedules](https://www.geeksforgeeks.org/dbms/recoverability-in-dbms/) are those in which a transaction commits only after all transactions whose values it has read have also committed.
- Key Point: If T2 reads a value written by T1, then T2 must commit after T1.
**Example**: Consider the following schedule involving two transactions T1  and T2 .
![Non-Serializable-Scheduling](assets/Non-Serializable-Scheduling-1234415139.webp)
Recoverable Schedule
This is a recoverable schedule since T1  commits before T2 , that makes the value read by T2  correct. There can be three types of recoverable schedule:
**ii. Cascading Schedule:** A schedule where:
- Failure of one transaction forces all dependent transactions to abort.
- Happens when transactions read uncommitted data.
![Cascade-abort](assets/Cascade-abort-95cc5ba9af.webp)
Cascading Abort
**iii. Cascadeless Schedule**: A schedule where:
- A transaction only reads committed data.
- Prevents cascading aborts.
- Key Point: T2 can read the value written by T1 only after T1 commits.
**Example:**  Consider the following schedule involving two transactions T1  and T2 .
![Cascadeless-Schedule](assets/Cascadeless-Schedule-115f13bc24.webp)
Cascadeless Schedule
This schedule is cascadeless. Since the updated value of **A** is read by T2  only after the updating transaction i.e. T1 commits.
**Example:** Consider the following schedule involving two transactions T1 and T2 .
![Cascadeless-Schedule-2-](assets/Cascadeless-Schedule-2--2467887353.webp)
It is a recoverable schedule but it does not avoid cascading aborts. It can be seen that if T1 aborts, T2 will have to be aborted too in order to maintain the correctness of the schedule as T2 has already read the uncommitted value written by T1 .
**iv. Strict Schedule:** It's a stronger form of cascadeless schedule that follows the following rules:
- A transaction cannot read or write a data item written by another transaction until that transaction commits or aborts.
- Prevents dirty reads and dirty writes.
**Example:** Consider the following schedule involving two transactions T1  and T2 .
![Strict-Schedule](assets/Strict-Schedule-8efe6e140e.webp)
Strict Schedule
This is a strict schedule since T2 reads and writes A which is written by T1 only after the commit of T1 .
**v. Non-Recoverable Schedule:** A schedule where:
- A transaction commits after reading **uncommitted data** from another transaction.
- If the writer transaction later aborts, the schedule becomes invalid.
- Key Point: These schedules must be avoided since they lead to inconsistencies.
**Example**: Consider the following schedule involving two transactions T1 and T2.
![Non-Recoverable-Schedule](assets/Non-Recoverable-Schedule-95879568a4.webp)
Non-Recoverable Schedule
T2 read the value of A written by T1, and committed. T1 later aborted, therefore the value read by T2 is wrong, but since T2 committed, this schedule is non-recoverable.
**Summary of Relationships**
- Cascadeless schedules are stricter than recoverable schedules or are a subset of recoverable schedules.
- Strict schedules are stricter than cascadeless schedules or are a subset of cascadeless schedules.
- Serial schedules satisfy constraints of all recoverable, cascadeless and strict schedules and hence is a subset of strict schedules.
The following Venn diagram shows the hierarchical relationship among the different types of schedules:
![Serializability-venn-diagram](assets/Serializability-venn-diagram-c616e28d89.webp)
Relationship Venn Diagram of Types of Schedules
**Question:** Consider the following schedule:
> S:R1(A), W2(A), Commit2, W1(A), W3(A), Commit3, Commit1
Which of the following is true?
(A) The schedule is view serializable schedule and strict recoverable schedule(
B) The schedule is non-serializable schedule and strict recoverable schedule
(C) The schedule is non-serializable schedule and is not strict recoverable schedule.
(D) The Schedule is serializable schedule and is not strict recoverable schedule
**Solution:** The schedule can be depicted as:
![example-problem](assets/example-problem-fcd6c4e9f3.webp)
The schedule is view-serializable because it matches the serial order T1 → T2 → T3 (initial read, intermediate writes, and final write all match this order).
- The schedule is not strict because T1 writes A, and T3 writes A before T1 commits, which violates the rule that a transaction must wait for the previous writer to commit.
- The schedule is recoverable, but not strict recoverable (Correct option is D).
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/types-of-schedules-in-dbms/)

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
