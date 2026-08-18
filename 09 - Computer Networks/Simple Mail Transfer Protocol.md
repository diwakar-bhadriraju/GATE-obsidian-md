---
title: "Simple Mail Transfer Protocol (SMTP)"
subject: "Computer Networks"
topic: "Application Layer"
source: "https://www.geeksforgeeks.org/computer-networks/simple-mail-transfer-protocol-smtp/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Application Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/application-layer
---


> [!abstract] Simple Mail Transfer Protocol (SMTP)
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Application Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/simple-mail-transfer-protocol-smtp/)

---

# Simple Mail Transfer Protocol (SMTP)

SMTP is an application-layer protocol used to send and transfer email between servers. It relies on a TCP connection to port 25 to reliably deliver messages from a client to an email server.
- Uses TCP for reliable message transmission
- Servers listen on port 25 for incoming email
- Client establishes a TCP connection before sending mail
- Core protocol for email delivery between mail servers
![Simple Mail Transfer Protocol](assets/SMTP-Gif-4606ad4bac.gif)
SMTP
## **Types of SMTP Protocol**
The SMTP model supports two types of email delivery methods: **end-to-end** and **store-and-forward**.
- **End-to-end** delivery is used between organizations. In this method, the email is sent directly from the sender's SMTP client to the recipient's SMTP server without passing through intermediate servers.
- **Store-and-forward** is used within organizations that have TCP/IP and SMTP-based networks. In this method, the email may pass through several intermediate servers (Message Transfer Agents, or MTAs) before reaching the recipient.
![smtp-2](assets/smtp-2-581b3128c6.webp)
SMTP
- **SMTP.com**: Platform providing transaction email, relay, and delivery services at affordable prices.
- **Industry Trust**: Regarded as the most trusted sender by ISPs with decades of experience.
- **Customer Base**: Trusted by over 100,000 customers over the years.
- **User-Friendly**: Extremely intuitive and easy to set up for seamless integration.
- **Business Integration**: Seamlessly integrates into existing business systems.
- **Easy Migration**: Effortless migration from other email providers.
## Features
**The following are the key features of SMTP.com:**
- **Dedicated IP:** Provides a unique sending IP to improve deliverability and maintain a strong sender reputation.
- **Email API:** Enables fast and seamless integration with detailed documentation, allowing businesses to connect in just minutes.
- **24/7 Customer Support:** Offers round-the-clock human support across all plans, including website assistance and live chat for quick, reliable solutions.
- **High-Volume Sending Solutions:** Ideal for enterprises sending over 250 million emails monthly, with customized quotes and tailored infrastructure.
- **Reputation Defender:** An add-on service that automatically scans, cleans, and monitors email lists to maintain healthy sender reputation—no integration required.
## **Model of SMTP System**
![122w3](assets/122w3-1d40d5cec0.webp)
SMTP Model
- **User at a Terminal (Sender):** The person composing the email using a mail application (e.g., Outlook, Thunderbird, webmail).
- **User Agent (Sender):** The email client software that allows the sender to create, edit, and send emails.
   It hands the outgoing email to the system’s mail queue.
