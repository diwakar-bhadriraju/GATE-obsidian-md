---
title: "fork() in C"
subject: "Operating System"
topic: "Processes, Threads, CPU Scheduling"
source: "https://www.geeksforgeeks.org/c/fork-system-call/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Processes, Threads, CPU Scheduling"
tags:
  - gate/cs
  - subject/operating-system
  - topic/processes-threads-cpu-scheduling
---


> [!abstract] fork() in C
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Processes, Threads, CPU Scheduling`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/c/fork-system-call/)

---

# fork() in C

The Fork system call is used for creating a new process in Linux, and Unix systems, which is called the **child process**, which runs concurrently with the process that makes the fork() call (parent process). After a new child process is created, both processes will execute the next instruction following the fork() system call.
The child process uses the same pc(program counter), same CPU registers, and same open files which use in the parent process. It takes no parameters and returns an integer value.
Below are different values returned by **fork().**
- **Negative Value**: The creation of a child process was unsuccessful, then it returns -1.
- **Zero**: Returned to the newly created child process.
- **Positive value**: Returned to parent or caller. The value contains the process ID of the newly created child process.
![creating a fork process](assets/Fork_in_C-67c32f7638.jpg)
> **Note:** fork() is threading based function, to get the correct output run the program on a local system.
Also, if you're interested in understanding process control and memory allocation in C, the[**C Programming Course Online with Data Structures**](https://www.geeksforgeeks.org/courses/c-Programming-basic-to-advanced?utm_campaign=287_fork_in_c&utm_medium=gfgcontent_icp&utm_source=geeksforgeeks) covers these topics in depth.
**Please note that the below programs don’t compile in a Windows environment.**
## **Example of fork() in C**
````c
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>
int main()
{
    // make two process which run same
    // program after this instruction
    pid_t p = fork();
    if(p<0){
      perror("fork fail");
      exit(1);
    }
    printf("Hello world!, process_id(pid) = %d \n",getpid());
    return 0;
}
````
**Output**
```
Hello world!, process_id(pid) = 31
Hello world!, process_id(pid) = 32
```
### **Example 2: Calculate the number of times hello is printed.**
````c
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>
int main()
{
    fork();
    fork();
    fork();
    printf("hello\n");
    return 0;
}
````
**Output**
```
hello
hello
hello
hello
hello
hello
hello
hello
```
**Explanation**
The number of times 'hello' is printed is equal to the number of processes created. Total Number of Processes = 2n, where n is the number of fork system calls. So here n = 3, 23 = 8 Let us put some label names for the three lines:
```
fork ();   // Line 1fork ();   // Line 2fork ();   // Line 3       L1       // There will be 1 child process     /     \     // created by line 1.  L2      L2    // There will be 2 child processes /  \    /  \   //  created by line 2L3  L3  L3  L3  // There will be 4 child processes                 // created by line 3
```
So there is a total of eight processes (new child processes and one original process). If we want to represent the relationship between the processes as a tree hierarchy it would be the following:
- Main process: **P0**
- Processes created by the **1st fork: P1**
- Processes created by the **2nd fork: P2, P3**
- Processes created by the **3rd fork: P4, P5, P6, P7**
![tree-diagram-of-processes](assets/tree-diagram-of-processes-ff9ceb6900.webp)
### **Example 3: Predict the Output of the following program.**
````c
#include <stdio.h>
#include <stdlib.h>
#include <sys/types.h>
#include <unistd.h>
void forkexample()
{
    pid_t p;
    p = fork();
    if(p<0)
    {
      perror("fork fail");
      exit(1);
    }
    // child process because return value zero
    else if ( p == 0)
        printf("Hello from Child!\n");
    // parent process because return value non-zero.
    else
        printf("Hello from Parent!\n");
}
int main()
{
    forkexample();
    return 0;
}
````
**Output**
```
Hello from Parent!
Hello from Child!
```
> **Note:** In the above code, a child process is created. fork() returns 0 in the child process and positive integer in the parent process. Here, two outputs are possible because the parent process and child process are running concurrently. So we don’t know whether the OS will first give control to the parent process or the child process.
Parent process and child process are running the same program, but it does not mean they are identical. OS allocates different data and states for these two processes, and the control flow of these processes can be different. See the next example:
### **Example 4: Predict the Output of the following program.**
````c
#include <stdio.h>
#include <stdlib.h>
#include <sys/types.h>
#include <unistd.h>
void forkexample()
{
    int x = 1;
    pid_t p = fork();
      if(p<0){
      perror("fork fail");
      exit(1);
    }
    else if (p == 0)
        printf("Child has x = %d\n", ++x);
    else
        printf("Parent has x = %d\n", --x);
}
int main()
{
    forkexample();
    return 0;
}
````
**Output**
```
Parent has x = 0
Child has x = 2
```
       or
**Output**
```
Child has x = 2Parent has x = 0
```
Here, global variable change in one process does not affect two other processes because the data/state of the two processes is different. And also parent and child run simultaneously so two outputs are possible.
### **fork() vs exec()**
The fork system call creates a new process. The new process created by fork() is a copy of the current process except for the returned value. On the other hand, the exec() system call replaces the current process with a new program.
### 1. A process executes the following code
````c
for (i = 0; i < n; i++)
    fork();
````
The total number of child processes created is **(GATE-CS-2008)**
(A) n 
(B) 2^n – 1
(C) 2^n
(D) 2^(n+1) – 1
See [this](https://www.geeksforgeeks.org/questions/a-process-executes-the-following-code-for-i/) for a solution.
### 2. Consider the following code fragment:
````c
if (fork() == 0) {
    a = a + 5;
    printf("%d, %d\n", a, &a);
}
else {
    a = a –5;
    printf("%d, %d\n", a, &a);
}
````
Let u, v be the values printed by the parent process, and x, y be the values printed by the child process. Which one of the following is TRUE? **(GATE-CS-2005)**
(A) u = x + 10 and v = y
(B) u = x + 10 and v != y
(C) u + 10 = x and v = y
(D) u + 10 = x and v != y
See [this](https://www.geeksforgeeks.org/questions/consider-the-following-code-fragment-if-fork-0/) for a solution.
### 3. Predict the output of the below program.
````c
#include <stdio.h>
#include <unistd.h>
int main()
{
    fork();
    fork() && fork() || fork();
    fork();
    printf("forked\n");
    return 0;
}
````
See [this](https://www.geeksforgeeks.org/cpp/fork-and-binary-tree/) for the solution
**Related Articles :**
- [C program to demonstrate fork() and pipe()](https://www.geeksforgeeks.org/c/c-program-demonstrate-fork-and-pipe/)
- [Zombie and Orphan Processes in C](https://www.geeksforgeeks.org/c/zombie-and-orphan-processes-in-c/)
- [fork() and memory shared b/w processes created using it](https://www.geeksforgeeks.org/c/fork-memory-shared-bw-processes-created-using/)
This article is contributed by **Team GeeksforGeeks** and **Kadam Patel**. If you like GeeksforGeeks and would like to contribute, you can also write an article using [write.geeksforgeeks.org](https://write.geeksforgeeks.org/) or mail your article to review-team@geeksforgeeks.org. See your article appearing on the GeeksforGeeks main page and help other Geeks. Please write comments if you find anything incorrect, or you want to share more information about the topic discussed above.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/c/fork-system-call/)

## GATE CS

- Subject: Operating System
- Topic: Processes, Threads, CPU Scheduling

> [!note] Related notes
>
> - [[Benefits of Multithreading]]
> - [[Context Switching in OS]]
> - [[Difference between multitasking, multithreading and multiprocessing]]
> - [[Difference between thread and process]]
> - [[Fork function call]]
> - [[Introduction of System Call]]
> - [[Microkernel]]
> - [[Monolithic Kernel and key differences from Microkernel]]
> - [[Multi threading models]]
> - [[Multithreading]]
