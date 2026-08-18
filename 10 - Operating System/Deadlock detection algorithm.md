---
title: "Deadlock Detection Algorithm in Operating System"
subject: "Operating System"
topic: "Deadlock"
source: "https://www.geeksforgeeks.org/operating-systems/deadlock-detection-algorithm-in-operating-system/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Deadlock"
tags:
  - gate/cs
  - subject/operating-system
  - topic/deadlock
---


> [!abstract] Deadlock Detection Algorithm in Operating System
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Deadlock`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/deadlock-detection-algorithm-in-operating-system/)

---

# Deadlock Detection Algorithm in Operating System

In operating systems, managing resources like memory, files, and processors is very important. Sometimes, processes (or programs) get stuck waiting for each other to release resources, leading to a situation called a deadlock. To handle deadlocks, operating systems use special methods called deadlock detection algorithms. These algorithms help identify when a deadlock has happened so that the system can fix the problem. This is different from methods that try to prevent deadlocks from happening at all, which can be more restrictive.
## Deadlock Detection Algorithm
A deadlock detection algorithm is a technique used by an operating system to identify deadlocks in the system. This algorithm checks the status of processes and resources to determine whether any deadlock has occurred and takes appropriate actions to recover from the deadlock.
Deadlock detection algorithms work by regularly checking the current state of resource usage in the system. They often use a visual tool called a resource allocation graph. This graph shows which processes are using which resources and which resources each process is waiting for. By looking for cycles in this graph, the algorithm can spot deadlocks.
Deadlock detection algorithms are vital in operating systems to prevent processes from getting stuck in a circular wait.
The algorithm employs several times varying data structures:  
- **Available:** A vector of length m indicates the number of available resources of each type.
- **Allocation:** An n\*m matrix defines the number of resources of each type currently allocated to a process. The column represents resource and rows represent a process.
- **Request:** An n\*m matrix indicates the current request of each process. If request[i][j] equals k then process P  i  is requesting k more instances of resource type R  j  .
Now, the [Bankers algorithm](https://www.geeksforgeeks.org/operating-systems/bankers-algorithm-in-operating-system-2/) includes a **Safety Algorithm / Deadlock Detection Algorithm**
The algorithm for finding out whether a system is in a safe state can be described as follows:
### **Steps of Algorithm**
- Let **Work**  and  **Finish**  be vectors of length m and n respectively. Initialize  **Work= Available**  . For  **i=0, 1, ...., n-1**  , if  **Request**  **i**  = 0, then  **Finish[i]**  = true; otherwise,  **Finish[i]**  = false.
- Find an index i such that both
   a)  **Finish[i] == false**
   b)  **Request**  **i**  **<= Work**
   If no such  **i**  exists go to step 4.
- **Work= Work+ Allocation** **i**
   **Finish[i]= true**
   Go to Step 2.
- If **Finish[i]== false**  for some i, 0<=i<n, then the system is in a deadlocked state. Moreover, if  **Finish[i]==false**  the process P  i  is deadlocked.
### Example:
![allocation, request matrix](assets/deadlockdetection-69594d7338.jpg)
- In this, Work = [0, 0, 0] &
   Finish = [false, false, false, false, false]
- **i=0** is selected as both Finish[0] = false and [0, 0, 0]<=[0, 0, 0].
- Work =[0, 0, 0]+[0, 1, 0] =>[0, 1, 0] &
   Finish = [true, false, false, false, false].
- **i=2** is selected as both Finish[2] = false and [0, 0, 0]<=[0, 1, 0].
- Work =[0, 1, 0]+[3, 0, 3] =>[3, 1, 3] &
   Finish = [true, false, true, false, false].
- **i=1** is selected as both Finish[1] = false and [2, 0, 2]<=[3, 1, 3].
- Work =[3, 1, 3]+[2, 0, 0] =>[5, 1, 3] &
   Finish = [true, true, true, false, false].
- **i=3** is selected as both Finish[3] = false and [1, 0, 0]<=[5, 1, 3].
- Work =[5, 1, 3]+[2, 1, 1] =>[7, 2, 4] &
   Finish = [true, true, true, true, false].
- **i=4** is selected as both Finish[4] = false and [0, 0, 2]<=[7, 2, 4].
- Work =[7, 2, 4]+[0, 0, 2] =>[7, 2, 6] &
   Finish = [true, true, true, true, true].
- Since Finish is a vector of all true it means **there is no deadlock**  in this example.
## Other Algorithm for Deadlock Detection
- **Wait-For Graph:** A graphical representation of the system's processes and resources. A directed edge is created from a process to a resource if the process is waiting for that resource. A cycle in the graph indicates a deadlock.
- **Banker's Algorithm:** A resource allocation algorithm that ensures that the system is always in a safe state, where deadlocks cannot occur.
- **Resource Allocation Graph** : A graphical representation of processes and resources, where a directed edge from a process to a resource means that the process is currently holding that resource. Deadlocks can be detected by looking for cycles in the graph.
- **Detection by System Modeling:** A mathematical model of the system is created, and deadlocks can be detected by finding a state in the model where no process can continue to make progress.
- **Timestamping** : Each process is assigned a timestamp, and the system checks to see if any process is waiting for a resource that is held by a process with a lower timestamp.
These algorithms are used in different operating systems and systems with different resource allocation and synchronization requirements. The choice of algorithm depends on the specific requirements of the system and the trade-offs between performance, complexity, and accuracy.
If a system does not employ either a deadlock prevention or deadlock avoidance algorithm then a deadlock situation may occur. In this case- 
- Apply an algorithm to examine the system's state to determine whether deadlock has occurred.
- Apply an algorithm to recover from the deadlock. For more refer-[Deadlock Recovery](https://www.geeksforgeeks.org/operating-systems/deadlock-detection-recovery/)
## Advantages of Deadlock Detection Algorithms
- **Improved System Stability:** Deadlocks are a major concern in [operating systems](https://www.geeksforgeeks.org/operating-systems/what-is-an-operating-system/) , and detecting and resolving deadlocks can help to improve the stability of the system.
- **Better Resource Utilization:** By detecting deadlocks and freeing resources, the operating system can ensure that resources are efficiently utilized and that the system remains responsive to user requests.
- **Easy Implementation:** Some deadlock detection algorithms, such as the [Wait-For Graph](https://www.geeksforgeeks.org/computer-networks/wait-for-graph-deadlock-detection-in-distributed-system/) , are relatively simple to implement and can be used in a wide range of operating systems and systems with different resource allocation and synchronization requirements.
## Disadvantages of Deadlock Detection Algorithms
- **Performance Overhead:** Deadlock detection algorithms can introduce a significant overhead in terms of performance, as the system must regularly check for deadlocks and take appropriate action.
- **Complexity:** Some deadlock detection algorithms, such as the [Resource Allocation Graph](https://www.geeksforgeeks.org/operating-systems/resource-allocation-graph-rag-in-operating-system/) or Timestamping, are more complex to implement and require a deeper understanding of the system and its behavior.
- **False Positives and Negatives:** Deadlock detection algorithms are not perfect and may produce false positives or negatives, indicating the presence of deadlocks when they do not exist or failing to detect deadlocks that do exist.
- Overall, the choice of deadlock detection algorithm depends on the specific requirements of the system, the trade-offs between performance, complexity, and accuracy, and the risk tolerance of the system. The operating system must balance these factors to ensure that deadlocks are detected and resolved effectively and efficiently.
## Conclusion
Deadlock detection algorithms are important for identifying and resolving situations where processes get stuck waiting for resources held by each other. By regularly checking resource usage and identifying cycles of dependencies, these algorithms help maintain system stability and efficiency. This ensures that processes can run smoothly without being interrupted by [deadlocks](https://www.geeksforgeeks.org/operating-systems/introduction-of-deadlock-in-operating-system/).
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/deadlock-detection-algorithm-in-operating-system/)

## GATE CS

- Subject: Operating System
- Topic: Deadlock

> [!note] Related notes
>
> - [[Banker’s Algorithm]]
> - [[Banker’s Algorithm Print all the safe state]]
> - [[Deadlock Detection And Recovery]]
> - [[Deadlock Prevention And Avoidance]]
> - [[Methods of resource allocation to processes by operating system]]
> - [[Process Management Deadlock Introduction]]
> - [[Program for Banker’s Algorithm Set 1]]
> - [[Program for Deadlock free condition]]
> - [[Resource Allocation Graph]]
> - [[Allocating kernel memory]]
