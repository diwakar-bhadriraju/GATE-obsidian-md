---
title: "Producer Consumer Solution using Semaphores"
subject: "Operating System"
topic: "Inter‐process Communication, Concurrency, and Synchronization"
source: "https://www.geeksforgeeks.org/operating-systems/producer-consumer-problem-using-semaphores-set-1/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Inter‐process Communication, Concurrency, and Synchronization"
tags:
  - gate/cs
  - subject/operating-system
  - topic/inter-process-communication-concurrency-and-synchronization
---


> [!abstract] Producer Consumer Solution using Semaphores
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Inter‐process Communication, Concurrency, and Synchronization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/producer-consumer-problem-using-semaphores-set-1/)

---

# Producer Consumer Solution using Semaphores

The Producer-Consumer problem is a classic synchronization problem in operating systems where multiple processes or threads share a common buffer. Proper synchronization prevents race conditions and ensures correct access to the shared resource.
- Producers insert data items into the shared buffer.
- Consumers remove and process data items from the shared buffer.
### Synchronization Requirements
The synchronization mechanism must satisfy the following conditions:
- Producers cannot insert items when the buffer is full.
- Consumers cannot remove items when the buffer is empty.
- Only one process can access the shared buffer (critical section) at a time.
## Semaphore: The Synchronization Tool
A semaphore is an integer-based signaling mechanism used to coordinate access to shared resources. The semaphore solution uses three semaphores:
| Semaphore | Purpose |
| --- | --- |
| mutex | Provides mutual exclusion while accessing the shared buffer. |
| full | Counts the number of filled buffer slots. |
| empty | Counts the number of empty buffer slots. |
### Semaphore Operations
A semaphore supports two atomic operations.
**wait():** Decreases the semaphore value. If the value becomes zero or negative, the calling process waits until the resource becomes available.
> wait(S)
> {
>  while (S <= 0);
>  S--;
> }
**signal():** Increases the semaphore value and wakes a waiting process if one exists.
> signal(S)
> {
>  S++;
> }
### Semaphore Initialization
Initially, the buffer is empty.
> mutex = 1; // binary semaphore for mutual exclusion
> full = 0; // initially no filled slots
> empty = n; // buffer size
## Producer Algorithm
The producer first checks whether an empty slot is available. If space exists, it enters the critical section, inserts the item, and then updates the semaphore values.
> do {
>  // Produce an item
>  wait(empty);
>  wait(mutex);
>  // Insert item into buffer
>  signal(mutex);
>  signal(full);
> } while (true);
## Consumer Algorithm
The consumer waits until the buffer contains at least one item. After entering the critical section, it removes an item and updates the semaphore values.
> do {
>  wait(full);
>  wait(mutex);
>  // Remove item from buffer
>  signal(mutex);
>  signal(empty);
> } while (true);
### Working of the Semaphore Solution
The producer and consumer coordinate using the three semaphores.
- empty prevents producers from inserting into a full buffer.
- full prevents consumers from removing from an empty buffer.
- mutex ensures only one process accesses the shared buffer at a time.
**Code Example Using POSIX Semaphores**
````cpp
#include <iostream>
#include <thread>
#include <mutex>
#include <condition_variable>
#include <cstdlib>
#include <ctime>
#define BUFFER_SIZE 5
#define MAX_ITEMS 20
int buffer[BUFFER_SIZE];
int in = 0, out = 0, count = 0;
std::mutex mutex;
std::condition_variable not_full;
std::condition_variable not_empty;
// Producer function
void producer() {
    while (true) {
        int item = rand() % 100; // produce an item
        std::unique_lock<std::mutex> lock(mutex);
        while (count == BUFFER_SIZE) // buffer full
            not_full.wait(lock);
        buffer[in] = item;
        std::cout << "Produced: " << item << " at " << in << std::endl;
        in = (in + 1) % BUFFER_SIZE;
        count++;
        not_empty.notify_one(); // signal buffer has item
        lock.unlock();
        std::this_thread::sleep_for(std::chrono::seconds(1)); // simulate production time
    }
}
// Consumer function
void consumer() {
    while (true) {
        std::unique_lock<std::mutex> lock(mutex);
        while (count == 0) // buffer empty
            not_empty.wait(lock);
        int item = buffer[out];
        std::cout << "Consumed: " << item << " at " << out << std::endl;
        out = (out + 1) % BUFFER_SIZE;
        count--;
        not_full.notify_one(); // signal buffer has space
        lock.unlock();
        std::this_thread::sleep_for(std::chrono::seconds(1)); // simulate consumption time
    }
}
int main() {
    std::srand(std::time(0));
    std::thread prod(producer);
    std::thread cons(consumer);
    prod.join();
    cons.join();
    return 0;
}
````
````c
#include <stdio.h>
#include <pthread.h>
#include <stdlib.h>
#include <unistd.h>
#define BUFFER_SIZE 5
int buffer[BUFFER_SIZE];
int in = 0, out = 0, count = 0;
pthread_mutex_t mutex;
pthread_cond_t not_full;
pthread_cond_t not_empty;
// Producer function
void* producer(void* arg) {
    while (1) {
        int item = rand() % 100; // produce an item
        pthread_mutex_lock(&mutex);
        while (count == BUFFER_SIZE) // buffer full
            pthread_cond_wait(&not_full, &mutex);
        buffer[in] = item;
        printf("Produced: %d at %d\n", item, in);
        in = (in + 1) % BUFFER_SIZE;
        count++;
        pthread_cond_signal(&not_empty); // signal buffer has item
        pthread_mutex_unlock(&mutex);
        sleep(1); // simulate production time
    }
    return NULL;
}
// Consumer function
void* consumer(void* arg) {
    while (1) {
        pthread_mutex_lock(&mutex);
        while (count == 0) // buffer empty
            pthread_cond_wait(&not_empty, &mutex);
        int item = buffer[out];
        printf("Consumed: %d at %d\n", item, out);
        out = (out + 1) % BUFFER_SIZE;
        count--;
        pthread_cond_signal(&not_full); // signal buffer has space
        pthread_mutex_unlock(&mutex);
        sleep(1); // simulate consumption time
    }
    return NULL;
}
int main() {
    pthread_t prod, cons;
    pthread_mutex_init(&mutex, NULL);
    pthread_cond_init(&not_full, NULL);
    pthread_cond_init(&not_empty, NULL);
    pthread_create(&prod, NULL, producer, NULL);
    pthread_create(&cons, NULL, consumer, NULL);
    pthread_join(prod, NULL);
    pthread_join(cons, NULL);
    pthread_mutex_destroy(&mutex);
    pthread_cond_destroy(&not_full);
    pthread_cond_destroy(&not_empty);
    return 0;
}
````
````java
import java.util.concurrent.locks.Condition;
import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;
public class ProducerConsumer {
    private static final int BUFFER_SIZE = 5;
    private static final int[] buffer = new int[BUFFER_SIZE];
    private static int in = 0, out = 0, count = 0;
    private static final Lock lock = new ReentrantLock();
    private static final Condition notFull = lock.newCondition();
    private static final Condition notEmpty = lock.newCondition();
    public static void main(String[] args) {
        Thread producer = new Thread(ProducerConsumer::producer);
        Thread consumer = new Thread(ProducerConsumer::consumer);
        producer.start();
        consumer.start();
    }
    private static void producer() {
        while (true) {
            int item = (int) (Math.random() * 100); // produce an item
            lock.lock();
            try {
                while (count == BUFFER_SIZE) // buffer full
                    notFull.await();
                buffer[in] = item;
                System.out.println("Produced: " + item + " at " + in);
                in = (in + 1) % BUFFER_SIZE;
                count++;
                notEmpty.signal(); // signal buffer has item
            } catch (InterruptedException e) {
                e.printStackTrace();
            } finally {
                lock.unlock();
            }
            try {
                Thread.sleep(1000); // simulate production time
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
    private static void consumer() {
        while (true) {
            lock.lock();
            try {
                while (count == 0) // buffer empty
                    notEmpty.await();
                int item = buffer[out];
                System.out.println("Consumed: " + item + " at " + out);
                out = (out + 1) % BUFFER_SIZE;
                count--;
                notFull.signal(); // signal buffer has space
            } catch (InterruptedException e) {
                e.printStackTrace();
            } finally {
                lock.unlock();
            }
            try {
                Thread.sleep(1000); // simulate consumption time
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}
````
````python3
import threading
import random
import time
BUFFER_SIZE = 5
buffer = [0] * BUFFER_SIZE
in_index = out_index = count = 0
mutex = threading.Lock()
not_full = threading.Condition(mutex)
not_empty = threading.Condition(mutex)
# Producer function
def producer():
    global in_index, out_index, count
    while True:
        item = random.randint(0, 99)  # produce an item
        with not_full:
            while count == BUFFER_SIZE:  # buffer full
                not_full.wait()
            buffer[in_index] = item
            print(f'Produced: {item} at {in_index}')
            in_index = (in_index + 1) % BUFFER_SIZE
            count += 1
            not_empty.notify()  # signal buffer has item
        time.sleep(1)  # simulate production time
# Consumer function
def consumer():
    global in_index, out_index, count
    while True:
        with not_empty:
            while count == 0:  # buffer empty
                not_empty.wait()
            item = buffer[out_index]
            print(f'Consumed: {item} at {out_index}')
            out_index = (out_index + 1) % BUFFER_SIZE
            count -= 1
            not_full.notify()  # signal buffer has space
        time.sleep(1)  # simulate consumption time
if __name__ == '__main__':
    prod_thread = threading.Thread(target=producer)
    cons_thread = threading.Thread(target=consumer)
    prod_thread.start()
    cons_thread.start()
    prod_thread.join()
    cons_thread.join()
````
**Explanation**
- The producer waits if the buffer becomes full and the consumer waits if the buffer becomes empty.
- A mutex protects the shared buffer from simultaneous access.
- Condition variables notify waiting threads whenever data is produced or consumed.
## Advantages of Semaphore Solution
Semaphores provide an effective way to coordinate producer and consumer processes by controlling access to the shared buffer.
- Prevents race conditions while accessing shared resources.
- Avoids buffer overflow and buffer underflow.
- Ensures proper synchronization between producers and consumers.
- Supports safe communication between multiple concurrent processes or threads.
> **Related article:**[Semaphores in Process Synchronization](https://www.geeksforgeeks.org/operating-systems/semaphores-in-process-synchronization/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/producer-consumer-problem-using-semaphores-set-1/)

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
