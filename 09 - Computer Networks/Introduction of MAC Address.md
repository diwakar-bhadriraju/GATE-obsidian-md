---
title: "What is MAC Address?"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/mac-address-in-computer-network/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] What is MAC Address?
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/mac-address-in-computer-network/)

---

# What is MAC Address?

To communicate or transfer data from one computer to another, we need an address. In computer networks, various types of addresses are introduced; each works at a different layer. [A MAC address](https://www.geeksforgeeks.org/computer-networks/mac-address-in-computer-network/), which stands for Media Access Control Address, is a physical address that works at the Data Link Layer. In this article, we will discuss addressing a DLL, which is the MAC Address. 
So, go through the article if you are eager to learn what is MAC address and its components.
**Table of Content**
- [What is MAC (Media Access Control) Address?](#what-is-mac-media-access-control-address)
- [Format of MAC Address](#format-of-mac-address)
- [Types of MAC Address](#types-of-mac-address)
- [Reason to have both IP and MAC addresses.](#reason-to-have-both-ip-and-mac-addresses)
- [Why should the MAC address be unique in the LAN network?](#why-should-the-mac-address-be-unique-in-the-lan-network)
- [How do I find the MAC Address?](#how-do-i-find-the-mac-address)
- [What is MAC Cloning?](#what-is-mac-cloning)
- [Characteristics of MAC Address](#characteristics-of-mac-address)
- [Advantages of MAC Address](#advantages-of-mac-address)
- [Disadvantages of MAC Address](#disadvantages-of-mac-address)
## What is MAC (Media Access Control) Address?
**MAC Addresses** are unique **48-bit** hardware numbers of a computer that are embedded into a network card (known as a [**Network Interface Card**](https://www.geeksforgeeks.org/computer-networks/nic-full-form/)) during manufacturing. The MAC Address is also known as the [**Physical Address**](https://www.geeksforgeeks.org/operating-systems/logical-and-physical-address-in-operating-system/) of a network device. In the IEEE 802 standard, the data link layer is divided into two sublayers:
1. Logical Link Control (LLC) Sublayer
2. Media Access Control (MAC) Sublayer
**The MAC** address is used by the Media Access Control (MAC) sublayer of the [Data-Link Layer](https://www.geeksforgeeks.org/computer-networks/data-link-layer/). MAC Address is worldwide unique since millions of network devices exist and we need to uniquely identify each. 
A **MAC address** uniquely identifies network interfaces. For more on networking fundamentals and concepts like MAC addresses, the [**GATE CS Self-Paced Course**](https://www.geeksforgeeks.org/courses/category/gate?utm_source=test_series&utm_medium=cse/) is a comprehensive guide.
![Media Access Control Address](assets/mac-be9c97a94d.jpg)
## Format of MAC Address
To understand what is MAC address is, it is very important that first you understand the format of the MAC Address. So a MAC Address is a 12-digit hexadecimal number (48-bit binary number), which is mostly represented by Colon-Hexadecimal notation.
The First 6 digits (say 00:40:96) of the MAC Address identify the manufacturer, called the OUI (**Organizational Unique Identifier**). IEEE Registration Authority Committee assigns these MAC prefixes to its registered vendors. 
Here are some OUI of well-known manufacturers:
```
CC:46:D6 - Cisco 3C:5A:B4 - Google, Inc.3C:D9:2B - Hewlett Packard00:9A:CD - HUAWEI TECHNOLOGIES CO.,LTD
```
The rightmost six digits represent **Network Interface Controller**, which is assigned by the manufacturer. 
As discussed above, the MAC address is represented by Colon-Hexadecimal notation. But this is just a conversion, not mandatory. MAC address can be represented using any of the following formats:
![Format of MAC Address](assets/mac-notation-6238db7262.jpg)
**Note:** Colon-Hexadecimal notation is used by **Linux OS** and Period-separated Hexadecimal notation is used by **Cisco Systems**.  
## Types of MAC Address
**1. Unicast:** A Unicast-addressed frame is only sent out to the interface leading to a specific NIC. If the LSB (least significant bit) of the first octet of an address is set to zero, the frame is meant to reach only one receiving NIC. The MAC Address of the source machine is always Unicast. 
![Unicast ](assets/unicast-9b97c363a7.jpg)
**2. Multicast:** The multicast address allows the source to send a frame to a group of devices. In Layer-2 (Ethernet) Multicast address, the LSB (least significant bit) of the first octet of an address is set to one. IEEE has allocated the address block 01-80-C2-xx-xx-xx (01-80-C2-00-00-00 to 01-80-C2-FF-FF-FF) for group addresses for use by standard protocols. 
![Multicast](assets/MULTICAST-01e5d0692c.jpg)
**3. Broadcast:**Similar to Network Layer, Broadcast is also possible on the underlying layer( Data Link Layer). Ethernet frames with ones in all bits of the destination address (FF-FF-FF-FF-FF-FF) are referred to as the broadcast addresses. Frames that are destined with MAC address FF-FF-FF-FF-FF-FF will reach every computer belonging to that LAN segment. 
### Broadcast
## Reason to Have Both IP and MAC Addresses.
The reason for having both IP and MAC addresses lies in the way the Internet works, specifically in the structure of the OSI Model. This model is a conceptual framework that describes how data is sent and received over a network. It's divided into seven layers, each performing specific functions.
- **Layer 2**  uses  **MAC addresses**  and is responsible for packet delivery from  **hop to hop**  .
- **Layer 3**  uses  **IP addresses**  and is responsible for packet delivery from  **end to end**  .
Layer 2 [**(Data Link Layer**](https://www.geeksforgeeks.org/computer-networks/data-link-layer/)**)** uses a **MAC (Media Access Control) address**. These are unique identifiers assigned to network interfaces for communications at the data link layer. The primary function of MAC addresses is to manage how data is transported from one network node to another on a direct, physical basis - this is also referred to as "hop to hop" delivery.
On the other hand, Layer 3 **(** [**Network Layer**](https://www.geeksforgeeks.org/computer-networks/network-layer-services-packetizing-routing-and-forwarding/) **)** uses an **IP (Internet Protocol) address**. These IP addresses are used to identify devices on a network and to route traffic between networks. The IP addresses ensure that the data gets from its original source reaches its final destination and it is also called "end-to-end" delivery of data.
When a computer sends data, it first wraps it in an IP header, which includes the source and destination IP addresses. This IP header, along with the data, is then encapsulated in a MAC header, which includes the source and destination MAC addresses for the current "hop" in the path.
As the data travels from one router to the next, the MAC address header is stripped off and a new one is generated for the next hop. However, the IP header, which was generated by the original computer, remains intact until it reaches the final destination. This process illustrates how the IP header manages the "end to end" delivery, while the MAC headers handle the "hop to hop" delivery.
So, Both IP and MAC addresses are essential for the functioning of the Internet. While MAC addresses facilitate the direct, physical transfer of data between network nodes, IP addresses ensure that the data reaches its final destination.
## Why Should the MAC Address Be Unique in the LAN Network?
Consider a **LAN (**[**Local Area Network**](https://www.geeksforgeeks.org/computer-networks/virtual-lan-vlan/)**)** as a large gathering where everyone is engaged in conversations. Now, let's suppose that there are two individuals at this gathering who coincidentally share the same name. This scenario would inevitably create confusion, right? If someone calls out that name, both individuals would respond, making it challenging to discern the intended recipient of the message.
In a similar manner, within a network, each device possesses a distinct identifier referred to as a MAC (Media Access Control) address. Think of it as a unique name assigned to the device. When information is transmitted across the network, it is directed to a specific MAC address, much like a letter being addressed to a specific individual.
However, if multiple devices within the same network were to have identical MAC addresses, it would result in confusion and disrupt the network's functioning. The network would struggle to ascertain which device should receive the transmitted information. To prevent this confusion and ensure the accurate delivery of information, it is vital for each device on a network to possess a unique MAC address.
## How Do I Find the MAC Address?
A MAC address is mostly used to configure a router for a network device or during troubleshooting. The address of our computer device can be easily checked with any operating device. All the Apple devices connected to our home network contain a unique MAC address. Manufacturers may identify a MAC address by other names, such as the physical address, hardware ID, wireless ID, and Wi-Fi address.
Following are the steps which help to find MAC addresses for different OS
### **MAC address on Windows**
Here is the Step-by-Step guide to finding MAC addresses on Windows.
**Command:**
```
ipconfig /all
```
**Step 1 -** Press **Window Start** or Click on Windows Key.
![windows-ss-1](assets/windows-ss-1-e8e87121e2.jpg)**Step 2 -** In the search box, type **cmd,** and the command prompt will get open.
![cmd-ss-2](assets/cmd-ss-2-6e09d8a4b8.jpg)
**Step 3 -** Click on cmd, the command prompt window will display,
![ss-cmd-new](assets/ss-cmd-new-9e80f92821.jpg)
**Step 4 -** In the command prompt type **ipconfig/all** command and then press enter.
![ipmg](assets/ipmg-c1cdf90c4a.jpg)
**Step 5 -** As you will scroll down, each physical address is the MAC address of your device.
![ipmg-(1)](assets/ipmg--1--7c47f3fa05.jpg)
### MAC Address on MacOS
Here is a step-by-step guide to finding MAC addresses on a Mac operating system.
**Command for MAC Address in MacOS:**
```
TCP/IP Control Panel
```
**Step 1 -** Click on System Settings.
![tt](assets/tt-d23a8bcd78.jpg)
**Step 2 -** In the system settings, click on the **MAC network** option.
![network-mac-3](assets/network-mac-3-ce8f2bab0b.jpg)
**Step 3 -** Then go to the **advanced settings.**
![advanced-mac-3](assets/advanced-mac-3-272441bdc3.jpg)
**Step 4 -** Here you find your MAC address.
![ip-mac-1](assets/ip-mac-1-31a5a25272.jpg)
### MAC Address on Unix/Linux
Here is a step-by-step guide to finding MAC addresses on a Unix/Linux operating system.
**Command For MAC Address in Unix/Linux:**
```
ifconfig -aip link list ip address show
```
\_\_mask-blockquote\_\_index=1\_\_
## What is MAC Cloning?
Some ISPs use MAC addresses to assign an IP address to the gateway device. When a device connects to the ISP, the DHCP server records the MAC address and then assigns an IP address. Now the system will be identified through the MAC address. When the device gets disconnected, it loses the IP address.
If the user wants to reconnect, the [DHCP](https://www.geeksforgeeks.org/computer-networks/dynamic-host-configuration-protocol-dhcp/) server checks if the device is connected before. If so, then the server tries to assign the same [IP address](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-an-ip-address/) (in case the lease period has not expired). In case the user changed the router, the user has to inform the ISP about the new MAC address because the new MAC address is unknown to [ISP](https://www.geeksforgeeks.org/computer-networks/internet-service-provider-isp-hierarchy/), so the connection cannot be established. 
Or the other option is **Cloning**, user can simply clone the registered MAC address with ISP. Now router keeps reporting the old MAC addresses to ISP and there will be no connection issue.
## Characteristics of MAC Address
The Media Access Control address (MAC address) is a unique identifier assigned to most network adapters or network interface cards (NICs) by the manufacturer for identification and use in the Media Access Control protocol sub-layer.
An Ethernet MAC address is a 48-bit binary value expressed as 12 hexadecimal digits (4 bits per hexadecimal digit). MAC addresses are in a flat structure and thus they are not routable on the Internet. Serial interfaces do not use MAC addresses. It does NOT contain a network and host portion with the address. It is used to deliver the frame to the destination device.
- MAC addresses are used in LAN (Local Area Network) environments to identify devices and allow communication between them.
- MAC addresses are burned into the hardware of a network interface card (NIC) and cannot be changed, except in some rare cases where the manufacturer has provided a specific tool to do so.
- The first 3 bytes of a MAC address represent the manufacturer ID, while the last 3 bytes represent a unique identifier assigned by the manufacturer.
- MAC addresses are often used in conjunction with [ARP](https://www.geeksforgeeks.org/ethical-hacking/how-address-resolution-protocol-arp-works/)  (Address Resolution Protocol) to resolve IP addresses to MAC addresses for communication on a LAN.
- Some operating systems, such as Windows and [Linux](https://www.geeksforgeeks.org/linux-unix/linux-vs-unix/) , allow you to view the MAC address of your network adapter through a command prompt or network settings.
## Advantages of MAC Address
1. **Uniqueness:**  Each MAC address is unique, which means that devices on the network can be easily identified and managed.
2. **Simplicity:**  MAC addresses are easy to configure and manage, and do not require any additional network infrastructure.
3. **Compatibility:**  MAC addresses are widely used and supported by a variety of networking technologies and protocols, making them compatible with many different systems.
4. **Security:**  MAC addresses can be used to restrict access to a network by only allowing devices with authorized MAC addresses to connect.
5. **Fault-tolerance:**  In case of hardware or software failure, a device can be easily replaced without affecting the network, as long as the new device has the same MAC address as the old one.
6. **Multicasting:**  MAC addresses can be used for multicasting, allowing a single packet to be sent to multiple devices at once.
7. **Efficiency:**  MAC addresses allow for efficient communication on the network, as they enable devices to quickly and easily identify and communicate with each other.
8. **Lower network overhead:**  MAC addresses reduce network overhead by allowing devices to communicate directly with each other without the need for additional routing or addressing.
9. **Ease of troubleshooting:**  MAC addresses can be used to troubleshoot network issues by identifying the source of problems and tracking network activity.
10. **Flexibility:**  MAC addresses can be used to support a variety of network configurations and topologies, including peer-to-peer, client-server, and hybrid models.
## Disadvantages of MAC Address
1. **Limited address space:**  MAC addresses are 48-bit numbers, which means that there is a finite number of possible MAC addresses. This can lead to address conflicts if multiple devices have the same MAC address.
2. **Spoofing:**  MAC addresses can be easily spoofed, allowing unauthorized devices to gain access to the network.
3. **Inefficiency:**  MAC addresses are not hierarchical, which can make it difficult to efficiently manage large networks.
4. **Static addressing:**  MAC addresses are typically assigned at the time of manufacture and cannot be easily changed. This can be a disadvantage in situations where devices need to be reconfigured or replaced.
5. **Limited scope:** [MAC addresses](https://www.geeksforgeeks.org/computer-networks/mac-address-in-computer-network/)  are only used for identifying devices within a local network segment, and cannot be used to identify devices outside of this segment.
6. **Hardware-dependent:**  MAC addresses are tied to the  [network interface card](https://www.geeksforgeeks.org/installation-guide/how-to-install-a-network-interface-card/) (NIC) of a device, which means that if the NIC fails or is replaced, the MAC address also changes.
7. **Lack of encryption:**  MAC addresses are sent in plain text, which can make them vulnerable to interception and eavesdropping.
8. **No inherent security:**  While MAC filtering can be used to restrict access to a network, MAC addresses themselves do not provide any inherent security features.
9. **MAC address collisions:**  In rare cases, MAC addresses can collide, which can cause network disruptions and make it difficult to identify and manage devices on the network.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/mac-address-in-computer-network/)

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
