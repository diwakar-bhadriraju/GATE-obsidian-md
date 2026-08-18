---
title: "Starvation in DBMS"
subject: "Database Management System"
topic: "Transactions and Concurrency Control"
source: "https://www.geeksforgeeks.org/dbms/starvation-in-dbms/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Transactions and Concurrency Control"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/transactions-and-concurrency-control
---


> [!abstract] Starvation in DBMS
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Transactions and Concurrency Control`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/starvation-in-dbms/)

---

# Starvation in DBMS

Starvation in DBMS is a problem that happens when some processes are unable to get the resources they need because other processes keep getting priority. This can happen in situations like locking or scheduling, where some processes keep getting the resources first, leaving others waiting indefinitely.
This can cause delays or even stop certain operations from completing. In this article, we will explore what causes starvation, its effects, and how it can be prevented to make sure all processes are treated fairly.
![starvation](assets/starvation-3109f29d52.webp)
Starvation
**Example 1:**
Imagine you are waiting at a restaurant to place your order. Every time the waiter comes, they serve people who arrived after you because they are VIPs or because the waiter is prioritizing large group orders. You’ve been waiting for hours, but your turn never comes. This is similar to starvation, where someone is stuck waiting indefinitely while others get served first.
**Example 2:**
Suppose there are 3 transactions namely T1, T2, and T3 in a database that is trying to acquire a lock on data item ' I '. Now, suppose the scheduler grants the lock to T1(maybe due to some priority), and the other two transactions are waiting for the lock. As soon as the execution of T1 is over, another transaction T4 also comes over and requests a lock on data item I. Now, this time the scheduler grants lock to T4, and T2, T3 has to wait again. In this way, if new transactions keep on requesting the lock, T2 and T3 may have to wait for an indefinite period of time, which leads to Starvation. 
## **Reasons for Starvation**
Starvation in DBMS happens when some transactions or processes are unable to get the resources they need, often because other processes are prioritized or due to poor resource management. Here are the main reasons for starvation in simple terms:
- **Unfair Prioritization**: If lower-priority processes keep competing with higher-priority ones, they might be ignored for a long time, leading to indefinite waiting.
- **Inappropriate Locking Strategy**: When resources are managed poorly, such as using a priority queue, lower-priority processes may never get access to locked resources.
- **Uncontrolled Resource Allocation:** If processes keep passing resources to others without considering the system’s overall needs, some processes might never get the resources they require**.**
- **Queue Mismanagement**: If resources are always passed to the next process in a queue, new processes keep getting added, and some may end up waiting indefinitely.
- **Repeated Victim Selection**: Sometimes, the same transaction is repeatedly chosen as a "victim" during resource allocation, causing it to stay stuck without progress.
- **Resource Leakage**: If resources are lost or mismanaged due to system errors, there may not be enough available to meet the demands of all processes.
- **High Demand vs. Limited Resources**: If the demand for resources is much higher than the supply, no matter how well resources are managed, some processes will inevitably experience starvation.
- **Random Resource Allocation**: If resources are assigned randomly instead of following a proper queue, some processes may end up waiting much longer than others.
- **Denial-of-Service Attacks**: Intentional attacks can overwhelm the system, making it impossible for legitimate processes to get the resources they need, causing starvation.
## **Solutions to starvation**
- **Increase Priority Over Time:** If a process or transaction has been waiting too long, its priority can be gradually increased. This ensures it will eventually be served. However, care should be taken as newer processes may end up waiting longer.
- **Modification in Victim Selection algorithm:** If a transaction has been a victim of repeated selections, then the algorithm can be modified by lowering its priority over other transactions.
- **First Come First Serve approach:** A fair scheduling approach i.e. [FCFS](https://www.geeksforgeeks.org/dsa/first-come-first-serve-cpu-scheduling-non-preemptive/) can be adopted, In which the transaction can acquire a lock on an item in the order, in which the requested lock.
- [**Wait-die and wound wait scheme**](https://www.geeksforgeeks.org/dbms/deadlock-in-dbms/)**:** These techniques use timestamps to decide the order of resource allocation, ensuring older transactions are prioritized, which helps prevent starvation.
- **Timeout Mechanism:** A timeout mechanism can be implemented in which a transaction is only allowed to wait for a certain amount of time before it is aborted or restarted. This ensures that no transaction waits indefinitely, and prevents the possibility of starvation.
- **Resource Reservation:** A resource reservation scheme can be used to allocate resources to a transaction before it starts execution. This ensures that the transaction has access to the necessary resources and reduces the chances of waiting for a resource indefinitely.
- **Preemption:** Preemption involves the forcible removal of a lock from a transaction that has been waiting for a long time, in favor of another transaction that has a higher priority or has been waiting for a shorter time. Preemption ensures that no transaction waits indefinitely, and prevents the possibility of starvation.
- **Dynamic Lock Allocation:** In this approach, locks are allocated dynamically based on the current state of the system. The system may analyze the current lock requests and allocate locks in such a way that prevents deadlocks and reduces the chances of starvation.
- **Parallelism:** By allowing multiple transactions to execute in parallel, the system can ensure that no transaction waits indefinitely, and reduces the chances of starvation. This approach requires careful consideration of the potential for conflicts and race conditions between transactions.
## Techniques Used by DBMSs to Prevent or Mitigate Starvation
Starvation in a DBMS can harm system performance and fairness. To solve this problem, different methods are used to make sure resources are shared properly and all processes or transactions get a fair chance. Here’s a closer look at these solutions:
### **Resource Allocation Policies**
**Purpose:** Ensures resources are distributed fairly among transactions and processes.
**How It Works:**
- DBMSs implement policies to allocate resources based on predefined fairness rules.
- These policies prevent specific transactions or processes from being perpetually denied access to resources.
- For example, [round-robin](https://www.geeksforgeeks.org/operating-systems/round-robin-scheduling-in-operating-system/) or proportional sharing techniques can ensure balanced allocation.
**Benefits:**
- No process or transaction consistently gets priority over others.
- Promotes equitable sharing of resources, reducing the risk of starvation.
### **Priority-Based Scheduling**
**Purpose:** Ensures high-priority tasks are executed first while considering fairness for lower-priority ones.
**How It Works:**
- DBMSs assign priorities to transactions or processes based on factors like urgency, importance, or wait time.
- High-priority processes are given preference, but long-waiting low-priority processes can have their priority dynamically increased to prevent starvation.
- Techniques like [**aging**](https://www.geeksforgeeks.org/operating-systems/starvation-and-aging-in-operating-systems/) (gradually increasing the priority of waiting tasks) are used.
**Benefits:**
- Balances immediate needs (high-priority tasks) with fairness (preventing indefinite delays for low-priority tasks).
Read more about Priority-Based Scheduling, [Here](https://www.geeksforgeeks.org/operating-systems/priority-scheduling-in-operating-system/).
### **Timeout Mechanisms**
**Purpose:** Prevents processes or transactions from being blocked indefinitely.
**How It Works:**
- A timeout period is set for resource requests.
- If a transaction waits longer than the timeout period, the resources it holds are released, or the process is restarted with a fresh attempt.
- This prevents deadlocks and prolonged blocking of other processes.
**Benefits:**
- Frees up resources for other waiting transactions.
- Ensures no process is stuck indefinitely, reducing the likelihood of starvation.
### **Resource Management Techniques**
**Purpose:** Prevents any single transaction or process from monopolizing resources.
**How It Works:**
- **Resource Quotas:** Each transaction is allocated a specific amount of resources. Once it reaches the quota, it must release resources before continuing.
- **Resource Limits:** Caps are placed on the number of resources any transaction can hold, ensuring availability for others.
- Dynamic reallocation of unused resources ensures fair distribution.
**Benefits:**
- Limits excessive resource usage by individual transactions.
- Promotes balanced and efficient resource utilization.
These techniques collectively help DBMSs ensure fairness, prevent indefinite waiting, and maintain overall system efficiency, even under high demand or conflicting priorities.
## Disadvantages of Starvation
- **Decreased performance:** Starvation can cause decreased performance in a DBMS by preventing transactions from making progress and causing a bottleneck.
- **Increased response time:** Starvation can increase response time for transactions that are waiting for resources, leading to poor user experience and decreased productivity.
- **Inconsistent data:** If a transaction is unable to complete due to starvation, it may leave the database in an inconsistent state, which can lead to data corruption and other problems.
- **Difficulty in troubleshooting:** Starvation can be difficult to troubleshoot because it may not be immediately apparent which transaction is causing the problem.
- **Potential for deadlock:** If multiple transactions are competing for the same resources, starvation can lead to deadlock, where none of the transactions can proceed, causing a complete system failure.
## Conclusion
Starvation in DBMS is a serious issue that can affect the fairness, efficiency, and overall performance of a database system. It occurs when certain processes or transactions are unable to get the resources they need due to unfair prioritization or poor resource management. This can lead to delays, increased response times, and even system failure.
However, by implementing effective solutions like fair scheduling, timeout mechanisms, and better resource management techniques, starvation can be minimized or prevented altogether. Ensuring all transactions and processes are treated fairly not only improves the performance of the DBMS but also creates a more reliable and efficient system. Addressing starvation is essential for maintaining consistency, ensuring smooth operation, and providing a positive user experience in database systems.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/starvation-in-dbms/)

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
