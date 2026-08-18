---
title: "DHCP Relay Agent in Computer Network"
subject: "Computer Networks"
topic: "Application Layer"
source: "https://www.geeksforgeeks.org/computer-networks/dhcp-relay-agent-in-computer-network/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Application Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/application-layer
---


> [!abstract] DHCP Relay Agent in Computer Network
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Application Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/dhcp-relay-agent-in-computer-network/)

---

# DHCP Relay Agent in Computer Network

Prerequisite - [Dynamic Host Configuration Protocol (DHCP)](https://www.geeksforgeeks.org/computer-networks/dynamic-host-configuration-protocol-dhcp/), [How DHCP server dynamically assigns IP address to a host?](https://www.geeksforgeeks.org/operating-systems/how-dhcp-server-dynamically-assigns-ip-address-to-a-host/) 
To assign an IP address to the host dynamically, the DHCP client exchanges DHCP messages with the DHCP server in the DORA process. 
In the DORA process, the discover and request message is broadcast, the offer and the acknowledgement message is broadcast or unicast depending upon the value of the broadcast flag i.e. If the value of the broadcast flag is 1, then the offer and acknowledgement message is broadcast and if 0, the messages are unicast. But this is valid only when the DHCP server is present in the same network because the router doesn't forward any broadcast packet. What if the server is present in a different network? Here comes the role of DHCP relay agent. 
**DHCP Relay Agent -** 
The DHCP relay agent is any TCP/IP host which is used to forward requests and replies between the DHCP server and client when the server is present on a different network. Relay agents receive DHCP messages and then generate a new DHCP message to send out on another INTERFACE. Also, the DHCP relay agent adds a giaddr (gateway address of the packet) field and also the Relay agent information option 82 if enabled. The options field is removed when the server reply is forwarded to the host.
DHCP relay agents are commonly used in large enterprise networks where the DHCP server is located on a different network segment than the client devices.The DHCP relay agent listens for DHCP broadcast messages from the client devices and then forwards those messages to the DHCP server, encapsulating them in a unicast packet.The DHCP relay agent may be configured with one or more IP addresses of DHCP servers that it can forward requests to.The giaddr field in the DHCP relay agent message is used to indicate the IP address of the relay agent interface on which the message was received.The Relay Agent Information option (option 82) may be used to add additional information to the DHCP request message, such as the interface or port number on which the request was received, or the VLAN ID of the requesting device.DHCP relay agents may be implemented in dedicated hardware devices, or they may be implemented in software on routers or other network devices.Some DHCP relay agents may include additional features such as DHCP packet filtering, rate limiting, or access control based on the source or destination IP address.If a DHCP relay agent is not properly configured, it can cause delays or failures in the DHCP process, leading to network connectivity issues for client devices.
**Note -** The discover and request messages are unicast by the DHCP relay agent. 
**Example -**
![](assets/dhcp1-0f44be1fe3.jpg)
Here is a topology in which there is a DHCP client having no IP address. There is a DHCP server having IP address 192.168.2.2 and there is a router in the middle which we want as the DHCP relay agent has an IP address 192.168.1.1 on interface fa0/0 and 192.168.2.1 on interface fa0/1.
![](assets/dhcp2-654cfae9e1.jpg)
Now, first, the discover message is broadcast by the DHCP client to find out the DHCP server which is received by the switch as it is in the same broadcast domain. The switch broadcast the DHCP packet in the network, received by both PC and Router(DHCP Relay Agent). The PC and the router receive the broadcast packet but the PC drops the packet as the DHCP server is present in the different network therefore the packet has to be delivered to the default gateway only.
![](assets/dhcp3-0885059f72.jpg)
The router, with DHCP relay agent feature, enabled, replaces the source address with its own address and the destination IP address with DHCP server IP address i.e. the DHCP relay agent unicast the packet to DHCP server. DHCP relay agent adds giaddr field into the packet and forwards it to the DHCP server. giaddr field is added to the packet so that the server should know from which pool, it has to assign the IP address. 
In our case, the giaddr field will contain 192.168.1.1 (IP address of the interface on which the router [DHCP relay agent] receives the discover message).
![](assets/dhcp4-0cd31379da.jpg)
The server replies with a unicast DHCP offer to the router offering the unleashed IP address.
![](assets/dhcp5-c16fe82883.jpg)
In return, the router broadcast the DHCP Offer message to the network which has sent the DHCP request. The broadcast message is received by a switch as shown in the above figure.
![](assets/dhcp6-9851b2c08e.jpg)
The switch broadcasts the DHCP offer message to the hosts. Therefore, the message is received by the DHCP client
![](assets/dhcp7-9cb24d4e09.jpg)
Now, the DHCP client broadcast the DHCP request message, showing the acceptance of the IP address, for the server which is received by the switch. The switch broadcast the DHCP request message to the other host and the router(DHCP Relay Agent)as shown in the above figure.
![](assets/dhcp8-b7036d484b.jpg)
The router replaces the source IP address with its own IP address and destination IP remains the same i.e. It is unicast by the DHCP relay agent
![](assets/dhcp9-f57407df21.jpg)
The server replies with a unicast DHCP Acknowledgement message to the router (DHCP relay agent) as shown in the above figure.
![](assets/dhcp10-eeeef6bc08.jpg)
The router in turn broadcast the DHCP Acknowledgement message to the network it receives the DHCP request for an IP address. The broadcast message is received by a switch as shown in the above figure.
![](assets/dhcp11-467f423d14.jpg)
The broadcast DHCP Acknowledgement message is received by the DHCP client as the switch broadcast the message through all its ports. 
**Configuration -** 
This is the basic configuration of the client, router, dhcp\_server. The router has been assigning IP addresses 192.168.1.1 on fa0/0 and 192.168.2.1 on fa0/1.
```
ROUTER(config)#int f0/0
ROUTER(config-if)#ip address 192.168.1.1 255.255.255.0
ROUTER(config-if)#no shutdown
ROUTER(config)#int f0/1
ROUTER(config-if)#ip address 192.168.2.1 255.255.255.0
ROUTER(config-if)#no shutdown
```
The DHCP\_SERVER is assigned IP Address 192.168.2.2 on the interface fa0/0 and the DHCP pool is defined with name POOL1 and network of 192.168.1.0 with subnet mask 255.255.255.0 is assigned to the pool POOL1.
```
DHCP_SERVER(config)#int f0/0
DHCP_SERVER(config-if)#ip address 192.168.2.2 255.255.255.0
DHCP_SERVER(config-if)#no shutdown
DHCP_SERVER(config)#ip dhcp pool POOL1
DHCP_SERVER(dhcp-config)#network 192.168.1.0 255.255.255.0
DHCP_SERVER(dhcp-config)#default-router 192.168.1.1
DHCP_SERVER(dhcp-config)#exit
```
Now, the IP helper-address command is used for configuring the router as a DHCP relay agent, giving 192.168.2.2 the address of DHCP\_server.
```
ROUTER(config)#int f0/0
ROUTER(config-if)#ip helper-address 192.168.2.2
ROUTER(config-if)#exit
```
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/dhcp-relay-agent-in-computer-network/)

## GATE CS

- Subject: Computer Networks
- Topic: Application Layer

> [!note] Related notes
>
> - [[Address Resolution in DNS]]
> - [[Basics of Wi-Fi]]
> - [[DNS (Domain Name Server) NetWorking]]
> - [[DNS Spoofing or DNS Cache poisoning]]
> - [[Dynamic Host Configuration Protocol]]
> - [[File Transfer Protocol]]
> - [[How DHCP server dynamically assigns IP address to a host]]
> - [[HTTP Non-Persistent & Persistent Connection]]
> - [[LiFi vs WiFi]]
> - [[Multipurpose Internet mail extension]]
