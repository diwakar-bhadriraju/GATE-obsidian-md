---
title: "Conflict Serializability in DBMS"
subject: "Database Management System"
topic: "Transactions and Concurrency Control"
source: "https://www.geeksforgeeks.org/dbms/conflict-serializability-in-dbms/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Database Management System/Transactions and Concurrency Control"
tags:
  - gate/cs
  - subject/database-management-system
  - topic/transactions-and-concurrency-control
---


> [!abstract] Conflict Serializability in DBMS
> 
> **Subject:** `Database Management System` &nbsp;|&nbsp; **Topic:** `Transactions and Concurrency Control`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dbms/conflict-serializability-in-dbms/)

---

# Conflict Serializability in DBMS

Conflict Serializability ensures that a concurrent schedule produces the same result as some serial execution by reordering non-conflicting operations. It maintains data consistency and is stricter than View Serializability, which allows more flexibility but still preserves correctness.
- **Non-conflicting operations:** Two operations are considered non-conflicting if they operate on separate data items, or if they involve the same data item but both are read operations.
## Conflicting Operations
Two operations are said to be conflicting if all conditions are satisfied: 
- They belong to different transactions
- They operate on the same data item
- Atleast one of them is a write operation
| **Operation by Tᵢ** | **Operation by Tⱼ** | **Conflict Status** |
| --- | --- | --- |
| read(Q) | read(Q) | No Conflict |
| read(Q) | write(Q) | Conflict |
| write(Q) | read(Q) | Conflict |
| write(Q) | write(Q) | Conflict |
Consider the following schedule: 
> S1: R1(A), W1(A), R2(A), W2(A), R1(B), W1(B), R2(B), W2(B)
If Oi and Oj are two operations in a transaction and Oi< Oj (Oi is executed before Oj), same order will follow in the schedule as well. Using this property, we can get two transactions of schedule S1: 
> T1: R1(A), W1(A), R1(B), W1(B)
> T2: R2(A), W2(A), R2(B), W2(B)
**Possible Serial Schedules are: T1->T2 or T2->T1** 
-> **Swapping non-conflicting operation**s R2(A) and R1(B) in S1, the schedule becomes, 
> **S11:** R1(A), W1(A), R1(B), **W**2**(A)**,** R2(A), **W**1**(B)**,** R2(B), W2(B)
-> Similarly, **swapping non-conflicting operations** W2(A) and W1(B) in S11, the schedule becomes, 
> **S12:** R1(A), W1(A), R1(B), W1(B), R2(A), W2(A), R2(B), W2(B)
S12 is a serial schedule in which all operations of T1 are performed before starting any operation of T2. Since S has been transformed into a serial schedule S12 by swapping non-conflicting operations of S1, S1 is conflict serializable.
Let us take another Schedule: 
> S2: R2(A), W2(A), R1(A), W1(A), R1(B), W1(B), R2(B), W2(B)
Two transactions will be:  
> T1: R1(A), W1(A), R1(B), W1(B)
> T2: R2(A), W2(A), R2(B), W2(B)
**Possible Serial Schedules are: T1->T2 or T2->T1** 
Original Schedule is as:  
> **S2:** R2(A), W2(A), **R**1**(A)**,** W1(A), R1(B), W1(B), **R**2**(B)**,** W2(B)
Swapping non-conflicting operations R1(A) and R2(B) in S2, the schedule becomes, 
> **S21:** R2(A), W2(A), R2(B), **W**1**(A)**,** R1(B), W1(B), R1(A), **W**2**(B)**
Similarly, swapping non-conflicting operations W1(A) and W2(B) in S21, the schedule becomes,  
> **S22:** R2(A), W2(A), R2(B), W2(B), R1(B), W1(B), R1(A), W1(A)
In schedule S22, all operations of T2 are performed first, but operations of T1 are not in order (order should be R1(A), W1(A), R1(B), W1(B)). So S2 is not conflict serializable.
## Testing Conflict Serializability
A Precedence Graph or Serialization Graph is used commonly to test the Conflict Serializability of a schedule. It is a directed Graph (V, E) consisting of a set of nodes V = {T1, T2, T3..........Tn} and a set of directed edges E = {e1, e2, e3..................em}.
The graph contains one node for each Transaction Ti. An edge ei is of the form Tj --> Tk where Tj is the starting node of ei and Tk is the ending node of ei. An edge ei​ is drawn from node Tj to node Tk if a conflicting operation in Tj occurs before the corresponding conflicting operation in Tk​ in the schedule. The Algorithm can be written as:
- Create a node T in the graph for each participating transaction in the schedule.
- For the conflicting operation read\_item(X) and write\_item(X) - If a Transaction Tj executes a read\_item (X) after Ti executes a write\_item (X), draw an edge from Ti to Tj in the graph.
- For the conflicting operation write\_item(X) and read\_item(X) - If a Transaction Tj executes a write\_item (X) after Ti executes a read\_item (X), draw an edge from Ti to Tj in the graph.
- For the conflicting operation write\_item(X) and write\_item(X) - If a Transaction Tj executes a write\_item (X) after Ti executes a write\_item (X), draw an edge from Ti to Tj in the graph.
- Schedule S is serializable if there is no cycle in the precedence graph.
If there is no cycle in the precedence graph, it means we can construct a serial schedule S' which is conflict equivalent to schedule S. The serial schedule S' can be found by [Topological Sorting](https://www.geeksforgeeks.org/dsa/topological-sorting-indegree-based-solution/) of the acyclic precedence graph. Such schedules can be more than 1. For example, Consider the schedule S:
> S: r1(x) r1(y) w2(x) w1(x) r2(y)
## Creating Precedence Graph
**Step 1:** Make two nodes corresponding to Transaction T1 and T2.
![Step 1](assets/2-11-8759e53ecc.webp)
**Step 2:** For the conflicting pair r1(x) w2(x), where r1(x) happens before w2(x), draw an edge from T1 to T2.
![Step 2](assets/3-10-7c617c0683.png)
**Step 3:** For the conflicting pair w2(x) w1(x), where w2(x) happens before w1(x), draw an edge from T2 to T1.
![Step 3](assets/4-9-b9b6908b5b.png)
Since the graph is cyclic, we can conclude that it is not conflict serializable to any schedule serial schedule. Let us try to infer a serial schedule from this graph using topological ordering.
The edge T1-->T2 tells that T1 should come before T2 in the linear ordering. The edge T2 --> T1 tells that T2 should come before T1 in the linear ordering. So, we can not predict any particular order (when the graph is cyclic). Therefore, no serial schedule can be obtained from this graph. 
Consider another schedule S1:
> S1: r1(x) r3(y) w1(x) w2(y) r3(x) w2(x)
![Precedence Graph](assets/22-7-6eb2290957.png)
The graph for this schedule is: Since the graph is acyclic, the schedule is conflict serializable. Performing Topological Sort on this graph would give us a possible serial schedule that is conflict equivalent to schedule S1. In Topological Sort, we first select the node with in-degree 0, which is T1. This would be followed by T3 and T2. So, S1 is [conflict serializable](https://www.geeksforgeeks.org/dbms/conflict-serializability-in-dbms/) since it is conflict equivalent to the [serial schedule](https://www.geeksforgeeks.org/dbms/equivalent-serial-schedule-of-conflict-serializable-schedule-in-dbms/) T1 T3 T2.
## Advantages of Conflict Serializability
- **Consistency:** Conflict serializability guarantees that the transactions' outcomes correspond to the sequence in which they were carried out.
- **Correctness:** Regardless of the order in which transactions were submitted, conflict serializability guarantees that transactions are executed correctly.
- **Decreased Overhead:** By doing away with pointless locking and other conflict resolution techniques, conflict serializability lowers overhead.
- **Enhanced Concurrency:** By enabling concurrent execution of operations without causing conflicts, conflict serializability enhances concurrency.
## Disadvantages of Conflict Serializability
- **Complexity:** Conflict serializability can be complex to implement, especially in large and complex databases.
- **Reduced Performance:** Conflict serializability can reduce performance by introducing delays and overhead due to locking and other conflict resolution mechanisms.
- **Limited Concurrency:** Conflict serializability can limit the degree of concurrency in the system because it may delay some transactions to avoid conflicts.
- **Increased Overhead:** Conflict serializability requires additional overhead to maintain the order of the transactions and ensure that they do not conflict with each other.
> Read more about [Precedence Graph for testing Conflict Serializability](https://www.geeksforgeeks.org/dbms/precedence-graph-for-testing-conflict-serializability-in-dbms/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dbms/conflict-serializability-in-dbms/)

## GATE CS

- Subject: Database Management System
- Topic: Transactions and Concurrency Control

> [!note] Related notes
>
> - [[ACID Properties in DBMS]]
> - [[Cascadeless in DBMS]]
> - [[Categories of Two Phase Locking]]
> - [[Concurrency Control Techniques]]
> - [[Database Recovery Techniques]]
> - [[Deadlock in DBMS]]
> - [[Graph Based Protocol]]
> - [[How to test if two schedules are View Equal or not]]
> - [[Implementation of Locking in DBMS]]
> - [[Introduction to Concurrency Control]]
