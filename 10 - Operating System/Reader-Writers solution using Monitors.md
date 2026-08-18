---
title: "Reader-Writers solution using Monitors"
subject: "Operating System"
topic: "Inter‐process Communication, Concurrency, and Synchronization"
source: "https://www.geeksforgeeks.org/operating-systems/reader-writers-solution-using-monitors/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Inter‐process Communication, Concurrency, and Synchronization"
tags:
  - gate/cs
  - subject/operating-system
  - topic/inter-process-communication-concurrency-and-synchronization
---


> [!abstract] Reader-Writers solution using Monitors
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Inter‐process Communication, Concurrency, and Synchronization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/reader-writers-solution-using-monitors/)

---

# Reader-Writers solution using Monitors

Prerequisite - [Process Synchronization](https://www.geeksforgeeks.org/operating-systems/introduction-of-process-synchronization/), [Monitors](https://www.geeksforgeeks.org/operating-systems/monitors-in-process-synchronization/), [Readers-Writers Problem](https://www.geeksforgeeks.org/operating-systems/readers-writers-problem-set-1-introduction-and-readers-preference-solution/) Considering a shared Database our objectives are:
- Readers can access database only when there are no writers.
- Writers can access database only when there are no readers or writers.
- Only one thread can manipulate the state variables at a time.
**What is the Reader-Writers problem?**
The Reader-Writers problem is a classical synchronization problem in computer science, where multiple threads (readers and writers) need to access a shared resource (e.g., a database) in a mutually exclusive way, while avoiding conflicts and ensuring correctness.
**How does the Reader-Writers solution using Monitors ensure fairness?**
The Reader-Writers solution using Monitors ensures a kind of back-and-forth form of fairness, where once a reader is waiting, readers will get in next, and if a writer is waiting, one writer will get in next. This is mostly fair, although once it lets a reader in, it lets all waiting readers in all at once, even if some showed up “after” other waiting writers. In the “EndWrite” code (it signals CanWrite without checking for waiting writers), in the EndRead code (same thing), and in StartRead (signals CanRead at the end).
**Basic structure of a solution -**
```
Reader()
   Wait until no writers
   Access database
   Check out – wake up a waiting writer
Writer()
   Wait until no active readers or writers
   Access database
   Check out – wake up waiting readers or writer
```
--Now let's suppose that a writer is active and a mixture of readers and writers now show up. **Who should get in next?** --Or suppose that a writer is waiting and an endless of stream of readers keep showing up. **Would it be fair for them to become active?** So we’ll implement a kind of back-and-forth form of fairness:
- **Once a reader is waiting, readers will get in next.**
- **If a writer is waiting, one writer will get in next.**
**Implementation of the solution using monitors:-**
1. The methods should be executed with mutual exclusion i.e. At each point in time, at most one thread may be executing any of its methods.
2. Monitors also provide a mechanism for threads to temporarily give up exclusive access, in order to wait for some condition to be met, before regaining exclusive access and resuming their task.
3. Monitors also have a mechanism for signaling other threads that such conditions have been met.
4. So in this implementation only mutual exclusion is not enough. Threads attempting an operation may need to wait until some assertion P holds true.
5. While a thread is waiting upon a condition variable, that thread is not considered to occupy the monitor, and so other threads may enter the monitor to change the monitor's state.
**Code -**
````c
// STATE VARIABLES
// Number of active readers; initially = 0
int NReaders = 0;
// Number of waiting readers; initially = 0
int WaitingReaders = 0;
// Number of active writers; initially = 0
int NWriters = 0;
// Number of waiting writers; initially = 0
int WaitingWriters = 0;
Condition canRead = NULL;
Condition canWrite = NULL;
Void BeginWrite()
{
    // A writer can enter if there are no other
    // active writers and no readers are waiting
    if (NWriters == 1 || NReaders > 0) {
        ++WaitingWriters;
        wait(CanWrite);
        --WaitingWriters;
    }
    NWriters = 1;
}
Void EndWrite()
{
    NWriters = 0;
    // Checks to see if any readers are waiting
    if (WaitingReaders)
        Signal(CanRead);
    else
        Signal(CanWrite);
}
Void BeginRead()
{
    // A reader can enter if there are no writers
    // active or waiting, so we can have
    // many readers active all at once
    if (NWriters == 1 || WaitingWriters > 0) {
        ++WaitingReaders;
        // Otherwise, a reader waits (maybe many do)
        Wait(CanRead);
        --WaitingReaders;
    }
    ++NReaders;
    Signal(CanRead);
}
Void EndRead()
{
    // When a reader finishes, if it was the last reader,
    // it lets a writer in (if any is there).
    if (--NReaders == 0)
        Signal(CanWrite);
}
````
**Understanding the solution:-**
1. If a writer is waiting, readers queue up.
2. If a reader (or another writer) is active or waiting, writers queue up.
3. This is mostly fair, although once it lets a reader in, it lets ALL waiting readers in all at once, even if some showed up “after” other waiting writers.
4. In the “EndWrite” code (it signals CanWrite without checking for waiting writers)
5. In the EndRead code (same thing)
6. In StartRead (signals CanRead at the end)
> With Semaphores we never did have a "fair" solution of this sort. In fact it can be done but the code is quite tricky. Here the straightforward solution works in the desired way! Monitors are less error-prone and also easier to understand.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/reader-writers-solution-using-monitors/)

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
