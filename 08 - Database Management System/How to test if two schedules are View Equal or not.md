---
title: "Condition of schedules to be View-equivalent"
subject: "Database Management System"
topic: "Transactions and Concurrency Control"
source: "https://www.geeksforgeeks.org/dbms/condition-of-schedules-to-be-view-equivalent/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Transactions and Concurrency Control"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/transactions-and-concurrency-control
---


> [!abstract] Condition of schedules to be View-equivalent
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Transactions and Concurrency Control`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/condition-of-schedules-to-be-view-equivalent/)

---

# Condition of schedules to be View-equivalent

In a database system, a schedule is a sequence of operations (such as read and write operations) performed by transactions in the system. Serial or one by one execution of schedules has less resource utilization and low throughput. To improve it, two or more transactions are run concurrently.
- View Serializability guarantees that even though transactions run concurrently, their outcome will be identical to the result achieved if the transactions were executed one by one in a specific order.
- It is a concept in concurrency control that determines whether a non-serial schedule can be rearranged to act like a serial schedule without conflicts.
- It ensures data consistency and integrity when multiple transactions are executed at the same time.
## View Serializable and View Equivalent
A schedule is [**view serializable**](https://www.geeksforgeeks.org/dbms/view-serializability-in-dbms/) if it is view equivalent to a serial schedule. In simple terms:
- **Serial Schedule**: Transactions are executed one after another without interleaving.
- **View Equivalent**: Two schedules are view equivalent if they produce the same final state of the database and ensure the same read/write behavior for all transactions.
A schedule S1 is view-equivalent to schedule S2 if:
1. Initial Read Condition:
If a transaction reads the initial value of Q in S1, it must also read the initial value of Q in S2.
2. Read-From Condition:
If Ti reads the value of Q written by Tj in S1, then Ti must read the value of Q written by the same Tj in S2.
3. Final Write Condition:
The transaction performing the final write(Q) in S1 must also perform the final write(Q) in S2.
View-equivalence is indeed a weaker condition than [conflict serializability](https://www.geeksforgeeks.org/dbms/conflict-serializability-in-dbms/). While conflict serializability strictly enforces the order of conflicting operations (like reads and writes on the same data), view equivalence focuses on ensuring that the outcome of the schedule is identical to that of a serial schedule, regardless of the exact operation order.
This weaker condition allows more concurrency and flexibility in executing transactions, as long as:
1. The first read of a data item matches the corresponding read in the serial schedule.
2. The final writes to each data item are the same as in the serial schedule.
3. The intermediate reads are consistent with the corresponding writes.
Two schedules S1 and S2 are said to be view-equivalent if the below conditions are satisfied : 
**1.Initial Reads:** If in schedule S, transaction Ti reads the initial value of Q, then in schedule S’ also transaction Ti must read the initial value of Q. For example, if transaction T1 reads data item A in schedule S, then in schedule S', T1 must also read A as its first operation to maintain consistency.
![initial_Read](assets/initial_Read-660-027864b648.webp)
Initial Read
**2.Intermediate/Updated Reads:** If in a schedule S, a transaction Ti executes executes read(Q), and that value was produced by transaction Tj (if any), then in schedule S’ also transaction Ti must read the value of Q that was produced by the same write(Q) operation of transaction Tj. For example, if T3 reads the value of B updated by T2 in schedule S then in S', T3 must read the value of B updated by T2.
![updated_read](assets/updated_read-660-a335b002a6.webp)
Updated Read
**3.Final Update:** The transaction (if any) that performs the final write(Q) operation in schedule S must also perform the final write(Q) operation in schedule S’. For example, if T3 is the last transaction to write to A in schedule S, then T3 must also be the last transaction to write to A in schedule S'
![final_update](assets/final_update-660-b224e47d0c.webp)
Final Write
### Steps to find View Serializable
Step 1- Find if schedule is conflict serializable or not.
Step 2- Find the possible serial schedule -> 3!
Step 3- Choose one of them and check for view equivalent conditions.
Step 4- If view equivalent schedule matches the condition, it is view serializable.
**Example of View Serializable Schedule**
| Step | Transaction | Operation | Explanation |
| --- | --- | --- | --- |
| 1 | T1 | W(A) | T1 writes the initial value of A. |
| 2 | T2 | R(A) | T2 reads A written by T1. |
| 3 | T2 | W(B) | T2 writes a new value of B. |
| 4 | T1 | R(B) | T1 reads B written by T2. |
 **Serial Schedule Equivalent**
| Step | Transaction | Operation | Explanation |
| --- | --- | --- | --- |
| 1 | T1 | W(A) | T1 writes A — same as original schedule. |
| 2 | T2 | R(A) | T2 reads A written by T1 — matches the original read. |
| 3 | T2 | W(B) | T2 writes B — must occur before T1 reads B. |
| 4 | T1 | R(B) | T1 reads the value of B written by T2 — same as original schedule. |
### **Condition 1: Initial Reads**
- In the original schedule, **T2 reads A written by T1**.
- In the corrected serial schedule, this is preserved:
  - T1 writes A → T2 reads A.
### **Condition 2: Final Writes**
- Final write on **A** is by **T1** (unchanged).
- Final write on **B** is by **T2** (unchanged).
### **Condition 3: Intermediate Reads**
- In the original schedule, **T1 reads B written by T2**.
- In the corrected serial schedule, T1 reads B **after** T2 writes B.
Thus, **T1 → T2** is the correct serial order.
Read more about [Polygraph to check view Serializability](https://www.geeksforgeeks.org/dbms/polygraph-to-check-view-serializabilty-in-dbms/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/condition-of-schedules-to-be-view-equivalent/)

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
> - [[Implementation of Locking in DBMS]]
> - [[Introduction to Concurrency Control]]
