---
title: "Network Address Translation (NAT)"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/network-address-translation-nat/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Network Address Translation (NAT)
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/network-address-translation-nat/)

---

# Network Address Translation (NAT)

Network Address Translation (NAT) allows multiple devices in a private network to access the internet using a single public IP address. It helps conserve IPv4 addresses and hides internal systems for added security.
- Translates private IP addresses into public IP addresses and vice versa.
- Reduces IPv4 shortage by allowing multiple devices to share one public IP
- Hides internal network addresses from external networks.
- Uses port mapping (PAT) to manage multiple device connections simultaneously
![7](assets/7-3773553a31.jpg)
Network Address Translation
> **Note:** IPv4 provides only 2³² (about 4.3 billion) addresses, which is insufficient considering the massive number of devices connected to the Internet. NAT prevents IP exhaustion by enabling thousands of private devices to share a limited number of public IP addresses.
## Working
NAT ways to function is listed as below:
1. A device sends a request, reaches the NAT enabled router.
2. Router replaces the private IP with its public IP and assigns a unique port.
3. NAT stores this mapping in the NAT table.
4. When the server responds, NAT uses the stored entry to send the packet to the correct internal device.
![working_of_nat](assets/working_of_nat-60cb43c562.webp)
### Reason This Works
- Many devices can share one public IP
- Port numbers separate device traffic
- Internal IPs stay hidden from the internet
### Examples
- **Connecting Private Networks to the Internet**: A NAT enabled router translates all private IPs to a single public IP, allowing internal devices to access the Internet securely.
- **Linking Multiple Office Locations**: Organizations use NAT to translate IPs between branches, enabling communication across locations while maintaining private IP schemes internally.
> **Note:** When the response arrives from the external server, NAT uses the stored entry to identify the correct internal device. It then replaces the public IP and port with the original private IP and forwards the packet back to the device.
## Port Number Masking in NAT
Port number masking is required when multiple internal devices use the same port number to communicate with the same external destination.
- Modifies both the private IP address and the source port number
- Creates a unique mapping entry in the NAT table
- Distinguishes traffic from different internal devices
- Ensures that returning packets are delivered to the correct device
## NAT Inside and Outside Addresses
In NAT terminology, inside and outside describe the location of devices relative to the local network and define which addresses are subject to translation.
![NAT](assets/NAT-c4bdfa9eab.webp)
NAT Inside & Outside Address
- Inside addresses belong to the internal network and are typically translated by NAT.
- Outside addresses belong to external networks and are generally not controlled by the organization.
- Translation usually occurs when inside addresses communicate with outside networks.
- These terms help identify the source and destination addresses during NAT processing.
## Types of NAT
There are three main types of NAT based on address mapping methods.
![Static-NAT](assets/Static-NAT-dc33f51969.webp)
Types of NAT
### 1. Static NAT
Static NAT creates a one-to-one mapping between a private IP address and a public IP address.
- Each private IP is permanently mapped to one public IP
- Used for hosting servers that must be accessible from the Internet
- Simple and predictable configuration
- Not cost-effective for large networks
- Requires a separate public IP for each internal device
### 2. Dynamic NAT
Dynamic NAT maps private IP addresses to public IP addresses from a predefined pool.
- Public IPs are assigned temporarily as needed
- Mapping changes when sessions end
- If the public IP pool is exhausted, new requests are denied
- Suitable for networks with limited simultaneous users
- Still requires multiple public IP addresses
### 3. Port Address Translation (PAT)
PAT, also known as NAT Overload, allows multiple private IPs to share a single public IP using different port numbers.
- Uses port numbers to distinguish device traffic
- Enables many devices to access the Internet with one public IP
- Most commonly used NAT type
- Highly cost-effective
- Supports large networks with thousands of users
## NAT Techniques
- **Static Mapping**: Maps a specific private IP to a fixed public IP.
- **IP Masquerading**: Hides an entire private network behind a single public IP.
- **Translation Table Mapping**: Uses a NAT table to track multiple private - public mappings.
- **PAT (Port Address Translation)**: Adds port - level translation for efficient IP usage.
- **Round - Robin Mapping**: Distributes incoming connections from a single public IP to multiple private IPs in sequence.
## Advantages
- Conserves public IPv4 addresses
- Allows multiple devices to share a single public IP
- Hides internal IP addresses from external networks
- Improves privacy by masking internal network structure
## Disadvantages
- Breaks end-to-end connectivity
- Can cause issues with VoIP, gaming, and peer-to-peer applications
- Adds processing overhead on the router
- Makes direct peer-to-peer communication more complex
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/network-address-translation-nat/)

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
