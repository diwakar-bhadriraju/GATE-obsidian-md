---
title: "Fork Function Call"
subject: "Operating System"
topic: "Processes, Threads, CPU Scheduling"
source: "https://www.geeksforgeeks.org/operating-systems/fork-function-call/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Processes, Threads, CPU Scheduling"
tags:
  - gate/cs
  - subject/operating-system
  - topic/processes-threads-cpu-scheduling
---


> [!abstract] Fork Function Call
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Processes, Threads, CPU Scheduling`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/fork-function-call/)

---

# Fork Function Call

In this article, we are going to see the fork function call in detail with the help of an example. A function call is an operating system call that is used to create a copy of a process which is also called a **child process**. This function call is used in a system that supports multitasking.
## Purpose of Fork()
At its core, a function call is a fundamental [operating system](https://www.geeksforgeeks.org/operating-systems/operating-systems/) request. In the case of fork(), its primary purpose is to create a copy of the current process, which is often referred to as a **child process**. This child process is essentially a clone of the parent process, sharing much of the same code, data, and resources.
## **Return Values of Fork ()**
**Understanding the return values of fork() is crucial when we are using a** [**function**](https://www.geeksforgeeks.org/c/c-functions/) **in our code:**
- **Return Value of -1:** If fork() returns -1, it signifies that the creation of a child [process](https://www.geeksforgeeks.org/operating-systems/difference-between-process-and-thread/) was unsuccessful. This typically occurs when system resources are exhausted, and no more processes can be created.
- **Return value of 0:** When fork() returns 0, it means you are in the newly created child process. This is a key differentiator that allows the program to execute different logic or tasks in the parent and child processes.
- **Positive return value (Process ID):** If fork() returns a positive value, it is indicative of the parent process. This value contains the Process ID (PID) of the newly created child process. The PID is essential for tracking and managing multiple processes concurrently.
### **Example of Fork() in C**
````c
#include <stdio.h>
#include <unistd.h>
int main() {
    pid_t child_pid;
    //create a child process
    child_pid = fork();
    if (child_pid < 0) {
        // Error occurred while forking
        printf("Fork failed\n");
        return 1;
    } else if (child_pid == 0) {
        // Child process
        printf("Child process: PID = %d\n", getpid());
        printf("Hello from the child!\n");
    } else {
        // Parent process
        printf("Parent process: PID = %d\n", getpid());
        printf("Child process created with PID = %d\n", child_pid);
    }
    return 0;
}
````
### **Output**
```
Parent process: PID = 1915Child process created with PID = 1919Child process: PID = 1919 runningChild process finished executionParent process finished execution
```
## **Advantages of a fork function call**
- **Exact Copy Creation**: fork() allows you to create an exact copy of the parent process. This is incredibly useful for scenarios where you need multiple processes to perform similar tasks, each with its own isolated execution environment.
- **Efficiency Through Inheritance**: Inherited code and data between parent and child processes can result in more efficient memory usage. Changes made in one process do not affect the other unless explicitly shared, enhancing code modularity.
- **Concurrency Support**: The ability to create multiple processes concurrently is a cornerstone of modern [multitasking](https://www.geeksforgeeks.org/operating-systems/multitasking-operating-system/) systems. fork() provides a straightforward way to achieve this concurrency, enabling applications to handle multiple tasks simultaneously.
## Conclusion
In conclusion, the fork() function call is a fundamental concept in the world of multitasking and [concurrent](https://www.geeksforgeeks.org/operating-systems/concurrency-in-operating-system/) programming. By understanding its behavior and advantages, developers can harness its power to build efficient and responsive software systems. Whether creating a simple command line utility or a complex, multi-threaded application, the fork() function call is a valuable tool in programming.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/fork-function-call/)

## GATE CS

- Subject: Operating System
- Topic: Processes, Threads, CPU Scheduling

> [!note] Related notes
>
> - [[Benefits of Multithreading]]
> - [[Context Switching in OS]]
> - [[Difference between multitasking, multithreading and multiprocessing]]
> - [[Difference between thread and process]]
> - [[fork() in C]]
> - [[Introduction of System Call]]
> - [[Microkernel]]
> - [[Monolithic Kernel and key differences from Microkernel]]
> - [[Multi threading models]]
> - [[Multithreading]]
