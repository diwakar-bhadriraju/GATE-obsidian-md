---
title: "Dining Philosophers Problem"
subject: "Operating System"
topic: "Inter‐process Communication, Concurrency, and Synchronization"
source: "https://www.geeksforgeeks.org/operating-systems/dining-philosophers-problem/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Inter‐process Communication, Concurrency, and Synchronization"
tags:
  - gate/cs
  - subject/operating-system
  - topic/inter-process-communication-concurrency-and-synchronization
---


> [!abstract] Dining Philosophers Problem
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Inter‐process Communication, Concurrency, and Synchronization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/dining-philosophers-problem/)

---

# Dining Philosophers Problem

The **Dining Philosopher Problem** is a classic synchronization and concurrency problem that deals with resource sharing, deadlock, and starvation in systems where multiple processes require limited resources. In this article, we will discuss the Dining Philosopher Problem in detail along with proper implementation.
## Problem Statement
The **Dining Philosopher Problem** involves 'n' philosophers sitting around a circular table. Each philosopher alternates between two states: **thinking** and **eating**. To eat, a philosopher needs two chopsticks, one on their left and one on their right. However, the number of chopsticks is equal to the number of philosophers, and each chopstick is shared between two neighboring philosophers.
The standard problem considers the value of 'n' as 5 i.e. we deal with 5 Philosophers sitting around a circular table.
### **Constraints and Conditions for the** **Problem**
- Every Philosopher needs two forks to eat.
- Every Philosopher may pick up the forks on the left or right but only one fork at once.
- Philosophers only eat when they have two forks. We have to design such a protocol i.e. pre and post protocol which ensures that a philosopher only eats if he or she has two forks.
- Each fork is either clean or dirty.
![Dining Philosophers Problem](assets/dfp-300x220-6693f91d59.png)
### **Solution**
The correctness properties it needs to satisfy are:
- **Mutual Exclusion Principle:** No two Philosophers can have the two forks simultaneously.
- **Free from Deadlock:** Each philosopher can get the chance to eat in a certain finite time.
- **Free from Starvation:** When few Philosophers are waiting then one gets a chance to eat in a while.
- **No strict Alternation**
- **Proper utilization of time**
### **Algorithm**
```
loop forever    p1: think    p2: preprotocol    p3: eat    p4: postprotocol
```
### **First Attempt**
We assume that each philosopher is initialized with its index I and that addition is implicitly modulo 5. Each fork is modeled as a semaphore where wait corresponds to taking a fork and signal corresponds to putting down a fork.
**Algorithm**
```
semaphore array[0..4] fork ← [1, 1, 1, 1, 1]loop forever       p1 : think                       p2 : wait(fork[i])       p3 : wait(fork[i + 1])       p4 : eat       p5 : signal(fork[i])       p6 : signal(fork[i + 1])
```
**Problem with this solution:**
This solution may lead to a deadlock under an interleaving that has all the philosophers pick up their left forks before any of them tries to pick up a right fork. In this case, all the Philosophers are waiting for the right fork but no one will execute a single instruction.
### **Second Attempt**
One way to tackle the above situation is to limit the number of philosophers entering the room to four. By doing this one of the philosophers will eventually get both the fork and execute all the instruction leading to no deadlock.
**Algorithm**
```
semaphore array[0..4] fork ← [1, 1, 1, 1, 1]   semaphore room ← 4   loop forever       p1 : think                       p2 : wait(room)                               p3 : wait(fork[i])                                         p4 : wait(fork[i + 1])                                                  p5 : eat                                                       p6 : signal(fork[i])                p7 : signal(fork[i + 1])                         p8 : signal(room)
```
In this solution, we somehow interfere with the given problem as we allow only four philosophers.
### **Third Attempt**
We use the asymmetric algorithm in the attempt where the first four philosophers execute the original solution but the fifth philosopher waits for the right fork and then for the left fork.
**Algorithm**
```
semaphore array [0..4] fork ← [1,1,1,1,1]
```
### **For the** **first Four Philosophers**
```
loop forever   p1 : think               p2 : wait(fork[i])                        p3 : wait(fork[i + 1])                                 p4 : eat                                      p5 : signal(fork[i])                                               p6: signal(fork[i + 1])                   
```
### **For the Fifth Philosopher**
```
loop forever   p1 : think               p2 : wait(fork[0])                        p3 : wait(fork[4])                                 p4 : eat                                      p5 : signal(fork[0])                                               p6 : signal(fork[4])
```
**Note:** This solution is also known as **Chandy/Misra Solution**.
### **Advantages of this Solution**
- Allows a large degree of concurrency
- Free from Starvation
- Free from Deadlock
- More Flexible Solution
- Economical
- Fairness
- Boundedness
The above discussed the solution for the problem using semaphore. Now with monitors, Here, Monitor maintains an array of the fork which counts the number of free forks available to each philosopher. The take Forks operation waits on a condition variable until two forks are available. It decrements the number of forks available to its neighbor before leaving the monitor. After eating, a philosopher calls release Forks which updates the array fork and checks if freeing these forks makes it possible to signal.
## **Algorithm**
```
monitor ForkMonitor:integer array[0..4]fork ← [2,2,2,2,2]                                                       condition array[0..4]OKtoEatoperation takeForks(integer i)                  if(fork[i]!=2)waitC(OKtoEat[i])fork[i+1]<- fork[i+1]-1fork[i-1] <- fork[i-1]-1   operation releaseForks(integer i)fork[i+1] <- fork[i+1]+1fork[i-1] <- fork[i-1]if(fork[i+1]==2)signalC(OKtoEat[i+1])         if(fork[i-1]==2)signalC(OKtoEat[i-1])
```
**For Each Philosopher**
```
loop forever :     p1 : think             p2 : takeForks(i)                     p3 : eat                           p4 : releaseForks(i)
```
Here Monitor will ensure all such needs mentioned above.
## **Implementation of Dining Philosophers Problem**
Here is the Program for the same using monitors in C++ as follows.
C++14
````cpp14
// Header file include
#include <bits/stdc++.h>
#include <pthread.h>
#include <unistd.h>
using namespace std;
#define N 10
#define THINKING 2
#define HUNGRY 1
#define EATING 0
#define LEFT (phnum + 4) % N
#define RIGHT (phnum + 1) % N
// Philosopher index
int phil[N];
int times = 200;
class monitor
{
    // state of the philosopher
    int state[N];
    // Philosopher condition variable
    pthread_cond_t phcond[N];
    // mutex variable for synchronization
    pthread_mutex_t condLock;
  public:
    // Test for the desired condition
    // i.e. Left and Right philosopher are not reading
    void test(int phnum)
    {
        if (state[(phnum + 1) % 5] != EATING and state[(phnum + 4) % 5] != EATING and state[phnum] == HUNGRY)
        {
            state[phnum] = EATING;
            pthread_cond_signal(&phcond[phnum]);
        }
    }
    // Take Fork function
    void take_fork(int phnum)
    {
        pthread_mutex_lock(&condLock);
        // Indicates it is hungry
        state[phnum] = HUNGRY;
        // test for condition
        test(phnum);
        // If unable to eat.. wait for the signal
        if (state[phnum] != EATING)
        {
            pthread_cond_wait(&phcond[phnum], &condLock);
        }
        cout << "Philosopher " << phnum << " is Eating" << endl;
        pthread_mutex_unlock(&condLock);
    }
    // Put Fork function
    void put_fork(int phnum)
    {
        pthread_mutex_lock(&condLock);
        // Indicates that I am thinking
        state[phnum] = THINKING;
        test(RIGHT);
        test(LEFT);
        pthread_mutex_unlock(&condLock);
    }
    // constructor
    monitor()
    {
        for (int i = 0; i < N; i++)
        {
            state[i] = THINKING;
        }
        for (int i = 0; i < N; i++)
        {
            pthread_cond_init(&phcond[i], NULL);
        }
        pthread_mutex_init(&condLock, NULL);
    }
    // destructor
    ~monitor()
    {
        for (int i = 0; i < N; i++)
        {
            pthread_cond_destroy(&phcond[i]);
        }
        pthread_mutex_destroy(&condLock);
    }
}
// Global Object of the monitor
phil_object;
void *philosopher(void *arg)
{
    int c = 0;
    while (c < times)
    {
        int i = *(int *)arg;
        sleep(1);
        phil_object.take_fork(i);
        sleep(0.5);
        phil_object.put_fork(i);
        c++;
    }
}
int main()
{
    // Declaration...
    pthread_t thread_id[N];
    pthread_attr_t attr;
    // Initialization...
    pthread_attr_init(&attr);
    pthread_attr_setdetachstate(&attr, PTHREAD_CREATE_JOINABLE);
    for (int i = 0; i < N; i++)
    {
        phil[i] = i;
    }
    // Creating...
    for (int i = 0; i < N; i++)
    {
        pthread_create(&thread_id[i], &attr, philosopher, &phil[i]);
        cout << "Philosopher " << i + 1 << " is thinking..." << endl;
    }
    // Joining....
    for (int i = 0; i < N; i++)
    {
        pthread_join(thread_id[i], NULL);
    }
    // Destroying
    pthread_attr_destroy(&attr);
    pthread_exit(NULL);
    return 0;
}
````
````python3
# Importing required libraries
import threading
import time
# Constants
N = 10
THINKING = 2
HUNGRY = 1
EATING = 0
times = 200
# Philosopher index
phil = [i for i in range(N)]
class Monitor:
    def __init__(self):
        # state of the philosopher
        self.state = [THINKING] * N
        # Philosopher condition variable
        self.phcond = [threading.Condition() for _ in range(N)]
    # Test for the desired condition
    # i.e. Left and Right philosopher are not eating
    def test(self, phnum):
        with self.phcond[phnum]:
            if (self.state[(phnum + 1) % N] != EATING and
                self.state[(phnum + N - 1) % N] != EATING and
                    self.state[phnum] == HUNGRY):
                self.state[phnum] = EATING
                self.phcond[phnum].notify()
    # Take Fork function
    def take_fork(self, phnum):
        with self.phcond[phnum]:
            # Indicates it is hungry
            self.state[phnum] = HUNGRY
            # test for condition
            self.test(phnum)
            # If unable to eat.. wait for the signal
            if self.state[phnum] != EATING:
                self.phcond[phnum].wait()
            print(f"Philosopher {phnum} is Eating")
    # Put Fork function
    def put_fork(self, phnum):
        with self.phcond[phnum]:
            # Indicates that I am thinking
            self.state[phnum] = THINKING
            self.test((phnum + 1) % N)
            self.test((phnum + N - 1) % N)
