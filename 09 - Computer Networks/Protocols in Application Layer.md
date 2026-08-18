---
title: "Protocols in Application Layer"
subject: "Computer Networks"
topic: "Application Layer"
source: "https://www.geeksforgeeks.org/computer-networks/protocols-application-layer/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Application Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/application-layer
---


> [!abstract] Protocols in Application Layer
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Application Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/protocols-application-layer/)

---

# Protocols in Application Layer

Application layer protocols are those protocols utilized at the application layer of the OSI (Open Systems Interconnection) and TCP/IP models. They facilitate communication and data sharing between software applications on various network devices. These protocols define the rules and standards that allow applications to interact and communicate quickly and effectively over a network.
> **Note:** A critical part of this layer is the set of Application Layer Protocols, which define the rules, message formats and processes for communication between applications across different systems. These protocols standardize how data is requested, transferred and presented.
## Common Application Layer Protocols in Computer Networks
### 1. TELNET
- TELNET Provides remote login and terminal emulation services.
- Allows users to access resources of a remote server as if logged in locally.
- Port Number: 23
**Command:**  
> telnet [\\RemoteServer]
> \\RemoteServer
> :Specifies the name of the server
> to which you want to connect
### 2. FTP
- FTP stands for File Transfer Protocol. It is the protocol that actually lets us transfer files. It can facilitate this between any two machines using it. But FTP is not just a protocol but it is also a program.
- FTP promotes sharing of files via remote computers with reliable and efficient data transfer.
- The Port number for FTP is 20 for data and 21 for control.
**Command** 
> ftp machinename
### 3. TFTP
- TFTP is a Simplified version of FTP, suitable for quick file transfers without authentication.
- Often used for transferring boot files or firmware updates.
- Port: 69
**Command** 
> tftp [ options... ] [host [port]] [-c command]
### 4. NFS
- [NFS](https://www.geeksforgeeks.org/operating-systems/network-file-system-nfs/) Allows remote systems to mount and access files over a network as if they were local.
- Used for resource centralization.
- Port: 2049
**Command** 
> service nfs start
### 5. SMTP
- Used for sending emails across networks.
- Works with Mail Transfer Agents (MTA) for message forwarding.
- Port: 25 (SMTP), also 587 for secure transmission.
**Command** 
> MAIL FROM:<mail@abc.com?
### 6. LPD
- Designed for printer sharing over a network.
- Receives and processes print requests.
- Port: 515
**Command** 
> lpd [ -d ] [ -l ] [ -D DebugOutputFile]
### 7. X window
- Provides a graphical user interface (GUI) environment for client-server applications.
- Commonly used in UNIX/Linux systems.
- Port: 6000+ (increments for each server)
**Command**  
> Run xdm in runlevel 5
### 8. SNMP
- [SNMP](https://www.geeksforgeeks.org/computer-networks/simple-network-management-protocol-snmp/) is Used for network device management and monitoring.
- Allows administrators to query devices and receive alerts.
- Ports: 161 (TCP), 162 (UDP)
**Command**:
> snmpget -mALL -v1 -cpublic snmp\_agent\_Ip\_address sysName.0
### 9. DNS
- Translates domain names into IP addresses (e.g., www.abc.com -> 198.105.232.4).
- Essential for web browsing.
- Port: 53
**Command:**  
> ipconfig /flushdns
### 10. DHCP
- [DHCP](https://www.geeksforgeeks.org/computer-networks/dynamic-host-configuration-protocol-dhcp/) Assigns IP addresses dynamically to hosts on a network.
- Provides additional configuration details like default gateway and DNS.
- Ports: 67 (Server), 68 (Client)
**Command:** 
> clear ip dhcp binding {address | \* }
### 11. HTTP/HTTPS
- HTTP is used for accessing web resources, while HTTPS adds encryption for secure transactions.
- Stateless and client-server based.
- Ports: 80 (HTTP), 443 (HTTPS)
**Command:**
> curl http://example.com
### 12. POP
POP stands for Post Office Protocol and the latest version is known as POP3 (Post Office Protocol version 3). This is a simple protocol used by User agents for message retrieval from mail servers. 
- POP protocol work with Port number 110.
- It uses TCP for establishing connections.
> **Note:** POP works in dual mode- Delete mode, Keep Mode. In Delete mode, it deletes the message from the mail server once they are downloaded to the local system. In Keep mode, it doesn't delete the message from the mail server and also facilitates the users to access the mails later from the mail server.
### 13. IRC
- [IRC](https://www.geeksforgeeks.org/computer-networks/internet-relay-chat-irc/) Provides real-time text messaging for one-to-one or group communication.
- Supports file and media sharing.
- Port: 6667
**Command:**
> irc [server]
### 14. MIME
- [MIME](https://www.geeksforgeeks.org/computer-networks/multipurpose-internet-mail-extension-mime-protocol/) Extends email capabilities to support multimedia like images, video and programs.
- Works alongside SMTP to transmit non-text data.
- Not a standalone protocol, but an extension.
### 15. NNTP (Network News Transfer Protocol)
- [NNTP](https://www.geeksforgeeks.org/computer-networks/network-news-transfer-protocol-nntp/) allows reading and posting messages to Usenet newsgroups. Supports message exchange and discussion forums.
- Port: Typically TCP 119.
- Use case: Online forums and discussion boards before the rise of web forums.
**Command:**
> nntp [server]
### 16. LDAP (Lightweight Directory Access Protocol)
- [LDAP](https://www.geeksforgeeks.org/computer-networks/lightweight-directory-access-protocol-ldap/) provides access and management of directory services over a network. Supports user authentication, resource lookup, and directory management.
- Port: Typically TCP/UDP 389, secure version (LDAPS) uses TCP 636.
- Use case: Active Directory in Windows, corporate directories.
**Command:**
> ldap [server]
### 17. NTP (Network Time Protocol)
- [NTP](https://www.geeksforgeeks.org/computer-networks/network-time-protocol-ntp/) synchronizes system clocks across networked devices. Supports accurate timestamps for logging and security.
- Port: UDP 123.
- Use case: Keeping servers and network devices in sync, e.g., for financial transactions or logging.
**Command:**
> ntp [server]
### 18. MQTT (Message Queue Telemetry Transport Protocol)
- [MQTT](https://www.geeksforgeeks.org/computer-networks/introduction-of-message-queue-telemetry-transport-protocol-mqtt/) provides lightweight messaging for IoT devices. Supports publish/subscribe communication between devices and brokers.
- Port: Typically TCP 1883, secure version (MQTTS) uses TCP 8883.
- Use case: IoT sensors, home automation, telemetry systems.
**Command:**
> mqtt [broker] [topic]
### 19. SIP (Session Initiation Protocol)
- [SIP](https://www.geeksforgeeks.org/computer-networks/session-initiation-protocol/) establishes, manages, and terminates multimedia sessions. Supports VoIP calls, video calls, and conferencing.
- Ports: TCP/UDP 5060 (non-encrypted), TCP/UDP 5061 (encrypted with TLS).
- Use case: VoIP services, video conferencing, and instant messaging apps.
**Command:**
> sip [server]
### Related Articles:
> - [Application layer protocols](https://www.geeksforgeeks.org/computer-networks/application-layer-protocols-in-tcp-ip/)
> - [OSI (Open Systems Interconnection)](https://www.geeksforgeeks.org/computer-networks/open-systems-interconnection-model-osi/)
> - [TELNET](https://www.geeksforgeeks.org/computer-networks/introduction-to-telnet/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/protocols-application-layer/)

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
