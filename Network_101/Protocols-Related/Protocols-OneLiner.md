# Protocols based on OSI Model::

---

## 🎯 **Layer 7: Application Layer (A)**  
Handles user interaction and network services.

| **Protocol** | **Purpose/Usage** | **Port(s)** |
|--------------|-------------------|-------------|
| HTTP | Web traffic | 80 |
| HTTPS | Secure web traffic | 443 |
| FTP | File transfer (control) | 21 |
| FTPS | Secure file transfer | 990 |
| SFTP (via SSH) | Secure file transfer | 22 |
| SMTP | Email sending | 25 |
| SMTPS (with SSL/TLS) | Secure email sending | 465 |
| POP3 | Email retrieval | 110 |
| IMAP | Email retrieval with sync | 143 |
| IMAPS | Secure IMAP | 993 |
| DNS | Domain name resolution | 53 |
| DHCP | Dynamic IP assignment | 67, 68 |
| Telnet | Remote CLI access (insecure) | 23 |
| SSH | Secure remote access | 22 |
| RDP | Remote desktop access | 3389 |
| SNMP | Network management | 161, 162 |
| NTP | Time synchronization | 123 |
| LDAP | Directory services | 389 |
| LDAPS | Secure LDAP | 636 |
| SIP | VoIP signaling | 5060, 5061 |
| TFTP | Trivial file transfer | 69 |
| SMB | File sharing and access | 445 |
| MQTT | IoT messaging protocol | 1883, 8883 |

---

## 🎯 **Layer 6: Presentation Layer (P)**  
Ensures data format, encryption, and compression.

| **Protocol/Standard** | **Purpose/Usage** | **Port(s)** |
|-----------------------|-------------------|-------------|
| SSL/TLS | Encrypts and secures communication | 443 |
| ASCII/Unicode | Character encoding | N/A |
| JPEG/PNG/GIF | Image formats | N/A |
| MPEG/MP3/MP4 | Audio and video formats | N/A |
| XML/JSON | Data serialization | N/A |
| Base64 | Binary to ASCII encoding | N/A |
| X.509 | Digital certificate standard | N/A |

---

## 🎯 **Layer 5: Session Layer (S)**  
Manages sessions and connections between applications.

| **Protocol** | **Purpose/Usage** | **Port(s)** |
|--------------|-------------------|-------------|
| NetBIOS | LAN name resolution and session management | 137-139 |
| PPTP | VPN tunneling | 1723 |
| SIP | Manages VoIP and multimedia sessions | 5060, 5061 |
| RPC | Remote procedure calls | 135 |
| RTSP | Media streaming control | 554 |
| H.323 | Audio-visual communication | 1720 |
| SMB | File sharing and session management | 445 |
| SOCKS | Proxy protocol | 1080 |

---

## 🎯 **Layer 4: Transport Layer (T)**  
Handles end-to-end communication and data flow control.

| **Protocol** | **Purpose/Usage** | **Port(s)** |
|--------------|-------------------|-------------|
| TCP | Reliable, connection-oriented communication | Dynamic |
| UDP | Fast, connectionless communication | Dynamic |
| SCTP | VoIP and signaling reliability | Dynamic |
| DCCP | Datagram congestion control | Dynamic |

---

## 🎯 **Layer 3: Network Layer (N)**  
Routes data between devices and manages addressing.

| **Protocol** | **Purpose/Usage** | **Port(s)** |
|--------------|-------------------|-------------|
| IP (IPv4/IPv6) | Routing and addressing | N/A |
| ICMP | Error reporting and diagnostics | N/A |
| IGMP | Multicast group management | N/A |
| ARP/RARP | Resolves IP to MAC and vice versa | N/A |
| OSPF | Interior gateway protocol | 89 |
| BGP | Exterior gateway protocol | 179 |
| GRE | VPN tunneling protocol | 47 |

---

## 🎯 **Layer 2: Data Link Layer (D)**  
Provides node-to-node communication and MAC addressing.

| **Protocol/Standard** | **Purpose/Usage** | **Port(s)** |
|-----------------------|-------------------|-------------|
| Ethernet (IEEE 802.3) | LAN communication | N/A |
| PPP (Point-to-Point Protocol) | WAN communication | N/A |
| STP (Spanning Tree Protocol) | Prevents switching loops | N/A |
| LLDP | Device discovery | N/A |
| MAC | Media Access Control | N/A |
| VLAN | Virtual LAN segmentation | N/A |
| MPLS | Network traffic management | N/A |

---

## 🎯 **Layer 1: Physical Layer (P)**  
Handles physical transmission of raw data over media.

| **Protocol/Standard** | **Purpose/Usage** | **Port(s)** |
|-----------------------|-------------------|-------------|
| Ethernet (Physical) | Wired LAN communication | N/A |
| Wi-Fi (IEEE 802.11) | Wireless communication | N/A |
| Bluetooth (IEEE 802.15.1) | Wireless PAN communication | N/A |
| DSL/Fiber Optics | High-speed internet | N/A |
| RS-232 | Serial communication | N/A |
| Infrared/Zigbee | Short-range wireless communication | N/A |
| SONET/SDH | High-speed fiber-optic networks | N/A |

---

## 🎉 **Sorted with Mnemonic:**
👉 **APSTNDP**  
- **A:** Application Layer  
- **P:** Presentation Layer  
- **S:** Session Layer  
- **T:** Transport Layer  
- **N:** Network Layer  
- **D:** Data Link Layer  
- **P:** Physical Layer  
