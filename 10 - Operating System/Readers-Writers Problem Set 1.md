---
title: "Readers-Writers Problem"
subject: "Operating System"
topic: "Inter‐process Communication, Concurrency, and Synchronization"
source: "https://www.geeksforgeeks.org/operating-systems/readers-writers-problem-set-1-introduction-and-readers-preference-solution/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Inter‐process Communication, Concurrency, and Synchronization"
tags:
  - gate/cs
  - subject/operating-system
  - topic/inter-process-communication-concurrency-and-synchronization
---


> [!abstract] Readers-Writers Problem
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Inter‐process Communication, Concurrency, and Synchronization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/readers-writers-problem-set-1-introduction-and-readers-preference-solution/)

---

# Readers-Writers Problem

The Readers-Writers Problem is a classic synchronization issue in operating systems. It deals with coordinating access to shared data (e.g., database, file) by multiple processes or threads.
- **Readers**: Multiple readers can read the shared data **simultaneously** without causing inconsistency (since they don’t modify data).
- **Writers**: Only **one writer** can access the data at a time, and no readers are allowed while writing (to prevent data corruption).
The challenge is to design a synchronization scheme that ensures:
1. Multiple readers can access data together if no writer is writing.
2. Writers have exclusive access no other reader or writer can enter during writing.
## Variants of the Problem
**1. Readers Preference**
- Readers are given priority.
- No reader waits if the resource is available for reading, even if a writer is waiting.
- Writers may suffer from **starvation**.
**2. Writers Preference**
- Writers are prioritized over readers.
- Ensures writers won’t starve, but readers may wait longer.
### Solution When Reader Has The Priority Over Writer
Here priority means, no reader should wait if the shared resource is currently open for reading. There are four types of cases that could happen here.
| Case | Process 1 | Process 2 | Allowed/Not Allowed |
| --- | --- | --- | --- |
| Case 1 | Writing | Writing | Not Allowed |
| Case 2 | Writing | Reading | Not Allowed |
| Case 3 | Reading | Writing | Not Allowed |
| Case 4 | Reading | Reading | Allowed |
## Synchronization Variables
- **mutex:** Ensures mutual exclusion when updating the reader count (readcnt).
- **wrt:** Controls access to the shared data (used by both readers and writers).
- **readcnt:** Number of readers currently in the critical section.
## Semaphore Operations
- **wait():** Decreases semaphore value, blocks if < 0.
- **signal():** Increases semaphore value, wakes waiting process if any.
### Reader Process(Reader Preference)
1. Reader requests the entry to critical section.
2. If allowed: 
- it increments the count of number of readers inside the critical section. If this reader is the first reader entering, it locks the **wrt** semaphore to restrict the entry of writers if any reader is inside.
- It then, signals [mutex](https://www.geeksforgeeks.org/operating-systems/mutex-vs-semaphore/) as any other reader is allowed to enter while others are already reading.
- After performing reading, it exits the critical section. When exiting, it checks if no more reader is inside, it signals the semaphore "wrt" as now, writer can enter the critical section.
3. If not allowed, it keeps on waiting.
> do {
>
> wait(mutex); // Lock before updating readcnt
>  readcnt++;
>
> if (readcnt == 1)
>  wait(wrt); // First reader blocks writers
>  signal(mutex); // Allow other readers in
>
> // ---- Critical Section (Reading) ----
>
> wait(mutex);
>  readcnt--;
>  if (readcnt == 0)
>  signal(wrt); // Last reader allows writers
>  signal(mutex); // Unlock
> } while(true);
**Explanation:**
- When a reader enters, it locks mutex to update readcnt.
- If it’s the first reader, it locks wrt so writers are blocked.
- Multiple readers can now read the data simultaneously.
- When a reader exits, it decrements readcnt.
- If it’s the last reader, it unlocks wrt so writers can proceed.
The first reader blocks writers, the last reader allows writers, and all readers in between share the resource. This gives preference to readers, but writers may starve.
### Writer’s Process
> do {
>  wait(wrt); // Lock resource
>
>  // ---- Critical Section (Writing) ----
>
>  signal(wrt); // Release resource
> } while(true);
**Explanation:**
- **wait(wrt):** Writer locks the resource to get exclusive access.
- **Critical Section:** Writer performs writing (no other reader or writer can enter).
- **signal(wrt):** Writer releases the resource after finishing.
Only one writer can write at a time, and no readers are allowed while writing. This ensures data integrity.
The Readers-Writers Problem highlights the need for proper synchronization when multiple processes access shared data.
- Readers Preference solution allows many readers to access simultaneously while blocking writers, improving read efficiency.
- However, writers may starve if readers keep arriving continuously.
- To avoid this, Writers Preference or a Fair solution (using queues or advanced semaphores) can be used to ensure no starvation and balanced access.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/readers-writers-problem-set-1-introduction-and-readers-preference-solution/)

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
