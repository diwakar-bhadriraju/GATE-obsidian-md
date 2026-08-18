---
title: "Line Configuration in Computer Networks"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/line-configuration-computer-networks/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Line Configuration in Computer Networks
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/line-configuration-computer-networks/)

---

# Line Configuration in Computer Networks

A network is two or more devices connected through a link. A link is a communication pathway that transfers data from one device to another. Devices can be a computer, printer, or any other device that is capable to send and receive data. For visualization purposes, imagine any link as a line drawn between two points.
For communication to occur, two devices must be connected in some way to the same link at the same time. There are two possible types of connections:
1. **Point-to-Point Connection**
2. **Multipoint Connection**
**Point-to-Point Connection:**
1. A point-to-point connection provides a dedicated link between two devices.
2. The entire capacity of the link is reserved for transmission between those two devices.
3. Most point-to-point connections use an actual length of wire or cable to connect the two ends, but other options such as microwave or satellite links are also possible.
4. Point to point network topology is considered to be one of the easiest and most conventional networks 
   topologies.
5. It is also the simplest to establish and understand.
Example: Point-to-Point connection between the remote control and Television for changing the channels.
![](assets/point-to-point-connection-963265d025.jpg)
### Here are some features of different line configurations in computer networks:
#### Point-to-Point:
- Uses a dedicated link to connect two devices
- Simple and easy to set up
- Limited to two devices only
- Does not require a network interface card (NIC) or a hub/switch
- Can become complex and difficult to manage as the network grows
#### Multipoint:
- Uses a single link to connect three or more devices
- More complex than point-to-point configuration
- Can be more efficient and cost-effective for larger networks
- Devices share the same link, which can lead to collisions and lower performance
- Commonly used in LANs and MANs
#### Star:
- All devices in the network are connected to a central hub or switch
- Easy to manage and troubleshoot
- Provides good performance and reliability
- A single point of failure (the hub or switch) can affect the entire network
- Requires additional hardware and cabling
#### Mesh:
- Every device is connected to every other device in the network
- Provides the highest level of reliability and redundancy
- Can handle high traffic and heavy loads
- Very expensive and difficult to manage
- Commonly used in mission-critical networks and large WANs
Choosing the right line configuration depends on the specific needs of the network, including factors such as the size of the network, the type of data being transmitted, the level of reliability required, and the available resources. Different line configurations can offer various advantages and disadvantages, and the optimal configuration will depend on the specific use case.
**Advantages of Point-to-Point Connection:**
1. **High Bandwidth:** A point-to-point connection provides a dedicated link between two devices, which means that the entire capacity of the link is reserved for the two devices. As a result, point-to-point connections usually offer high bandwidth, which makes them suitable for transferring large amounts of data quickly.
2. **Security:** Point-to-point connections are more secure than multipoint connections because the link is dedicated to only two devices. There is no risk of other devices eavesdropping on the communication or interfering with it in any way.
3. **Reliability:** Because a point-to-point connection provides a dedicated link between two devices, it is usually more reliable than a shared link. If there is a problem with the link, it is easier to troubleshoot and fix because there are only two devices involved.
4. **Reduced Latency:** Point-to-point connections offer lower latency than multipoint connections because there is no contention for the link. This means that data can be transmitted more quickly, which is especially important for real-time applications such as video conferencing or online gaming.
5. **Increased Control:** Point-to-point connections provide greater control over network traffic and bandwidth allocation. This allows for more efficient use of network resources and can help to prevent issues such as network congestion and bottlenecks.
6. **Improved Performance:** Point-to-point connections can improve network performance by reducing packet loss and increasing the speed of data transmission. This can lead to faster data transfers, improved application performance, and a better overall user experience.
7. **Distance:** Point-to-point connections can be established over longer distances than multipoint connections. This is because the dedicated link provides a stronger signal, which can travel further without losing strength.
8. **Cost-Effective:** Point-to-point connections can be cost-effective in certain situations, such as connecting two buildings or offices that are located far apart. In some cases, it may be more cost-effective to establish a point-to-point connection than to invest in a more complex multipoint network.
9. **Easy to Manage:** Point-to-point connections are easy to manage because there are only two devices involved. This reduces the complexity of network administration and makes it easier to troubleshoot problems if they arise.
**Disadvantages of Point-to-Point Connection:**
1. **Cost:** Setting up a point-to-point connection can be more expensive than setting up a shared link. This is because a dedicated link requires its own infrastructure, such as cables, routers, and switches.
2. **Scalability:** Point-to-point connections are not easily scalable, as they require a separate link for each pair of devices. This can be a limitation for large networks that require many devices to be connected.
3. **Maintenance:** Because a point-to-point connection provides a dedicated link between two devices, it requires more maintenance than a shared link. If there is a problem with the link, it is the responsibility of the network administrator to troubleshoot and fix it.
4. **Limited Flexibility:** Point-to-point connections offer limited flexibility compared to multipoint connections because they only allow communication between two devices. This can be a limitation for applications that require collaboration or coordination between multiple devices.
5. **Time-consuming Installation:** Setting up a point-to-point connection can be time-consuming, as it requires a dedicated link to be established between two devices. This can be a disadvantage in situations where time is critical, such as in emergency response situations.
6. **Vulnerability to Failure:** Point-to-point connections are vulnerable to failure if there is a problem with one of the devices or the link itself. This can lead to downtime and disruption of network services, which can be costly for businesses.
7. **Limited Redundancy:** Point-to-point connections offer limited redundancy compared to multipoint connections, as there is no alternative link available if the primary link fails. This can be a disadvantage in situations where high availability is critical, such as in mission-critical applications.
8. **Limited Collaboration:** Point-to-point connections limit collaboration between multiple devices, which can be a disadvantage in situations where multiple devices need to work together to achieve a common goal. This can be a limitation for applications such as video conferencing or online gaming.
9. **Limited Interoperability:** Point-to-point connections may have limited interoperability with other devices or networks. This can be a disadvantage in situations where multiple devices or networks need to communicate with each other.
**Multipoint Connection :**
1. It is also called Multidrop configuration. In this connection, two or more devices share a single link.
2. If more than two devices share the link then the channel is considered a 'shared channel'. With shared capacity, there can be two possibilities in a Multipoint Line configuration:
**Spatial Sharing:** If several devices can share the link simultaneously, it's called Spatially shared line configuration.
**Temporal (Time) Sharing:** If users must take turns using the link, then it's called Temporally shared or Time Shared Line configuration.
![](assets/tempralSharing-a438f1b993.jpg)
**Advantages of Multipoint Connection:**
1. **Cost-Effective:** Multipoint connections are usually less expensive than point-to-point connections because they allow multiple devices to share the same resources, such as cables, routers, and switches.
2. **Scalability:** Multipoint connections are more scalable than point-to-point connections because they allow multiple devices to be connected to the same link. This makes them suitable for large networks that require many devices to be connected.
3. **Flexibility:** Multipoint connections are more flexible than point-to-point connections because they allow multiple devices to communicate with each other over the same link. This makes them suitable for applications that require collaboration or coordination between multiple devices.
4. **Increased Efficiency:** Multipoint connections can improve network efficiency by allowing multiple devices to transmit data simultaneously. This reduces the chances of network congestion and improves overall network performance.
5. **Simplified Management:** Multipoint connections simplify network management by reducing the number of physical connections that need to be managed. This reduces the complexity of network administration and makes it easier to troubleshoot problems.
6. **Enhanced Collaboration:** Multipoint connections enable multiple users to collaborate in real-time, regardless of their location. This allows teams to work together more efficiently and effectively, improving productivity and reducing delays.
7. **Improved Reliability:** Multipoint connections can improve network reliability by providing redundant paths for data transmission. If one path fails, data can be automatically rerouted through another path, ensuring that network connectivity is maintained.
8. **Greater Access:** Multipoint connections can provide greater access to network resources, such as servers, printers, and storage devices. This allows users to share resources and collaborate more effectively, improving productivity and reducing costs.
9. **Improved Security:** Multipoint connections can improve network security by allowing for centralized monitoring and control of network traffic. This makes it easier to detect and prevent security threats, such as unauthorized access or data breaches.
**Disadvantages of Multipoint Connection:**
1. **Limited Bandwidth:** Multipoint connections usually offer limited bandwidth because the link is shared by multiple devices. As a result, the speed of the link may be affected by the number of devices using it.
2. **Security:** Multipoint connections are less secure than point-to-point connections because the link is shared by multiple devices. There is a risk of other devices eavesdropping on the communication or interfering with it in some way.
3. **Reliability:** Multipoint connections are less reliable than point-to-point connections because the link is shared by multiple devices. If there is a problem with the link, it can affect multiple devices, which can be difficult to troubleshoot and fix.
4. **Latency:** Multipoint connections may have higher latency than point-to-point connections due to the increased number of devices accessing the same link. This can lead to delays in data transmission and affect the overall performance of the network.
5. **Complexity:** Multipoint connections can be more complex to set up and configure than point-to-point connections. This is because multiple devices need to be connected and configured to work together on the same link, which can be challenging to manage.
6. **Network Congestion:** Multipoint connections can be prone to network congestion, especially during peak usage periods. When multiple devices are using the same link simultaneously, it can cause a bottleneck, resulting in slower network speeds and performance issues.
7. **Limited Control:** Multipoint connections may provide limited control over network traffic and bandwidth allocation. This can result in some devices consuming more bandwidth than others, leading to issues such as slow network speeds and poor performance.
8. **Interference:** Multipoint connections may be more susceptible to interference from external sources such as electromagnetic interference or radio-frequency interference. This can lead to degraded network performance and connectivity issues.
9. **Limited Distance:** Multipoint connections may be limited in terms of distance due to the shared nature of the link. As the distance increases, the signal strength may weaken, leading to connectivity issues and lower network performance.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/line-configuration-computer-networks/)

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
