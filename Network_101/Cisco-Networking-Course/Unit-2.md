# TCP/IP Addressing Related.
## Module 5-7:

## 1. TCP/IP Model: `Protocol Model`
![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/8a2c282d-d03a-4912-8d23-6bc2aeb756df)

## 2. OSI Model: `Reference Model`
![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/3212eb9a-0af7-44d1-a617-38c2d71eefe8)

## 3. Ethernet Frame: `Solely used in LAN for communication`
- Ethernet is a technology commonly used in local area networks for communication. Devices access the Ethernet LAN using an Ethernet Network Interface Card (NIC). Each Ethernet NIC has a unique address permanently embedded on the card known as a Media Access Control (MAC) address. The MAC address for both the source and destination are fields in an Ethernet frame.
- `Ethernet frame can carry 46 to 1500 bytes of user data`. During the encapsulation process, other fields are added, such as destination MAC address, source MAC address, and FCS. The size of Ethernet frames is normally limited to a maximum of 1518 bytes and a minimum of 64 bytes.

![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/0be93456-ef9b-401d-a607-582a5a6b2c36)

**Note**: `Data is encapsulated Data which is IPv4 / IPv6 Packet.`

![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/066ae353-71fc-4341-b2f5-6ac52f87b2fa)

## 4. IP Packet Structure:
An IP packet consists of a header and a data payload. The IP header contains various fields that provide necessary information for routing and delivery. Here is a breakdown of the key fields within the IP header:
```
Version (4 bits):
Identifies the version of the IP protocol in use. For example, IPv4 uses version 4.

Header Length (4 bits):
Specifies the length of the IP header in 32-bit words.

Type of Service (8 bits):
Includes fields for Differentiated Services Code Point (DSCP) and Explicit Congestion Notification (ECN), allowing for quality of service and congestion management.

Total Length (16 bits):
Represents the total length of the IP packet, including both the header and the data.

Identification (16 bits), Flags (3 bits), Fragmentation Offset (13 bits):
Used for fragmentation and reassembly of IP packets if needed.

Time-to-Live (TTL) (8 bits):
Indicates the maximum number of hops the packet can take before being discarded.

Protocol (8 bits):
Identifies the higher-layer protocol (e.g., TCP, UDP) used in the data part of the IP packet.

Header Checksum (16 bits):
Ensures the integrity of the IP header during transmission.

Source IP Address (32 bits) and Destination IP Address (32 bits):
Specify the source and destination devices' IP addresses, respectively.

Options (Variable Length):
May include additional information or instructions related to the IP packet.

Padding (Variable Length):
Added to ensure that the total length of the IP header is a multiple of 32 bits.

Data (Payload):
Carries the actual data being transmitted. The size and format of the data part depend on the higher-layer protocol identified in the "Protocol" field.
```
![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/bb194251-2f8d-4a11-aabb-a175aee92325)
![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/e3e97d57-6423-4f48-bcfa-cbb6ad826f8b)
`4 Bytes x 6 = 24 Headers Bytes`
`Data Varies the Size`


## 5. In an Ethernet network, each NIC in the network checks every arriving frame to see if the destination MAC address in the frame matches its own MAC address. If there is no match, the device discards the frame. If there is a match, the NIC passes the frame up to the next OSI layer.

## 6. Protocol function to the description while taking into consideration that a network client is visiting a web site.
![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/fb943811-8895-435c-9ee0-7df3fdaf652e)

## 7. Notes:
- `Fiber optic cables themselves are immune to electromagnetic interference (EMI)` due to their optical nature.
- A `backbone network (or network backbone) is a central infrastructure` that connects multiple smaller networks or network segments within an organization or across multiple locations.


