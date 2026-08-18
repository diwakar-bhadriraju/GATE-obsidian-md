---
title: "Classless Addressing in IP Addressing"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/ip-addressing-classless-addressing/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Classless Addressing in IP Addressing
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/ip-addressing-classless-addressing/)

---

# Classless Addressing in IP Addressing

The network address identifies a specific network on the Internet. It is used to determine the range of IP addresses within that network and to calculate the total number of possible hosts that can exist in the network.
A subnet mask is a 32-bit binary value used to separate the network portion and host portion of an IP address. When a bitwise AND operation is performed between an IP address and the subnet mask, the resulting value represents the network address of that IP block.
In classful addressing, each IP address class has a predefined default subnet mask that determines the boundary between the network and host portions of the address.
> - Class A - 255.0.0.0
> - Class B - 255.255.0.0
> - Class C - 255.255.255.0
**Question:** Given the IP address 132.6.17.85 and the default Class B subnet mask, find the network (beginning) address.
**Solution:** The default subnet mask for a Class B address is 255.255.0.0, which means the first two bytes represent the network portion, while the last two bytes represent the host portion. By setting the host bits to zero, the network address is obtained. Therefore, the network address is 132.6.0.0.
## **Subnetting**
Subnetting is the process of dividing a large block of IP addresses into smaller, contiguous sub-blocks and assigning them to smaller networks. It is widely used in classless addressing to efficiently manage and utilize IP address space.
A subnet is a logical subdivision of a larger network. Subnetting improves network efficiency by reducing unnecessary traffic. It allows data to travel shorter paths within the network, minimizing the need to pass through multiple routers and improving overall performance.
## **Classless Addressing**
Classless addressing is an improved IP addressing system designed to reduce IP address wastage by allowing flexible allocation of address blocks. Unlike classful addressing, it does not rely on fixed network classes. Instead, it uses some of the host bits as network bits to create subnets based on actual requirements.
In classless addressing, an IP address is written along with a prefix length, usually indicated by a / symbol, such as 192.168.1.1/28. The prefix length specifies how many bits out of the 32-bit IP address are used for the network portion. The subnet mask is created by setting the specified number of bits to 1 and the remaining bits to 0. For example, a /28 prefix results in the subnet mask 255.255.255.240.
CIDR also supports supernetting, where multiple contiguous Class C networks can be combined into a larger network, such as a /23 or /22. This allows efficient routing and better utilization of the IPv4 address space. In classless addressing, IP address blocks are assigned dynamically according to specific rules rather than fixed classes.
- Removes dependency on Class A, B, and C
- Uses host bits as additional network bits
- IP address is written with a prefix length (e.g., /28)
- Subnet mask is derived from the prefix
- Reduces IP address wastage
- Supports supernetting and route aggregation
- Improves scalability and routing efficiency
### **Some Values Calculated in Subnetting:**
1. Number of subnets : 2(Given bits for mask - No. of bits in default mask)
2. Subnet address : AND result of subnet mask and the given IP address
3. Broadcast address : By putting the host bits as 1 and retaining the network bits as in the IP address
4. Number of hosts per subnet : 2(32 - Given bits for mask) - 2
5. First Host ID : Subnet address + 1 (adding one to the binary representation of the subnet address)
6. Last Host ID : Subnet address + Number of Hosts
````cpp
#include <bits/stdc++.h>
using namespace std;
string ip_classless(string ip){
    // Extract the first octet as a string and then convert it to an int using stoi function
    int first_octet=stoi(ip.substr(0,ip.find('.')));
    if(first_octet>=0 and first_octet<=127){
        // Means the IP Address in Class A
        return ip+"/8";
    }
    if(first_octet>=128 and first_octet<=191){
        // Means the IP Address is in Class B
        return ip+"/16";
    }
    if(first_octet>=192 and first_octet<=223){
        // Means the IP Address is in Class C
        return ip+"/24";
    }
    return "Reserved IP Address. Invalid.";
}
//Driver Code
int main() {
    // Will store the ip address as an input in ip variable
    string ip;
    cout<<"Enter the IP Address: ";
    cin>>ip;
    cout<<ip_classless(ip)<<endl;
    // This Code is contributed by Himesh Singh Chauhan
    return 0;
}
````
````c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
char *ip_classless(char *ip_address) {
    int i, j, k;
    int octets[4];
    char *mask = (char *) malloc(sizeof(char) * 16);
    int bits = 0;
    for (i = 0, j = 0, k = 0; i < strlen(ip_address); i++) {
        if (ip_address[i] == '.') {
            octets[j++] = atoi(ip_address + k);
            k = i + 1;
        }
    }
    octets[j] = atoi(ip_address + k);
    for (i = 0; i < 4; i++) {
        int octet = octets[i];
        for (j = 7; j >= 0; j--) {
            if (octet >= (1 << j)) {
                bits++;
                octet -= (1 << j);
            } else if (bits % 8 != 0) {
                break;
            }
        }
    }
    sprintf(mask, "%s/%d", ip_address, bits);
    return mask;
}
int main() {
    char ip_address[16];
    printf("Enter an IP address in classful notation: ");
    scanf("%s", ip_address);
    printf("Classless address: %s\n", ip_classless(ip_address));
    return 0;
}
````
````python3
def ip_classless(ipaddress):
    '''
        Will return the Classless IP Address
    '''
    # Alongwith the info of the Default Subnet Mask, info like no. of bits used for NID and no. of bits used for HID can also be specified as they depend on the Class only
    # The no. of Hosts can also be specified on the basis of the Input IP Address
    # Gets the First Octet through String Slicing
    firstOctet=int(ipaddress[:ipaddress.index('.')])
    if(0<=firstOctet<=127):
      # Means this is Class A IP Address
        return ipaddress+'/8'
    elif(128<=firstOctet<=191):
      # Means this is a Class B IP Address
        return ipaddress+'/16'
    elif(192<=firstOctet<=223):
      # Means this is a Class C IP Address
        return ipaddress+'/24'
    else:
        print("This is a reserved IP Address, INVALID!!")
