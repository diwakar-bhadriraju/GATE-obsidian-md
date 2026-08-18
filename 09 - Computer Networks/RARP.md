---
title: "Reverse Address Resolution Protocol - RARP"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/what-is-rarp/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Reverse Address Resolution Protocol - RARP
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/what-is-rarp/)

---

# Reverse Address Resolution Protocol - RARP

Reverse Address Resolution Protocol (RARP) is a network protocol that allows a device to discover its IP address when only its MAC (Media Access Control) address is known. It was designed for systems such as diskless workstations, which do not have permanent storage to save their IP addresses. These devices boot from ROM and must request their IP address dynamically from a RARP server on the local network.
![rarp](assets/rarp-b3c1064d49.webp)
RARP
> **Note:** RARP was standardized in RFC 903 (1984) but is now considered obsolete, replaced by more flexible protocols like BOOTP and DHCP.
## Components of RARP
1. **IP Address Assignment:** Normally, a machine stores its IP address in a configuration file. Diskless systems cannot do this and rely on RARP for IP assignment.
2. **Physical Address:** Every network device has a unique MAC address, stored in its Network Interface Card (NIC).
3. **RARP Request**: A device broadcasts a request containing its MAC address to ask for the corresponding IP address.
4. **RARP Server:** The server maintains a mapping of MAC addresses to IP addresses. On receiving a request, it replies with the correct IP address.
## Working of RARP
Reverse ARP (RARP) is a network protocol used by a client machine in a local area network ([LAN](https://www.geeksforgeeks.org/computer-networks/lan-full-form/)) to obtain its Internet Protocol ([IP](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-an-ip-address/)) address from the gateway router's [ARP](https://www.geeksforgeeks.org/ethical-hacking/how-address-resolution-protocol-arp-works/) (Address Resolution Protocol) table. When a machine doesn't have the memory to store its IP address, such as diskless machines or newly configured systems, it uses RARP to request an IP address.
![rarp-working](assets/rarp-working-7924eb8439.webp)
RARP
1. **RARP Request**: A client broadcasts a RARP request containing its MAC address.
2. **Server Lookup**: A RARP server (or gateway router with ARP table) checks its mapping of MAC -> IP.
3. **RARP Reply**: If a match is found, the server responds with the client’s IP address.
4. **Client Configuration**: The client configures itself with the provided IP and can now communicate on the network.
## RARP Packet Format & Encapsulation
**Packet Format:** The format of the RARP packet is identical to the [ARP](https://www.geeksforgeeks.org/ethical-hacking/how-address-resolution-protocol-arp-works/) packet format. The key difference lies in the Operation field.
- For a RARP Request message, the value of the Operation field is 3.
- For a RARP Reply message, the value of the Operation field is 4.
![rarp-2](assets/rarp-2-7038f34cad.webp)
RARP Packet
**Encapsulation**: RARP packets are encapsulated directly into data-link layer frames (e.g., Ethernet frames) so they can be transmitted over the LAN.
## Difference Between RARP and ARP
| RARP | ARP |
| --- | --- |
| A protocol used to map a physical (MAC) address to an IP address | A protocol used to map an IP address to a physical (MAC) address |
| To obtain the IP address of a network device when only its MAC address is known | To obtain the MAC address of a network device when only its IP address is known |
| Client broadcasts its MAC address and requests an IP address and the server responds with the corresponding IP address | Client broadcasts its IP address and requests a MAC address and the server responds with the corresponding MAC address |
| Rarely used in modern networks as most devices have a pre-assigned IP address | Widely used in modern networks to resolve IP addresses to MAC addresses |
| RFC 903 Standardization | RFC 826 Standardization |
| It uses the value 3 for requests and 4 for responses | It uses the value 1 for requests and 2 for responses |
## Is RARP Obsolete?
Yes. RARP is obsolete and rarely used in modern networks because of its limitations. It has been replaced by:
1. **BOOTP (Bootstrap Protocol):** Provides IP along with gateway, DNS and configuration.
2. **DHCP (Dynamic Host Configuration Protocol):** Extension of BOOTP, most widely used today for dynamic IP assignment and full configuration support.
## Issues in RARP
- Limited scalability
- Lack of security
- No subnetting support
- Router incompatibility
- Compatibility issues with modern networks
## Pros of RARP
- Simplifies configuration for diskless machines.
- Automatic IP assignment reduces manual errors.
- Prevents conflicts by uniquely mapping MAC to IP.
- Legacy support for older devices.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/what-is-rarp/)

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
