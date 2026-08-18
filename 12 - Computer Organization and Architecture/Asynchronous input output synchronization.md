---
title: "Asynchronous I/O Synchronization"
subject: "Computer Organization and Architecture"
topic: "I/O interface (Interrupt and DMA mode)"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-asynchronous-input-output-synchronization/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/I/O interface (Interrupt and DMA mode)"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/i/o-interface-interrupt-and-dma-mode
---


> [!abstract] Asynchronous I/O Synchronization
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `I/O interface (Interrupt and DMA mode)`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-asynchronous-input-output-synchronization/)

---

# Asynchronous I/O Synchronization

Asynchronous I/O synchronization is a technique used to transfer data between the CPU and external devices without using a common clock signal. Data transfer occurs at irregular and unpredictable intervals, depending on the device’s speed.
- Unlike synchronous I/O, which uses a clock signal for fixed-rate transfer, asynchronous I/O is suitable for devices with variable speeds. It avoids unnecessary waiting and improves efficiency when devices are slower or operate independently.
- In asynchronous I/O, CPU does not wait continuously; it performs other tasks and responds when interrupt occurs. The device sends a signal, and the CPU initiates data transfer accordingly.
### Problem in Asynchronous I/O
There is no fixed timing, so it is uncertain whether the data on the bus is valid or ready.
### Solution Mechanisms
- Strobe Control – One device signals when data is ready
- Handshaking – Both sender and receiver exchange signals to ensure correct data transfer
Strobe has no confirmation mechanism, whereas handshaking ensures reliable data transfer using acknowledgment signals.
### **1. Strobe Mechanism:**
**Source initiated Strobe:** When source initiates the process of data transfer. Strobe is just a signal.
![](assets/as-8-8fd03651a2.png)
- First, source puts data on the data bus and ON the strobe signal.
- Destination on seeing the ON signal of strobe, read data from the data bus.
- After reading data from the data bus by destination, strobe gets OFF. Signals can be seen as: ![](assets/22-4-19e2397547.jpg)
It shows that first data is put on the data bus and then strobe signal gets active.
**Destination initiated signal:** When destination initiates the process of data transfer. ![](assets/as-9-d86fcaf4cf.png)
- First, the destination ON the strobe signal to ensure the source to put the fresh data on the data bus.
- Source on seeing the ON signal puts fresh data on the data bus.
- Destination reads the data from the data bus and strobe gets OFF signal. Signals can be seen as: ![](assets/ao-25d8ff28e7.png)
It shows that first strobe signal gets active then data is put on the data bus.
**Problems faced in Strobe based asynchronous I/O**
- In Source initiated Strobe, it is assumed that destination has read the data from the data bus but there is no surety.
- In Destination initiated Strobe, it is assumed that source has put the data on the data bus but there is no surety.
- This problem is overcome by Handshaking.
### **2. Handshaking Mechanism:**
**Source initiated Handshaking -** When source initiates the data transfer process. It consists of signals:
- **DATA VALID:** if ON tells data on the data bus is valid otherwise invalid.
- **DATA ACCEPTED:** if ON tells data is accepted otherwise not accepted. ![](assets/ap-2-303cdc2af4.png)
- Source places data on the data bus and enable Data valid signal.
- Destination accepts data from the data bus and enable Data accepted signal.
- After this, disable Data valid signal means data on data bus is invalid now.
- Disable Data accepted signal and the process ends. Now there is surety that destination has read the data from the data bus through data accepted signal. Signals can be seen as: ![](assets/ai-d60250a0c8.png)
It shows that first data is put on the data bus then data valid signal gets active and then data accepted signal gets active. After accepting the data, first data valid signal gets off then data accepted signal gets off.
**Destination initiated Handshaking:** When destination initiates the process of data transfer.
- **REQUEST FOR DATA:** if ON requests for putting data on the data bus.
- **DATA VALID:** if ON tells data is valid on the data bus otherwise invalid data. ![](assets/ap-1-ec39a093ab.png)
- When destination is ready to receive data, Request for Data signal gets activated.
- Source in response puts data on the data bus and enabled Data valid signal.
- Destination then accepts data from the data bus and after accepting data, disabled Request for Data signal.
- At last, Data valid signal gets disabled means data on the data bus is no more valid data. Now there is surety that source has put the data on the data bus through data valid signal. Signals can be seen as: ![](assets/au-e4a667fc64.png)
It shows that first Request for Data signal gets active then data is put on data bus then Data valid signal gets active. After reading data, first Request for Data signal gets OFF then Data valid signal gets OFF.
### **Advantages**
- **Flexibility:** Allows for flexible data transfer rates and can adapt to varying transfer speeds without the need for synchronization. This is particularly useful when dealing with slow or intermittent devices.
- **Resource efficiency:** Because data transfer is not synchronized to a clock signal, asynchronous I/O synchronization can be more resource-efficient than synchronous I/O synchronization. It can reduce the overhead of synchronization and improve the utilization of system resources.
- **Reduced latency:** Help reduce latency, or the delay between the initiation of a data transfer and its completion. This can improve the responsiveness and overall performance of the system.
- **Better error handling:** Provide better error handling, as it allows for the detection and handling of errors during data transfer. This can help ensure that data is transferred accurately and reliably.
- **Compatibility:** Compatible with a wide range of devices and systems, making it a flexible and widely used technique for managing data transfer.
**Disadvantages**
- **Complexity:** Can be more complex to implement than synchronous I/O synchronization, as it requires interrupt-driven I/O and other techniques to manage data transfer.
- **Overhead:** Result in higher overhead than synchronous I/O synchronization, as the CPU must constantly monitor for interrupt signals and initiate data transfer when necessary.
- **Latency:** Help reduce latency in some cases, it can also introduce additional latency when waiting for interrupt signals from devices.
- **Synchronization issues:** Can introduce synchronization issues, particularly when dealing with multiple devices or large data transfers. It can be difficult to ensure that data is transferred in the correct order and that all devices are properly synchronized.
- **Compatibility issues:** May not be compatible with all devices and systems, particularly those that require fixed data transfer rates or specific synchronization protocols.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-asynchronous-input-output-synchronization/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: I/O interface (Interrupt and DMA mode)

> [!note] Related notes
>
> - [[AI, ML & Data Science]]
> - [[Aptitude]]
> - [[BUS Arbitration]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
> - [[Clusters In Computer Organisation]]
> - [[Computer Ports]]
> - [[Connect]]
> - [[Corporate Solution]]
> - [[CS Core Subjects]]
> - [[DevOps]]
