---
title: "Program to determine class, Network and Host ID of an IPv4 address"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/dsa/program-determine-class-network-host-id-ipv4-address/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Program to determine class, Network and Host ID of an IPv4 address
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/program-determine-class-network-host-id-ipv4-address/)

---

# Program to determine class, Network and Host ID of an IPv4 address

Given a valid IPv4 address in the form of string and it follows [Class Full](https://www.geeksforgeeks.org/computer-networks/introduction-of-classful-ip-addressing/) addressing. The task is to determine the class of the given IPv4 address as well as separate the Network and Host ID parts from it.
**Examples:**
```
Input : 1.4.5.5
Output :
Given IP address belongs to Class A
Network ID is 1
Host ID is 4.5.5
Input : 130.45.151.154
Output :
Given IP address belongs to Class B
Network ID is 130.45
Host ID is 151.154
```
**Approach**
1. **For determining the class:** The idea is to check the first octet of the IP addresses. As we know, for class **A** first octet will range from **1 - 126**, for class **B** first octet will range from **128 - 191**, for class **C** first octet will range from **192- 223**, for class **D** first octet will range from **224 - 239**, for class **E** first octet will range from **240 - 255**.
2. **For determining the Network and Host ID:** We know that [Subnet Mask](https://www.iplocation.net/subnet-mask) for Class **A** is **8**, for Class **B** is **16** and for Class **C** is **24** whereas Class **D** and **E** are not divided into Network and Host ID.
   For 2nd Example, the first octet is 130. So, it belongs to Class **B**. Class B has a subnet mask of 16. So, the first 16 bit or first two octets are the Network ID part and the rest is the Host ID part. 
   Hence, the Network ID is **130.45** and the Host ID is **151.154**
````C
// C program to determine class, Network
// and Host ID of an IPv4 address
#include<stdio.h>
#include<string.h>
// Function to find out the Class
char findClass(char str[])
{
    // storing first octet in arr[] variable
    char arr[4];
    int i = 0;
    while (str[i] != '.')
    {
        arr[i] = str[i];
        i++;
    }
    i--;
    // converting str[] variable into number for
    // comparison
    int ip = 0, j = 1;
    while (i >= 0)
    {
        ip = ip + (str[i] - '0') * j;
        j = j * 10;
        i--;
    }
    // Class A
    if (ip >=1 && ip <= 126)
        return 'A';
    // Class B
    else if (ip >= 128 && ip <= 191)
        return 'B';
    // Class C
    else if (ip >= 192 && ip <= 223)
        return 'C';
    // Class D
    else if (ip >= 224 && ip <= 239)
        return 'D';
    // Class E
    else
        return 'E';
}
// Function to separate Network ID as well as
// Host ID and print them
void separate(char str[], char ipClass)
{
    // Initializing network and host array to NULL
    char network[12], host[12];
    for (int k = 0; k < 12; k++)
        network[k] = host[k] = '\0';
    // for class A, only first octet is Network ID
    // and rest are Host ID
    if (ipClass == 'A')
    {
        int i = 0, j = 0;
        while (str[j] != '.')
            network[i++] = str[j++];
        i = 0;
        j++;
        while (str[j] != '\0')
            host[i++] = str[j++];
        printf("Network ID is %s\n", network);
        printf("Host ID is %s\n", host);
    }
    // for class B, first two octet are Network ID
    // and rest are Host ID
    else if (ipClass == 'B')
    {
        int i = 0, j = 0, dotCount = 0;
        // storing in network[] up to 2nd dot
        // dotCount keeps track of number of
        // dots or octets passed
        while (dotCount < 2)
        {
            network[i++] = str[j++];
            if (str[j] == '.')
                dotCount++;
        }
        i = 0;
        j++;
        while (str[j] != '\0')
            host[i++] = str[j++];
        printf("Network ID is %s\n", network);
        printf("Host ID is %s\n", host);
    }
    // for class C, first three octet are Network ID
    // and rest are Host ID
    else if (ipClass == 'C')
    {
        int i = 0, j = 0, dotCount = 0;
        // storing in network[] up to 3rd dot
        // dotCount keeps track of number of
        // dots or octets passed
        while (dotCount < 3)
        {
            network[i++] = str[j++];
            if (str[j] == '.')
                dotCount++;
        }
        i = 0;
        j++;
        while (str[j] != '\0')
            host[i++] = str[j++];
        printf("Network ID is %s\n", network);
        printf("Host ID is %s\n", host);
    }
    // Class D and E are not divided in Network
    // and Host ID
    else
        printf("In this Class, IP address is not"
           " divided into Network and Host ID\n");
}
// Driver function is to test above function
int main()
{
    char str[] = "192.226.12.11";
    char ipClass = findClass(str);
    printf("Given IP address belongs to Class %c\n",
                                           ipClass);
    separate(str, ipClass);
    return 0;
}
````
````Java
// Java program to determine class, Network
// and Host ID of an IPv4 address
class NetworkId{
    static String findClass(String str){
        // Calculating first occurrence of '.' in str
        int index = str.indexOf('.');
        // First octate in str in decimal form
        String ipsub = str.substring(0,index);
        int ip = Integer.parseInt(ipsub);
        // Class A
        if (ip>=1 && ip<=126)
            return "A";
        // Class B
        else if (ip>=128 && ip<=191)
            return "B";
        // Class C
        else if (ip>=192 && ip<223)
            return "C";
        // Class D
        else if (ip >=224 && ip<=239)
            return "D";
        // Class E
        else
            return "E";
    }
    static void separate(String str, String ipClass){
        // Initializing network and host empty
        String network = "", host = "";
        if(ipClass == "A"){
            int index = str.indexOf('.');
            network = str.substring(0,index);
            host = str.substring(index+1,str.length());
        }else if(ipClass == "B"){
            //Position of breaking network and HOST id
            int index = -1;
            int dot = 2;
            for(int i=0;i<str.length();i++){
                if(str.charAt(i)=='.'){
                    dot -=1;
                    if(dot==0){
                        index = i;
                        break;
                    }
                }
            }
            network = str.substring(0,index);
            host = str.substring(index+1,str.length());
        }else if(ipClass == "C"){
            //Position of breaking network and HOST id
            int index = -1;
            int dot = 3;
            for(int i=0;i<str.length();i++){
                if(str.charAt(i)=='.'){
                    dot -=1;
                    if(dot==0){
                        index = i;
                        break;
                    }
                }
            }
            network = str.substring(0,index);
            host = str.substring(index+1,str.length());
        }else if(ipClass == "D" || ipClass == "E"){
            System.out.println("In this Class, IP address"+
            " is not divided into Network and Host IDs");
            return;
        }
        System.out.println("Network ID is "+network);
        System.out.println("Host ID is "+host);
    }
    public static void main(String[] args) {
        String str = "192.226.12.11";
        String ipClass = findClass(str);
        System.out.println("Given IP address belings to Class "+ipClass);
        separate(str,ipClass);
    }
}
````
````python3
#function to determine the class of an Ip address
def findClass(ip):
  if(ip[0] >= 0 and ip[0] <= 127):
    return "A"
  else if(ip[0] >=128 and ip[0] <= 191):
    return "B"
  else if(ip[0] >= 192 and ip[0] <= 223):
    return "C"
  else if(ip[0] >= 224 and ip[0] <= 239):
    return "D"
  else:
    return "E"
#function to separate network and host id from the given ip address
def separate(ip, className):
  #for class A network
  if(className == "A"):
    print("Network Address is : ", ip[0])
    print("Host Address is : ", ".".join(ip[1:4]))
  #for class B network
  else if(className == "B"):
    print("Network Address is : ", ".".join(ip[0:2]))
    print("Host Address is : ", ".".join(ip[2:4]))
  #for class C network
  else if(className == "C"):
    print("Network Address is : ", ".".join(ip[0:3]))
    print("Host Address is : ", ip[3])
  else:
    print("In this Class, IP address is not divided into Network and Host ID")
#driver's code
if __name__ == "__main__":
  ip = "192.226.12.11"
  ip = ip.split(".")
  ip = [int(i) for i in ip]
  #getting the network class
  networkClass = findClass(ip)
  print("Given IP address belongs to class : ", networkClass)
  #printing network and host id
  ip = [str(i) for i in ip]
  separate(ip, networkClass)
````
````csharp
/* C# program to determine class, Network
 and Host ID of an IPv4 address*/
using System;
class NetworkId
{
    static string FindClass(string str)
    {
        // Calculating first occurrence of '.' in str
        int index = str.IndexOf('.');
        // First octate in str in decimal form
        string ipsub = str.Substring(0, index);
        int ip = int.Parse(ipsub);
        // Class A
        if (ip >= 1 && ip <= 126)
            return "A";
        // Class B
        else if (ip >= 128 && ip <= 191)
            return "B";
        // Class C
        else if (ip >= 192 && ip < 223)
            return "C";
        // Class D
        else if (ip >= 224 && ip <= 239)
            return "D";
        // Class E
        else
            return "E";
    }
    static void Separate(string str, string ipClass)
    {
        // Initializing network and host empty
        string network = "", host = "";
        if (ipClass == "A")
        {
            int index = str.IndexOf('.');
            network = str.Substring(0, index);
            host = str.Substring(index + 1, str.Length - index - 1);
        }
        else if (ipClass == "B")
        {
            //Position of breaking network and HOST id
            int index = -1;
            int dot = 2;
            for (int i = 0; i < str.Length; i++)
            {
                if (str[i] == '.')
                {
                    dot--;
                    if (dot == 0)
                    {
                        index = i;
                        break;
                    }
                }
            }
            network = str.Substring(0, index);
            host = str.Substring(index + 1, str.Length - index - 1);
        }
        else if (ipClass == "C")
        {
            //Position of breaking network and HOST id
            int index = -1;
            int dot = 3;
            for (int i = 0; i < str.Length; i++)
            {
                if (str[i] == '.')
                {
                    dot--;
                    if (dot == 0)
                    {
                        index = i;
                        break;
                    }
                }
            }
            network = str.Substring(0, index);
            host = str.Substring(index + 1, str.Length - index - 1);
        }
        else if (ipClass == "D" || ipClass == "E")
        {
            Console.WriteLine("In this Class, IP address is not divided into Network and Host IDs");
            return;
        }
        Console.WriteLine("Network ID is " + network);
        Console.WriteLine("Host ID is " + host);
    }
    static void Main(string[] args)
    {
        string str = "192.226.12.11";
        string ipClass = FindClass(str);
        Console.WriteLine("Given IP address belongs to Class " + ipClass);
        Separate(str, ipClass);
    }
}
//This code is contributed by snehalsalokhe
````
**Output:**
```
Given IP address belongs to Class C
Network ID is 192.226.12
Host ID is 11
```
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/program-determine-class-network-host-id-ipv4-address/)

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
