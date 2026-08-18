---
title: "How DHCP server dynamically assigns IP address to a host?"
subject: "Computer Networks"
topic: "Application Layer"
source: "https://www.geeksforgeeks.org/operating-systems/how-dhcp-server-dynamically-assigns-ip-address-to-a-host/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Application Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/application-layer
---


> [!abstract] How DHCP server dynamically assigns IP address to a host?
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Application Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/how-dhcp-server-dynamically-assigns-ip-address-to-a-host/)

---

# How DHCP server dynamically assigns IP address to a host?

DHCP is an abbreviation for Dynamic Host Configuration Protocol. It is an application layer protocol used by hosts for obtaining network setup information. The DHCP is controlled by a DHCP server that **dynamically distributes** network configuration parameters such as IP addresses, subnet masks, and gateway addresses. 
**What is a Dynamic host configuration protocol?** 
- Dynamic - Automatically
- Host - Any computer that is connected to the network
- Configuration - To configure a host means to provide network information(IP address, subnet mask, Gateway address) to a host
- Protocol - Set of rules
Summing up, a DHCP server dynamically configures a host in a network. 
**The disadvantage of manually Configuring the host:** Configuring a host when it is connected to the network can be done either manually i.e., by the network administrator or by the DHCP server. In the case of home networks, manual configuration is quite easy. Whereas in large networks, the network administrator might face many problems. 
Also, the manual configuration is prone to mistakes. Say a Network administrator might assign an IP address that was already assigned. Thus, causing difficulty for both administrators as well as neighbors on the network. 
So, here comes the use of the DHCP server. Before discussing how the DHCP server works, let's go through the DHCP entities. 
**Configuring a host using DHCP :**
To configure a host, we require the following things: 
- **Leased IP address** - IP address to a host that lasts for a particular duration which goes for a few hours, a few days, or a few weeks.
- **Subnet Mask** - The host can know on which network it is on.
- **Gateway address** - The Gateway is the Internet Service Provider that connects users to the internet. The Gateway address lets the host know where the gateway is to connect to the internet.
**DHCP Entities**
- **DHCP server:**It automatically provides network information(IP address, subnet mask, gateway address) on lease. Once the duration is expired, that network information can be assigned to another machine.  It also maintains the data storage which stores the available IP addresses.
- **DHCP client:**Any node which requests an IP address allocation to a network is considered a DHCP client.
- **DHCP Relay Agent:**In case, we have only one DHCP server for multiple LAN's then this Agent which presents in every network forwards the DHCP request to the DHCP server. So, using DHCP Relay Agent we can configure multiple LANs with a single server.
**How DHCP server assigns an IP address to a host?**
1. **DHCPDISCOVER:** When a new node is connected to the network, it broadcasts the DHCPDISCOVER message which contains the source address as 0.0.0.0 to every node on the network including the server. DHCP server on receiving the message returns the DHCPOFFER message to the requested host which contains the server address and new IP address to the node.
2. **DHCPOFFER:** If there are multiple servers on the network, the host receives multiple DHCPOFFER messages. It is up to the host to select a particular message.
3. **DHCPREQUEST:**  The requested host on receiving the offer message, again broadcasts the DHCPREQUEST message on the network with the address of the server whose offer message is accepted by the host. The server which pertains to that server address sent by the host checks whether the address to be assigned to the node is available in the data storage.
4. **DHCPACK:** If the address is assigned, it marks the IP address in the storage as unavailable to ensure consistency. Now, the server sends a DHCPACK packet to the requested host which contains network information(IP address, subnet mask, gateway address). In case, if the address is assigned to another machine meanwhile, then the server sends the packet DHCPNAK to the requested host indicating that the IP address is assigned to some other machine.
5. **DHCPRELEASE:** And finally, If the host wants to move to another network or if it has finished its work, it sends the DHCPRELEASE packet to the server indicating that it wants to disconnect. Then the server marks the IP address as available in the storage so that it can be assigned to other machines.
**References:** 
For reference to DHCP protocol, [click here](https://www.youtube.com/watch?v=k4t-NJrKLgM)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/how-dhcp-server-dynamically-assigns-ip-address-to-a-host/)

## GATE CS

- Subject: Computer Networks
- Topic: Application Layer

> [!note] Related notes
>
> - [[Address Resolution in DNS]]
> - [[Basics of Wi-Fi]]
> - [[DHCP Relay Agent]]
> - [[DNS (Domain Name Server) NetWorking]]
> - [[DNS Spoofing or DNS Cache poisoning]]
> - [[Dynamic Host Configuration Protocol]]
> - [[File Transfer Protocol]]
> - [[HTTP Non-Persistent & Persistent Connection]]
> - [[LiFi vs WiFi]]
> - [[Multipurpose Internet mail extension]]