# Global Object of the monitor
phil_object = Monitor()
def philosopher(phnum):
    c = 0
    while c < times:
        time.sleep(1)
        phil_object.take_fork(phnum)
        time.sleep(0.5)
        phil_object.put_fork(phnum)
        c += 1
def main():
    # Creating...
    threads = []
    for i in range(N):
        t = threading.Thread(target=philosopher, args=(phil[i],))
        threads.append(t)
        t.start()
        print(f"Philosopher {i + 1} is thinking...")
    # Joining....
    for i in range(N):
        threads[i].join()
if __name__ == "__main__":
    main()
````
### **Output**
![Dining Philosophers Problem](assets/diningoutput1-cf6d6ecf12.png)
Output for Dining Philosophers problem for the above program
## Conclusion
The [Dining Philosopher Problem](https://www.geeksforgeeks.org/operating-systems/dining-philosopher-problem-using-semaphores/) teaches us how to handle shared resources in a system while avoiding issues like [deadlock](https://www.geeksforgeeks.org/dbms/deadlock-in-dbms/) and [starvation](https://www.geeksforgeeks.org/operating-systems/starvation-and-aging-in-operating-systems/). It highlights challenges like deadlock and starvation and teaches how to prevent them using proper [synchronization](https://www.geeksforgeeks.org/operating-systems/introduction-of-process-synchronization/) techniques. The problem is a classic example used to study synchronization and resource allocation in [concurrent systems](https://www.geeksforgeeks.org/operating-systems/concurrency-in-operating-system/).
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/dining-philosophers-problem/)

## GATE CS

- Subject: Operating System
- Topic: Inter‐process Communication, Concurrency, and Synchronization

> [!note] Related notes
>
> - [[Critical Section]]
> - [[Deadlock, Starvation, and Livelock]]
> - [[Dining Philosopher Problem Using Semaphores]]
> - [[Dining-Philosophers Solution Using Monitors]]
> - [[Inter Process Communication]]
> - [[Interprocess Communication Methods]]
> - [[IPC through shared memory]]
> - [[IPC using Message Queues]]
> - [[Lock variable synchronization mechanism]]
> - [[Mutex vs Semaphore]]
