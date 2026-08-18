---
title: "What is a Server?"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/what-is-server/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] What is a Server?
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/what-is-server/)

---

# What is a Server?

A server is a hardware device or software that processes requests sent over a network and replies to them. A client is the device that submits a request and waits for a response from the server. The computer system that accepts requests for online files and transmits those files to the client is referred to as a server in the context of the Internet.
## Server
A Server is a program or a device that provides functionality for called clients which are other programs or devices. This architecture is called the [client-server model](https://www.geeksforgeeks.org/system-design/client-server-model/).
A single overall computation is distributed across multiple processes or devices. Servers can provide various functionalities called services. These services include sharing data or resources among multiple clients or performing computations for a client. Multiple clients can be served by a single server, and a single client can use multiple servers.
## Key Characteristics of a Server
- **Provides Services:** Servers perform specific tasks like hosting websites, managing emails, storing files, or running applications. These services can vary depending on the server’s purpose. Each type of server performs a specific, well-defined task and is optimized for that role.
  - **File Server**: Stores and lets users share files over a network.
  - **Mail Server**: Sends, receives, and stores emails (e.g., Microsoft Exchange, Postfix).
  - **Database Server**: Provides database access and handles queries (e.g., MySQL, Oracle).
  - **Game Server**: Hosts online multiplayer games and syncs game data between players.
  - **Web Server**: Serves web pages to browsers (e.g., Apache, Nginx)
- **Listens for Requests:** Servers operate using a request-response model. They are always ready and listening on specific network ports for incoming requests. When a client (such as a browser or app) sends a request (like accessing a website), the server processes that request and sends back the appropriate response. It waits for requests from clients and responds accordingly.
- **Always On:** Servers typically run 24/7 to ensure continuous service availability. Servers are designed to run continuously, 24/7.To ensure availability of services (e.g., websites, apps, emails) at any time, from anywhere. Businesses, especially those operating globally, rely on uptime to keep services accessible. Many servers have redundant power supplies, cooling systems, and backup networks to prevent downtime.
- **Can Be Hardware or Software:**
  - **Hardware Server:** A powerful physical machine designed to handle multiple client requests.
  - **Software Server:** A program that performs server functions (e.g., a web server like Apache or Nginx).
## Components of Server
Specific components will differ based on the form factor and function of a given server, but common components are covered here.
- **Hardware:**  The dedicated server's [central processing unit (CPU)](https://www.geeksforgeeks.org/computer-science-fundamentals/central-processing-unit-cpu/) ,  [memory](https://www.geeksforgeeks.org/computer-science-fundamentals/computer-memory/) , [storage device](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-a-storage-device-definition-types-examples/) , network interfaces, and the server chassis are all included in this.
- **Network Connectivity:**  Over a  [local area network (LAN)](https://www.geeksforgeeks.org/computer-networks/lan-full-form/) , [wide area network (WAN)](https://www.geeksforgeeks.org/computer-science-fundamentals/wan-full-form/) , or the [internet](https://www.geeksforgeeks.org/computer-science-fundamentals/internet-and-its-services/) , server programs connect to the network architecture and communicate with client devices. To offer redundancy and accommodate various network setups, certain server form factors contain several network interfaces.
- **Server OS:**  This [operating system (OS)](https://www.geeksforgeeks.org/operating-systems/what-is-an-operating-system/)  was created with a particular kind of client/server environment in mind.
- **Management and Monitoring Tools:**  Instruments for remote management and performance monitoring are frequently included with servers.
- **Server Software:**  This server software supports a particular use case. [Software](https://www.geeksforgeeks.org/computer-science-fundamentals/software-and-its-types/) for email servers, web servers, and [database](https://www.geeksforgeeks.org/dbms/what-is-database/) servers are a few examples.
- **High-Availability Features:** [High-availability (HA)](https://www.geeksforgeeks.org/sql/high-availability-ha-in-sql-server/) capabilities are included on some servers to reduce downtime and guarantee continuous operation. This involves having access to numerous storage systems, backup power supply and network interfaces, and configuration management tools that enable automatic failover and [load balancing](https://www.geeksforgeeks.org/operating-systems/issues-related-to-load-balancing-in-distributed-system/) .
## Working of Server
![Working-of-Server](assets/Working-of-Server-768-8d7076d0b0.webp)
**Server Setup and Functionality :**
- A device must be configured to listen for client requests over a network to function as a server.
- This functionality can be provided by:
  - The operating system,
  - An installed application,
  - Or a combination of both.
**Examples of Server Setup :**
- **Windows Server OS** (by Microsoft):
  - Includes built-in features to listen and respond to client requests.
  - The server’s capabilities expand with additional roles or services installed (e.g., [DHCP, DNS](https://www.geeksforgeeks.org/computer-networks/difference-between-dns-and-dhcp/), File Services).
- **Apache Web Server**:
  - An application installed on top of any operating system (e.g., Windows, Linux).
  - Handles [**HTTP requests**](https://www.geeksforgeeks.org/node-js/different-kinds-of-http-requests/) from web browsers and delivers web pages in response.
**Client-Server Request-Response Model :**
- When a client needs data or functionality, it sends a request over the network to the server.
- The server receives the request, processes it, and returns the necessary information or service.
- This model is often referred to as the request-response or call-and-response model.
![Client-Server-Model](assets/Client-Server-Model-660-91ff83e696.webp)
Client Server Model
## Types of Servers and Their Applications
**Application Server**
These servers host web apps (computer programs that run inside a web browser) allowing users in the network to run and use them preventing the installation of a copy on their own computers. These servers need not be part of the [World Wide Web](https://www.geeksforgeeks.org/computer-networks/world-wide-web-www/). Their clients are computers with a [web browser](https://www.geeksforgeeks.org/computer-networks/web-browser/). 
**Catalog Server**
These servers maintain an index or table of contents of information that can be found across a large distributed network. Distributed networks may include computers, users, files shared on file servers, and web apps. Examples of catalog servers are directory servers and name servers.
Their clients are any computer program that needs to find something on the network. An example can be a domain member attempting to log in, an email client looking for an [email address](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-an-email-address/), or a user looking for a file 
**Communication Server**
These servers maintain an environment needed for one communication endpoint to find other endpoints and then communicate with them.
These servers may or may not include a directory of communication endpoints and a presence detection service, depending on the openness and security parameters of the network. Their clients are communication endpoints. 
**Computing Server**
These servers share vast amounts of computing resources which include CPU and random-access memory over a network. Any computer program that needs more CPU power and [RAM](https://www.geeksforgeeks.org/computer-organization-architecture/different-types-ram-random-access-memory/) than a personal computer can probably afford can use these types of servers.
The client must be a networked computer to implement the client–server model which is a necessity. 
**Database Server**
These servers maintain and share any form of database over a network. A database is an organized collection of data with predefined properties that may be displayed in a table.
Clients of these servers are [spreadsheets](https://www.geeksforgeeks.org/excel/introduction-to-excel-spreadsheet/), [accounting software,](https://www.geeksforgeeks.org/accountancy/sourcing-of-accounting-software/) asset management software, or virtually any computer program that consumes well-organized data, especially in large volumes. 
**Fax Server**
These servers share one or more fax machines over a network which eliminates the hassle of physical access. Any fax sender or recipient is the client of these servers.  
**File Server**
Shares files and folders, storage space to hold files and folders, or both, over a network. Networked computers are the intended clients, even though local programs can be clients.
![FileServer](assets/FileServer-660x330-d287f5b1cb.jpg)
File Server
**Game Server**
These servers enable several computers or gaming devices to play multiplayer games. Personal computers or gaming consoles are their clients. 
**Mail Server**
These servers make email communication possible in the same way as a post office makes snail mail communication possible. Clients of these servers are senders and recipients of email.
**Print Server**
These servers share one or more [printers](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-a-printer/) over a network which eliminates the hassle of physical access. Their clients are computers in need of printing something.
**Proxy Server**
This server acts as an intermediary between a client and a server accepting incoming traffic from the client and sending it to the server.
Reasons to use a proxy server include content control and filtering, improving traffic performance, preventing unauthorized network access, simply routing the traffic over a large and complex network. Their clients are any networked computer. 
**Web Server**
These servers host web pages. A web server is responsible for making the World Wide Web possible. Each website has one or more web servers. Their clients are computers with a web browser.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/what-is-server/)

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
> - [[Computer Networks Longest Prefix Matching in Routers]]
> - [[Difference between layer-2 and layer-3 switches]]
