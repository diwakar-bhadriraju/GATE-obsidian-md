---
title: "Peterson's Algorithm for Mutual Exclusion | Set 1 (Basic C implementation)"
subject: "Operating System"
topic: "Inter‐process Communication, Concurrency, and Synchronization"
source: "https://www.geeksforgeeks.org/c/petersons-algorithm-for-mutual-exclusion-set-1/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Inter‐process Communication, Concurrency, and Synchronization"
tags:
  - gate/cs
  - subject/operating-system
  - topic/inter-process-communication-concurrency-and-synchronization
---


> [!abstract] Peterson's Algorithm for Mutual Exclusion | Set 1 (Basic C implementation)
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Inter‐process Communication, Concurrency, and Synchronization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/c/petersons-algorithm-for-mutual-exclusion-set-1/)

---

# Peterson's Algorithm for Mutual Exclusion | Set 1 (Basic C implementation)

**Problem:** Given 2 processes i and j, you need to write a program that can guarantee mutual exclusion between the two without any additional hardware support.
**Solution:** There can be multiple ways to solve this problem, but most of them require additional hardware support. The simplest and the most popular way to do this is by using Peterson's Algorithm for mutual Exclusion. It was developed by Peterson in 1981 though the initial work in this direction was done by Theodorus Jozef Dekker who came up with **Dekker's algorithm** in 1960, which was later refined by Peterson and came to be known as **Peterson's Algorithm**.
Basically, Peterson’s algorithm provides guaranteed mutual exclusion by using only the shared memory. It uses two ideas in the algorithm:
1. Willingness to acquire lock.
2. Turn to acquire lock.
Prerequisite: [Multithreading in C](https://www.geeksforgeeks.org/c/multithreading-in-c/)
**Explanation**: The idea is that first a thread expresses its desire to acquire a lock and sets **flag[self] = 1** and then gives the other thread a chance to acquire the lock. If the thread desires to acquire the lock, then, it gets the lock and passes the chance to the 1st thread. If it does not desire to get the lock then the while loop breaks and the 1st thread gets the chance.
The below code implementation uses the POSIX threads (`pthread`), which is common in C programs and lower-level system programming but requires more manual work and typecasting.
````cpp
#include <iostream>
#include <pthread.h>
using namespace std;
int flag[2];
int turn;
const int MAX = 1e9;
int ans = 0;
void lock_init()
{
    flag[0] = flag[1] = 0;
    turn = 0;
}
void lock(int self)
{
    flag[self] = 1;
    turn = 1 - self;
    while (flag[1 - self] == 1 && turn == 1 - self);
}
void unlock(int self)
{
    flag[self] = 0;
}
void* func(void* s)
{
    int i = 0;
    int self = (int)s;
    cout << "Thread Entered: " << self << endl;
    lock(self);
    for (i = 0; i < MAX; i++)
        ans++;
    unlock(self);
    return nullptr;
}
int main()
{
    pthread_t p1, p2;
    lock_init();
    pthread_create(&p1, nullptr, func, (void*)0);
    pthread_create(&p2, nullptr, func, (void*)1);
    pthread_join(p1, nullptr);
    pthread_join(p2, nullptr);
    cout << "Actual Count: " << ans << " | Expected Count: " << MAX * 2 << endl;
    return 0;
````
````c
// mythread.h (A wrapper header file with assert
// statements)
#ifndef __MYTHREADS_h__
#define __MYTHREADS_h__
#include <pthread.h>
#include <assert.h>
#include <sched.h>
void Pthread_mutex_lock(pthread_mutex_t *m)
{
    int rc = pthread_mutex_lock(m);
    assert(rc == 0);
}
void Pthread_mutex_unlock(pthread_mutex_t *m)
{
    int rc = pthread_mutex_unlock(m);
    assert(rc == 0);
}
void Pthread_create(pthread_t *thread, const pthread_attr_t *attr,
           void *(*start_routine)(void*), void *arg)
{
    int rc = pthread_create(thread, attr, start_routine, arg);
    assert(rc == 0);
}
void Pthread_join(pthread_t thread, void **value_ptr)
{
    int rc = pthread_join(thread, value_ptr);
    assert(rc == 0);
}
#endif // __MYTHREADS_h__
````
````java
import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;
public class PetersonSpinlockThread {
    // Shared variables for mutual exclusion
    private static int[] flag = new int[2];
    private static int turn;
    private static final int MAX = (int) 1e9;
    private static int ans = 0;
    private static Lock mutex = new ReentrantLock();
    // Initialize lock variables
    private static void lockInit() {
        flag[0] = flag[1] = 0;
        turn = 0;
    }
    // Acquire lock
    private static void lock(int self) {
        flag[self] = 1;
        turn = 1 - self;
        // Spin until the other thread releases the lock
        while (flag[1 - self] == 1 && turn == 1 - self);
    }
    // Release lock
    private static void unlock(int self) {
        flag[self] = 0;
    }
    // Function representing the critical section
    private static void func(int self) {
        int i = 0;
        System.out.println("Thread Entered: " + self);
        lock(self); // Acquire the lock
        for (i = 0; i < MAX; i++)
            ans++;
        unlock(self); // Release the lock
    }
    // Main method
    public static void main(String[] args) throws InterruptedException {
        // Create two threads
        Thread t1 = new Thread(() -> func(0));
        Thread t2 = new Thread(() -> func(1));
        lockInit(); // Initialize lock variables
        t1.start(); // Start thread 1
        t2.start(); // Start thread 2
        t1.join(); // Wait for thread 1 to finish
        t2.join(); // Wait for thread 2 to finish
        // Print the final count
        System.out.println("Actual Count: " + ans + " | Expected Count: " + MAX * 2);
    }
}
````
````python3
import threading
# Shared variables for mutual exclusion
flag = [0, 0]
turn = 0
MAX = int(1e9)
ans = 0
mutex = threading.Lock()
# Initialize lock variables
def lock_init():
    global flag, turn
    flag = [0, 0]
    turn = 0
# Acquire lock
def lock(self):
    global flag, turn
    flag[self] = 1
    turn = 1 - self
    # Spin until the other thread releases the lock
    while flag[1 - self] == 1 and turn == 1 - self:
        pass
# Release lock
def unlock(self):
    global flag
    flag[self] = 0
# Function representing the critical section
def func(self):
    global ans
    i = 0
    print(f"Thread Entered: {self}")
    with mutex:
        lock(self)  # Acquire the lock
        for i in range(MAX):
            ans += 1
        unlock(self)  # Release the lock
# Main method
def main():
    # Create two threads
    t1 = threading.Thread(target=lambda: func(0))
    t2 = threading.Thread(target=lambda: func(1))
    lock_init()  # Initialize lock variables
    t1.start()  # Start thread 1
    t2.start()  # Start thread 2
    t1.join()  # Wait for thread 1 to finish
    t2.join()  # Wait for thread 2 to finish
    # Print the final count
    print(f"Actual Count: {ans} | Expected Count: {MAX * 2}")
if __name__ == "__main__":
    main()
````
````javascript
const flag = [0, 0];
let turn = 0;
const MAX = 1e9;
let ans = 0;
function lock_init() {
    flag[0] = flag[1] = 0;
    turn = 0;
}
function lock(self) {
    flag[self] = 1;
    turn = 1 - self;
    while (flag[1 - self] === 1 && turn === 1 - self);
}
function unlock(self) {
    flag[self] = 0;
}
async function func(self) {
    let i = 0;
    console.log("Thread Entered:", self);
    lock(self);
    for (i = 0; i < MAX; i++)
        ans++;
    unlock(self);
}
async function main() {
    lock_init();
    const promise1 = func(0);
    const promise2 = func(1);
    await Promise.all([promise1, promise2]);
    console.log("Actual Count:", ans, "| Expected Count:", MAX * 2);
}
main();
//This code is contribuited by Prachi.
````
**Output:**
```
Thread Entered: 1Thread Entered: 0Actual Count: 2000000000 | Expected Count: 2000000000
```
The produced output is 2\*109 where 109 is incremented by both threads.
Read more about [Peterson's Algorithm for Mutual Exclusion | Set 2](https://www.geeksforgeeks.org/dsa/petersons-algorithm-for-mutual-exclusion-set-2-cpu-cycles-and-memory-fence/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/c/petersons-algorithm-for-mutual-exclusion-set-1/)

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
