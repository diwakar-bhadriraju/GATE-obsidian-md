---
title: "Categories of Two Phase Locking"
subject: "Database Management System"
topic: "Transactions and Concurrency Control"
source: "https://www.geeksforgeeks.org/dbms/categories-of-two-phase-locking-strict-rigorous-conservative/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Transactions and Concurrency Control"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/transactions-and-concurrency-control
---


> [!abstract] Categories of Two Phase Locking
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Transactions and Concurrency Control`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/categories-of-two-phase-locking-strict-rigorous-conservative/)

---

# Categories of Two Phase Locking

Two-Phase Locking (2PL) is a technique in database management systems designed to ensure consistency and isolation during concurrent transactions.
There are three categories: 
1. Strict 2-PL
2. Rigorous 2-PL
3. Conservative 2-PL
## 1. Strict Two-Phase Locking Protocol (Strict 2PL)
The Strict Two-Phase Locking Protocol is a variation of the Two-Phase Locking (2PL) protocol that adds a specific rule for releasing exclusive (X) locks. In addition to following the two phases (growing and shrinking), strict 2PL ensures that:
**All Exclusive (X) Locks are Held Until the Transaction Commits or Aborts:**
- A transaction can acquire locks during the growing phase.
- It cannot release any exclusive locks until it has completed its operations and either committed or aborted.
- This rule prevents other transactions from accessing data modified by an ongoing transaction, ensuring data consistency.
**Benefits:**
- **Recoverable Schedule:** Ensures that if a transaction fails, no other transactions depend on its uncommitted changes.
- **Cascadeless Schedule:** Prevents cascading rollbacks, as other transactions cannot read uncommitted data.
![strict_2_pl](assets/strict_2_pl-97f7bff3ca.webp)
Strict 2PL
The image demonstrates a Strict Two-Phase Locking (2PL) Protocol scenario with two transactions, T1 and T2 accessing and modifying two database accounts A and B. Here’s a step-by-step explanation:
### **Initial Database State:**
- Account A=1000
- Account B=1000
### **Steps in the Schedule:**
#### **Transaction T1​:**
1. BEGIN**:** T1​ starts and acquires an exclusive lock (X-Lock) on A. This means T1 can read and modify A, and no other transaction can access A during this time.
2. T1​ reads A and subtracts 100 from it (A=900).
3. T1 acquires an X-Lock on B and adds 100 to B (B=1100).
4. T1​ unlocks A and B only after committing. At this point, the changes made by T1​ become visible to other transactions.
#### **Transaction T2:**
1. BEGIN**:** T2​ starts and tries to acquire a shared lock (S-Lock) on A to read its value.
2. T2​ waits because T1 is holding an exclusive lock on A. This prevents T2​ from reading the uncommitted data ensuring no dirty reads.
3. Once T1​ commits and releases the lock on A, T2​ acquires the S-Lock on A, reads A=900 and moves on.
4. T2 acquires an S-Lock on B, reads B=1100 and calculates A+B=2000.
5. T2 unlocks both A and B after committing.
**Final Output:**
- After T1​ commits, T2​ reads the updated values of A and B and the result A+B=2000 reflects the committed changes.
## 2. Rigorous Two-Phase Locking (Rigorous 2PL)
Rigorous 2PL is a stricter version of the Two-Phase Locking (2PL) protocol. In this protocol:
- All locks (both shared and exclusive) are held by a transaction until it either commits or aborts.
- Locks are only released after the transaction finishes, ensuring that no other transaction can access the locked data until the first transaction is fully complete.
This means that no other transaction can read or write the data being used by the current transaction until it is committed or rolled back. This ensures data consistency and avoids issues like dirty reads or cascading rollbacks.
![dbms2](assets/dbms2-181d617666.webp)
Sequence of Transactions
**Explantion of the above transactions is given below:**
**T1 (left column)**
1. lock-exclusive(A) → T1 locks data item A exclusively.
2. lock-exclusive(B) → T1 also locks B exclusively.
3. Reads and modifies A: read(A) → A = A + 50 → write(A).
4. Reads and modifies B: read(B) → B = B + 100 → write(B).
5. commit is performed before releasing any locks.
6. unlock(A) and unlock(B) happen after commit.
**Follows Rigorous 2PL**: No locks are released before the transaction commits.
**T2 (right column)**
1. lock-exclusive(A) → T1 locks A exclusively.
2. Reads and modifies A: read(A) → A = A + 50 → write(A).
3. commit is executed.
4. unlock(A) is done after commit.
**Follows Rigorous 2PL**: Even with a single item, lock is held until commit.
Hence, it gives us freedom from Cascading Abort which was still there in Basic 2-PL and moreover guarantee Strict Schedules but still, [Deadlocks](https://www.geeksforgeeks.org/operating-systems/introduction-of-deadlock-in-operating-system/) are possible! 
> **Note:** The difference between Strict 2-PL and Rigorous 2-PL is that Rigorous is more restrictive, it requires both Exclusive and Shared locks to be held until after the Transaction commits and this is what makes the implementation of Rigorous 2-PL easier.  
## 3. Conservative Two-Phase Locking (Conservative 2PL)
[Conservative 2PL](https://www.geeksforgeeks.org/dbms/categories-of-two-phase-locking-strict-rigorous-conservative/) is a variation of the Two-Phase Locking protocol designed to prevent deadlocks entirely. It is also known as the Static-2PL. The key feature of Conservative 2PL is that a transaction acquires all the locks it needs at the very beginning of the transaction before it starts executing. If the transaction cannot acquire all the required locks, it does not proceed and waits until all locks become available.
![conservative_2pl](assets/conservative_2pl-44129e24c8.webp)
Conservative 2PL Protocol
This example demonstrates Conservative Two-Phase Locking (Conservative 2PL), where each transaction acquires all the locks it needs at the beginning of the transaction to avoid deadlocks. Here's a detailed explanation of how it aligns with the principles of Conservative 2PL:
#### **Transaction T1​ (left column):**
1. **Lock-Exclusive(A):** T1​ acquires an exclusive lock on A before performing any operation on it.
2. **Lock-Exclusive(B):** Before proceeding further, T1 also acquires an exclusive lock on B ensuring that both resources required by T1​ are locked at the start.
3. **Operations on A:** T1 reads the value of A, increments it by 50 and writes the updated value back to A.
4. **Unlock(A):** After completing all operations on A, T1​ releases the lock on A.
5. **Operations on B:** T1​ reads the value of B, increments it by 100 and writes the updated value back to B.
6. **Unlock(B):** T1 releases the lock on B after finishing all operations.
#### **Transaction T2 (right column):**
1. **Lock-Exclusive(A):** T2 attempts to acquire an exclusive lock on A at the start of the transaction. If T1​ still holds the lock on A T2​ waits until T1​ releases it.
2. **Operations on A:** Once T2​ acquires the lock it reads A, increments it by 50 and writes the updated value back to A.
3. **Unlock(A):** T2​ releases the lock on A, after completing its operations.
### **Advantages of Conservative 2PL:**
1. **Deadlock-Free:** Deadlocks are avoided because a transaction either acquires all required locks at once or waits until it can.
2. **Efficient Use of Locks:** Transactions do not hold partial locks while waiting for others, reducing contention.
3. **Consistency and Serializability:** Like all 2PL variants, it ensures consistent and serializable schedules.
[Venn Diagram](https://www.geeksforgeeks.org/maths/venn-diagram/) below shows the classification of schedules that are rigorous and strict. The universe represents the schedules that can be serialized as 2-PL. Now as the diagram suggests, and it can also be logically concluded, if a schedule is Rigorous then it is Strict. We can also think in another way, say we put a restriction on a schedule which makes it strict adding another to the list of restrictions make it Rigorous.
![420851502](assets/420851502-88c2f95cd0.webp)
### Related PYQs
> [GATE CS | IT 2004 | Question 77](https://www.geeksforgeeks.org/questions/consider-the-following-schedule-s-of-transactions-t1-and/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/categories-of-two-phase-locking-strict-rigorous-conservative/)

## GATE CS

- Subject: Database Management System
- Topic: Transactions and Concurrency Control

> [!note] Related notes
>
> - [[ACID Properties in DBMS]]
> - [[Cascadeless in DBMS]]
> - [[Concurrency Control Techniques]]
> - [[Conflict Serializability]]
> - [[Database Recovery Techniques]]
> - [[Deadlock in DBMS]]
> - [[Graph Based Protocol]]
> - [[How to test if two schedules are View Equal or not]]
> - [[Implementation of Locking in DBMS]]
> - [[Introduction to Concurrency Control]]
