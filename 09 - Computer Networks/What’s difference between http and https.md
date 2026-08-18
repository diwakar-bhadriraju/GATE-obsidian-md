---
title: "Difference between http:// and https://"
subject: "Computer Networks"
topic: "Application Layer"
source: "https://www.geeksforgeeks.org/computer-networks/difference-between-http-and-https/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Application Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/application-layer
---


> [!abstract] Difference between http:// and https://
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Application Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/difference-between-http-and-https/)

---

# Difference between http:// and https://

When browsing the internet, you often see website URLs starting with either http:// or https://. These prefixes indicate how data is transferred between your browser and the website’s server. While both HTTP and HTTPS are communication protocols, the key difference lies in security.
![http:// and https://](assets/HTTPSdrawio-660x368-c92fbb7583.jpg)
## What is HTTP?
HTTP (HyperText Transfer Protocol) is an application-layer protocol used for transferring data over the web. It was introduced by Tim Berners-Lee to enable communication between web browsers and web servers. [HTTP](https://www.geeksforgeeks.org/html/what-is-http/) defines a set of rules that allow clients (browsers) to request resources such as web pages, images, or videos from servers. 
![HTTP](assets/http-3d09c420a4.jpg)
HTTP
### Key Points about HTTPKey:
- Uses plain text for data transmission
- Does not provide encryption or authentication
- Vulnerable to data interception and modification
- Default port number: 80
> **Note:** HTTP does not encrypt data, sensitive information such as passwords or payment details can be easily compromised.
### How HTTP Works
1. The client sends an HTTP request (e.g., GET or POST) to the server.
2. The server processes the request.
3. The server sends an HTTP response containing: Status code (e.g., 200, 404), Headers and Response body (data or error message).
## What is HTTPS?
[HTTPS](https://www.geeksforgeeks.org/computer-networks/https-full-form/) stands for Hyper Text Transfer Protocol Secure. HTTP Secure (HTTPS), could be a combination of the Hypertext Transfer Protocol with the SSL/[TLS](https://www.geeksforgeeks.org/computer-networks/transport-layer-security-tls/) convention to supply encrypted communication and secure distinguishing proof of an arranged web server. HTTPS is more secure than HTTP because HTTPS is certified by the [SSL(Secure Socket Layer)](https://www.geeksforgeeks.org/computer-networks/secure-socket-layer-ssl/). Whatever website you are visiting on the internet, if its URL is HTTP, then that website is not secure.
![HTTPS](assets/Untitled-Diagram-51-81b8fe98f4.png)
HTTPS
### Why HTTPS is Secure
- Data is encrypted, preventing eavesdropping
- Server identity is verified using digital certificates
- Protects against man-in-the-middle attacks
Modern browsers clearly mark HTTPS websites as secure, and many features work only over HTTPS.
### How HTTPS Works
1. The client initiates a secure connection.
2. The server presents its SSL/TLS certificate.
3. The client verifies the certificate with a trusted authority.
4. An encrypted session is established.
5. All HTTP data is transferred securely inside this encrypted channel.
Default port used by HTTPS: 443
## Difference Between HTTP and HTTPS
| **HTTP** | **HTTPS** |
| --- | --- |
| HTTP stands for HyperText Transfer Protocol. In HTTP, the URL begins with “http://”. | HTTPS stands for HyperText Transfer Protocol Secure. In HTTPS, the URL starts with “https://”. |
| HTTP uses port number 80 for communication. | HTTPS uses port number 443 for communication. |
| Hyper-text exchanged using HTTP goes as plain text i.e. anyone between the browser and server can read it relatively easily if one intercepts this exchange of data and due to which it is Insecure. | HTTPS is considered to be secure but at the cost of processing time because Web Server and Web Browser need to exchange encryption keys using Certificates before actual data can be transferred. |
| HTTP Works at the [Application Layer](https://www.geeksforgeeks.org/computer-networks/application-layer-in-osi-model/). | HTTPS works at [Transport Layer](https://www.geeksforgeeks.org/computer-networks/transport-layer-responsibilities/). |
| HTTP does not use encryption, which results in low security in comparison to HTTPS. | HTTPS uses Encryption which results in better security than HTTP. |
| HTTP speed is faster than HTTPS. | HTTPS speed is slower than HTTP. |
| HTTP does not use data hashtags to secure data. | HTTPS will have the data before sending it and returning it to its original state on the receiver side. |
| HTTP is used to transfer text, video, and images via web pages. | HTTPS is used to transfer data securely via a network. |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/difference-between-http-and-https/)

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
