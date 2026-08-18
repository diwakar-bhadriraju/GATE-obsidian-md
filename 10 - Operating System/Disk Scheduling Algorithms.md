---
title: "Disk Scheduling Algorithms"
subject: "Operating System"
topic: "File System and Disk Scheduling"
source: "https://www.geeksforgeeks.org/operating-systems/disk-scheduling-algorithms/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/File System and Disk Scheduling"
tags:
  - gate/cs
  - subject/operating-system
  - topic/file-system-and-disk-scheduling
---


> [!abstract] Disk Scheduling Algorithms
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `File System and Disk Scheduling`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/disk-scheduling-algorithms/)

---

# Disk Scheduling Algorithms

Disk scheduling algorithms manage how data is read from and written to a computer's hard disk. These algorithms help determine the order in which disk read and write requests are processed.
- Disk scheduling is also known as I/O Scheduling.
- The main goals of disk scheduling are to optimize the performance of disk operations, reduce the time it takes to access data and improve overall system efficiency.
- Common disk scheduling methods include First-Come, First-Served (FCFS), Shortest Seek Time First (SSTF), SCAN, C-SCAN, LOOK, and C-LOOK.
### Importance of Disk Scheduling in Operating System
- Multiple I/O requests may arrive by different processes and only one I/O request can be served at a time by the disk controller. Thus other I/O requests need to wait in the waiting queue and need to be scheduled.
- Two or more requests may be far from each other so this can result in greater disk arm movement.
- Hard drives are one of the slowest parts of the computer system and thus need to be accessed in an efficient manner.
### Characteristics of Disk Scheduling
- **Seek Time**: Time taken to move the disk arm to the track where data is located.
- **Rotational Latency**: Time taken for the desired sector to rotate under the read/write head.
- **Transfer Time**: Time taken to actually read or write the data, depending on disk speed and data size.
> Disk Access Time = Seek Time + Rotational Latency + Transfer Time
>  Total Seek Time = Total head Movement \* Seek Time
![Disk Access Time and Disk Response Time](assets/disc-scheduling-algorithms-94af2066bb.png)
Disk Access Time and Disk Response Time
**Disk Response Time**
- **Response Time**: The time a request waits before its I/O operation starts.
- **Average Response Time**: The mean waiting time of all requests.
- **Variance in Response Time**: How much individual waiting times differ from the average.
## Goals of Disk Scheduling Algorithms
- Minimize Seek Time
- Maximize Throughput
- Minimize Latency
- Ensuring Fairness
- Efficiency in Resource Utilization
## Disk Scheduling Algorithms
There are several Disk Several Algorithms. We will discuss in detail each one of them.
- FCFS (First Come First Serve)
- SSTF (Shortest Seek Time First)
- SCAN
- C-SCAN
- LOOK
- C-LOOK
- RSS (Random Scheduling)
- LIFO (Last-In First-Out)
- N-STEP SCAN
- F-SCAN
### **1. FCFS (First Come First Serve)**
FCFS (First Come First Serve) is the simplest disk scheduling algorithm where requests are processed in the order they arrive in the queue. It is easy to implement but may lead to higher seek time and lower efficiency.
- Processes requests in arrival order
- Simple and easy to implement
- No starvation of requests
- May result in high seek time and poor performance
![First Come First Serve](assets/fcfs3-77bfcdd05a.jpg)
First Come First Serve
Suppose the order of request is- (50,82,170,43,140,24,16,190) and current position of Read/Write head is: 50 
> So, total overhead movement  (total distance covered by the disk arm) =
> (82-50)+(170-82)+(170-43)+(140-43)+(140-24)+(24-16)+(190-16) =642
**Advantages of FCFS**
Here are some of the advantages of First Come First Serve.
- Every request gets a fair chance
- No indefinite postponement
**Disadvantages of FCFS**
Here are some of the disadvantages of First Come First Serve.
- Does not try to optimize seek time
- May not provide the best possible service
> Learn more in detail: [FCFS](https://www.geeksforgeeks.org/dsa/fcfs-disk-scheduling-algorithms/)
### **2. SSTF (Shortest Seek Time First)**
SSTF (Shortest Seek Time First) is a disk scheduling algorithm that selects the request closest to the current disk arm position, minimizing seek time. It improves performance compared to FCFS by reducing average response time and increasing system throughput.
- Selects the request with minimum seek time
- Executes requests closest to the disk head first
- Reduces average seek time and improves efficiency
- May cause starvation of distant requests
**Example:**
![Shortest Seek Time First](assets/sstf1-e5b45a5048.jpg)
Shortest Seek Time First
Suppose the order of request is- (82,170,43,140,24,16,190) and current position of Read/Write head is: 50
> total overhead movement (total distance covered by the disk arm) =
> (50-43)+(43-24)+(24-16)+(82-16)+(140-82)+(170-140)+(190-170) =208
**Advantages of Shortest Seek Time First**
Here are some of the advantages of Shortest Seek Time First.
- The average Response Time decreases
- Throughput increases
**Disadvantages of Shortest Seek Time First**
Here are some of the disadvantages of Shortest Seek Time First.
- Overhead to calculate seek time in advance
- Can cause Starvation for a request if it has a higher seek time as compared to incoming requests
- The high variance of response time as SSTF favors only some requests
> Learn More in detail: [shortest seek time first](https://www.geeksforgeeks.org/operating-systems/program-for-sstf-disk-scheduling-algorithm/)
### **3. SCAN**
The SCAN algorithm is a disk scheduling method where the disk arm moves in one direction, servicing requests along the way, and then reverses direction at the end, similar to an elevator. It provides better performance than simple algorithms but may cause longer waiting time for some requests.
- Disk arm moves in one direction servicing requests
- Reverses direction after reaching the end
- Also known as the elevator algorithm
- Mid-range requests are served faster, others may wait longer
- **Example:**
![SCAN Algorithm](assets/scan4-1ae29d8437.jpg)
SCAN Algorithm
Suppose the requests to be addressed are-82,170,43,140,24,16,190 and the Read/Write arm is at 50, and it is also given that the disk arm should move **"towards the larger value".**
> SCAN goes to disk end even if no request exists there
Therefore, the total overhead movement  (total distance covered by the disk arm)  is calculated as
> = (199-50) + (199-16) = 332
**Advantages of SCAN Algorithm**
Here are some of the advantages of the SCAN Algorithm.
- High throughput
- Low variance of response time
- Average response time
**Disadvantages of SCAN Algorithm**:
- Head may move to disk end unnecessarily
- High waiting time for some requests
- New requests may wait longer
> Learn More in detail: [SCAN](https://www.geeksforgeeks.org/dsa/scan-elevator-disk-scheduling-algorithms/)
### **4. C-SCAN**
C-SCAN (Circular SCAN) is an improvement over the SCAN algorithm where the disk arm moves in one direction only. Instead of reversing, it jumps back to the beginning of the disk and continues servicing requests, providing more uniform wait times.
- Disk arm moves in one direction only
- After reaching the end, it jumps to the beginning
- Services requests in a circular manner
- Provides more uniform waiting time compared to SCAN
**Example:**
![Circular SCAN](assets/cscan1-0091a5678e.jpg)
Circular SCAN
Suppose the requests to be addressed are- 82,170,43,140,24,16,190 and the Read/Write arm is at 50, and it is also given that the disk arm should move **"towards the larger value".**
So, the total overhead movement  (total distance covered by the disk arm) is calculated as:
> =(199-50) + (199-0) + (43-0) = 391
**Advantages of C-SCAN Algorithm**:
- Eliminates starvation of requests
- Better performance for heavy disk load
- More fair than SCAN algorithm
> Learn more in detail: [**C-SCAN**](https://www.geeksforgeeks.org/dsa/scan-elevator-disk-scheduling-algorithms/)
**Disadvantages of C-SCAN Algorithm**:
- Extra head movement due to return to start
- Increased seek time compared to SCAN in light load
- More overhead because of circular movement
### **5. LOOK**
LOOK is a disk scheduling algorithm similar to SCAN, but instead of moving the disk arm to the end, it only goes up to the last pending request in that direction and then reverses, reducing unnecessary movement.
- Moves disk arm only up to the last request, not the disk end
- Reverses direction after servicing the last request
- Avoids unnecessary disk traversal
- Improves efficiency and reduces seek time compared to SCAN
**Example:**
![LOOK Algorithm](assets/look1-bc2f30add4.jpg)
LOOK Algorithm
Suppose the requests to be addressed are- 82,170,43,140,24,16,190 and the Read/Write arm is at 50, and it is also given that the disk arm should move "towards the larger value". 
So, the total overhead movement  (total distance covered by the disk arm) is calculated as:
> = (190-50) + (190-16) = 314
**Advantages**
- **Reduced Unnecessary Movement:** The disk arm only goes as far as the last request in each direction, avoiding travel to the disk’s physical end (unlike SCAN).
- **Faster Response:** Less head movement leads to quicker service for requests.
**Disadvantages of LOOK Algorithm:**
- Waiting time can still be high for some requests
- Performance depends on request distribution
- Not completely fair to newly arrived requests
> Learn more in detail: [LOOK](https://www.geeksforgeeks.org/operating-systems/look-disk-scheduling-algorithm/)
### 6. C-LOOK
C-LOOK is similar to C-SCAN but avoids unnecessary movement by going only up to the last request in one direction and then jumping to the last request at the other end, instead of going to the disk’s extreme end.
- Moves only up to the last request in one direction
- Jumps to the last request at the other end
- Does not go to the physical disk end
- Reduces unnecessary movement and improves efficiency
**Example:** Suppose the requests to be addressed are-82,170,43,140,24,16,190 and the Read/Write arm is at 50, and it is also given that the disk arm should move "towards the larger value" 
![C-LOOK](assets/clook1-be6299344f.jpg)
C-LOOK
So, the total overhead movement (total distance covered by the disk arm) is calculated as
> = (190-50) + (190-16) + (43-16) = 341
**Advantages:**
- **Uniform Wait Time:** Requests are serviced in a circular manner, so waiting times are more predictable and fair.
- **Reduced Head Movement**: The arm only goes as far as the last request in one direction, then jumps back, saving time compared to C-SCAN.
**Disadvantages of C-LOOK Algorithm:**
- Extra head movement due to circular scanning
- Increased seek time compared to LOOK under light load
- Newly arrived requests may have to wait for a full cycle
> Learn more in detail: [C-LOOK](https://www.geeksforgeeks.org/operating-systems/c-look-disk-scheduling-algorithm/)
### 7. RSS (Random Scheduling)
Random Scheduling is a technique where selects requests randomly for servicing. It is useful in systems with unpredictable conditions like random processing times or machine failures, and is mainly used for analysis and simulation.
- Selects processes randomly for execution
- Suitable for systems with unpredictable or stochastic behavior
- Used in simulation and performance analysis
- Simple but not efficient for practical scheduling
### 8. LIFO (Last-In First-Out)
In LIFO (Last In, First Out) algorithm, the newest jobs are serviced before the existing ones i.e. in order of requests that get serviced the job that is newest or last entered is serviced first, and then the rest in the same order. 
- Maximizes locality and resource utilization
- Can seem a little unfair to other requests and if new requests keep coming in, it causes starvation to the old and existing ones.
### 9. N-STEP SCAN
N-STEP SCAN is a disk scheduling algorithm where requests are divided into groups of size N and each group is processed completely before moving to the next. This ensures fair service and prevents starvation of requests.
- Divides requests into fixed-size groups (buffers) of N
- Processes all requests in one group before taking new ones
- New requests are placed in a separate buffer
- Ensures fairness and guarantees service for all requests
It eliminates the starvation of requests completely.
> Learn more in detail: [N-STEP SCAN](https://www.geeksforgeeks.org/operating-systems/n-step-scan-disk-scheduling/)
### 10. F-SCAN
This algorithm uses two sub-queues. During the scan, all requests in the first queue are serviced and the new incoming requests are added to the second queue. All new requests are kept on halt until the existing requests in the first queue are serviced. 
- **Prevents Arm Stickiness:** The head doesn’t get stuck near one area because requests are split into two queues.
- **Fairness:** All requests in the first queue are guaranteed service before moving to the second, avoiding indefinite delays.
> Learn more in detail: [F-SCAN](https://www.geeksforgeeks.org/operating-systems/fscan-disk-scheduling-algorithm/)
> **Note:** Average Rotational latency is generally taken as 1/2(Rotational latency).
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/disk-scheduling-algorithms/)

## GATE CS

- Subject: Operating System
- Topic: File System and Disk Scheduling

> [!note] Related notes
>
> - [[Difference between FAT32, exFAT, and NTFS File System]]
> - [[File Access Methods]]
> - [[File Allocation Methods]]
> - [[File Directory Path Name]]
> - [[File Systems]]
> - [[Last Minute Notes – Operating Systems]]
> - [[Operating System Free space management]]
> - [[Program for SSTF disk scheduling algorithm]]
> - [[Structures of Directory]]
> - [[Allocating kernel memory]]
