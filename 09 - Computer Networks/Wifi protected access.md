---
title: "Wifi Protected Access (WPA)"
subject: "Computer Networks"
topic: "Application Layer"
source: "https://www.geeksforgeeks.org/computer-networks/wifi-protected-access-wpa/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Application Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/application-layer
---


> [!abstract] Wifi Protected Access (WPA)
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Application Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/wifi-protected-access-wpa/)

---

# Wifi Protected Access (WPA)

The two security protocols and security certification programs are **Wi-Fi Protected Access (WPA)** and **Wi-Fi Protected Access II (WPA2)**. These are developed by the Wi-Fi Alliance to secure wireless computer networks. The Alliance defined these protocols because of the serious weaknesses the researchers found in the previous system, **Wired Equivalent Privacy (WEP)**. In this article, we will learn about the wep, wpa, versions of wpa, working with wpa, and how to identify the security type.
## What is WEP?
Wired Equivalent Privacy (WEP) is an early security protocol for wireless networks. Introduced in 1997, WEP was designed to provide a level of security comparable to wired networks by encrypting data sent over Wi-Fi. It uses a static key to encrypt data, which is shared between devices and the wireless router. However, WEP has significant weaknesses, such as [vulnerabilities](https://www.geeksforgeeks.org/ethical-hacking/vulnerabilities-in-information-security/) to various hacking methods, making it easy for attackers to break the encryption and access the network. Because of these issues, WEP has been largely replaced by more secure protocols like WPA and WPA2.
## What is Wifi Protected Access (WPA)?
WPA also referred to as the draft IEEE 802.11i standard became available in 2003. The Wi-Fi Alliance made it an intermediate measure in anticipation of the availability of the more secure and complex WPA2, which became available in 2004 and is a common short for the full IEEE 802.11i standard. In 2003, WPA also known as the TKIP standard became accessible. It was meant to be a stopgap measure by the Wi-Fi Alliance before the more complicated and secure WPA2 became available in 2004. WPA2 is a common acronym for the entire IEEE 802.11i (or IEEE 802.11i-2004) standard.
In January 2018, with several security improvements over WPA2 Wi-Fi Alliance announced the release of **WPA3**. 
## Versions of WPA
There are some different versions of WPA which include WPA, WPA2, and WPA3. Different versions have different features, Below mentioned are versions of WiFi Protected Access:
### 1. **WPA**
The WPA is an intermediate measure to take the place of WEP. WPA could be implemented through firmware upgrades on wireless network interface cards that were designed for WEP in 1999. However, since more changes were required in the wireless access points (APs) than those needed on the network cards, most pre-2003 APs could not be upgraded to support WPA. 
The WPA protocol implements almost all of the IEEE 802.11i standard. WEP used a 64-bit or 128-bit encryption key that must be manually entered on wireless access points and devices which once entered can never be changed. TKIP employs a per-packet key, which means that it dynamically generates a new 128-bit key for each packet and thus prevents the types of attacks that compromise WEP. 
WPA includes a Message Integrity Check, which is designed to prevent an attacker from altering or resending data packets. This replaced the cyclic redundancy check (CRC) that was used by the WEP standard. CRC's had a main flaw in that it did not provide a sufficiently strong data integrity guarantee for the packets it handled. Well-tested message authentication codes existed to solve these problems, but they required too much computation to be used on old network cards. WPA uses a message integrity check algorithm called TKIP to verify the integrity of the packets. TKIP is much stronger than a CRC, but the algorithm used in WPA2 is stronger. Researchers discovered a flaw in WPA similar to older weaknesses in WEP and the limitations of the message integrity code hash function, named Michael, that is used to retrieve the keystream from short packets to use for re-injection and [spoofing](https://www.geeksforgeeks.org/computer-networks/what-is-spoofing-in-cyber-security/). 
### **2. WPA2**
WPA2 replaced WPA. WPA2, which requires testing and certification by the Wi-Fi Alliance, implemented the mandatory elements of IEEE 802.11i. Particularly, it included mandatory support for CCMP(Counter Mode CBC-MAC Protocol), an AES(Advanced Encryption Standard) based encryption mode. Certification began in September 2004. WPA2 certification is mandatory for all new devices to bear the Wi-Fi trademark from March 13, 2006. 
### What are the New Features Does the WPA2 Protocol Offer?
WPA was replaced in 2004 with WPA2. WPA2 employs the Block Chaining Message Authentication Code Protocol (CCMP), a Counter Mode Cypher. The Advanced Encryption Standard (AES) algorithm, which verifies the authenticity and integrity of messages, forms the foundation of the CCMP protocol. Compared to the original Temporal Key Integrity Protocol (TKIP) used by WPA, CCMP is more robust and dependable.
However, WPA2 still has security flaws. The risk of unwanted access to the company wireless network is the main one among those weaknesses. This occurs when an attack vector on specific [Wi-Fi Protected Setup (WPS)](https://www.geeksforgeeks.org/computer-networks/wifi-protected-setup-wps/) access points is compromised. To deter such threats, it is advised that WPS be turned off for every WPA2 attack vector access point. Threat actors can use downgrade attacks to target more vulnerabilities in WPA2.
### **3. WPA3**
In 2018, Wi-Fi Protected Access 3, or WPA3, replaced WPA2. The most recent and improved version of WPA is WPA3. In 2018, the Wi-Fi Alliance started certifying goods that had been WPA3-approved. Not all devices immediately incorporate WPA3 capability. Users must either purchase brand-new routers that support WPA3 or have the equipment upgraded by the manufacturer in order to use WPA3-approved devices, such as wireless [routers](https://www.geeksforgeeks.org/computer-networks/introduction-of-a-router/).
## What are the New Features Does the WPA3 Protocol Offer?
In 2018, Wi-Fi Protected Access 3, or WPA3, replaced WPA2. WPA3 is the most recent version of the WPA protocol. In 2018, the Wi-Fi Alliance started to certify products that met WPA3 standards. Not every device has WPA3 support added to it automatically. If users want to use wireless routers or other WPA3-approved devices, they have two options: either purchase new routers that enable WPA3 or have the manufacturer update the device. A comparable 192-bit cryptographic strength (in WPA3-EAP enterprise mode), 384-bit Hashed Message Authentication Mode ([HMAC](https://www.geeksforgeeks.org/computer-networks/what-is-hmachash-based-message-authentication-code/)), 256-bit Broadcast/Multicast Integrity Protocol (BIP-GMAC-256), 256-bit Galois/Counter Mode Protocol encryption (GCMP-256), SAE exchange, and WiFi Device Provisioning Protocol (DPP).
## **Working with WPA**
When establishing a network for others to connect to and when connecting to a wireless network, you'll see options for employing WPA. Although it was intended to enable pre-WPA devices like those that use WEP, some only function with WPA after a firmware update. Some things are just not compatible.
Despite the protocol being more secure than WEP, attacks can still be made against WPA pre-shared keys. Your best line of defence is a passphrase that can withstand [brute-force attacks](https://www.geeksforgeeks.org/computer-networks/brute-force-attack/).
## Security Issues with WPA
- Key shared ahead of time If users rely on a weak password or passphrase, WPA and WPA2 are still susceptible to password cracking attempts.
- Insufficient upfront secrecy
- Due to the lack of forward secrecy offered by WPA and WPA2, an adversary may be able to passively and covertly gather all packets encrypted with that PSK transmitted in the past and even in the future once they ascertain the pre-shared key.
- Tactics known as denial of service, in which an attacker overloads the network with messages, impairing the availability of network resources
- [Eavesdropping](https://www.geeksforgeeks.org/computer-networks/what-is-an-eavesdropping-attack/) is the practice of unauthorised third parties intercepting data being transferred across secure networks. Spoofing and [session hijacking](https://www.geeksforgeeks.org/ethical-hacking/session-hijacking/) are methods by which an attacker obtains access to network resources and data by impersonating a legitimate user.
## How to Identify Your Wi-Fi Security Type?
To identify your Wi-Fi security type, follow these steps:
**1. On Windows**:
- Click the Wi-Fi icon in the taskbar and select your network.
- Right-click on your Wi-Fi network and select **Properties**.
- Look for the **Security type** under the "Network security settings" section.
**2. On macOS**:
- Click the Wi-Fi icon in the menu bar and select **Open Network Preferences**.
- Click **Advanced**, then select your network.
- Look for the **Security** field in the details.
**3. On Mobile Devices**:
- **iOS**: Open **Settings** > **Wi-Fi** > Tap on your network (i) > Check the **Security** field.
- **Android**: Open **Settings** > **Wi-Fi** > Tap on your network > Check the **Security** field.
**4. Router Settings**:
- Log in to your router’s admin page (typically by entering the router’s [IP address](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-an-ip-address/) in your browser).
- Navigate to the **Wireless** or **Security** settings section.
- Check the **Security Mode** or **Encryption** settings to see your Wi-Fi security type.
- Common security types include WPA2, WPA3, WEP, and WPA
## **Difference Between WEP and WPA**
A security standard for computers with wireless internet connections is called **Wi-Fi Protected Access (WPA)**. The Wi-Fi Alliance developed it to improve upon the original Wi-Fi security standard, **Wired Equivalent Privacy (WEP)**, in terms of data encryption and user authentication.
| Features | WEP | WPA |
| --- | --- | --- |
| **Encryption** | Relies on RC4 encryption set of rules. | Supports TKIP and AES encryption algorithms for more potent protection. |
| **Vulnerabilities** | Vulnerable to numerous attacks, including brute-pressure attacks, packet sniffing, and key restoration assaults. | Addresses among the vulnerabilities found in WEP, presenting stronger safety towards attacks. |
| **Key Management** | Uses static encryption keys which can be manually configured and infrequently changed. | Supports dynamic key exchange protocols, such as WPA-Personal (the use of Pre-Shared Key) or WPA-Enterprise (using IEEE 802.1X authentication), for advanced key management and protection. |
| **Compatibility** | Widely supported by older Wi-Fi devices, however compatibility can be reducing as it's far considered outdated. | Compatible with most present day Wi-Fi devices, although older devices won't aid newer encryption protocols like AES. |
| **Security Protocol** | Uses WEP encryption protocol. | Uses more potent encryption protocols inclusive of TKIP (Temporal Key Integrity Protocol) and later [AES (Advanced Encryption Standard)](https://www.geeksforgeeks.org/computer-networks/advanced-encryption-standard-aes/). |
For more, you can refer to [Difference Between WEP and WPA](https://www.geeksforgeeks.org/computer-networks/difference-between-wep-and-wpa/).
## Conclusion
**Wi-Fi Protected Access (WPA)** improved the security of wireless networks by fixing the weaknesses in older methods like WEP. It introduced better encryption and key management. While WPA2 and WPA3 are now more commonly used because they are even more secure, WPA was an important step in making Wi-Fi safer. Knowing about WPA helps us understand why it’s important to use up-to-date security for protecting Wi-Fi connections.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/wifi-protected-access-wpa/)

## GATE CS

- Subject: Computer Networks
- Topic: Application Layer

> [!note] Related notes
>
> - [[Address Resolution in DNS]]
> - [[Basics of Wi-Fi]]
> - [[DHCP Relay Agent]]
> - [[DNS (Domain Name Server) NetWorking]]
> - [[DNS Spoofing or DNS Cache poisoning]]
> - [[Dynamic Host Configuration Protocol]]
> - [[File Transfer Protocol]]
> - [[How DHCP server dynamically assigns IP address to a host]]
> - [[HTTP Non-Persistent & Persistent Connection]]
> - [[LiFi vs WiFi]]
