---
title: "Dining Philosopher Solution using Semaphores"
subject: "Operating System"
topic: "Inter‐process Communication, Concurrency, and Synchronization"
source: "https://www.geeksforgeeks.org/operating-systems/dining-philosopher-problem-using-semaphores/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Inter‐process Communication, Concurrency, and Synchronization"
tags:
  - gate/cs
  - subject/operating-system
  - topic/inter-process-communication-concurrency-and-synchronization
---


> [!abstract] Dining Philosopher Solution using Semaphores
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Inter‐process Communication, Concurrency, and Synchronization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/dining-philosopher-problem-using-semaphores/)

---

# Dining Philosopher Solution using Semaphores

The Dining Philosopher Problem is a classic synchronization problem introduced by Edsger Dijkstra in 1965. It illustrates the challenges of resource sharing in concurrent programming, such as deadlock, starvation, and mutual exclusion.
![os](assets/os-f488542a64.webp)
### Problem Statement
- K philosophers sit around a circular table.
- Each philosopher alternates between thinking and eating.
- There is one chopstick between each philosopher (total K chopsticks).
- A philosopher must pick up two chopsticks (left and right) to eat.
- Only one philosopher can use a chopstick at a time.
**The challenge:** Design a synchronization mechanism so that philosophers can eat without causing **deadlock** (all waiting forever) or **starvation** (some never get a chance to eat).
## Issues in the Problem
1. **Deadlock:** If every philosopher picks up their left chopstick first, no one can pick up the right one circular wait.
2. **Starvation:** Some philosophers may never get a chance to eat if others keep eating.
3. **Concurrency Control:** Must ensure no two adjacent philosophers eat simultaneously.
## **Semaphore Solution to Dining Philosopher**
We use **semaphores** to manage chopsticks and avoid deadlock.
### Algorithm
- Each chopstick is represented as a binary semaphore (mutex).
- Philosopher must acquire both left and right semaphores before eating.
- After eating, the philosopher releases both semaphores.
### **Pseudocode**
> semaphore chopstick[5] = {1,1,1,1,1};
>
> Philosopher(i):
> while(true) {
>  think();
>  wait(chopstick[i]); // pick left chopstick
>  wait(chopstick[(i+1)%5]); // pick right chopstick
>
> eat();
>
> signal(chopstick[i]); // put left chopstick
>  signal(chopstick[(i+1)%5]); // put right chopstick
>
> }
### Explanation:
- **semaphore chopstick[5] = {1,1,1,1,1};** Each chopstick is a binary semaphore initialized to 1 (available).
- **think();** Philosopher spends time thinking.
- **wait(chopstick[i]);** Tries to pick the left chopstick. If it’s free, philosopher takes it; otherwise waits.
- **wait(chopstick[(i+1)%5]);** Tries to pick the right chopstick (using modulo for circular table).
- **eat();** Philosopher eats once both chopsticks are acquired.
- **signal(chopstick[i]);** and **signal(chopstick[(i+1)%5]); P**uts down both chopsticks, making them available for neighbors.
## **Code**
````cpp
#include <iostream>
#include <thread>
#include <vector>
#include <semaphore>
#include <unistd.h>
#define N 5  // Number of philosophers
std::counting_semaphore<N> chopstick[N];   // One semaphore for each chopstick
void philosopher(int id) {
    while (true) {
        std::cout << "Philosopher " << id << " is thinking...\n";
        std::this_thread::sleep_for(std::chrono::seconds(1));
        // Pick up left chopstick
        chopstick[id].acquire();
        // Pick up right chopstick
        chopstick[(id + 1) % N].acquire();
        std::cout << "Philosopher " << id << " is eating...\n";
        std::this_thread::sleep_for(std::chrono::seconds(2));
        // Put down left chopstick
        chopstick[id].release();
        // Put down right chopstick
        chopstick[(id + 1) % N].release();
        std::cout << "Philosopher " << id << " finished eating and put down chopsticks.\n";
    }
}
int main() {
    std::vector<std::thread> threads(N);
    // Initialize chopstick semaphores
    for (int i = 0; i < N; i++) {
        chopstick[i] = std::counting_semaphore<N>(1);
    }
    // Create philosopher threads
    for (int i = 0; i < N; i++) {
        threads[i] = std::thread(philosopher, i);
    }
    // Join threads (never ends in this example)
    for (auto& th : threads) {
        if (th.joinable()) {
            th.join();
        }
    }
    return 0;
}
````
````java
import java.util.concurrent.Semaphore;
import java.util.concurrent.TimeUnit;
public class DiningPhilosophers {
    private static final int N = 5;  // Number of philosophers
    private static final Semaphore[] chopstick = new Semaphore[N];
    public static void main(String[] args) {
        // Initialize chopstick semaphores
        for (int i = 0; i < N; i++) {
            chopstick[i] = new Semaphore(1);
        }
        // Create philosopher threads
        for (int i = 0; i < N; i++) {
            new Thread(new Philosopher(i)).start();
        }
    }
    static class Philosopher implements Runnable {
        private final int id;
        Philosopher(int id) {
            this.id = id;
        }
        @Override
        public void run() {
            while (true) {
                System.out.println("Philosopher " + id + " is thinking...");
                sleep(1);
                // Pick up left chopstick
                try { chopstick[id].acquire(); } catch (InterruptedException e) { e.printStackTrace(); }
                // Pick up right chopstick
                try { chopstick[(id + 1) % N].acquire(); } catch (InterruptedException e) { e.printStackTrace(); }
                System.out.println("Philosopher " + id + " is eating...");
                sleep(2);
                // Put down left chopstick
                chopstick[id].release();
                // Put down right chopstick
                chopstick[(id + 1) % N].release();
                System.out.println("Philosopher " + id + " finished eating and put down chopsticks.");
            }
        }
        private void sleep(int seconds) {
            try { TimeUnit.SECONDS.sleep(seconds); } catch (InterruptedException e) { e.printStackTrace(); }
        }
    }
}
````
````python3
import threading
import time
from threading import Semaphore
N = 5  # Number of philosophers
chopstick = [Semaphore(1) for _ in range(N)]
def philosopher(id):
    while True:
        print(f'Philosopher {id} is thinking...')
        time.sleep(1)
        # Pick up left chopstick
        chopstick[id].acquire()
        # Pick up right chopstick
        chopstick[(id + 1) % N].acquire()
        print(f'Philosopher {id} is eating...')
        time.sleep(2)
        # Put down left chopstick
        chopstick[id].release()
        # Put down right chopstick
        chopstick[(id + 1) % N].release()
        print(f'Philosopher {id} finished eating and put down chopsticks.')
