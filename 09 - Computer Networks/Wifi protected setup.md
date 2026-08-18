---
title: "Wifi Protected Setup (WPS)"
subject: "Computer Networks"
topic: "Application Layer"
source: "https://www.geeksforgeeks.org/computer-networks/wifi-protected-setup-wps/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Application Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/application-layer
---


> [!abstract] Wifi Protected Setup (WPS)
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Application Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/wifi-protected-setup-wps/)

---

# Wifi Protected Setup (WPS)

The **Wifi protected setup (WPS)** is a wireless network security standard that tries to make connections between a router and wireless devices in a faster and easier way. WPS works only for wireless networks that use a password that is protected with the **Wifi Protected Access Personal (WPA)** or **Wifi Protected Access2 (WPA2)** Personal security protocols. WPS does not work on wireless networks that use the disfavoured Wired Equivalent Privacy (WEP) security, which can be cracked easily by any hacker with basic skills. 
An optional certification program based on a technology called Wi-Fi Protected SetupTM makes it easier to set up security-enabled Wi-Fi® networks in homes and small offices. Wi-Fi Protected Setup allows network configuration and security activation using well-known procedures (such as pressing a button or entering a PIN) that are accessible to most users.
In a standard setup, you can't connect a wireless device to a wireless network until you know the network name **(also named Service Set Identifier(SSID))** and its password (also called WPA-PSK key). If you want to connect a device, like your smartphone or a laptop, to your wireless network then on your device, you must first pick the network that you want to connect to and then enter its security password. 
![WPS](assets/222-9-660-fee20a154a.png)
WPS
## **What can WPS do?**
WPS can sometimes simplify the connection process. Here’s how **WPS connections** can be performed: 
- First, click the WPS button on your router to turn on the discovery of new devices. Then select the network you want to connect to on your device. The device is automatically connected to the wireless network without entering the network password.
- Devices like wireless printers or range extenders have their own WPS button that can be used for making quick connections. These devices can be connected to a wireless network by pressing the WPS button on the router and then on those devices. There is no need to input any data during this process. WPS automatically sends the network password, and these devices remember it for future use. The devices will be able to connect to the same network in the future without using the WPS button again.
- A third method involves the use of an eight-digit PIN. All routers with WPS enabled to have a PIN code that is generated automatically and cannot be configured by the users. This PIN can be found on the WPS configuration page on your router. Some devices are without a WPS button but with WPS support they ask for that PIN. If the pin is entered, they authenticate themselves and connect to the wireless network.
- The last method also involves using an eight-digit PIN. Some devices without a WPS button but with WPS support generate a client PIN. This PIN can be entered in your router's wireless configuration panels, and then the router will use it to add that device to the network.
The first two methods are fast but the last two methods do not provide any benefits regarding the time it takes to connect devices to your wireless network. The **eight-digit PIN** needs to be typed and typing the wireless network password is just slow. The fourth method of connecting to a wireless network is even slower because the router's wireless configuration section needs to be accessed and the PIN is to be typed provided by the client device. 
## WPS Operation Method
- **Push Button**: WPS capability requires the pressing of buttons located on the rear of the router and client devices. Some routers and devices have virtualized features that require activation through software on the individual devices. The device connects automatically without a password once the buttons are enabled.
- **PIN:**  The access point or client device must be entered with the PIN found on the sticker that is adhered to the access point. Certain routers provide an instant PIN as soon as the device is connected, which can be used to enter the network. Devices that do not support WPS but do support the protocol use the immediate PIN feature.
- **Network Feild Communication:** To allow Near Field Communication (NFC) between a client device and an access point, the client device must be brought very close to the access point. The gadget is linked to the network and authenticated using a near field communicator. Support is offered on an optional basis. This is an out-of-band technique where the channel transfers data directly without utilising WPS.
- **USB:** Data is sent between the new device that has to be connected and the access point using a USB flash drive. Although this mode is deprecated, optional support is still offered.
## **Advantages of WPS**
- WPS configures the network name [(SSID)](https://www.geeksforgeeks.org/computer-networks/ssid-full-form/) and WPA security key automatically for the access point having WPS enabled on the network.
- SSID security key or passphrase need not be known when connecting WPS-enabled devices.
- WPS keys are randomly generated so no one can guess or figure out your security key or passphrase.
- Long sequences of hexadecimal codes or passphrases need not be entered.
- Extensible Authentication Protocol (EAP) is used to securely exchange information and network credentials over the air, which is one of the authentication protocols used in WPA2.
- The less predictable and randomly generated key reduces the possibility of a network breach.
- removes the requirement to input a complex passphrase in hexadecimal.
- Sensitive data can be transmitted securely with WPS thanks to the introduction of [Extensible Authentication Protocol (EAP)](https://www.geeksforgeeks.org/computer-networks/wireless-security-part-2/) in WPA2 encryption.
## **Disadvantages of WPS**
- Network mode where wireless devices are communicated directly to each other without an access point is not supported by WPS.
- The WPS cannot be used if WiFi devices on the network are not WPS certified or WPS-compatible.
- It is very difficult to add a non-WPS client device to the network as long sequences of hexadecimal characters are generated by the WPS technology.
- The increased security offered by WPS is not available to devices that are not certified for WPS.
- The user will need to manually enter the lengthy hexadecimal passphrase on non-WPS devices.
- "Ad Hoc" connections, which let devices talk to each other directly, are not supported by WPS. Every connection needs to travel via the AP.
- WPS is still a relatively new technology, so not all devices support it.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/wifi-protected-setup-wps/)

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
