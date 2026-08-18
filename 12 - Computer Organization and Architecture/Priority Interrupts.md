---
title: "Priority Interrupts"
subject: "Computer Organization and Architecture"
topic: "I/O interface (Interrupt and DMA mode)"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/priority-interrupts-sw-polling-daisy-chaining/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/I/O interface (Interrupt and DMA mode)"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/i/o-interface-interrupt-and-dma-mode
---


> [!abstract] Priority Interrupts
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `I/O interface (Interrupt and DMA mode)`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/priority-interrupts-sw-polling-daisy-chaining/)

---

# Priority Interrupts

Priority interrupt refers to a mechanism or signal in computing systems that allows a high-priority task or process to temporarily halt a lower-priority task to ensure the timely execution of complex operations. It enables the system to respond immediately to urgent events, such as hardware signals or real-time demands, by pausing the current execution, saving its state, and servicing the higher-priority request first. Once the interrupt is handled, the system resumes the original task.
### SOFTWARE METHOD – POLLING
In this method, all interrupts are serviced by branching to the same service program. This program then checks with each device if it is the one generating the interrupt. The order of checking is determined by the priority that has to be set.
- The device having the highest priority is checked first, and then devices are checked in descending order of priority.
- If the device is checked to be generating the interrupt, another service program is called which works specifically for that particular device.
The structure will look something like this-
```
if (device[0].flag)
    device[0].service();
else if (device[1].flag)
    device[1].service();
.
.
.
.
.
.
else
    //raise error
```
The major disadvantage of this method is that it is quite slow. To overcome this, we can use hardware solution, one of which involves connecting the devices in series. This is called Daisy-chaining method.
### HARDWARE METHOD – DAISY CHAINING
The daisy-chaining method involves connecting all the devices that can request an interrupt in a serial manner. This configuration is governed by the priority of the devices. The device with the highest priority is placed first followed by the second highest priority device and so on. The given figure depicts this arrangement.
![processor_data_bus](assets/processor_data_bus-543f3ac227.webp)
**WORKING:** There is an interrupt request line which is common to all the devices and goes into the CPU.
- When no interrupts are pending, the line is in HIGH state. But if any of the devices raises an interrupt, it places the interrupt request line in the LOW state.
- The CPU acknowledges this interrupt request from the line and then enables the interrupt acknowledge line in response to the request.
- This signal is received at the PI(Priority in) input of device 1.
- If the device has not requested the interrupt, it passes this signal to the next device through its PO(priority out) output. (PI = 1 & PO = 1)
However, if the device had requested the interrupt, (PI =1 & PO = 0)
- The device consumes the acknowledge signal and block its further use by placing 0 at its PO(priority out) output.
- The device then proceeds to place its interrupt vector address(VAD) into the data bus of CPU.
- The device puts its interrupt request signal in HIGH state to indicate its interrupt has been taken care of.
- If a device gets 0 at its PI input, it generates 0 at the PO output to tell other devices that acknowledge signal has been blocked. (PI = 0 & PO = 0)
Hence, the device having PI = 1 and PO = 0 is the highest priority device that is requesting an interrupt. Therefore, by daisy chain arrangement we have ensured that the highest priority interrupt gets serviced first and have established a hierarchy. The farther a device is from the first device, the lower its priority.
### Priority interrupts:
**Advantages:**
- Priority interrupts allow for the efficient handling of high-priority tasks that require immediate attention. This is especially important in real-time systems where certain tasks must be completed within strict time constraints.
- They are more efficient than software polling as the processor does not waste time constantly checking for events that have not occurred.
- Priority interrupts are also more deterministic, as the response time to an event can be accurately predicted based on its priority level.
**Disadvantages:**
- One potential disadvantage of priority interrupts is the possibility of lower priority tasks being starved of resources if high-priority tasks are continuously interrupting the processor.
- If not implemented properly, priority interrupts can lead to priority inversion, where a low-priority task holds a resource required by a higher-priority task, causing a delay in the high-priority task's execution.
### Software polling:
**Advantages:**
- Software polling is relatively simple to implement and does not require specialized hardware.
- It can be used to detect events that occur at irregular intervals, as the processor can check for events whenever it is not performing other tasks.
### Disadvantages:
- Software polling is less efficient than priority interrupts as the processor must constantly check for events even if none have occurred.
- In real-time systems, software polling may not be suitable as it is difficult to guarantee the response time to an event, especially if the processor is busy with other tasks.
### Daisy chaining:
**Advantages:**
- Daisy chaining allows multiple devices to share a single interrupt line, reducing the number of interrupt lines required.
- It is relatively simple to implement and does not require specialized hardware.
**Disadvantages:**
- Daisy chaining can result in increased response time as each device must wait for the previous device to complete its interrupt handling before it can start its own.
- It can also be difficult to implement and troubleshoot, especially if there are multiple devices on the same interrupt line.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/priority-interrupts-sw-polling-daisy-chaining/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: I/O interface (Interrupt and DMA mode)

> [!note] Related notes
>
> - [[AI, ML & Data Science]]
> - [[Aptitude]]
> - [[Asynchronous input output synchronization]]
> - [[BUS Arbitration]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
> - [[Clusters In Computer Organisation]]
> - [[Computer Ports]]
> - [[Connect]]
> - [[Corporate Solution]]
> - [[CS Core Subjects]]
