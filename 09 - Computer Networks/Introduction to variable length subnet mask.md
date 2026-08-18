---
title: "Introduction of Variable Length Subnet Mask (VLSM)"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/introduction-of-variable-length-subnet-mask-vlsm/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Introduction of Variable Length Subnet Mask (VLSM)
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/introduction-of-variable-length-subnet-mask-vlsm/)

---

# Introduction of Variable Length Subnet Mask (VLSM)

Variable Length Subnet Mask (VLSM) is a subnetting technique that allows network administrators to divide an IP network into **subnets of different sizes**. Instead of using one fixed subnet mask for all subnets (as in FLSM), VLSM allows you to apply **multiple subnet masks within the same network**, based on the number of hosts each subnet requires.
This flexibility makes VLSM one of the most efficient IP addressing methods used in modern networks.
# **Why Do We Need VLSM?**
In traditional subnetting (Fixed Length Subnet Mask → FLSM), **all subnets must have the same size**.
 This often leads to wastage of IP addresses.
### **Example of Wastage in FLSM**
If you use a /24 mask (255.255.255.0), each subnet gets **254 usable IP addresses**.
But if:
- One department needs only **10 hosts**
- Another needs **50 hosts**
Both still receive 254 IPs → **huge wastage**.
VLSM solves this by allowing subnets with **different masks**, such as:
- Smaller subnet mask → **More hosts**
- Larger subnet mask → **Fewer hosts**
This ensures **minimum IP wastage**.
# **What is VLSM?**
VLSM stands for **Variable Length Subnet Mask**.
It means:
You can use **more than one mask** inside the same Class A/B/C network.
 You can create **subnets of different sizes** based on actual requirements.
 It is often described as **subnetting the subnet**.
VLSM improves scalability, optimizes IP usage, and is widely used in real-world routing environments (like OSPF, EIGRP, BGP).
## **How VLSM Works (Step-by-Step Procedure)**
Let’s take a scenario:
A network administrator has the IP block: **192.168.1.0/24**, and four departments:
| Department | Required Hosts |
| --- | --- |
| Sales & Purchase | 120 |
| Development | 50 |
| Accounts | 26 |
| Management | 5 |
### **Step 1: Determine Required Block Sizes**
Each subnet must provide enough hosts to cover:
- Network address
- Broadcast address
- Host IPs
So, pick block sizes ≥ required hosts.
### **Step 2: Sort Requirements in Descending Order**
### Largest requirements first:
1. Sales & Purchase → **120 hosts**
2. Development → **50 hosts**
3. Accounts → **26 hosts**
4. Management → **5 hosts**
### **Step 3: Start Assigning Subnets from Largest Block**
### **1. Sales & Purchase (120 hosts)**
Nearest block size → **/25** (126 hosts)
 Subnet: **192.168.1.0/25**
 Mask: **255.255.255.128**
### **2. Development (50 hosts)**
Nearest block size → **/26** (62 hosts)
 Subnet: **192.168.1.128/26**
 Mask: **255.255.255.192**
### **3. Accounts (26 hosts)**
Nearest block size → **/27** (30 hosts)
 Subnet: **192.168.1.192/27**
 Mask: **255.255.255.224**
### **4. Management (5 hosts)**
Nearest block size → **/29** (6 hosts)
 Subnet: **192.168.1.224/29**
 Mask: **255.255.255.248**
Although /28 (14 hosts) could also work, /29 is chosen to **minimize wastage**.
# **Advantages of VLSM over FLSM**
### **1. Efficient IP Utilization**
VLSM allows allocating small subnets for fewer hosts and larger ones for bigger departments, reducing overall IP wastage.
### **2. High Flexibility**
Network administrators can design subnet sizes based on exact requirements, which is especially useful in complex networks.
### **3. Better Scalability**
As the network grows, new subnets can be added without redesigning the entire IP plan.
### **4. Improved Performance**
Well-sized subnets reduce unnecessary broadcast traffic, improving network performance.
### **5. Reduced Management Overhead**
Optimized addressing makes it easier to track and maintain subnets—especially in large organizations.
### **6. Essential for Public IP Allocation**
VLSM is critical when using public IP addresses because wastage must be minimized.
# **Disadvantages of VLSM**
### **1. Increased Complexity**
Requires advanced planning and knowledge of subnetting.
### **2. Higher Management Overhead**
More subnets mean more configurations and documentation.
### **3. Risk of IP Fragmentation**
Subnets can become scattered, making the IP space appear fragmented.
### **4. Compatibility Limitations**
Older hardware/protocols may not support VLSM.
### **5. Configuration Errors**
Manual planning can lead to mistakes, causing IP conflicts or routing issues.
### **6. Potential Reduced Performance**
If poorly designed, too many small subnets can cause congestion.
### **7. Increased Training Requirements**
Network staff must understand subnetting deeply.
### **8. Possible Security Issues**
Improperly isolated subnets may expose sensitive data.
### **9. Higher Cost**
Advanced routers and software are sometimes required, increasing overall network cost.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/introduction-of-variable-length-subnet-mask-vlsm/)

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
