---
title: "Traceroute in Network Layer"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/traceroute-in-network-layer/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Traceroute in Network Layer
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/traceroute-in-network-layer/)

---

# Traceroute in Network Layer

Traceroute is a tool widely used by network engineers and system administrators for tracing the path a packet travels from a source point to another destination point. By sequentially tracking each router along a packet’s path, traceroute reveals not only which routers a packet encounters but also how long it takes to get from one router (“hop”) to the next.
In general this tool also shows the invisible route data packets follow which helps professionals identify, troubleshoot latency, and gain deeper insights into the network’s structure. Understanding traceroute and its mechanisms at the network layer provides the foundational knowledge needed to maintain robust, efficient, and high-performing communication channels.
## Introduction to Traceroute
A traceroute is a network diagnostic tool that shows the route an [IP packet](https://www.geeksforgeeks.org/computer-networks/tcp-ip-packet-format/) takes from your computer to a specific destination. It works by sending a series of packets with increasing Time-to-Live ([TTL](https://www.geeksforgeeks.org/computer-networks/what-is-time-to-live-ttl/)) values to the target host. Each router along the path decreases the TTL value by one. When the TTL reaches zero, the router sends an [ICMP](https://www.geeksforgeeks.org/computer-networks/internet-control-message-protocol-icmp/) Time Exceeded message back to the source, revealing the IP address of that router.
It shows you the complete route to a [destination address](https://www.geeksforgeeks.org/computer-networks/destination-ip-addresses/). It also shows the time taken (or delays) between intermediate routers. Below is an example of the Windows operating system. 
## How to Run a Traceroute?
### **1. Windows**
1. **Open Command Prompt:**
   - Press the Windows key, type "cmd," and press Enter.
2. **Run the Traceroute Command:**
   - Type `tracert` followed by the target website or IP address, then press Enter. **For example**:
```
tracert google.com
```
![tracert](assets/computer-network-traceroute-2-953096660a.png)
### **What Does the** A**bove Output Mean?**
A first column is a serial number for intermediate routers. In the above output, three packets are sent to every hop to get a good estimate of delays for every router. The three columns show the time taken by three different packets. The last column is the IP/Name of intermediate routers. The output shows three delays for the first hop, followed by delays for the second router and so on. 
### **2. macOS**
1. **Open Terminal:**
   - Go to the Applications folder, then Utilities, and open Terminal.
2. **Run the Traceroute Command:**
   - Type `traceroute` followed by the target website or IP address, then press Enter. **For example:**
```
traceroute google.com
```
### **3. Linux**
1. **Open Terminal:**
   - Open the terminal application on your Linux distribution.
2. **Run the Traceroute Command:**
   - Type `traceroute` followed by the target website or IP address, then press Enter. **For example:**
```
traceroute google.com
```
## **How Does Traceroute Work?**
Traceroute operates by sending a series of data packets to a target address while controlling a key parameter called the “Time to Live” (TTL).
- **Initial TTL:** Traceroute starts by sending a data packet to the target address with a Time to Live (TTL) value of 1.
- **First Hop Response:** The packet reaches the first router (hop), which discards it when the TTL expires and sends back an error message, revealing its IP and response time.
- **Incrementing TTL:** Traceroute then sends another packet with a TTL of 2, which passes the first router and reaches the second hop, again prompting an error response.
- **IP Address Identification:** By increasing the TTL by 1 each time, traceroute gradually uncovers every hop along the path, collecting addresses and delay times at each step.
- **Complete Route Mapping:** This process continues until the packet reaches the destination, resulting in a map of every router the data passes through, helping identify slow links or network issues along the route.
**As shown in the below diagram, there are intermediate routers between source and destination.**
![Working of Traceroute](assets/computer-network-traceroute-1c7a77b560.png)
## What is Traceroute Used For?
Traceroute is commonly used to:
- **Diagnose Network Problems:** By showing each step along the path from your device to a target server, traceroute helps identify where delays, timeouts, or failures occur, making it easier to pinpoint the source of connectivity issues.
- **Measure Network Performance:** It provides the travel time ([latency](https://www.geeksforgeeks.org/computer-networks/what-is-latency/)) between each hop, allowing you to see which links are causing slowdowns and how efficiently data moves through the network.
- **Understand Routing Paths:** Traceroute shows the exact path data takes across various routers and networks, offering insight into the complexity of internet routing and helping administrators optimize their network configurations.
- **Network Troubleshooting:** It helps identify [network congestions](https://www.geeksforgeeks.org/computer-networks/what-is-network-congestion-common-causes-and-how-to-fix-them/), packet loss, or routing issues.
- **Security Analysis:** It can reveal potential security risks, such as misconfigured routers or unauthorized network devices.
- **Network Optimization:** It helps optimize network performance by identifying slow or congested links.
## How To Read A Traceroute Report?
A traceroute report is a line-by-line breakdown of the path a packet takes from your computer to a specific destination. Each line represents a "hop," or a network device, such as a [router](https://www.geeksforgeeks.org/computer-networks/introduction-of-a-router/), that the packet passes through.
- **Look at the Hop Numbers:** Each line in a traceroute output represents a “**hop**,” or a step in the journey from your device to the destination. Hop 1 is typically your local router, and each subsequent hop is another router along the route.
- **Identify the Hostnames and IP Addresses:** Next to the hop number, you’ll see either a hostname, an [IP address](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-an-ip-address/), or both. Hostnames often give clues about the router’s location or the internet service provider ([ISP](https://www.geeksforgeeks.org/computer-networks/internet-service-provider-isp-hierarchy/)). For example a hostname might indicate a city or a data center.
- **Check the Response Times (Latency):** Each hop usually shows a series of response times (in milliseconds). Smaller numbers mean faster responses. A sudden jump in latency can pinpoint where delays occur. For example if hops 1–5 show response times around 10–20 ms, but hop 6 jumps to 300 ms, that’s where a slowdown begins.
- **Look for Timeouts (Asterisks):** If traceroute can’t get a response from a hop, it often shows asterisks **(\*)** instead of numbers. Occasional timeouts don’t always mean a problem, some routers don’t respond to traceroute requests. However repeated timeouts might indicate a routing issue or a downed router.
- **Follow the Path to the Destination:** The last line of the traceroute should show the destination’s IP or hostname with a stable response time. If the route completes, you’ll know the sequence of routers the data passed through. If it doesn’t then you can see at which hop the path fails or stops responding.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/traceroute-in-network-layer/)

## GATE CS

- Subject: Computer Networks
- Topic: Network Layer

> [!note] Related notes
>
> - [[Administrative Distance (AD) and Autonomous System (AS)]]
> - [[ARP, Reverse ARP(RARP), Inverse ARP (InARP), Proxy ARP and Gratuitous ARP]]
> - [[C Program to find IP Address, Subnet Mask & Default Gateway]]
> - [[Circuit Switching]]
> - [[Classes of routing protocols – Set 3]]
> - [[Classification of Routing Algorithms – Set 1]]
> - [[Collision Domain and Broadcast Domain]]
> - [[Computer Network Circuit Switching VS Packet Switching]]
> - [[Computer Network Servers]]
> - [[Computer Networks Longest Prefix Matching in Routers]]
