---
title: "Simple Network Management Protocol (SNMP)"
subject: "Computer Networks"
topic: "Application Layer"
source: "https://www.geeksforgeeks.org/computer-networks/simple-network-management-protocol-snmp/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Application Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/application-layer
---


> [!abstract] Simple Network Management Protocol (SNMP)
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Application Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/simple-network-management-protocol-snmp/)

---

# Simple Network Management Protocol (SNMP)

Simple Network Management Protocol (SNMP) is a widely used protocol for network management that provides a standardized framework for monitoring and managing network devices such as routers, switches, servers, printers,firewalls, and load balancer. It operates within the application layer of the Internet protocol suite and allows network administrators to manage network performance, find and solve network problems, and plan for network growth.In this article we will see SNMP protocol in detail. 
## What is Simple Network Management Protocol (SNMP)?
**Simple Network Management Protocol (SNMP)** is an Internet Standard protocol used for managing and monitoring network-connected devices in IP networks. SNMP is an [application layer protocol](https://www.geeksforgeeks.org/computer-networks/protocols-application-layer/) that uses UDP port number 161/162. SNMP is used to monitor the network, detect network faults, and sometimes even to configure remote devices. 
## Architecture of SNMP
There are mainly three main components in SNMP architecture:
- **SNMP Manager:** It is a centralized system used to monitor the network. It is also known as a Network Management Station (NMS). A [router](https://www.geeksforgeeks.org/computer-networks/introduction-of-a-router/) that runs the SNMP server program is called an agent, while a host that runs the SNMP client program is called a manager.
- **SNMP agent:** It is a software management software module installed on a managed device. The manager accesses the values stored in the database, whereas the agent maintains the information in the database. To ascertain if the router is congested or not, for instance, a manager can examine the relevant variables that a router stores, such as the quantity of packets received and transmitted.
- **Management Information Base:**[MIB](https://www.geeksforgeeks.org/ethical-hacking/snmp-in-wireshark/)  consists of information on resources that are to be managed. This information is organized hierarchically. It consists of objects instances which are essentially variables. A MIB, or collection of all the objects under management by the manager, is unique to each agent. System, interface, address translation, IP, [UDP](https://www.geeksforgeeks.org/computer-networks/user-datagram-protocol-udp/) , and EGP , [ICMP](https://www.geeksforgeeks.org/computer-networks/internet-control-message-protocol-icmp/) , [TCP](https://www.geeksforgeeks.org/computer-networks/what-is-transmission-control-protocol-tcp/) are the eight categories that make up MIB. The MIB object is home to these groups.
![](assets/snmpenumeration-0b0043eff6.jpg)
## **SNMP Messages**
- **GetRequest** : It is simply used to retrieve data from SNMP agents. In response to this, the SNMP agent responds with the requested value through a response message.
- **GetNextRequest :** To get the value of a variable, the manager sends the agent the GetNextRequest message. The values of the entries in a table are retrieved using this kind of communication. The manager won't be able to access the values if it doesn't know the entries' indices. The GetNextRequest message is used to define an object in certain circumstances.
- **SetRequest :** It is used by the SNMP manager to set the value of an object instance on the SNMP agent.
- **Response :** When sent in response to the Set message, it will contain the newly set value as confirmation that the value has been set.
- **Trap :** These are the message sent by the agent without being requested by the manager. It is sent when a fault has occurred.
- **InformRequest :** It was added to SNMPv2c and is used to determine if the manager has received the trap message or not. It is the same as a trap but adds an acknowledgement that the trap doesn't provide.
## **SNMP Security Levels**
- **noAuthNoPriv:** This (no authentication, no privacy) security level uses a community string for authentication and no encryption for privacy.
- **authNopriv:** This security level ( [authentication](https://www.geeksforgeeks.org/computer-networks/difference-between-authentication-and-authorization/) , no privacy) uses HMAC with Md5 for authentication and no encryption is used for privacy.
- **authPriv:** This security level (authentication, privacy) uses [HMAC](https://www.geeksforgeeks.org/computer-networks/what-is-hmachash-based-message-authentication-code/)  with [MD5](https://www.geeksforgeeks.org/computer-networks/what-is-the-md5-algorithm/) or SHA for authentication and encryption uses the DES-56 algorithm.
## Versions of SNMP
- **SNMPv1:** It uses community strings for authentication and uses UDP only. SNMPv1 is the first version of the protocol. It is described in RFCs 1155 and 1157 and is simple to set up.
- **SNMPv2c:** It uses community strings for authentication. It uses UDP but can be configured to use TCP. Improved MIB structure elements, transport mappings, and protocol packet types are all included in this updated version. However, it also makes use of the current "community-based" SNMPv1 administrative structure, which is why the version is called SNMPv2c. RFC 1901, RFC 1905, and RFC 1906 all describe it.
- **SNMPv3:** It uses Hash-based MAC with [MD5](https://www.geeksforgeeks.org/computer-networks/what-is-the-md5-algorithm/) or [SHA](https://www.geeksforgeeks.org/java/sha-1-hash-in-java/) for authentication and DES-56 for privacy. This version uses TCP. Therefore, the conclusion is the higher the version of SNMP, the more secure it will be. NMPv3 provides the remote configuration of SNMP entities. This is the most secure version to date because it also includes authentication and encryption, which may be used alone or in combination. RFC 1905, RFC 1906, RFC 2571, RFC 2572, RFC 2574, and RFC 2575.6 are the RFCs for SNMPv3.
## **Characteristics of SNMP**
- SNMP is used to monitor network.
- It detects any network faults.
- It can also be used to configure remote devices.
- It allows a standardized way of collecting information about all kinds of devices from various manufacturers among the networking industry.
## Advantages of SNMP
- It is easy to implement.
- Agents are widely implemented.
- Agent level overhead is minimal.
- It is robust and extensible.
- Polling approach is good for[LAN](https://www.geeksforgeeks.org/computer-networks/types-of-area-networks-lan-man-and-wan/) based managed object.
- It offers the best direct manager agent interface.
## Limitation of SNMP
- It does not scale well.
- There is no object orietned data view.
- It has no standard control definition.
- It has many implementation specific (private MIB) extensions.
- It has high communication overhead due to polling
## Conclusion
The Simple Network Management Protocol (SNMP) is an important protocol for managing and monitoring network-connected devices in [IP networks](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-an-ip-address/). It enables administrators to effectively monitor network performance, discover and address errors, and configure remote devices. While SNMP's simplicity and popularity provide significant advantages, it also has drawbacks, such as scalability concerns and high communication costs. Despite its drawbacks, SNMP remains an important in network management.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/simple-network-management-protocol-snmp/)

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
> - [[How DHCP server dynamically assigns IP address to a host]]
> - [[HTTP Non-Persistent & Persistent Connection]]
> - [[LiFi vs WiFi]]
