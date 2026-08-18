---
title: "Types of Routing"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/types-of-routing/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Types of Routing
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/types-of-routing/)

---

# Types of Routing

Routing is the process of determining paths through a network for sending data packets. It ensures that data moves effectively from source to destination, making the best use of network resources and ensuring consistent communication.
Routing is performed by layer 3 (or network layer) devices to deliver the packet by choosing an optimal path from one network to another. It is an autonomous process handled by the network devices to direct a data packet to its intended destination. The node here refers to a network device called Router.
Routing is essential for determining the optimal path for data packets across networks. Different routing techniques, such as static, dynamic, and hybrid, are used depending on the network. The  [**GATE CS Self-Paced Course**](https://www.geeksforgeeks.org/courses/category/gate?utm_source=test_series&utm_medium=cse/)  provides thorough coverage of routing algorithms, making it easier to grasp this critical networking concept
## Types of Routing
[Routing](https://www.geeksforgeeks.org/computer-networks/what-is-routing/) is typically of 3 types, each serving its purpose and offering different functionalities.
![Types-of-Routing](assets/Types-of-Routing-142d605d94.jpg)
Types of Routing
## **1. Static Routing**
[Static routing](https://www.geeksforgeeks.org/computer-networks/difference-between-static-and-dynamic-routing/) is also called as “non-adaptive routing”. In this, routing configuration is done manually by the network administrator. Let’s say for example, we have 5 different routes to transmit data from one node to another, so the network administrator will have to manually enter the routing information by assessing all the routes.
### **Advantages of Static Routing**
- No routing overhead for the router [CPU](https://www.geeksforgeeks.org/computer-organization-architecture/difference-between-cpu-and-gpu/) which means a cheaper router can be used to do routing.
- It adds security because only an only administrator can allow routing to particular networks only.
- No [bandwidth](https://www.geeksforgeeks.org/computer-networks/introduction-to-bandwidth/) usage between [routers](https://www.geeksforgeeks.org/computer-networks/introduction-of-a-router/).
### **Disadvantage of Static Routing**
- For a large network, it is a hectic task for administrators to manually add each route for the network in the [routing table](https://www.geeksforgeeks.org/computer-networks/routing-tables-in-computer-network/) on each router.
- The administrator should have good knowledge of the topology. If a new administrator comes, then he has to manually add each route so he should have very good knowledge of the routes of the topology.
### **Configuration of Static Routing**
![static-routing](assets/static-routing-2d186129c1.jpg)
R1 having IP address 172.16.10.6/30 on s0/0/1, 192.168.20.1/24 on fa0/0. 
R2 having IP address 172.16.10.2/30 on s0/0/0, 192.168.10.1/24 on fa0/0. 
R3 having IP address 172.16.10.5/30 on s0/1, 172.16.10.1/30 on s0/0, 10.10.10.1/24 on fa0/0. 
Now because only static routes for router R3: 
> R3(config)#ip route 192.168.10.0 255.255.255.0 172.16.10.2
> R3(config)#ip route 192.168.20.0 255.255.255.0 172.16.10.6
Here, provided the route for the 192.168.10.0 network where 192.168.10.0 is its network I'd and 172.16.10.2 and 172.16.10.6 are the next-hop address. 
Now, configuring for R2: 
> R2(config)#ip route 192.168.10.0 255.255.255.0 172.16.10.1
> R2(config)#ip route 10.10.10.0 255.255.255.0 172.16.10.1
> R2(config)#ip route 172.16.10.0 255.255.255.0 172.16.10.1
Similarly for R1: 
> R1(config)#ip route 192.168.20.0 255.255.255.0 172.16.10.5
> R1(config)#ip route 10.10.10.0 255.255.255.0 172.16.10.5
> R1(config)#ip route 172.16.10.0 255.255.255.0 172.16.10.5
## **2. Default Routing**
This is the method where the router is configured to send all packets toward a single router (next hop). It doesn't matter to which network the packet belongs, it is forwarded out to the router which is configured for default routing. It is generally used with stub routers. A stub router is a router that has only one route to reach all other networks. 
### **Advantages** of Default Routing
- Default routing provides a “last resort” route for packets that don’t match any specific route in the routing table. It ensures that packets are not dropped and can reach their intended destination.
- It simplifies network configuration by reducing the need for complex routing tables.
- Default routing improves network reliability and reduces packet loss.
### **Disadvantages** of Default Routing
- Relying solely on default routes can lead to inefficient routing, as it doesn’t consider specific paths.
- Using default routes may introduce additional [network latency](https://www.geeksforgeeks.org/computer-networks/what-is-latency/).
### **Configuration of Default Routing**
Using the same topology which we have used for static routing before.
![dynamic-routing](assets/dynamic-routing-8a59d3369b.jpg)
In this topology, R1 and R2 are stub routers so we can configure default routing for both these routers.  Configuring default routing for R1: 
> R1(config)#ip route 0.0.0.0 0.0.0.0 172.16.10.5
Now configuring default routing for R2: 
> R2(config)#ip route 0.0.0.0 0.0.0.0 172.16.10.1
## **3. Dynamic Routing**
Dynamic routing makes automatic adjustments of the routes according to the current state of the route in the routing table. Dynamic routing uses protocols to discover network destinations and the routes to reach them. [RIP](https://www.geeksforgeeks.org/computer-networks/routing-v-s-routed-protocols-in-computer-network/) and [OSPF](https://www.geeksforgeeks.org/computer-networks/open-shortest-path-first-ospf-protocol-fundamentals/) are the best examples of dynamic routing protocols. Automatic adjustments will be made to reach the network destination if one route goes down. A dynamic protocol has the following features: 
- The routers should have the same dynamic protocol running in order to exchange routes.
- When a router finds a change in the topology then the router advertises it to all other routers.
### **Advantages of Dynamic Routing**
- Easy to configure.
- More effective at selecting the best route to a destination remote network and also for discovering remote networks.
### **Disadvantage of Dynamic Routing**
- Consumes more [bandwidth](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-bandwidth-definition-working-importance-uses/) for communicating with other neighbors.
- Less secure than static routing.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/types-of-routing/)

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
