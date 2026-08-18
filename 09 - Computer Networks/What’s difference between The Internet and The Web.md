---
title: "What’s difference between The Internet and The Web ?"
subject: "Computer Networks"
topic: "Application Layer"
source: "https://www.geeksforgeeks.org/computer-networks/whats-difference-internet-web/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Application Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/application-layer
---


> [!abstract] What’s difference between The Internet and The Web ?
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Application Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/whats-difference-internet-web/)

---

# What’s difference between The Internet and The Web ?

**The Internet** is a global network of networks while **the Web**, also referred to formally as World Wide Web (www) is a collection of information that is accessed via **the Internet**. Another way to look at this difference is that **the Internet** is infrastructure while **the Web** is served on top of that infrastructure. Alternatively, **the Internet** can be viewed as a big **Web** that stores. At a high level, we can even think of **the Internet** as hardware and **the Web** as software!
Web applications use HTTP protocol which is a layer over TCP protocol. In contrast, internet applications can use either TCP or UDP protocol. To visualize the difference think of it as the internet is a network of many computers connected so you can use any port say 90 to send or receive data. In contrast, the web port is fixed as HTTP uses port 80 to communicate, and also the data that is sent is HTML, CSS, and JavaScript. So if you want a feel of an internet application make a socket connection at a random port and send data to another computer via the socket. So in this case you are using the internet for communication and not the web.
## What is the Internet?
In 1995 the first connection was established over what is today known as the Internet. The internet provides a quick and easy exchange of information and is identified as the central tool in this Age of Information.
![internt](assets/internt-300-526408928d.png)
Internet
## What is the WWW?
The World Wide Web, or "Web" for short, is a massive collection of digital pages to access information over the internet. The World Wide Web(WWW) is an internet based service, which uses common set of rules known as Protocols, to distribute documents across the Internet in a standard way.
The Web is viewed through web software such as Google Chrome, Internet Explorer, [Mozilla Firefox](https://www.geeksforgeeks.org/techtips/mozilla-firefox-browser/) etc. The Web uses HTTP protocol, to transmit data and allows applicants to communicate in order to exchange business logic. Web documents also contain graphics, sounds, text and video.
![web](assets/web-300-b367cfbae1.png)
World Wide Web
## Difference Between The Internet and The Web
| Feature | Internet | WWW |
| --- | --- | --- |
| Definition | A global system of interconnected computer networks that use [**TCP/IP protocol**](https://www.geeksforgeeks.org/computer-networks/tcp-ip-in-computer-networking/) to link devices worldwide. | A system of interlinked hypertext documents and multimedia content accessible via the Internet.. |
| Scope | All types of digital communication such as gaming, chatting, file sharing, email, etc. | Specifically refers to the collection of web pages and websites accessible via web browsers. |
| Components | Hardware(servers, routers, devices), protocols(TCP/IP, FTP, [SMTP](https://www.geeksforgeeks.org/computer-networks/simple-mail-transfer-protocol-smtp/), etc) and various services. | Websites, web pages, web servers and hyperlinks that are used to navigate between them. |
| Protocols used | TCP/IP, [FTS](https://www.geeksforgeeks.org/computer-networks/file-transfer-protocol-ftp-in-application-layer/), SMTP, [IMAP](https://www.geeksforgeeks.org/computer-networks/internet-message-access-protocol-imap/) and many more. | Mainly [HTTP/HTTPS](https://www.geeksforgeeks.org/computer-networks/difference-between-http-and-https-2/) |
| Invention | Originated in the late 1960s and early 1970s as [ARPANET](https://www.geeksforgeeks.org/computer-networks/arpanet-full-form/) | 1989 by Tim Berners-Lee |
| Examples | Email services, VoIP, Online gaming, Cloud storage and more. | Websites like Google, Wikipidea, Youtube, Amazon, Facebook |
| Usage | Used for all forms of digital communication and data exchange. | Used mainly for accessing information and multimedia using web browsers. |
## Conclusion
The [Internet](https://www.geeksforgeeks.org/computer-science-fundamentals/introduction-to-internet/) is known as “interconnection of computer networks”. The Internet is a massive network of networks. It connects millions of computers together globally, forming a network in which any computer can communicate with any other computer as long as they are both connected to the Internet. Information that travels over the Internet does so via a variety of languages known as [protocols](https://www.geeksforgeeks.org/computer-science-fundamentals/types-of-internet-protocols/). The [World Wide Web](https://www.geeksforgeeks.org/computer-networks/world-wide-web-www/), or “Web” for short, or simply Web, is a massive collection of digital pages to access information over the Internet.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/whats-difference-internet-web/)

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
