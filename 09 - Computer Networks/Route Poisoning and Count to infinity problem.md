---
title: "Route Poisoning and Count to infinity problem in Routing"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/route-poisoning-and-count-to-infinity-problem-in-routing/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Route Poisoning and Count to infinity problem in Routing
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/route-poisoning-and-count-to-infinity-problem-in-routing/)

---

# Route Poisoning and Count to infinity problem in Routing

The main issue with **D**istance Vector **R**outing (DVR) protocols is Routing Loops since [Bellman-Ford Algorithm](https://www.geeksforgeeks.org/dsa/bellman-ford-algorithm-dp-23/) cannot prevent loops. This routing loop in the DVR network causes the Count to Infinity Problem. Routing loops usually occur when an interface goes down or two routers send updates at the same time. 
**Counting to infinity problem:**
![](assets/counting-to-infinity-d53d6b1ebe.jpg)
So in this example, the Bellman-Ford algorithm will converge for each router, they will have entries for each other. B will know that it can get to C at a cost of 1, and A will know that it can get to C via B at a cost of 2. 
![](assets/counting-to-infinity2-30c89f81c7.jpg)
If the link between B and C is disconnected, then B will know that it can no longer get to C via that link and will remove it from its table. Before it can send any updates it's possible that it will receive an update from A which will be advertising that it can get to C at a cost of 2. B can get to A at a cost of 1, so it will update a route to C via A at a cost of 3. A will then receive updates from B later and update its cost to 4. They will then go on feeding each other bad information toward infinity which is called as **Count to Infinity problem**.
### Solution for Count to Infinity problem:-
**Route Poisoning:**
When a route fails, distance vector protocols spread the *bad news* about a route failure by poisoning the route. Route poisoning refers to the practice of advertising a route, but with a special metric value called Infinity. Routers consider routes advertised with an infinite metric to have failed. Each distance vector routing protocol uses the concept of an actual metric value that represents infinity. RIP defines infinity as 16. The main disadvantage of poison reverse is that it can significantly increase the size of routing announcements in certain fairly common network topologies.
![](assets/route-poison-78c454aa40.jpg)
**Split horizon:**
If the link between B and C goes down, and B had received a route from A, B could end up using that route via A. A would send the packet right back to B, creating a loop. But according to the Split horizon Rule, Node A does not advertise its route for C (namely A to B to C) back to B. On the surface, this seems redundant since B will never route via node A because the route costs more than the direct route from B to C.
Consider the following network topology showing Split horizon-
![](assets/route-poison2-8f5bbe0ec5.jpg)
- In addition to these, we can also use split horizon with route poisoning were above both techniques will be used combined to achieve efficiency and less increase the size of routing announcements.
- Split horizon with Poison reverse technique is used by Routing Information Protocol (RIP) to reduce routing loops. Additionally, **Holddown timers** can be used to avoid the formation of loops. The hold-down timer immediately starts when the router is informed that the attached link is down. Till this time, the router ignores all updates of the down route unless it receives an update from the router of that downed link. During the timer, If the downlink is reachable again, the routing table can be updated.
**References:** 
<https://en.wikipedia.org/wiki/Distance-vector_routing_protocol#Count-to-infinity_problem> 
<https://en.wikipedia.org/wiki/Route_poisoning> 
<https://en.wikipedia.org/wiki/Split_horizon_route_advertisement>
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/route-poisoning-and-count-to-infinity-problem-in-routing/)

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
