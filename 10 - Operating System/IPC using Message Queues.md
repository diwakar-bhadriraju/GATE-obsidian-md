---
title: "IPC using Message Queues"
subject: "Operating System"
topic: "Inter‐process Communication, Concurrency, and Synchronization"
source: "https://www.geeksforgeeks.org/operating-systems/ipc-using-message-queues/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Inter‐process Communication, Concurrency, and Synchronization"
tags:
  - gate/cs
  - subject/operating-system
  - topic/inter-process-communication-concurrency-and-synchronization
---


> [!abstract] IPC using Message Queues
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Inter‐process Communication, Concurrency, and Synchronization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/ipc-using-message-queues/)

---

# IPC using Message Queues

**Inter-Process Communication (IPC)** is a method for communication within processes to exchange data, control information, or synchronizing tasks. There are various methods available for inter-process communication (IPC), like [IPC using shared memory](https://www.geeksforgeeks.org/operating-systems/ipc-shared-memory/), message passing, semaphores, sockets, and message queues.
Message Queue is the most common way for [IPC](https://www.geeksforgeeks.org/operating-systems/inter-process-communication-ipc/), which allow processes to send and receive messages in a queue-like manner.
## Message Queues
A Message Queue is a linked list of messages stored within the kernel and identified by a message queue identifier and it is used to send and receive messages between processes in a [**first-in-first-out (FIFO)**](https://www.geeksforgeeks.org/dsa/fifo-first-in-first-out-approach-in-programming/) manner. 
The **msgget()** function is used to create a new queue or open an existing queue and new messages are added to the end of a queue by using **msgsnd()**.
In a message queue every message has a positive long integer type field, a non-negative length, and the actual data bytes (corresponding to the length), all of which are specified to msgsnd() when the message is added to a queue. Messages are fetched from a queue by **msgrcv()**.
> **Note:** We don't have to fetch the messages in a first-in, first-out order. Instead, we can fetch messages based on their type field.
![](assets/message-queue1-525a9b637e.png)
## IPC Using Message Queues
The Inter-Process Communication (IPC) is essential for the enabling processes to the communicate and synchronize with the each other in an operating system. Among the various IPC mechanisms message queues provide the robust and flexible method for the processes to exchange data in a queued orderly fashion. It enables [asynchronous communication](https://www.geeksforgeeks.org/system-design/synchronous-vs-asynchronous-communication-system-design/), where messages are placed in a queue and retrieved by processes in a convenient manner.
### **Message Queue for Writer/Sender Process**
````c
#include <stdio.h>
#include <sys/ipc.h>
#include <sys/msg.h>
#define MAX 10
// structure for message queue
struct mesg_buffer {
    long mesg_type;
    char mesg_text[100];
} message;
int main()
{
    key_t key;
    int msgid;
    // ftok to generate unique key
    key = ftok("progfile", 65);
    // msgget creates a message queue
    // and returns identifier
    msgid = msgget(key, 0666 | IPC_CREAT);
    message.mesg_type = 1;
    printf("Write Data : ");
    fgets(message.mesg_text,MAX,stdin);
    // msgsnd to send message
    msgsnd(msgid, &message, sizeof(message), 0);
    // display the message
    printf("Data send is : %s \n", message.mesg_text);
    return 0;
}
````
### **Message Queue for Reader/Reciever Process**
````c
#include <stdio.h>
#include <sys/ipc.h>
#include <sys/msg.h>
// structure for message queue
struct mesg_buffer {
    long mesg_type;
    char mesg_text[100];
} message;
int main()
{
    key_t key;
    int msgid;
    // ftok to generate unique key
    key = ftok("progfile", 65);
    // msgget creates a message queue
    // and returns identifier
    msgid = msgget(key, 0666 | IPC_CREAT);
    // msgrcv to receive message
    msgrcv(msgid, &message, sizeof(message), 1, 0);
    // display the message
    printf("Data Received is : %s \n",
                    message.mesg_text);
    // to destroy the message queue
    msgctl(msgid, IPC_RMID, NULL);
    return 0;
}
````
**Output**
![](assets/message-queue-fb36fcdd52.png)
### Working of IPC using Message Queue
1. **Creating/Accessing a Message Queue:** The first step is to creatr or access a message queue using the **msgget()** function. The msgget function creates a new meaage queue if the queue does not exists.
2. **Sending the Message:** After successfully creating/accessing the message queue a process can now send a message to the queue using **msgsnd()** function which will be stored in the message queue in a format that contains message type and actual message content.
3. **Receiving the Message:** Once the message is added in the queue, it can be retrieved from the queue by another process using msgrcv(). This function allows the receiving process to specify the message type it wants to read. The message is then removed from the queue once it is received.
4. **Delete the Message Queue:** We can use the msgctl() function to delete the message queue if it is no longer needed.
### Functions of Message Queue
The Message queues are powerful IPC tools that allow processes to send and receive messages in the FIFO (First In, First Out) order. Here are the primary functions of the message queues:
- **Message Storage:** A message queue stores messages sent by the one process until they are retrieved by the another process. Each message is placed in the queue and remains there until it is read by the receiving process.
- **Ordered Communication:** The Message queues ensure that messages are delivered in the order they were sent. This ordered communication is vital in the scenarios where the sequence of the operations matters.
- **Asynchronous Communication:** With message queues, processes do not need to be synchronized or directly connected. A sending process can place a message in the queue and receiving process can retrieve it later allowing for the asynchronous communication.
- **Decoupling of Processes:** The Message queues allow processes to be decoupled meaning the sending and receiving processes do not need to be aware of the each other’s existence or state. They interact indirectly through the queue which can improve modularity and scalability.
- **Prioritization:** The Some message queue implementations allow the messages to be prioritized where certain messages can be processed before others based on the priority levels.
- **Error Handling:** The Message queues can be designed to handle errors such as retries for the failed message deliveries or logging of the undelivered messages for the troubleshooting.
### **System calls used for message queues:**
- **ftok()**: to generate a unique key.
- **msgget()**: to Create a new queue or access an existing queue either returns the message queue identifier for a newly created message queue or returns the identifiers for a queue which exists with the same key value.
- **msgsnd()**: to add message to a message queue.
- **msgrcv()**: for retrieving messages from a queue.
- **msgctl()**: used to delete message queue.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/ipc-using-message-queues/)

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
> - [[Lock variable synchronization mechanism]]
> - [[Mutex vs Semaphore]]
