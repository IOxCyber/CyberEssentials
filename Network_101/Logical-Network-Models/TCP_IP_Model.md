## TCP/IP model: `ATIN` or `ATID` `Protocol Model`
- Transmission Control Protocol/Internet Protocol and is a suite of communication protocols used to interconnect network devices on the internet.

1. Application Layer: `Session & Representation`
- This layer performs the functions of the top three layers of the OSI model, i.e., Application, Presentation, and Session Layer. 
- `Responsible for node-to-node communication/session and controls user-interface` specifications.
```
::Protocols::
HTTP: Hypertext Transfer Protocol is used for communication between web browsers and web servers, enabling the retrieval and display of web pages.
FTP: File Transfer Protocol is used for transferring files between computers over a network.
SMTP: Simple Mail Transfer Protocol is used for sending and receiving email messages.
DNS: Domain Name System is used for translating domain names (e.g., www.example.com) into IP addresses.
SSH: Secure Shell is used for secure remote login and command execution on networked devices.
Telnet: Telnet allows remote access and allows text communication on networked devices.
SNMP: Simple Network Management Protocol is used for network management and monitoring of devices.
DHCP: Dynamic Host Configuration Protocol is used for automatic IP address assignment to devices in a network.
POP: Post Office Protocol is used for retrieving email from a mail server.
IMAP: Internet Message Access Protocol is used for accessing and managing email messages on a remote mail server, used by Microsoft Outlook,apple Mail.
SNTP: Simple Network Time Protocol is used for time synchronization in networked devices.
NFS: Network File System allows file sharing between computers in a network.
RTSP: Real-Time Streaming Protocol is used for streaming multimedia content over the internet.
```

2. Transport/Host-to-Host Layer: `Transmission Control of Data`
- `Responsible for establishing and terminating connections between devices.`
- `Specifies how much data should be sent, when, and where at what rate`
- `Also responsible for formatting, compressing, and encrypting data for transmission, segments data into smaller units and adds necessary headers for delivery.`
```
::Protocols::
TCP: Transmission Control Protocol provides reliable, connection-oriented data delivery, commonly used for applications that require guaranteed delivery, such as web browsing, file transfer, and email.
UDP: User Datagram Protocol provides a connectionless, lightweight transport service, commonly used for real-time applications, streaming media, online gaming, and DNS.
```

3. Internet Layer: `Addressing & Routing`
- `Responsible for addressing and routing packets based on IP addresses`
```
::Protocols::
IP: Internet Protocol is the foundation of internet communication and is responsible for addressing and routing packets across networks.
ICMP: Internet Control Message Protocol is used for diagnostic and error reporting purposes, such as ping and traceroute.
ARP: Address Resolution Protocol is used for mapping IP addresses to physical MAC addresses in local networks.
IGMP: Internet Group Management Protocol is used for managing multicast group memberships.
IPv6: IPv6 is the next-generation internet protocol that provides a larger address space and improved features compared to IPv4.
``` 

4. Network Access Layer/Data Link Layer: `Physical Medium`
- Network access or Link layer `specifies the physical transmission of data over the network.`
- It also determines how bits should be optically signaled by hardware devices that interface directly with a network media such as coaxial, optical, fiber, or twisted-pair cables.
```
::Protocols::
Ethernet: Ethernet is widely used for wired local area networks (LANs) in homes, offices, and data centers.
Wi-Fi: Wi-Fi is used for wireless communication in various settings, such as homes, offices, public places, and campuses.
PPP: Point-to-Point Protocol is used for establishing a direct connection between two nodes, commonly used in Broadbands.
ATM: Asynchronous Transfer Mode is used in telecommunications networks, including high-speed data transfers and voice and video transmission.
Frame Relay: Frame Relay is a WAN technology that provides connectivity between remote locations in a cost-effective manner.
```

## Devices Used (Virtual/Physical):
1. Network Interface Layer (Link Layer):
```
Ethernet Switches (Physical)
Network Interface Cards (NICs) (Physical)
Wireless Access Points (Physical)
Virtual Switches (Virtual)
```
2. Internet Layer:
```
Routers (Physical)
Layer 3 Switches (Physical)
Virtual Routers (Virtual)
```
3. Transport Layer:
```
Servers (Physical or Virtual)
Firewalls (Physical or Virtual)
Load Balancers (Physical or Virtual)
```
4. Application Layer:
```
Web Servers (Physical or Virtual)
Email Servers (Physical or Virtual)
DNS Servers (Physical or Virtual)
Proxy Servers (Physical or Virtual)
Client Devices (Physical or Virtual)
```

# TCP / IP
## Diagram
<img width="399" alt="image" src="https://user-images.githubusercontent.com/40174034/216824616-0ed899b3-c30a-4bff-93cf-52147fc70902.png">
<img width="321" alt="image" src="https://user-images.githubusercontent.com/40174034/216824860-2a2f4c5b-8ba7-4137-9141-b1eec2574271.png">

# TCP/IP vs OSI:
<img width="510" alt="image" src="https://user-images.githubusercontent.com/40174034/216825514-c0fda9b9-41d4-4cb0-8712-09e37c78bc42.png">