threads = []
# Create philosopher threads
for i in range(N):
    thread = threading.Thread(target=philosopher, args=(i,))
    threads.append(thread)
    thread.start()
# Join threads (never ends in this example)
for thread in threads:
    thread.join()
````
### Explanation
**1. Semaphores for chopsticks**
> sem\_t chopstick[N];
Each chopstick is represented by a binary semaphore (1 = free, 0 = in use).
**2. Philosopher function**
- A philosopher thinks first.
- Then tries to pick up left chopstick (sem\_wait(chopstick[id])).
- Then pick up right chopstick (sem\_wait(chopstick[(id+1)%N])).
- After acquiring both chopsticks eats.
- Finally, puts down both chopsticks (sem\_post).
**3. Thread creation**
- Each philosopher is represented as a thread.
- pthread\_create() starts philosopher actions in parallel.
**4. Circular arrangement**: Right chopstick is (id+1)%N ensures philosopher 4 gets chopsticks 4 and 0.
### **Problem with this code**
If all philosophers pick up their left chopstick at the same time, they will all wait for the right chopstick deadlock.
### Deadlock Avoidance
One common fix is to allow only **N-1 philosophers** to pick chopsticks at a time. This breaks the circular wait condition.
> sem\_t room; // new semaphore
>
> sem\_init(&room, 0, N-1); // allow only N-1 philosophers inside
>
> // before picking chopsticks
> sem\_wait(&room);
>
> // after eating
> sem\_post(&room);
This ensures that at least one philosopher can always eat, preventing deadlock.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/dining-philosopher-problem-using-semaphores/)

## GATE CS

- Subject: Operating System
- Topic: Inter‐process Communication, Concurrency, and Synchronization

> [!note] Related notes
>
> - [[Critical Section]]
> - [[Deadlock, Starvation, and Livelock]]
> - [[Dining Philosopher Problem]]
> - [[Dining-Philosophers Solution Using Monitors]]
> - [[Inter Process Communication]]
> - [[Interprocess Communication Methods]]
> - [[IPC through shared memory]]
> - [[IPC using Message Queues]]
> - [[Lock variable synchronization mechanism]]
> - [[Mutex vs Semaphore]]
