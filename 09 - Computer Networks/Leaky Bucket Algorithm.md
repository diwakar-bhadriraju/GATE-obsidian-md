---
title: "Leaky bucket algorithm"
subject: "Computer Networks"
topic: "Transport Layer"
source: "https://www.geeksforgeeks.org/computer-networks/leaky-bucket-algorithm/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Transport Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/transport-layer
---


> [!abstract] Leaky bucket algorithm
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Transport Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/leaky-bucket-algorithm/)

---

# Leaky bucket algorithm

The Leaky Bucket Algorithm is a method used in networking to regulate the rate at which data is transmitted. It maintains a steady sending speed, even when data arrives in sudden bursts, preventing the network from becoming overloaded.
- Incoming packets are stored in a fixed-size buffer before transmission.
- Data is released into the network at a constant rate.
- Packets arriving after the buffer is full are discarded.
- Helps routers and switches use bandwidth in a controlled manner.
![bursty_flow](assets/bursty_flow-4f4d95c1bc.webp)
## Working
A Leaky Bucket algorithm uses a FIFO queue to regulate traffic. For fixed-size packets, a constant number are removed at each clock tick. For variable-size packets, transmission is based on a fixed byte/bit rate. The following is an algorithm for variable-length packets:  
1. Initialize a counter to n at the tick of the clock.
 2. Repeat until n is smaller than the packet size of the packet at the head of the queue.
- Pop a packet out of the head of the queue, say P.
- Send the packet P, into the network
- Decrement the counter by the size of packet P.
3. Reset the counter and go to step 1.
**Example:** Let n=1000 
**Let Packet =**
![leaky_algorithm_2](assets/leak-bucket-1-b26522e4e0.png)
- Since n > size of the packet at the head of the Queue, i.e. n > 200
- Therefore, n = 1000-200 = 800
- Packet size of 200 is sent into the network.
![leaky_algorithm_2](assets/leak-bucket-2-47c6541bc3.png)
- Now, again n > size of the packet at the head of the Queue, i.e. n > 400
- Therefore, n = 800-400 = 400
- Packet size of 400 is sent into the network.
![leaky_algorithm_2](assets/leak-bucket-3-6b390df927.png)
- Since, n < size of the packet at the head of the Queue, i.e.  n < 450Therefore, the procedure is stopped.
- Initialize n = 1000 on another tick of the clock.
- This procedure is repeated until all the packets are sent into the network.
Below is the implementation of above explained approach: 
````cpp
// cpp program to implement leakybucket
#include <bits/stdc++.h>
using namespace std;
int main()
{
    int no_of_queries, storage, output_pkt_size;
    int input_pkt_size, bucket_size, size_left;
    // initial packets in the bucket
    storage = 0;
    // total no. of times bucket content is checked
    no_of_queries = 4;
    // total no. of packets that can
    // be accommodated in the bucket
    bucket_size = 10;
    // no. of packets that enters the bucket at a time
    input_pkt_size = 4;
    // no. of packets that exits the bucket at a time
    output_pkt_size = 1;
    for (int i = 0; i < no_of_queries; i++) // space left
    {
        size_left = bucket_size - storage;
        if (input_pkt_size <= size_left) {
            // update storage
            storage += input_pkt_size;
        }
        else {
            printf("Packet loss = %d\n", input_pkt_size);
        }
        printf("Buffer size= %d out of bucket size= %d\n",
               storage, bucket_size);
        storage -= output_pkt_size;
    }
    return 0;
}
// This code is contributed by bunny09262002
// Improved by: rishitchaudhary
````
````java
// Java Implementation of Leaky bucket
import java.io.*;
import java.util.*;
class Leakybucket {
    public static void main(String[] args)
    {
        int no_of_queries, storage, output_pkt_size;
        int input_pkt_size, bucket_size, size_left;
        // initial packets in the bucket
        storage = 0;
        // total no. of times bucket content is checked
        no_of_queries = 4;
        // total no. of packets that can
        // be accommodated in the bucket
        bucket_size = 10;
        // no. of packets that enters the bucket at a time
        input_pkt_size = 4;
        // no. of packets that exits the bucket at a time
        output_pkt_size = 1;
        for (int i = 0; i < no_of_queries; i++) {
            size_left = bucket_size - storage; // space left
            if (input_pkt_size <= (size_left)) {
                storage += input_pkt_size;
            }
            else {
                System.out.println("Packet loss = "
                                   + input_pkt_size);
            }
            System.out.println("Buffer size= " + storage
                               + " out of bucket size= "
                               + bucket_size);
            storage -= output_pkt_size;
        }
    }
}
// Improved by: rishitchaudhary
````
````python3
# initial packets in the bucket
storage = 0
# total no. of times bucket content is checked
no_of_queries = 4
# total no. of packets that can
# be accommodated in the bucket
bucket_size = 10
# no. of packets that enters the bucket at a time
input_pkt_size = 4
# no. of packets that exits the bucket at a time
output_pkt_size = 1
for i in range(0, no_of_queries):  # space left
    size_left = bucket_size - storage
    if input_pkt_size <= size_left:
      # update storage
        storage += input_pkt_size
    else:
        print("Packet loss = ", input_pkt_size)
    print(f"Buffer size= {storage} out of bucket size = {bucket_size}")
    # as packets are sent out into the network, the size of the storage decreases
    storage -= output_pkt_size
