---
title: "Difference Between FAT32, exFAT, and NTFS File System"
subject: "Operating System"
topic: "File System and Disk Scheduling"
source: "https://www.geeksforgeeks.org/blogs/difference-between-fat32-exfat-and-ntfs-file-system/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/File System and Disk Scheduling"
tags:
  - gate/cs
  - subject/operating-system
  - topic/file-system-and-disk-scheduling
---


> [!abstract] Difference Between FAT32, exFAT, and NTFS File System
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `File System and Disk Scheduling`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/blogs/difference-between-fat32-exfat-and-ntfs-file-system/)

---

# Difference Between FAT32, exFAT, and NTFS File System

When you write data to a storage medium whether it's a hard drive or an SSD or an SD card or a micro SD card or a USB flash drive you need to write the data in such a way that it can be found again.  You can't just write it randomly on a drive and then expect to get it back one day when you need it. It needs to be organized and that organization is called a **file system.**
![Difference between FAT32, exFAT, and NTFS File System](assets/differencebetweenFAT32VsexFATVsNTFSmin-0d739482d1.png)
A File System is a collection of rules and algorithms that is responsible for translating logical file operations to the physical storage of information. In simpler words, we can say that the file system controls the flow of storage and retrieval of data in a device.
There are 3 types of the file system in a device:
1. FAT32
2. exFAT
3. NTFS
As mentioned earlier when you store a file on a disk, the operating system needs to know where the file is physically located. It needs to have a way to associate a file name with that file's contents. In addition to that, there might be other things like folders and file permissions, etc. In this article, we will look into the key difference between them.
## FAT32
FAT32 or the File Allocation Table file system is one of the oldest file systems available on the Windows machine. It was first introduced on MS-DOS 7.1 / Windows 95 OSR2 in 1996 replacing the previous FAT16 file system. It was originally developed for floppy disks however over the years it found its way onto the hard drive, USB flash drives, and SSD cards, and it was the default file system for windows up until Windows XP. There have been several variations of FAT, based on the size of the table as it's a file allocation table that holds information about the files like FAT8, FAT12, and FAT16. FAT32 is almost universally understood not only by PCs running Windows but also Linux, macOS, cameras, media players, game consoles, smart TVs, Android phones, and so on. Being one of the oldest file systems, it has some profound limitations.
But there are also some advantages of using a FAT32. They are listed below:
### Advantages:
- A FAT32 file system can hold up to 268,173,300 files, provided it is using 32KB clusters
- The backup FAT table copy gets automatically relocated to the root folder in FAT32 systems, which further can be used for the restoration of files.
- In FAT32 file systems, the drive sizes are between 2 and 16 TB with 64KB clusters.
- FAT32 is the official format for SD and SDHC cards.
- It's also the defacto standard for many USB flash drives and even some types of external hard drives.
### Limitations:
- Each file in a FAT32 drive can have a maximum size of 4GB (GigaBytes).
- No control over file permissions and data security.
- The native disk's maximum disk size for FAT32 is 32 GB. It is possible to expand it up to 2TB using 3rd party tools. The theoretical limit for the same is 16TB.
- FAT32 is no longer used on modern, internal Windows hard drives as most systems have adopted the NTFS standard. This can raise compatibility issues.
## exFAT
The extended File Allocation Table system or exFAT was designed by Microsoft and introduced in 2006.  It allows for files larger than 4GB. It was adopted by the SD card association for the default file system of cards greater than 32GB. The limits of exFAT are measured in PetaBytes(PB) and ExaBytes(EB). It is important to note that if an OEM wants to use exFAT it needs to pay for the license to Microsoft.
### Advantages:
- It supports the restoration of deleted files.
- Data recovery in the exFAT system is one of its highlights.
- There are no limits on file size or partition size practically.
### Limitations:
- It's not compatible with as many device types as compared to its predecessor FAT32.
- Unlike NTFS, advanced functionalities like Journaling functionality, disk quotas, file compression, etc are not available in exFAT.
- Data security is not as reliable as compared to NTFS.
## NTFS
The New Technology File System or NTFS was developed for Windows NT, and it was a default file system for all the members of the Windows NT family of operating systems right up until Windows XP which kind of combined NT and the framework of the traditional windows together. On Windows XP and the NTFS became the default for Windows including Windows 10 which you may well be using today. The file sizes in NTFS are measured in ExaBytes(EB).
### Advantages:
- It has features like file compression, file permission, and file encryption. These are all built-in at a file system level.
- NTFS is a **journaling file system**, meaning there are two types of data that are stored when you actually write some data to a disk. There's the actual file content, and metadata about the file like the file name, its permissions, its location on the disk, etc.  So any operations performed on the data like deletion or renaming or relocating file doesn't affect the data itself but just changes the metadata. A journal stores the intention of the file system before it starts its operations. This ultimately reduces system corruption due to unexpected restarts.
- No restrictions on the size of partitions
### Limitations:
- The biggest issue with the NTFS is compatibility with other systems. NTFS is petty much a Windows thing. But some cleanroom implementations for Linux and macOS not written by Microsoft are also available over the internet to overcome this restriction.
- It is relatively slow compared to its contemporaries.
- It has a small disk size.
- The macOS and most Linux distributions have Read-only support by default.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/blogs/difference-between-fat32-exfat-and-ntfs-file-system/)

## GATE CS

- Subject: Operating System
- Topic: File System and Disk Scheduling

> [!note] Related notes
>
> - [[Disk Scheduling Algorithms]]
> - [[File Access Methods]]
> - [[File Allocation Methods]]
> - [[File Directory Path Name]]
> - [[File Systems]]
> - [[Last Minute Notes – Operating Systems]]
> - [[Operating System Free space management]]
> - [[Program for SSTF disk scheduling algorithm]]
> - [[Structures of Directory]]
> - [[Allocating kernel memory]]