- **Queue of Mail to Be Sent:** A temporary storage area where outgoing emails wait before being processed by the mail server (Message Transfer Agent).
- **Message Transfer Agent (Client Side):** The software responsible for sending emails across the network. It retrieves messages from the outgoing queue and communicates with the receiving server.
- **TCP Connection (Port 25):** The client’s MTA opens a TCP connection to the server’s MTA on port 25. SMTP commands, responses, and mail data are exchanged over this connection.
- **Message Transfer Agent (Server Side):** The receiving email server accepts the incoming SMTP connection. It processes the incoming email and stores it for the user.
- **User Mailboxes:** The server stores the received messages in individual user mailboxes.
- **User Agent (Receiver):** The email application used by the recipient to access the mailbox. It retrieves emails using protocols like POP3 or IMAP.
- **User at a Terminal (Receiver):** The person reading the received email on their device.
## Components of SMTP
- **Mail User Agent (MUA):** It is a computer application that helps you in sending and retrieving mail. It is responsible for creating email messages for transfer to the [mail transfer agent(MTA).](https://www.geeksforgeeks.org/linux-unix/7-best-mail-transfer-agents-mtas-for-linux/)
- **Mail Submission Agent (MSA):** It is a computer program that receives mail from a Mail User Agent(MUA) and interacts with the Mail Transfer Agent(MTA) for the transfer of the mail.
- **Mail Transfer Agent (MTA):** It is software that has the work to transfer mail from one system to another with the help of SMTP.
- **Mail Delivery Agent (MDA):** A mail Delivery agent or Local Delivery Agent is basically a system that helps in the delivery of mail to the local system.
## How does SMTP Work?
![smtp](assets/smtp-869cbff2ce.webp)
SMTP
### 1. Sending Email:
- When a user wants to send an email, they use a User Agent (UA), like Outlook or Gmail.
- The email is handed over to the MTA, which is responsible for transferring the email to the recipient’s mail server.
### 2. SMTP Client and Server:
- **Sender-SMTP (Client)**: The email sender’s MTA initiates the connection to the recipient’s MTA (Receiver-SMTP).
- **Receiver-SMTP (Server)**: The receiving MTA listens for incoming connections and receives the email from the sender-SMTP.
- This communication happens over [TCP](https://www.geeksforgeeks.org/computer-networks/what-is-transmission-control-protocol-tcp/) port 25.
### 3. Relays and Gateways:
- **Relays**: In some cases, the email may pass through several intermediate MTAs before reaching the destination server. These MTAs act as **relays**.
- **Gateways**: If the sending and receiving systems use different email protocols (e.g., SMTP and non-SMTP), an **email gateway** can convert the email to the appropriate format for delivery.
### 4. Email Delivery:
- The sender’s MTA sends the email to the receiver’s MTA, either directly or through relays.
- The MTA uses the SMTP protocol to transfer the message. Once it’s delivered to the destination MTA, the email is placed in the recipient’s mailbox.
- The recipient’s User Agent (UA) can then download the email.
## SMTP Envelope
### Purpose
- The SMTP envelope contains information that guides email delivery between servers.
- It is distinct from the email headers and body and is not visible to the email recipient.
### Contents of the SMTP Envelope
- **Sender Address**: Specifies where the email originates.
- **Recipient Addresses**: Indicates where the email should be delivered.
- **Routing Information**: Helps servers determine the path for email delivery.
### Comparison to Regular Mail
- Think of the SMTP envelope as the **address on a physical envelope** for regular mail.
- Just like an envelope guides postal delivery, the SMTP envelope directs email servers on where to send the email.
## SMTP Commands
| S.No. | Keywor | Command form | Description | Usage |
| --- | --- | --- | --- | --- |
| 1. | HELO | HELO<SP><domain><CRLF> | It provides the identification of the sender i.e. the host name. | Mandatory |
| 2. | MAIL | MAIL<SP>FROM : <reverse-path><CRLF> | It specifies the originator of the mail. | Mandatory |
| 3. | RCPT | RCPT<SP>TO : <forward-path><CRLF> | It specifies the recipient of mail. | Mandatory |
| 4. | DATA | DATA<CRLF> | It specifies the beginning of the mail. | Mandatory |
| 5. | QUIT | QUIT<CRLF> | It closes the TCP connection. | Mandatory |
| 6. | RSET | RSET<CRLF> | It aborts the current mail transaction but the TCP connection remains open. | Highly recommended |
| 7. | VRFY | VRFY<SP><string><CRLF> | It is use to confirm or verify the user name. | Highly recommended |
| 8. | NOOP | NOOP<CRLF> | No operation | Highly recommended |
| 9. | TURN | TURN<CRLF> | It reverses the role of sender and receiver. | Seldom used |
| 10. | EXPN | EXPN<SP><string><CRLF> | It specifies the mailing list to be expanded. | Seldom used |
| 11. | HELP | HELP<SP><string><CRLF> | It send some specific documentation to the system. | Seldom used |
| 12. | SEND | SEND<SP>FROM : <reverse-path><CRLF> | It send mail to the terminal. | Seldom used |
| 13. | SOML | SOML<SP>FROM : <reverse-path><CRLF> | It send mail to the terminal if possible; otherwise to mailbox. | Seldom used |
| 14. | SAML | SAML<SP>FROM : <reverse-path><CRLF> | It send mail to the terminal and mailbox. | Seldom used |
## SMTP Ports
These ports play a important role in defining how email clients and servers communicate securely and efficiently across the internet using the SMTP protocol.
![mail_yourdomain_com](assets/mail_yourdomain_com-4db013f639.webp)
- **Port 587**: This is the most commonly used port for **secure SMTP submission** using **TLS (Transport Layer Security)**. It is recommended for client-to-server communication, as it ensures the security of the email transmission.
- **Port 465**: Previously used for **secure SMTP** (SMTPS), this port is **no longer considered an official standard** and is generally not recommended anymore. Many email providers have moved away from port 465 in favor of port 587.
- **Port 25**: This port is traditionally used for **SMTP relay** between mail servers, not for email submission from clients. It is often blocked by ISPs for outgoing mail due to its frequent use for spam and malicious activities.
- **Port 2525**: Although **not an official SMTP port**, it is sometimes used as an alternative for SMTP submission, especially in cases where port 25 is blocked or restricted. Many email providers support this port as an alternative for secure communication.
## Difference Between SMTP and Extended SMTP
| **SMTP** | **Extended SMTP** |
| --- | --- |
| Users were not verified in SMTP as a result of massive-scale scam emails being sent. | In [Extended SMTP,](https://www.geeksforgeeks.org/computer-networks/what-is-esmtp-extended-simple-mail-transfer-protocol/) authentication of the sender is done. |
| We cannot attach a Multimedia file in SMTP directly without the help of MMIE. | We can directly attach Multimedia FIle in ESMTP. |
| We cannot reduce the size of the email in SMTP. | We can reduce the size of the email in Extended SMTP. |
| SMTP clients open transmission with the command HELO. | The main identification feature for ESMTP clients is to open a transmission with the command EHLO (Extended HELLO). |
## **Advantages of SMTP**
- If necessary, the users can have a dedicated server.
- It allows for bulk mailing.
- Low cost and wide coverage area.
- Offer choices for email tracking.
- Reliable and prompt email delivery.
## **Disadvantages of SMTP**
- SMTP's common port can be blocked by several [firewalls](https://www.geeksforgeeks.org/computer-networks/introduction-of-firewall-in-computer-network/).
- SMTP security is a bigger problem.
- Its simplicity restricts how useful it can be.
- Just 7-bit ASCII characters can be used.
- If a message is longer than a certain length, SMTP servers may reject the entire message.
- Delivering your message will typically involve additional back-and-forth processing between servers, which will delay sending and raise the likelihood that it won't be sent.
## SMTP vs POP vs IMAP
| SMTP | POP | IMAP |
| --- | --- | --- |
| Stands for Simple mail transfer protocol | Stands for [Post Office Protocol.](https://www.geeksforgeeks.org/computer-networks/pop-full-form/) | Stands for [Internet Message Access Protocol.](https://www.geeksforgeeks.org/computer-networks/internet-message-access-protocol-imap/) |
| Used for sending mail. | Used for retrieving mail. | Used for retrieving mail. |
| it is push [protocol](https://www.geeksforgeeks.org/computer-networks/network-protocols/). | it is pull protocol. | it is pull protocol. |
| It work between sender’s mail server to receiver’s mail server and sender and sender’s mail server. | It work between receiver and receiver’s mail server. | It works between receiver and receiver’s mail server. |
| It does not store mail on server it just send the mail. | It download all the mail when it connected to internet. | It store all mail on server and download when it get request to download. |
| Works on TCP port number 25. | Works on TCP port number 110. | Works on TCP port number 143. |
| Connection oriented protocol. | Connection oriented protocol. | Connection oriented protocol. |
| It has persistence TCP connection. | It has persistence TCP connection. | It has persistence TCP connection. |
| [Stateless](https://www.geeksforgeeks.org/computer-networks/difference-between-stateless-and-stateful-protocol/) protocol. | Stateful protocol. | Stateful protocol. |
| It is in band protocol. | It is in band protocol. | It is in band protocol. |
| Not used at receiver side. | Used at receiver side. | Used at receiver side. |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/simple-mail-transfer-protocol-smtp/)

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
