---
title: "Free Space Management in Operating System"
subject: "Operating System"
topic: "File System and Disk Scheduling"
source: "https://www.geeksforgeeks.org/operating-systems/free-space-management-in-operating-system/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/File System and Disk Scheduling"
tags:
  - gate/cs
  - subject/operating-system
  - topic/file-system-and-disk-scheduling
---


> [!abstract] Free Space Management in Operating System
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `File System and Disk Scheduling`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/free-space-management-in-operating-system/)

---

# Free Space Management in Operating System

Free space management involves managing the available storage space on the hard disk or other secondary storage devices. To reuse the space released from deleting the files, a free space list is maintained. The free space list can be implemented mainly as:
![Free_space_management](assets/Free_space_management-bb25003d19.webp)
Free Space Management
- Bitmap or Bit vector
- Linked List
- Boundary Tags
- Free List
## Bitmap or Bit vector
In this approach, A [Bitmap](https://www.geeksforgeeks.org/dbms/bitmap-indexing-in-dbms/) or Bit Vector is series or collection of bits where each bit corresponds to a disk block. The bit can take two values 0 and 1:
- 0 indicates that the block is free and 1 indicates an allocated​ block.
- The given instance of disk blocks on the disk in Figure 1 can be represented by a bitmap of 16 bits as: 1111000111111001. ![Bitmap](assets/Bitmap-32f94bf230.webp)
  Bitmap
**Advantages:**
- Simple to understand.
- Finding the first free block is efficient. It requires scanning the words (a group of 8 bits) in a bitmap for a non-zero word. (A 0-valued word has all bits 0). The first free block is then found by scanning for the first 1 bit in the non-zero word.
**Disadvantages:**
- For finding a free block, Operating System needs to iterate all the blocks which is time consuming.
- The efficiency of this method reduces as the disk size increases.
## Linked List
In this approach, Free blocks are linked together in a list. Each free block stores the address of the next free block. The list is maintained dynamically as blocks are allocated and freed.
![Free_List](assets/Free_List-d0bae0d281.webp)
Linked List
> **Note:** The free space list head points to Block 5 which points to Block 6, the next free block and so on. The last free block would contain a null pointer indicating the end of free list.
**Advantages:**
- The total available space is used efficiently using this method.
- Dynamic allocation in Linked List is easy, thus can add the space as per the requirement dynamically.
**Disadvantages:**
- When the size of Linked List increases, the headache of maintaining pointers is also increases.
- This method is not efficient during iteration of each block of memory.
- I/O is required for free space list traversal.
## Boundary Tags
In this approach, Each block contains a boundary tag indicating its size and whether it is free or occupied. Adjacent free blocks are merged during deallocation to reduce fragmentation.
**Advantages**:
- Useful in memory management systems.
- Simplifies coalescing of adjacent free blocks.
**Disadvantages:**
- Slight overhead in storing tag information.
- More complex than bitmap or linked list.
## Free List
In this approach, The free blocks are maintained in a list (array or linked list). Each entry in the free list points directly to a free block on disk.
![disk_block](assets/disk_block-b994812fcd.webp)
Free List
**Advantages:**
- Fast allocation as free blocks are known upfront.
- Easy to traverse and maintain.
**Disadvantages:**
- Extra memory needed to store the list.
- May suffer from fragmentation over time.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/free-space-management-in-operating-system/)

## GATE CS

- Subject: Operating System
- Topic: File System and Disk Scheduling

> [!note] Related notes
>
> - [[Difference between FAT32, exFAT, and NTFS File System]]
> - [[Disk Scheduling Algorithms]]
> - [[File Access Methods]]
> - [[File Allocation Methods]]
> - [[File Directory Path Name]]
> - [[File Systems]]
> - [[Last Minute Notes – Operating Systems]]
> - [[Program for SSTF disk scheduling algorithm]]
> - [[Structures of Directory]]
> - [[Allocating kernel memory]]
