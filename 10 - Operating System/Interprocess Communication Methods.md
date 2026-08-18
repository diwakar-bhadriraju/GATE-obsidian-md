---
title: "Methods in Inter Process Communication"
subject: "Operating System"
topic: "Inter‐process Communication, Concurrency, and Synchronization"
source: "https://www.geeksforgeeks.org/operating-systems/methods-in-interprocess-communication/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Inter‐process Communication, Concurrency, and Synchronization"
tags:
  - gate/cs
  - subject/operating-system
  - topic/inter-process-communication-concurrency-and-synchronization
---


> [!abstract] Methods in Inter Process Communication
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Inter‐process Communication, Concurrency, and Synchronization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/methods-in-interprocess-communication/)

---

# Methods in Inter Process Communication

Inter-Process Communication (IPC) enables processes to interact and share data within an operating system. It provides mechanisms for coordinating tasks and managing dependencies between processes. IPC ensures the smooth execution of concurrent programs while maintaining efficiency and reliability.
- Facilitates interaction between independent processes
- Helps manage dependencies and task coordination
- Maintains efficiency and reliability in concurrent execution
![methods_in_ipc](assets/methods_in_ipc-59c549b1ca.webp)
## 1. Shared Memory
Shared Memory is an IPC method in which multiple processes share a common memory region to exchange data. Processes communicate by directly reading from and writing to this shared memory space, making it the fastest IPC technique. Since multiple processes access the same memory, synchronization mechanisms are required to prevent data inconsistency.
- Common memory space shared by processes
- Very fast communication
- No data copying between processes
- Requires synchronization (semaphores, mutexes)
[Shared memory](https://www.geeksforgeeks.org/operating-systems/ipc-shared-memory/) is best suited for applications that require frequent data exchange and high performance. It is commonly used in real-time systems and large-scale applications where speed is critical.
## 2. Message Passing
Message Passing is an IPC technique where processes communicate by sending and receiving messages through the operating system. The processes do not share memory, which makes this method safer and easier to manage. However, due to system call overhead, it is slower than shared memory.
- Communication through messages
- No shared memory required
- Managed by the operating system
- Safer but slower than shared memory
[Message passing](https://www.geeksforgeeks.org/operating-systems/ipc-using-message-queues/) supports both synchronous and asynchronous communication between processes. It is widely used in distributed systems where processes may run on different machines.
## 3. Pipes
Pipes are unidirectional communication channels used for inter-process communication between two related processes. One process writes data into the pipe, and the other reads it in a sequential manner. Pipes are simple and efficient for small data transfers on the same system.
- Unidirectional communication
- Used between related processes
- Simple and easy to use
- Types: Anonymous pipes and Named pipes (FIFOs)
## 4. Sockets
Sockets are communication endpoints that allow processes to communicate either on the same machine or over a network. They are commonly used in client–server systems. Sockets support different protocols such as TCP for reliable communication and UDP for faster communication.
- Supports network communication
- Works between different systems
- Uses TCP and UDP protocols
- Common in client–server applications
## 5. Semaphores
Semaphores are synchronization tools used in IPC to control access to shared resources. They ensure that only one process can enter a critical section at a time, preventing race conditions and data corruption. Semaphores are often used along with shared memory.
- Used for synchronization
- Prevents race conditions
- Controls access to shared resources
- Ensures mutual exclusion
## 6. Message Queues
Message Queues allow processes to communicate by sending messages to a queue managed by the operating system kernel. Messages remain in the queue until the receiving process retrieves them. This method supports asynchronous communication and provides reliable message delivery.
- Kernel-managed message storage
- Asynchronous communication
- Processes need not run simultaneously
- Reliable but slower than shared memory
Other methods include Memory-Mapped Files, Signals, Futures/Promises, and middleware-based message passing. These methods are used as per the communication requirements, system design, and process locations.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/methods-in-interprocess-communication/)

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
> - [[IPC through shared memory]]
> - [[IPC using Message Queues]]
> - [[Lock variable synchronization mechanism]]
> - [[Mutex vs Semaphore]]
