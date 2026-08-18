---
title: "P2P (Peer To Peer) File Sharing"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/p2p-peer-to-peer-file-sharing/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] P2P (Peer To Peer) File Sharing
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/p2p-peer-to-peer-file-sharing/)

---

# P2P (Peer To Peer) File Sharing

In Computer Networking, P2P (Peer-to-Peer) is a file-sharing technology, that allows users to access mainly the multimedia files like videos, music, e-books, games, etc. The individual users in this network are referred to as peers. The peers request files from other peers by establishing TCP or UDP connections.
## How Does P2P (Peer-to-Peer) Work?
A peer-to-peer network allows computer hardware and software to communicate without the need for a server. Unlike client-server architecture, there is no central server for processing requests in a [P2P architecture](https://www.geeksforgeeks.org/computer-networks/what-is-p2p-peer-to-peer-process/). The peers directly interact with one another without the requirement of a central server. 
Now, when one peer makes a request, multiple peers may have a copy of that requested object. Now the problem is how to get the IP addresses of all those peers. This is decided by the underlying architecture supported by the P2P systems. Using one of these methods, the client peer can get to know all the peers which have the requested object/file and the file transfer takes place directly between these two peers.
## P2P Architecture
1. Centralized Directory
2. Query Flooding
3. Exploiting Heterogeneity
### **1. Centralized Directory**
A centralized Directory is somewhat similar to [client-server architecture](https://www.geeksforgeeks.org/system-design/client-server-model/) in the sense that it maintains a huge central server to provide directory service. All the peers inform this central server of their IP address and the files they are making available for sharing. The server queries the peers at regular intervals to make sure if the peers are still connected or not. So basically this server maintains a huge database regarding which file is present at which IP addresses. The first system which made use of this method was **Napster**, for Mp3 distribution.
**Working**
- Now whenever a requesting peer comes in, it sends its query to the server.
- Since the server has all the information of its peers, so it returns the IP addresses of all the peers having the requested file to the peer.
- Now the file transfer takes place between these two peers.
![Centralized Directory](assets/p2p-centralized-6c6866d623.jpg)
Centralized Directory
The major problem with such an architecture is that there is a single point of failure. If the server crashes, the whole P2P network crashes. Also, since all of the processing is to be done by a single server so a huge amount of the database has to be maintained and regularly updated.
### 2. Query Flooding
Unlike the centralized approach, this method makes use of distributed systems. In this, the peers are supposed to be connected to an overlay network. It means if a connection/path exists from one peer to another, it is a part of this overlay network. In this overlay network, peers are called nodes, and the connection between peers is called an edge between the nodes, thus resulting in a graph-like structure. **Gnutella** was the first decentralized peer-to-peer network.
#### **Working**
- Now when one peer requests for some file, this request is sent to all its neighboring nodes i.e. to all nodes connected to this node. If those nodes don't have the required file, they pass on the query to their neighbors and so on. This is called query flooding.
- When the peer with the requested file is found (referred to as query hit), the query flooding stops and it sends back the file name and file size to the client, thus following the reverse path.
- If there are multiple query hits, the client selects from one of these peers.
**Gnutella:** Gnutella represents a new wave of P2P applications providing distributed discovery and sharing of resources across the Internet. Gnutella is distinguished by its support for anonymity and its decentralized architecture. A Gnutella network consists of a dynamically changing set of peers connected using TCP/IP.
![Query Flooding](assets/P2P-Peer-To-Peer--File-Sharing---Query-F-7d8cae46b4.png)
Query Flooding
This method also has some disadvantages, the query has to be sent to all the neighboring peers unless a match is found. This increases traffic in the network.
### 3. Exploiting Heterogeneity
This P2P architecture makes use of both the above-discussed systems. It resembles a distributed system like Gnutella because there is no central server for query processing. But unlike Gnutella, it does not treat all its peers equally. The peers with higher bandwidth and network connectivity are at a higher priority and are called **group leaders/supernodes**. The rest of the peers are assigned to these supernodes. These supernodes are interconnected and the peers under these supernodes inform their respective leaders about their connectivity, IP address, and the files available for sharing.
**KaZaA** technology is such an example that makes use of Napster and Gnutella. Thus, the individual group leaders along with their child peers form a Napster-like structure. These group leaders then interconnect among themselves to resemble a Gnutella-like structure.
#### Working
- This structure can process the queries in two ways.
- The first one is that the supernodes could contact other supernodes and merge their databases with their database. Thus, this supernode now has information about a large number of peers.
- Another approach is that when a query comes in, it is forwarded to the neighboring super nodes until a match is found, just like in Gnutella. Thus query flooding exists but with limited scope as each supernode has many child peers. Hence, such a system exploits the heterogeneity of the peers by designating some of them as group leaders/supernodes and others as their child peers
![Exploiting heterogeneity](assets/exploiting-7ae43f329b.jpg)
Exploiting heterogeneity
## P2P File Sharing Security Concerns
Steps that ensure that Sensitive Information on the network is secure:
- You must delete your sensitive information which you don't require and you can apply some restrictions to important file present within the network.
- For strong or accessing sensitive information, try to reduce or remove P2P file-sharing programs on computers.
- Constantly try to monitor the network to find unauthorized file-sharing programs.
- Try to block the unauthorized Peer-to-Peer file sharing programs within the perimeter of the network.
- Implement strong access controls and authentication mechanisms to prevent unauthorized access to sensitive information on the network.
- Use encryption techniques such as Secure Socket Layer (SSL) or Transport Layer Security (TLS) to protect data in transit between peers on the network.
- Implement firewalls, intrusion detection and prevention systems, and other security measures to prevent unauthorized access to the network and to detect and block malicious activity.
- Regularly update software and security patches to address known vulnerabilities in P2P file-sharing programs and other software used on the network.
- Educate users about the risks associated with P2P file-sharing and provide training on how to use these programs safely and responsibly.
- Use data loss prevention tools to monitor and prevent the transmission of sensitive data outside of the network.
- Implement network segmentation to limit the scope of a security breach in case of a compromise, and to prevent unauthorized access to sensitive areas of the network.
- Regularly review and audit the network to identify potential security threats and to ensure that security controls are effective and up-to-date.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/p2p-peer-to-peer-file-sharing/)

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
