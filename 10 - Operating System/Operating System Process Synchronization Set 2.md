---
title: "Process Synchronization | Set 2"
subject: "Operating System"
topic: "Inter‐process Communication, Concurrency, and Synchronization"
source: "https://www.geeksforgeeks.org/operating-systems/process-synchronization-set-2/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Inter‐process Communication, Concurrency, and Synchronization"
tags:
  - gate/cs
  - subject/operating-system
  - topic/inter-process-communication-concurrency-and-synchronization
---


> [!abstract] Process Synchronization | Set 2
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Inter‐process Communication, Concurrency, and Synchronization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/process-synchronization-set-2/)

---

# Process Synchronization | Set 2

**Process Synchronization** is a technique which is used to coordinate the process that use shared Data. There are two types of Processes in an Operating Systems:-
1. **Independent Process -** The process that does not affect or is affected by the other process while its execution then the process is called Independent Process. Example The process that does not share any shared variable, database, files, etc.
2. **Cooperating Process -** The process that affect or is affected by the other process while execution, is called a Cooperating Process. Example The process that share file, variable, database, etc are the Cooperating Process.
We have already introduced [Different Terms in Process Synchronization](https://www.geeksforgeeks.org/operating-systems/introduction-of-process-synchronization/).
Process Synchronization is mainly used for Cooperating Process that shares the resources.Let us consider an example of //racing condition image
![](assets/Race-condition-75945cef8a.png)
It is the condition where several processes tries to access the resources and modify the shared data concurrently and outcome of the process depends on the particular order of execution that leads to data inconsistency, this condition is called
**Race Condition :** This condition can be avoided using the technique called Synchronization or Process Synchronization, in which we allow only one process to enter and manipulates the shared data in Critical Section. //diagram of the view of CS
![](assets/CR_repr-283cd74b83.png)
This setup can be defined in various regions like:
- **Entry Section -** It is part of the process which decide the entry of a particular process in the Critical Section, out of many other processes.
- **Critical Section -** It is the part in which only one process is allowed to enter and modify the shared variable.This part of the process ensures that only no other process can access the resource of shared data.
- **Exit Section -** This process allows the other process that are waiting in the Entry Section, to enter into the Critical Sections. It checks that a process that after a process has finished execution in Critical Section can be removed through this Exit Section.
- **Remainder Section -** The other parts of the Code other than Entry Section, Critical Section and Exit Section are known as Remainder Section.
Critical Section problems must satisfy these three requirements:
1. **Mutual Exclusion -** It states that no other process is allowed to execute in the critical section if a process is executing in critical section.
2. **Progress -** When no process is in the critical section, then any process from outside that request for execution can enter in the critical section without any delay. Only those process can enter that have requested and have finite time to enter the process.
3. **Bounded Waiting -** An upper bound must exist on the number of times a process enters so that other processes are allowed to enter their critical sections after a process has made a request to enter its critical section and before that request is granted.
Process Synchronization are handled by two approaches:
1. **Software Approach -** In Software Approach, Some specific Algorithm approach is used to maintain synchronization of the data. Like in Approach One or Approach Two, for a number of two process, a temporary variable like (turn) or boolean variable (flag) value is used to store the data. When the condition is True then the process in waiting State, known as Busy Waiting State. This does not satisfy all the Critical Section requirements. Another Software approach known as Peterson's Solution is best for Synchronization. It uses two variables in the Entry Section so as to maintain consistency, like Flag (boolean variable) and Turn variable(storing the process states). It satisfy all the three Critical Section requirements. //Image of Peterson's Algorithm ![](assets/peterson-1-483161d3c5.png)
2. **Hardware Approach -** The Hardware Approach of synchronization can be done through Lock & Unlock technique.Locking part is done in the Entry Section, so that only one process is allowed to enter into the Critical Section, after it complete its execution, the process is moved to the Exit Section, where Unlock Operation is done so that another process in the Lock Section can repeat this process of Execution.This process is designed in such a way that all the three conditions of the Critical Sections are satisfied. //Image of Lock ![](assets/lock-2-d9c7d20295.png)
**Using Interrupts -**
These are easy to implement.When Interrupt are disabled then no other process is allowed to perform Context Switch operation that would allow only one process to enter into the Critical State. //Image of Interrupts
![](assets/interrupt-1-456e153673.png)
**Test\_and\_Set Operation -**
This allows boolean value (True/False) as a hardware Synchronization, which is atomic in nature i.e no other interrupt is allowed to access.This is mainly used in Mutual Exclusion Application. Similar type operation can be achieved through Compare and Swap function. In this process, a variable is allowed to accessed in Critical Section while its lock operation is ON.Till then, the other process is in Busy Waiting State. Hence Critical Section Requirements are achieved.
**A solution to a process synchronization problem should meet three important criteria:**
• Correctness: Data access synchronization and control synchronization should be performed in accordance with synchronization requirements of the problem.
• Maximum concurrency: A process should be able to operate freely except when it needs to wait for other processes to perform synchronization actions.
• No busy waits: To avoid performance degradation, synchronization should be performed through blocking rather than through busy waits
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/process-synchronization-set-2/)

## GATE CS

- Subject: Operating System
- Topic: Inter‐process Communication, Concurrency, and Synchronization

> [!note] Related notes
>
> - [[Critical Section]]
> - [[Deadlock, Starvation, and Livelock]]
> - [[Dining Philosopher Problem]]
> - [[Dining Philosopher Problem Using Semaphores]]
> - [[Dining-Philosophers Solution Using Monitors]]
> - [[Inter Process Communication]]
> - [[Interprocess Communication Methods]]
> - [[IPC through shared memory]]
> - [[IPC using Message Queues]]
> - [[Lock variable synchronization mechanism]]
