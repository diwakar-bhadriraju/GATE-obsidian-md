---
title: "Lock Variable Synchronization Mechanism"
subject: "Operating System"
topic: "Inter‐process Communication, Concurrency, and Synchronization"
source: "https://www.geeksforgeeks.org/operating-systems/lock-variable-synchronization-mechanism/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Inter‐process Communication, Concurrency, and Synchronization"
tags:
  - gate/cs
  - subject/operating-system
  - topic/inter-process-communication-concurrency-and-synchronization
---


> [!abstract] Lock Variable Synchronization Mechanism
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Inter‐process Communication, Concurrency, and Synchronization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/lock-variable-synchronization-mechanism/)

---

# Lock Variable Synchronization Mechanism

A lock variable provides the simplest synchronization mechanism for processes. Some noteworthy points regarding Lock Variables are- 
1. It's a **software mechanism** implemented in user mode, i.e. no support required from the Operating System.
2. It's a busy waiting solution (process continuously checks for a condition and hence wastes CPU cycles).
3. It can be used for more than two processes.
When Lock = 0 implies critical section is vacant (initial value ) and Lock = 1 implies critical section occupied.
The pseudocode looks something like this - 
```
// Entry sectionwhile(lock != 0);  // Note the semicolonLock = 1;// critical section...............................// Exit sectionLock = 0;
```
A more formal approach to the Lock Variable method for process synchronization can be seen in the following code snippet :
````cpp
#include <mutex>
#include <condition_variable>
char buffer[SIZE];
int count = 0,
    start = 0,
    end = 0;
std::mutex mtx;
std::condition_variable cv;
void put(char c)
{
    std::unique_lock<std::mutex> lock(mtx);
    while (count == SIZE) {
        cv.wait(lock);
    }
    count++;
    buffer[start] = c;
    start++;
    if (start == SIZE) {
        start = 0;
    }
    cv.notify_all();
}
char get()
{
    std::unique_lock<std::mutex> lock(mtx);
    while (count == 0) {
        cv.wait(lock);
    }
    count--;
    char c = buffer[end];
    end++;
    if (end == SIZE) {
        end = 0;
    }
    cv.notify_all();
    return c;
}
````
````c
#include <iostream>
#include <thread>
#include <mutex>
#include <condition_variable>
#define SIZE 5
char buffer[SIZE];
int count = 0, start = 0, end = 0;
std::mutex mtx;
std::condition_variable cv;
void put(char c) {
    std::unique_lock<std::mutex> lock(mtx);
    // wait if buffer is full
    cv.wait(lock, [] { return count < SIZE; });
    buffer[start] = c;
    start = (start + 1) % SIZE;
    count++;
    // wake ONE waiting consumer
    cv.notify_one();
}
char get() {
    std::unique_lock<std::mutex> lock(mtx);
    // wait if buffer is empty
    cv.wait(lock, [] { return count > 0; });
    char c = buffer[end];
    end = (end + 1) % SIZE;
    count--;
    // wake ONE waiting producer
    cv.notify_one();
    return c;
}
````
Here we can see a classic implementation of the reader-writer's problem. The buffer here is the shared memory and many processes are either trying to read or write a character to it. To prevent any ambiguity of data we restrict concurrent access by using a lock variable. We have also applied a constraint on the number of readers/writers that can have access.
Now every Synchronization mechanism is judged on the basis of three primary parameters : 
1. Mutual Exclusion.
2. Progress.
3. Bounded Waiting.
Of which [mutual exclusion](https://www.geeksforgeeks.org/operating-systems/mutual-exclusion-in-synchronization/) is the most important of all parameters. The Lock Variable doesn't provide mutual exclusion in some cases. This fact can be best verified by writing its pseudo-code in the form of an assembly language code as given below.
```
1. Load Lock, R0 ; (Store the value of Lock in Register R0.)2. CMP R0, #0 ; (Compare the value of register R0 with 0.)3. JNZ Step 1 ; (Jump to step 1 if value of R0 is not 0.)4. Store #1, Lock ; (Set new value of Lock as 1.)Enter critical section5. Store #0, Lock ; (Set the value of lock as 0 again.)
```
Now let's suppose that processes P1 and P2 are competing for Critical Section and their sequence of execution be as follows (initial value of Lock = 0) -
1. P1 executes statement 1 and gets pre-empted.
2. P2 executes statement 1, 2, 3, 4 and enters Critical Section and gets pre-empted.
3. P1 executes statement 2, 3, 4 and also enters Critical Section.
Here initially the R0 of process P1 stores lock value as 0 but fails to update the lock value as 1. So when P2 executes it also finds the LOCK value as 0 and enters Critical Section by setting LOCK value as 1. But the real problem arises when P1 executes again it doesn't check the updated value of Lock. It only checks the previous value stored in R0 which was 0 and it enters critical section.
This is only one possible sequence of execution among many others. Some may even provide mutual exclusion but we cannot dwell on that. According to murphy's law "**Anything that can go wrong will go wrong**". So like all easy things the Lock Variable Synchronization method comes with its fair share of Demerits but its a good starting point for us to develop better Synchronization Algorithms to take care of the problems that we face here.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/lock-variable-synchronization-mechanism/)

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
> - [[Mutex vs Semaphore]]
