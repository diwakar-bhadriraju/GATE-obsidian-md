---
title: "BUS Arbitration in Computer Organization"
subject: "Computer Organization and Architecture"
topic: "I/O interface (Interrupt and DMA mode)"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/bus-arbitration-in-computer-organization/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/I/O interface (Interrupt and DMA mode)"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/i/o-interface-interrupt-and-dma-mode
---


> [!abstract] BUS Arbitration in Computer Organization
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `I/O interface (Interrupt and DMA mode)`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/bus-arbitration-in-computer-organization/)

---

# BUS Arbitration in Computer Organization

In a computer system, multiple devices like CPU, memory, and I/O share a common bus. When more than one device tries to access the bus at the same time, conflicts occur. Bus arbitration is the process of resolving these conflicts and ensuring that only one device accesses the bus at a time.
- The device that gets control of the bus is called the bus master. A special unit called the bus arbiter selects which device will access the bus based on priority.
- After completing its operation, the current master releases the bus so another device can use it.
- Bus arbitration can be implemented using methods like centralized, decentralized, and distributed arbitration, depending on how control and priority are managed.
There are two approaches to bus arbitration:  
- **Centralized bus arbitration:** A single bus arbiter performs the required arbitration.
- **Distributed bus arbitration:** All devices participating in the selection of the next bus master.
### **Methods of Centralized BUS Arbitration**
**1. Daisy Chaining method:** It is a simple and cheaper method where all the bus masters use the same line for making bus requests. The bus grant signal serially propagates through each master until it encounters the first one that is requesting access to the bus. This master blocks the propagation of the bus grant signal, therefore any other requesting module will not receive the grant signal and hence cannot access the bus.
During any bus cycle, the bus master may be any device - the processor or any DMA controller unit, connected to the bus. 
![](assets/bus1-723bf64879.png)
**Advantages**
- Simplicity and Scalability.
- The user can add more devices anywhere along the chain, up to a certain maximum value.
**Disadvantages**
- The value of priority assigned to a device depends on the position of the master bus.
- Propagation delay arises in this method.
- If one device fails then the entire system will stop working.
**2. Polling or Rotating Priority method:** In this, the controller is used to generate the address for the master(unique priority), the number of address lines required depends on the number of masters connected in the system. The controller generates a sequence of master addresses. When the requesting master recognizes its address, it activates the busy line and begins to use the bus.
![](assets/bus2-7f666cce7f.png)
**Advantages**
- This method does not favor any particular device and processor.
- The method is also quite simple.
- If one device fails then the entire system will not stop working.
**Disadvantages**
- Adding bus masters is difficult as increases the number of address lines of the circuit.
**3. Fixed priority or Independent Request method**
In this, each master has a separate pair of bus request and bus grant lines and each pair has a priority assigned to it.  
The built-in priority decoder within the controller selects the highest priority request and asserts the corresponding bus grant signal.
![](assets/bus3-36f0da1091.png)**Advantages**
- This method generates a fast response.
**Disadvantages**
- Hardware cost is high as a large no. of control lines is required.
### Applications
- **Shared Memory Systems:** In shared memory systems, multiple devices need to access the memory to read or write data. Bus arbitration allows multiple devices to access the memory without interfering with each other.
- **Multi-Processor Systems:** In multi-processor systems, multiple processors need to communicate with each other to share data and coordinate processing. Bus arbitration allows multiple processors to share access to the bus to communicate with each other and with shared memory.
- **Input/Output Devices:** Input/Output devices such as keyboards, mice, and printers need to communicate with the processor to exchange data. Bus arbitration allows multiple input/output devices to share access to the bus to communicate with the processor and memory.
- **Real-time Systems:** In real-time systems, data needs to be transferred between devices and memory within a specific time frame to ensure timely processing. Bus arbitration can help to ensure that data transfer occurs within a specific time frame by managing access to the bus.
- **Embedded Systems:** In embedded systems, multiple devices such as sensors, actuators, and controllers need to communicate with the processor to control and monitor the system. Bus arbitration allows multiple devices to share access to the bus to communicate with the processor and memory.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/bus-arbitration-in-computer-organization/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: I/O interface (Interrupt and DMA mode)

> [!note] Related notes
>
> - [[AI, ML & Data Science]]
> - [[Aptitude]]
> - [[Asynchronous input output synchronization]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
> - [[Clusters In Computer Organisation]]
> - [[Computer Ports]]
> - [[Connect]]
> - [[Corporate Solution]]
> - [[CS Core Subjects]]
> - [[DevOps]]
