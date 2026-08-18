---
title: "Program to calculate the Round Trip Time (RTT)"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/dsa/program-calculate-round-trip-time-rtt/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Program to calculate the Round Trip Time (RTT)
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/program-calculate-round-trip-time-rtt/)

---

# Program to calculate the Round Trip Time (RTT)

**Round trip time(RTT)** is the length of time it takes for a signal to be sent plus the length of time it takes for an acknowledgment of that signal to be received. This time, therefore, consists of the propagation times between the two-point of the signal.
On the Internet, an end-user can determine the RTT to and from an IP(Internet Protocol) address by pinging that address. The result depends on various factors:-
- The data rate transfer of the source's internet connection.
- The nature of transmission medium.
- The physical distance between source and destination.
- The number of nodes between source and destination.
- The amount of traffic on the LAN(Local Area Network) to which end-user is connected.
- The number of other requests being handled by intermediate nodes and the remote server.
- The speed with which the intermediate node and the remote server function.
- The presence of Interference in the circuit.
Examples:
```
Input : www.geeksforgeeks.org
Output : Time in seconds : 0.212174892426
Input : www.cricbuzz.com
Output : Time in seconds : 0.55425786972
```
````python
# Python program to calculate RTT
import time
import requests
# Function to calculate the RTT
def RTT(url):
    # time when the signal is sent
    t1 = time.time()
    r = requests.get(url)
    # time when acknowledgement of signal
    # is received
    t2 = time.time()
    # total time taken
    tim = str(t2-t1)
    print("Time in seconds :" + tim)
# driver program
# url address
url = "http://www.google.com"
RTT(url)
````
````csharp
//c# program to calculate RTT
using System;
using System.Net;
class Program
{
    static void Main(string[] args)
    {
        string url = "http://www.google.com";
        // time when the signal is sent
        var t1 = DateTime.Now;
        using (var client = new WebClient())
        {
            var result = client.DownloadString(url);
        }
        // time when acknowledgement of signal
        // is received
        var t2 = DateTime.Now;
        // total time taken
        var timeTaken = t2 - t1;
        Console.WriteLine("Time in seconds : " + timeTaken.TotalSeconds);
    }
}
//this code is contributed by snehalsalokhe -> (Snehal Salokhe)
````
**Output:**
```
  Time in seconds :0.0579478740692
```
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/program-calculate-round-trip-time-rtt/)

## GATE CS

- Subject: Computer Networks
- Topic: Data Link Layer

> [!note] Related notes
>
> - [[Aloha]]
> - [[Back-off Algorithm for CSMA CD]]
> - [[Bit Stuffing]]
> - [[Carrier sense multiple access]]
> - [[Collision Avoidance in wireless networks]]
> - [[Collision Detection in CSMA CD]]
> - [[Computer Networks Error Detection]]
> - [[Controlled Access Protocols]]
> - [[Difference between Byte stuffing and Bit stuffing]]
> - [[Efficiency of CSMA CD]]
