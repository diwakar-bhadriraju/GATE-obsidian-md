---
title: "Dining-Philosophers Solution Using Monitors"
subject: "Operating System"
topic: "Inter‐process Communication, Concurrency, and Synchronization"
source: "https://www.geeksforgeeks.org/operating-systems/dining-philosophers-solution-using-monitors/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Inter‐process Communication, Concurrency, and Synchronization"
tags:
  - gate/cs
  - subject/operating-system
  - topic/inter-process-communication-concurrency-and-synchronization
---


> [!abstract] Dining-Philosophers Solution Using Monitors
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Inter‐process Communication, Concurrency, and Synchronization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/dining-philosophers-solution-using-monitors/)

---

# Dining-Philosophers Solution Using Monitors

Prerequisite: [Monitor](https://www.geeksforgeeks.org/operating-systems/monitors-in-process-synchronization/), [Process Synchronization](https://www.geeksforgeeks.org/operating-systems/introduction-of-process-synchronization/)
**Dining-Philosophers Problem -** N philosophers seated around a circular table 
![](assets/operating_system_din-97709ad9cf.png)
- There is one chopstick between each philosopher
- A philosopher must pick up its two nearest chopsticks in order to eat
- A philosopher must pick up first one chopstick, then the second one, not both at once
We need an algorithm for allocating these limited resources(chopsticks) among several processes(philosophers) such that solution is free from deadlock and free from starvation. There exist some algorithm to solve Dining - Philosopher Problem, but they may have deadlock situation. Also, a deadlock-free solution is not necessarily starvation-free. Semaphores can result in deadlock due to programming errors. Monitors alone are not sufficiency to solve this, we need monitors with *condition variables* **Monitor-based Solution to Dining Philosophers** We illustrate monitor concepts by presenting a deadlock-free solution to the dining-philosophers problem. Monitor is used to control access to state variables and condition variables. It only tells when to enter and exit the segment. This solution imposes the restriction that a philosopher may pick up her chopsticks only if both of them are available. To code this solution, we need to distinguish among three states in which we may find a philosopher. For this purpose, we introduce the following data structure: **THINKING -** When philosopher doesn't want to gain access to either fork. **HUNGRY -** When philosopher wants to enter the critical section. **EATING -** When philosopher has got both the forks, i.e., he has entered the section. Philosopher i can set the variable state[i] = EATING only if her two neighbors are not eating (state[(i+4) % 5] != EATING) and (state[(i+1) % 5] != EATING).
````cpp
// Dining-Philosophers Solution Using Monitors
monitor DP
{
    status state[5];
    condition self[5];
    // Pickup chopsticks
    Pickup(int i)
    {
        // indicate that I’m hungry
        state[i] = hungry;
        // set state to eating in test()
        // only if my left and right neighbors
        // are not eating
        test(i);
        // if unable to eat, wait to be signaled
        if (state[i] != eating)
            self[i].wait;
    }
    // Put down chopsticks
    Putdown(int i)
    {
        // indicate that I’m thinking
        state[i] = thinking;
        // if right neighbor R=(i+1)%5 is hungry and
        // both of R’s neighbors are not eating,
        // set R’s state to eating and wake it up by
        // signaling R’s CV
        test((i + 1) % 5);
        test((i + 4) % 5);
    }
    test(int i)
    {
        if (state[(i + 1) % 5] != eating
            && state[(i + 4) % 5] != eating
            && state[i] == hungry) {
            // indicate that I’m eating
            state[i] = eating;
            // signal() has no effect during Pickup(),
            // but is important to wake up waiting
            // hungry philosophers during Putdown()
            self[i].signal();
        }
    }
    init()
    {
        // Execution of Pickup(), Putdown() and test()
        // are all mutually exclusive,
        // i.e. only one at a time can be executing
for
    i = 0 to 4
        // Verify that this monitor-based solution is
        // deadlock free and mutually exclusive in that
        // no 2 neighbors can eat simultaneously
        state[i] = thinking;
    }
} // end of monitor
````
Above Program is a monitor solution to the dining-philosopher problem. We also need to declare
```
condition self[5];
```
This allows philosopher i to delay herself when she is hungry but is unable to obtain the chopsticks she needs. We are now in a position to describe our solution to the dining-philosophers problem. The distribution of the chopsticks is controlled by the monitor Dining Philosophers. Each philosopher, before starting to eat, must invoke the operation pickup(). This act may result in the suspension of the philosopher process. After the successful completion of the operation, the philosopher may eat. Following this, the philosopher invokes the putdown() operation. Thus, philosopher i must invoke the operations pickup() and putdown() in the following sequence:
```
DiningPhilosophers.pickup(i);
              ...
              eat
              ...
DiningPhilosophers.putdown(i);
```
It is easy to show that this solution ensures that **no two neighbors** are eating simultaneously and that no deadlocks will occur. We note, however, that it is possible for a philosopher to starve to death.
**When will the Deadlock occur?**
Deadlock occurs when two or more processes are blocked, waiting for each other to release a resource that they need. This can happen in solutions that allow a philosopher to pick up one chopstick at a time, or that allow all philosophers to pick up their left chopstick simultaneously.
**When will Starvation occur?**
Starvation occurs when a process is blocked indefinitely from accessing a resource that it needs. This can happen in solutions that give priority to certain philosophers or that allow some philosophers to continually acquire the chopsticks while others are unable to.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/dining-philosophers-solution-using-monitors/)

## GATE CS

- Subject: Operating System
- Topic: Inter‐process Communication, Concurrency, and Synchronization

> [!note] Related notes
>
> - [[Critical Section]]
> - [[Deadlock, Starvation, and Livelock]]
> - [[Dining Philosopher Problem]]
> - [[Dining Philosopher Problem Using Semaphores]]
> - [[Inter Process Communication]]
> - [[Interprocess Communication Methods]]
> - [[IPC through shared memory]]
> - [[IPC using Message Queues]]
> - [[Lock variable synchronization mechanism]]
> - [[Mutex vs Semaphore]]