ip=input("Enter an IP Address in Classful Notation: ")
print(ip_classless(ip))
# This code is contributed by Himesh Singh Chauhan
````
````csharp
using System;
class Program {
    static string IpClassless(string ipAddress)
    {
      // Initialize some variables
        int j = 0, k = 0;
        int[] octets = new int[4];
        int bits = 0;
        for (int i = 0; i < ipAddress.Length; i++) {
           // If we encounter a '.', extract the octet
            if (ipAddress[i] == '.') {
                octets[j++] = int.Parse(
                    ipAddress.Substring(k, i - k));
              // Convert the octet to an integer and store it
                k = i + 1;
              // Move the starting position of the next octet to the character after the '.'
            }
        }
      // Extract the final octet
        octets[j] = int.Parse(ipAddress.Substring(k));
        for (int i = 0; i < 4; i++) {
            int octet = octets[i];
            for (j = 7; j >= 0; j--) {
                if (octet >= (1 << j)) {
                    bits++;
                    octet -= (1 << j);// Subtract the value of the bit from the octet
                }
                else if (bits % 8 != 0) {
                    break;
   // If the current bit is 0 and the bit count is not a multiple of 8, stop counting bits
                }
                }
            }
        }
        return ipAddress + "/" + bits;// Return the input IP address with the bit count appended
    }
    static void Main(string[] args)
    {
        Console.WriteLine(
            "Enter an IP address in classful notation: ");
        string ipAddress = Console.ReadLine();
        Console.WriteLine("Classless address: "
                          + IpClassless(ipAddress));
    }
}
//The code is contributed by snehalsalokhe
````
### **Explanation:**
This program takes an IP address in classful notation as input (e.g. 192.168.0.0) and converts it to classless addressing (CIDR notation) by checking the Class of the IP address and setting the mask(number after '/') on that basis. The resulting CIDR notation is returned by the function ip\_classless.
```
Enter an IP address in classful notation: 192.168.0.0Classless address: 192.168.0.0/24
```
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/ip-addressing-classless-addressing/)

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
