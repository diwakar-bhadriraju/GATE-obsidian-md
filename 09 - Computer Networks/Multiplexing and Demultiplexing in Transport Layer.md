---
title: "Multiplexing and Demultiplexing in Transport Layer"
subject: "Computer Networks"
topic: "Transport Layer"
source: "https://www.geeksforgeeks.org/computer-networks/multiplexing-and-demultiplexing-in-transport-layer/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Transport Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/transport-layer
---


> [!abstract] Multiplexing and Demultiplexing in Transport Layer
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Transport Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/multiplexing-and-demultiplexing-in-transport-layer/)

---

# Multiplexing and Demultiplexing in Transport Layer

**Prerequisite -**[Layers of OSI Model](https://www.geeksforgeeks.org/computer-networks/open-systems-interconnection-model-osi/) 
Multiplexing and Demultiplexing services are provided in almost every protocol architecture ever designed. UDP and TCP perform the demultiplexing and multiplexing jobs by including two special fields in the segment headers: the source port number field and the destination port number field. 
**Multiplexing -** 
Gathering data from multiple application processes of the sender, enveloping that data with a header, and sending them as a whole to the intended receiver is called multiplexing. 
**Demultiplexing -** 
Delivering received segments at the receiver side to the correct app layer processes is called demultiplexing. 
![](assets/CN_Multiplexing-1-947369b2d9.jpg)
**Figure -** Abstract view of multiplexing and demultiplexing 
Multiplexing and demultiplexing are the services facilitated by the transport layer of the OSI model. 
![](assets/CN_Multiplexing-2-83502f7efa.jpg)
**Figure -** Transport layer- junction for multiplexing and demultiplexing 
There are two types of multiplexing and Demultiplexing : 
1. Connectionless Multiplexing and Demultiplexing
2. Connection-Oriented Multiplexing and Demultiplexing
**How Multiplexing and Demultiplexing is done -** 
For sending data from an application on the sender side to an application at the destination side, the sender must know the IP address of the destination and port number of the application (at the destination side) to which he wants to transfer the data. Block diagram is shown below : 
![](assets/CN_Multiplexing-3-21f483b128.jpg)
**Figure -** Transfer of packet between applications of sender and receiver 
Let us consider two messaging apps that are widely used nowadays viz. Hike and WhatsApp. Suppose A is the sender and B is the receiver. Both sender and receiver have these applications installed in their system (say smartphone). Suppose A wants to send messages to B in WhatsApp and hike both. In order to do so, A must mention the IP address of B and destination port number of the WhatsApp while sending the message through the WhatsApp application. Similarly, for the latter case, A must mention the IP address of B and the destination port number of the hike while sending the message. 
Now the messages from both the apps will be wrapped up along with appropriate headers(viz. source IP address, destination IP address, source port no, destination port number) and sent as a single message to the receiver. This process is called multiplexing. At the destination, the received message is unwrapped and constituent messages (viz messages from a hike and WhatsApp application) are sent to the appropriate application by looking to the destination the port number. This process is called demultiplexing. Similarly, B can also transfer the messages to A. 
![](assets/CN_Multiplexing-4-aa5022f60b.jpg)
**Figure -** Message transfer using WhatsApp and hike messaging application 
**References -** 
[Multiplexing/Demultiplexing](http://www.cs.ccsu.edu/~stan/classes/cs490/slides/networks4-ch3-1.pdf) 
[dcs.bbk.ac.uk](https://titan.dcs.bbk.ac.uk/~ptw/teaching/IWT/transport-layer/notes.html)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/multiplexing-and-demultiplexing-in-transport-layer/)

## GATE CS

- Subject: Computer Networks
- Topic: Transport Layer

> [!note] Related notes
>
> - [[Congestion Control]]
> - [[Differences between TCP and UDP]]
> - [[Error Control in TCP]]
> - [[Leaky Bucket Algorithm]]
> - [[TCP 3-Way Handshake Process]]
> - [[TCP Congestion Control]]
> - [[TCP Connection Establishment]]
> - [[TCP Connection Termination]]
> - [[TCP flags]]
> - [[TCP Server-Client implementation in C]]
