---
title: "Random Access Memory (RAM) and Read Only Memory (ROM)"
subject: "Computer Organization and Architecture"
topic: "Cache Memory"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/random-access-memory-ram-and-read-only-memory-rom/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Cache Memory"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/cache-memory
---


> [!abstract] Random Access Memory (RAM) and Read Only Memory (ROM)
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Cache Memory`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/random-access-memory-ram-and-read-only-memory-rom/)

---

# Random Access Memory (RAM) and Read Only Memory (ROM)

Memory is a fundamental component of computing systems, essential for performing various tasks efficiently. It plays a crucial role in how computers operate, influencing speed, performance, and data management. In the realm of computer memory, two primary types stand out: Random Access Memory (RAM) and Read-Only Memory (ROM). Understanding the difference between RAM and ROM is vital for appreciating their respective roles in a computer's operation. While RAM enables efficient processing and multitasking, ROM provides the necessary stability and reliability for system functions. Together, these memory types ensure that computers can operate smoothly and effectively in a digital landscape.
## Types of Memory
Memory is the most essential element of a computing system because without it computer can’t perform simple tasks. Both types of memory (RAM and ROM) are important for the computer, but they serve different purposes. RAM is used to store data that the computer is currently using, while ROM is used to store data that the computer needs to boot and operate. RAM is faster than ROM, as the data stored in it can be accessed and modified in any order, while data stored in ROM can only be read.
Computer memory is of two basic types:
1. Primary memory (RAM and ROM)
2. Secondary memory (Hard Drive, CD, etc).
![Classification of Computer Memory](assets/memory-85477bfac0.png)
Classification of Primary Memory
## Random Access Memory (RAM)
**Random Access Memory (RAM)**  is a type of computer memory that is used to temporarily store data that the computer is currently using or processing. RAM is volatile memory, which means that the data stored in it is lost when the power is turned off. RAM is typically used to store the operating system, application programs, and data that the computer is currently using.
- It is also called read-write **memory**  or the  **main memory**  or the  **primary memory**  .
- The programs and data that the CPU requires during the execution of a program are stored in this memory.
- It is a volatile memory as the data is lost when the power is turned off.
![RAM](assets/RAM-cbc6e7896e.jpg)
Random Access Memory
### Types of Random Access Memory (RAM)
- [Static RAM (SRAM)](https://www.geeksforgeeks.org/operating-systems/sram-full-form/)
- [Dynamic RAM (DRAM)](https://www.geeksforgeeks.org/computer-science-fundamentals/dram-full-form/)
**1. Static RAM:**  SRAM stands for Static Random Access Memory. It is a type of semiconductor which is widely used in computing devices and microprocessors.
**2. Dynamic RAM:**  DRAM stands for Dynamic Random Access Memory. It is made of Capacitors and has smaller data life span than Static RAM.
## **Difference Between DRAM and SRAM**
| Parameter | DRAM | SRAM |
| --- | --- | --- |
| Construction | Constructed of tiny capacitors that leak electricity. | Constructed of circuits similar to D flip-flops. |
| Data Retention | Requires a recharge every few milliseconds to maintain its data. | Holds its contents as long as power is available. |
| Cost | Inexpensive. | Expensive. |
| Speed | Slower than SRAM. | Faster than DRAM. |
| Storage Capacity | Can store many bits per chip. | Can not store many bits per chip. |
| Power Consumption | Uses less power. | Uses more power. |
| Heat Generation | Generates less heat. | Generates more heat. |
| Typical Usage | Used for main memory. | Used for cache. |
### Advantages of Random Access Memory (RAM)
- **Speed:** RAM is much faster than other types of storage, such as a hard drive or solid-state drive, which means that the computer can access the data stored in RAM more quickly.
- **Flexibility:** RAM is volatile memory, which means that the data stored in it can be easily modified or deleted. This makes it ideal for storing data that the computer is currently using or processing.
- **Capacity:** The capacity of RAM can be easily upgraded, which allows the computer to store more data in memory and thus improve performance.
- **Power Management:** RAM consumes less power compared to hard drives, and solid-state drives, which makes it an ideal memory for portable devices.
### Disadvantages of Random Access Memory (RAM)
- **Volatility:** RAM is volatile memory, which means that the data stored in it is lost when the power is turned off. This can be a problem for important data that needs to be preserved, such as unsaved work or files that have not been backed up.
- **Capacity:** The capacity of RAM is limited, and although it can be upgraded, it may still not be sufficient for certain applications or tasks that require a lot of memory.
- **Cost:** RAM can be relatively expensive compared to other types of memory, such as hard drives or solid-state drives, which can make upgrading the memory of a computer or device more costly.
## Read-Only Memory (ROM)
**Read Only Memory (ROM)**  is a type of computer memory that is used to permanently store data that does not need to be modified. ROM is non-volatile memory, which means that the data stored in it is retained even when the power is turned off. ROM is typically used to store the computer's BIOS (basic input/output system), which contains the instructions for booting the computer, as well as firmware for other hardware devices.
- Stores crucial information essential to operate the system, like the program essential to boot the computer.
- It is non-volatile.
- Always retains its data.
- Used in embedded systems or where the programming needs no change.
- Used in calculators and peripheral devices.
- ROM is further classified into four types- M **ROM**  ,  [**PROM**](https://www.geeksforgeeks.org/computer-networks/prom-full-form/)  ,  [**EPROM**](https://www.geeksforgeeks.org/computer-organization-architecture/eprom-full-form/)  , and  [**EEPROM**](https://www.geeksforgeeks.org/computer-organization-architecture/eeprom-full-form/)  .
![ROM](https://media.geeksforgeeks.org/wp-content/uploads/20240808071313/ROM_LOGO.jpg)
Read-Only Memory (ROM)
### **Types of Read-Only Memory (ROM)**
1. [PROM (Programmable Read-Only Memory)](https://www.geeksforgeeks.org/computer-networks/prom-full-form/)
2. [EPROM (Erasable Programmable Read Only Memory)](https://www.geeksforgeeks.org/computer-organization-architecture/eprom-full-form/)
3. [EEPROM (Electrically Erasable Programmable Read Only Memory)](https://www.geeksforgeeks.org/computer-organization-architecture/eeprom-full-form/)
4. MROM (Mask Read Only Memory)
**1. PROM (Programmable read-only memory):**  It can be programmed by the user. Once programmed, the data and instructions in it cannot be changed.
**2. EPROM (Erasable Programmable read-only memory):**  It can be reprogrammed. To erase data from it, expose it to ultraviolet light. To reprogram it, erase all the previous data.
**3. EEPROM (Electrically erasable programmable read-only memory):**  The data can be erased by applying an electric field, with no need for ultraviolet light. We can erase only portions of the chip.
**4. MROM(Mask ROM):**  Mask ROM is a kind of read-only memory, that is masked off at the time of production. Like other types of ROM, mask ROM cannot enable the user to change the data stored in it. If it can, the process would be difficult or slow.
### Advantages of Read Only Memory (ROM)
- **Non-volatility:** ROM is non-volatile memory, which means that the data stored in it is retained even when the power is turned off. This makes it ideal for storing data that does not need to be modified, such as the BIOS or firmware for other hardware devices.
- **Reliability:** Because the data stored in ROM is not easily modified, it is less prone to corruption or errors than other types of memory.
- **Power Management:** ROM consumes less power compared to other types of memory, which makes it an ideal memory for portable devices.
### Disadvantages of Read Only Memory (ROM)
- **Limited Flexibility:** ROM is read-only memory, which means that the data stored in it cannot be modified. This can be a problem for applications or firmware that need to be updated or modified.
- **Limited Capacity:** The capacity of ROM is typically limited, and upgrading it can be difficult or expensive.
- **Cost:** ROM can be relatively expensive compared to other types of memory, such as hard drives or solid-state drives, which can make upgrading the memory of a computer or device more costly.
## Difference Between RAM and ROM
| Parameter | RAM | ROM |
| --- | --- | --- |
| Storage Type | Temporary Storage. | Permanent Storage. |
| Storage Capacity | Store data in MBs. | Store data in GBs. |
| Data Volatility | Volatile. | Non-volatile. |
| Usage | Used in normal operations. | Used for startup process of computer. |
| Data Writing Speed | Writing data is faster. | Writing data is slower. |
## Conclusion
In the realm of computer memory, RAM (Random Access Memory) and ROM (Read-Only-Memory) play pivotal roles, each with its unique purpose. Think of RAM as the bustling workspace of your computer-where data is temporarily stored and readily accessible for quick tasks and modifications.
 However, this workspace is fleeting; once the power goes out, so does the information.
By grasping the distinctions between these two memory types, we can better appreciate their contributions to the seamless operation of computers, ensuring both efficiency the rapid responsiveness of RAM or the dependable permanence of ROM, each type of memory is indispensable in the digital landscape.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/random-access-memory-ram-and-read-only-memory-rom/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: Cache Memory

> [!note] Related notes
>
> - [[2D and 2.5D Memory organization]]
> - [[Cache Memory]]
> - [[Cache Organization Introduction]]
> - [[Different Types of RAM]]
> - [[Introduction to memory and memory units]]
> - [[Locality and Cache friendly code]]
> - [[Memory Hierarchy Design and its Characteristics]]
> - [[Memory Interleaving]]
> - [[RAM vs ROM]]
> - [[Read and Write operations in memory]]
