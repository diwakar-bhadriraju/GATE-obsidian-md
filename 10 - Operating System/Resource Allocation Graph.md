---
title: "Resource Allocation Graph (RAG)"
subject: "Operating System"
topic: "Deadlock"
source: "https://www.geeksforgeeks.org/operating-systems/resource-allocation-graph-rag-in-operating-system/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Deadlock"
tags:
  - gate/cs
  - subject/operating-system
  - topic/deadlock
---


> [!abstract] Resource Allocation Graph (RAG)
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Deadlock`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/resource-allocation-graph-rag-in-operating-system/)

---

# Resource Allocation Graph (RAG)

A Resource Allocation Graph (RAG) is a visual way to understand how resources are assigned in an operating system. Instead of using only tables to show which resources are allocated, requested or available, the RAG uses nodes and edges to clearly illustrate relationships between processes and their required resources.
- RAG shows which resources are allocated and which are requested by processes.
- It helps to visualize deadlocks more clearly than tables.
- RAG shows how allocation and requests affect the whole system.
- Processes = circles, Resources = squares and edges show allocation or request.
## Types of Vertices in RAG
In a Resource Allocation Graph, there are two types of vertices
**1. Process Vertex:**  Every process will be represented as a process vertex. Generally, the process will be represented with a circle.
**2. Resource Vertex:** Every resource will be represented as a resource vertex. It is also two types:
- **Single Instance Resource**: A resource with only one copy. In RAG, it is shown as a single node and only one process can use it at a time.
- **Multi Instance Resource**: A resource with multiple copies. In RAG, it is shown with multiple instances, so several processes can use different copies simultaneously.
![frame_3197](assets/frame_3197-5f42e516fe.webp)
Types of Vertices
## Types of Edges in RAG
There are two types of edges in RAG:
- **Assign Edge:** If you already assign a resource to a process then it is called Assign edge. This is shown by an arrow from the resource vertex to the process vertex.
- **Request Edge**: A request edge represents that a process is currently requesting a resource. This is shown by an arrow from the process vertex to the resource vertex.
![frame_3196](assets/frame_3196-b2f76e2002.webp)
Types of Edges
So, if a process is using a resource, an arrow is drawn from the resource node to the process node. If a process is requesting a resource, an arrow is drawn from the process node to the resource node.
### Example 1: (Single Instances RAG)
![frame_3195](assets/frame_3195-16a204a862.webp)
Single Instance with deadlock
If there is a cycle in the Resource Allocation Graph and each resource in the cycle provides only one instance, then the processes will be in deadlock. For example, if process P1 holds resource R1, process P2 holds resource R2 and process P1 is waiting for R2 and process P2 is waiting for R1, then process P1 and process P2 will be in deadlock.
![frame_3194](assets/frame_3194-2eeaeede3c.webp)
Single Instance without deadlock
Here's another example, that shows Processes P1 and P2 acquiring resources R1 and R2 while process P3 is waiting to acquire both resources. In this example, there is no deadlock because there is no circular dependency. So cycle in single-instance resource type is the sufficient condition for deadlock.
### Example 2: (Multi-instances RAG)
![frame_3193](assets/frame_3193-ae669f354c.webp)
Multi Instances without deadlock
From the above example, it is not possible to say the RAG is in a safe state or in an unsafe state. So to see the state of this RAG, let's construct the allocation matrix and request matrix.
![frame_3204](assets/frame_3204-cd0d5dd1bd.webp)
Resource Allocation Table
- The total number of processes are three: P1, P2 & P3 and the total number of resources are two: R1 & R2.
- **Allocation matrix:** For constructing the allocation matrix, just go to the resources and see to which process it is allocated.
  R1 is allocated to P1, therefore write 1 in allocation matrix and similarly, R2 is allocated to P2 as well as P3 and for the remaining element just write 0.
- **Request matrix:** In order to find out the request matrix, you have to go to the process and see the outgoing edges.
  P1 is requesting resource R2, so write 1 in the matrix and similarly, P2 requesting R1 and for the remaining element write 0.
  So now available resource is = (0, 0).
- **Checking deadlock (safe or not)**
![Checking deadlock](assets/hgh-1-304f234b0b.jpg)
- So there is no deadlock in this RAG. Even though there is a cycle, still there is no deadlock. Therefore in multi-instance resource cycle is not sufficient condition for deadlock.
![frame_3192](assets/frame_3192-184c2d04c0.webp)
Multi Instances with deadlock
Above example is the same as the previous example except that, the process P3 requesting for resource R1. So the table becomes as shown in below.
![frame_3191](assets/frame_3191-87b4fff921.webp)
Resource Allocation Table
So, the Available resource is = (0, 0), but requirement are (0, 1), (1, 0) and (1, 0). So you can't fulfill any one requirement. Therefore, it is in deadlock. Therefore every cycle in a multi-instance resource type graph is not a deadlock. If there has to be a deadlock, there has to be a cycle. So in case of RAG with multi-instance resource type, the cycle is a necessary condition for deadlock but not sufficient.
## Deadlock Detection using Resource Allocation Graph
A **Resource Allocation Graph (RAG)** is used to detect deadlocks by analyzing the relationships between processes and resources in a system. It visually represents how resources are allocated and requested.
- **If graph contains no cycles** no deadlock.
- **If graph contains a cycle** if only one instance per resource type, then deadlock.
- **If graph contains a cycle** if several instances per resource type, possibility of deadlock
Figure given below is an example of System in a Deadlock because all processes are **blocked** and cannot proceed
- P1 is waiting for R1, held by P2.
- P2 is waiting for R3, held by P3.
- P3 is waiting for an instance of R2, whose one instance is held by p1 and other is held by p2l.
![RAG1](assets/RAG1-f82922e1b6.webp)
RAG with Deadlock
Following is an example of Resource Allocation Graph with a cycle but no Deadlock
- The system has enough resources to break the cycle.
- At least one process in the cycle can complete and release resources, allowing the remaining processes to proceed.
![RAG2](assets/RAG2-a7b9618663.webp)
RAG with a cycle but no Deadlock
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/resource-allocation-graph-rag-in-operating-system/)

## GATE CS

- Subject: Operating System
- Topic: Deadlock

> [!note] Related notes
>
> - [[Banker’s Algorithm]]
> - [[Banker’s Algorithm Print all the safe state]]
> - [[Deadlock detection algorithm]]
> - [[Deadlock Detection And Recovery]]
> - [[Deadlock Prevention And Avoidance]]
> - [[Methods of resource allocation to processes by operating system]]
> - [[Process Management Deadlock Introduction]]
> - [[Program for Banker’s Algorithm Set 1]]
> - [[Program for Deadlock free condition]]
> - [[Allocating kernel memory]]
