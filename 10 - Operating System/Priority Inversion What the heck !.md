---
title: "Priority Inversion in Operating Systems"
subject: "Operating System"
topic: "Inter‐process Communication, Concurrency, and Synchronization"
source: "https://www.geeksforgeeks.org/operating-systems/priority-inversion/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Inter‐process Communication, Concurrency, and Synchronization"
tags:
  - gate/cs
  - subject/operating-system
  - topic/inter-process-communication-concurrency-and-synchronization
---


> [!abstract] Priority Inversion in Operating Systems
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Inter‐process Communication, Concurrency, and Synchronization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/priority-inversion/)

---

# Priority Inversion in Operating Systems

Priority inversion is a scheduling problem where a low-priority task holds a resource (like a lock) that a high-priority task needs. This forces the high-priority task to wait for the low one.
### Causes of Priority Inversion
- A low-priority task (L) acquires a shared resource that a high-priority task (H) will need later. When H requests that resource, it must wait for L to release it.
- While L holds that resource, a medium-priority task (M) which doesn’t require the resource becomes runnable and preempts L, because M has higher priority than L.
- As a result, the high-priority task (H) remains blocked, even though H outranks both L and M. Effectively, the priority order is inverted: M runs before H, despite H having the highest priority. This leads to unbounded priority inversion
### Types of Priority Inversion
- Bounded Priority Inversion
- Unbounded Priority Inversion
**1. Bounded Priority Inversion:** Bounded priority inversion occurs when a high-priority task is delayed by a lower-priority task holding a resource. The delay is predictable and limited to the time the lower-priority task holds the resource.
![priorityinversion](assets/priorityinversion-f615ce10f9.jpeg)
Bounded Priority Inversion
**Explanation:** Consider three tasks with the following priorities
- L (Low priority): Task L holds a mutex to access a shared resource.
- M (Medium priority): Task M does not require the shared resource.
- H (High priority): Task H needs the shared resource held by L.
**Sequence of Events:**
1. L acquires the mutex and enters its critical section.
2. H arrives and attempts to acquire the mutex but is blocked, waiting for L to release it.
3. M becomes ready to run and preempts L.
4. M executes until it completes its task.
5. L resumes, finishes its critical section, and releases the mutex.
6. H acquires the mutex and enters its critical section.
Outcome: H's execution is delayed by the time L holds the mutex and the time M runs. The total delay is predictable and equals the sum of L's critical section time and M's execution time.
**2. Unbounded Priority Inversion:** Unbounded priority inversion occurs when a medium-priority task (M) preempts L while it holds the lock. This action delays L from releasing the resource, which in turn delays H. The delay H experiences becomes unpredictable and can potentially be indefinite, hence the term "unbounded."
![unboundedpriorityinversionn](assets/unboundedpriorityinversionn-a7a4679e1f.jpeg)
Unbounded Priority Inversion
**Explanation:**
- Task L (Low Priority) starts and acquires a lock on a shared resource.
- Task H (High Priority) starts and needs the same lock. It gets blocked because Task L has it.
- This situation, where a high-priority task waits for a low-priority one, is called Priority Inversion.
- Task M (Medium Priority) now starts. Its priority is higher than Task L's.
- The scheduler lets Task M preempt Task L, so Task M begins running.
- This is the critical problem: Task M runs, preventing Task L from finishing its work.
- Because Task L can't run, it cannot release the lock.
- This means Task H remains blocked indefinitely, even though it's the most important task.
- The high-priority task is stuck waiting for a medium-priority task to finish, which is a serious flaw. This can cause a system failure or trigger a watchdog timer.
## Solutions to Priority Inversion
Priority inversion can lead to significant delays and system inefficiencies. To resolve or prevent this issue, the following solutions are commonly used:
- **Priority Inheritance**: Temporarily elevates the priority of the low-priority task holding the resource to match that of the highest-priority waiting task, ensuring timely resource release .
- **Priority Ceiling Protocol**: Assigns a maximum priority to each resource, preventing tasks with lower priorities from acquiring resources needed by higher-priority tasks .
- **Avoiding Blocking**: Utilizes non-blocking algorithms or designs systems to minimize shared resource usage, thereby reducing the chances of priority inversion .
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/priority-inversion/)

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
