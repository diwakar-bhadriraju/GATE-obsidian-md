---
title: "Deadlock Detection And Recovery"
subject: "Operating System"
topic: "Deadlock"
source: "https://www.geeksforgeeks.org/operating-systems/deadlock-detection-recovery/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Deadlock"
tags:
  - gate/cs
  - subject/operating-system
  - topic/deadlock
---


> [!abstract] Deadlock Detection And Recovery
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Deadlock`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/deadlock-detection-recovery/)

---

# Deadlock Detection And Recovery

Deadlock detection and recovery is the mechanism of detecting and resolving deadlocks in an operating system. In operating systems, deadlock recovery is important to keep everything running smoothly. A deadlock occurs when two or more processes are blocked, waiting for each other to release the resources they need.
- Deadlock detection is the process of identifying when processes are stuck waiting for resources held by other processes.
- Recovery is the method of resolving the deadlock to allow the system to continue functioning.
- Detection is done using techniques like Resource Allocation Graphs (RAG) or Wait-for Graphs.
- Once a deadlock is detected, recovery methods include process termination, resource preemption, or process rollback.
### Approaches to Deadlock Detection and Recovery
- **Prevention**: The operating system takes steps to prevent deadlocks from occurring by ensuring that the system is always in a safe state, where deadlocks cannot occur. This is achieved through resource allocation algorithms such as the [Banker's Algorithm](https://www.geeksforgeeks.org/operating-systems/bankers-algorithm-in-operating-system-2/).
- **Detection and Recovery:** If deadlocks do occur, the operating system must detect and resolve them. Deadlock detection algorithms, such as the Wait-For Graph, are used to identify deadlocks, and recovery algorithms, such as the Rollback and Abort algorithm, are used to resolve them. The recovery algorithm releases the resources held by one or more processes, allowing the system to continue to make progress.
### Prevention vs. Detection/Recovery
- Deadlock **prevention** aims to stop deadlocks entirely by carefully managing resource allocation rules.
- Deadlock **detection and recovery** identify deadlocks after they occur and then apply methods to resolve them.
- These strategies are important because deadlocks affect overall **system stability, performance, and reliability**.
- The operating system must choose an approach based on **system requirements**, such as workload type and resource usage patterns.
- Each method comes with trade-offs involving **performance overhead**, **implementation complexity**, and **acceptable risk levels**.
- A balanced strategy helps ensure deadlocks are **properly detected, managed, and resolved** without harming system efficiency.
Read more about - [Deadlock Prevention and Avoidance](https://www.geeksforgeeks.org/operating-systems/deadlock-prevention/)
## **Deadlock Detection**
Deadlock detection is a mechanism in operating systems used to identify whether a set of processes is stuck in a deadlock state. It analyzes resource allocation and process dependencies to detect cycles and determine if processes are waiting indefinitely for resources.
### **1. If Resources Have a Single Instance**
In this case for Deadlock detection, we can run an algorithm to check for the cycle in the Resource Allocation Graph. The presence of a cycle in the graph is a sufficient condition for deadlock.
In the below diagram, resource 1 and resource 2 have single instances. There is a cycle R1 → P1 → R2 → P2. So, Deadlock is Confirmed. 
![frame_3197.webp](assets/frame_3197-32e091447d.webp)
### **2. If There are Multiple Instances of Resource**s
Detection of the cycle is necessary but not a sufficient condition for deadlock detection, in this case, the system may or may not be in deadlock varies according to different situations.
For systems with multiple instances of resources, algorithms like [Banker's Algorithm](https://www.geeksforgeeks.org/operating-systems/bankers-algorithm-in-operating-system-2/) can be adapted to periodically check for deadlocks.
### **3. Wait-For Graph Algorithm**
The [Wait-For Graph Algorithm](https://www.geeksforgeeks.org/computer-networks/wait-for-graph-deadlock-detection-in-distributed-system/) is a deadlock detection algorithm used to detect deadlocks in a system where resources can have multiple instances. The algorithm works by constructing a Wait-For Graph, which is a directed graph that represents the dependencies between processes and resources.
![d.webp](assets/d-6dc220a921.webp)
## Deadlock Recovery
A traditional operating system such as Windows doesn't deal with deadlock recovery as it is a time and space-consuming process. [Real-time operating systems](https://www.geeksforgeeks.org/operating-systems/real-time-operating-system-rtos/) use Deadlock recovery. 
- **Killing The Process:** Killing all the processes involved in the deadlock. Killing process one by one. After killing each process check for deadlock again and keep repeating the process till the system recovers from deadlock. Killing all the processes one by one helps a system to break circular wait conditions.
- **Process Rollback**: Rollback deadlocked processes to a previously saved state where the deadlock condition did not exist. It requires checkpointing to periodically save the state of processes.
- **Resource Preemption:** Resources are preempted from the processes involved in the deadlock, and preempted resources are allocated to other processes so that there is a possibility of recovering the system from the deadlock. In this case, the system goes into starvation.
- **Concurrency Control:** Concurrency control mechanisms prevent data inconsistencies in systems with multiple concurrent processes. They ensure that processes do not access the same data simultaneously, avoiding errors and potential deadlocks. By managing access to shared resources, these mechanisms help maintain system stability and prevent processes from blocking each other.
![frame_35](assets/frame_35-4eaae04185.webp)
Kind of Recovery
## Advantages of Deadlock Detection and Recovery
- **Improved System Stability:** Deadlocks can cause system-wide stalls, and detecting and resolving deadlocks can help to improve the stability of the system.
- **Better Resource Utilization:** By detecting and resolving deadlocks, the operating system can ensure that resources are efficiently utilized and that the system remains responsive to user requests.
- **Better System Design**: Deadlock detection and recovery algorithms can provide insight into the behavior of the system and the relationships between processes and resources, helping to inform and improve the design of the system.
## Disadvantages of Deadlock Detection and Recovery
- **Performance Overhead:** Deadlock detection and recovery algorithms can introduce a significant overhead in terms of performance, as the system must regularly check for deadlocks and take appropriate action to resolve them.
- **Complexity:** Deadlock detection and recovery algorithms can be complex to implement, especially if they use advanced techniques such as the [Resource Allocation Graph](https://www.geeksforgeeks.org/operating-systems/resource-allocation-graph-rag-in-operating-system/) or Timestamping.
- **False Positives and Negatives:** [Deadlock detection algorithms](https://www.geeksforgeeks.org/operating-systems/deadlock-detection-algorithm-in-operating-system/) are not perfect and may produce false positives or negatives, indicating the presence of deadlocks when they do not exist or failing to detect deadlocks that do exist.
- **Risk of Data Loss**: In some cases, recovery algorithms may require rolling back the state of one or more processes, leading to data loss or corruption.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/deadlock-detection-recovery/)

## GATE CS

- Subject: Operating System
- Topic: Deadlock

> [!note] Related notes
>
> - [[Banker’s Algorithm]]
> - [[Banker’s Algorithm Print all the safe state]]
> - [[Deadlock detection algorithm]]
> - [[Deadlock Prevention And Avoidance]]
> - [[Methods of resource allocation to processes by operating system]]
> - [[Process Management Deadlock Introduction]]
> - [[Program for Banker’s Algorithm Set 1]]
> - [[Program for Deadlock free condition]]
> - [[Resource Allocation Graph]]
> - [[Allocating kernel memory]]