# This code is contributed by Arpit Jain
# Improved by: rishitchaudhary
````
````csharp
// C# Implementation of Leaking bucket
using System;
class Leakingbucket
{
  static void Main(string[] args)
  {
    int no_of_queries, storage, output_pkt_size;
    int input_pkt_size, bucket_size, size_left;
    // initial packets in the bucket
    storage = 0;
    // total no. of times bucket content is checked
    no_of_queries = 4;
    // total no. of packets that can
    // be accommodated in the bucket
    bucket_size = 10;
    // no. of packets that enters the bucket at a time
    input_pkt_size = 4;
    // no. of packets that exits the bucket at a time
    output_pkt_size = 1;
    for (int i = 0; i < no_of_queries; i++)
    {
      size_left = bucket_size - storage; // space left
      if (input_pkt_size <= (size_left))
      {
        storage += input_pkt_size;
      }
      else
      {
        Console.WriteLine("Packet loss = " + input_pkt_size);
      }
      Console.WriteLine("Buffer size= " + storage + " out of bucket size= " + bucket_size);
      storage -= output_pkt_size;
    }
  }
}
// This code is Contributed by phasing17
````
````javascript
// JS code to implement the approach
// initial packets in the bucket
let storage = 0;
// total no. of times bucket content is checked
let noOfQueries = 4;
// total no. of packets that can
// be accommodated in the bucket
let bucketSize = 10;
// no. of packets that enters the bucket at a time
let inputPktSize = 4;
// no. of packets that exits the bucket at a time
let outputPktSize = 1;
for (let i = 0; i < noOfQueries; i++) { // space left
let sizeLeft = bucketSize - storage;
if (inputPktSize <= sizeLeft) {
// update storage
storage += inputPktSize;
} else {
console.log("Packet loss = ", inputPktSize);
}
console.log(`Buffer size= ${storage} out of bucket size = ${bucketSize}`);
// as packets are sent out into the network, the size of the storage decreases
storage -= outputPktSize;
}
// This code is contributed by phasing17
````
**Output** 
> Buffer size= 4 out of bucket size= 10
> Buffer size= 7 out of bucket size= 10
> Buffer size= 10 out of bucket size= 10
> Packet loss = 4
> Buffer size= 9 out of bucket size= 10
## **Leaky Bucket vs Token Bucket**
| Leaky Bucket | Token Bucket |
| --- | --- |
| When the host has to send a packet , packet is thrown in bucket. | In this, the bucket holds tokens generated at regular intervals of time. |
| Bucket leaks at constant rate | Bucket has maximum capacity. |
| Bursty traffic is converted into uniform traffic by leaky bucket. | If there is a ready packet , a token is removed from Bucket and packet is send. |
| In practice bucket is a finite queue outputs at finite rate | If there is no token in the bucket, then the packet cannot be sent. |
## **Advantage**
- Prevents sudden traffic spikes that can cause congestion.
- Produces a smooth and consistent data flow.
- Simple to implement and requires minimal control logic.
- Makes bandwidth usage more predictable.
- Suitable for applications that require steady transmission.
## Disadvantages
- Does not handle burst traffic efficiently.
- Packets may be dropped when the buffer becomes full.
- Available bandwidth may remain unused during low traffic periods.
- Less adaptable to dynamic network conditions.
- Not ideal for highly variable data traffic.
## Applications
- Traffic shaping in routers and switches.
- Bandwidth control in Quality of Service (QoS) networks.
- Voice over IP (VoIP) to ensure stable call quality.
- Video streaming for continuous data delivery.
- Legacy networks such as ATM that require predictable traffic patterns.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/leaky-bucket-algorithm/)

## GATE CS

- Subject: Computer Networks
- Topic: Transport Layer

> [!note] Related notes
>
> - [[Congestion Control]]
> - [[Differences between TCP and UDP]]
> - [[Error Control in TCP]]
> - [[Multiplexing and Demultiplexing in Transport Layer]]
> - [[TCP 3-Way Handshake Process]]
> - [[TCP Congestion Control]]
> - [[TCP Connection Establishment]]
> - [[TCP Connection Termination]]
> - [[TCP flags]]
> - [[TCP Server-Client implementation in C]]
