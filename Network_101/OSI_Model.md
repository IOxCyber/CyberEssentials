OSI Model:
- Only conceptual/reference model to provide the interoperation & communication between different type of devices such as Linux, Windows, Mac
- The Open Systems Interconnection (OSI) model describes seven layers that computer systems use to communicate over a network.
- Conceptual model that 'provides a common basis for the coordination of ISO standards development for the purpose of systems interconnection'.

### To Remember: All People Seem To Need Data Processing. (APSTNDP)

**The Layers (Up to Down) as per Sender's POV**

## 1. Layer 1, the Application Layer: 
- **used by end-user software such as web browsers** and email clients.
- works at the user end to interact with user applications, QoS (quality of service), file transfer and email are the major popular services of the application layer.
- HTTP, SMTP, DHCP, FTP, Telnet, SNMP and SMPP.

## 2. Layer 2, the Presentation Layer: 
- prepares data for the application layer. It defines how two devices should **encode, encrypt, and compress data** so it is received correctly on the other end.
- encryption and decryption happens here.
- ensures that data is transferred in standardized formats by converting data formats into a format readable by the application layer.
- **XDR, TLS, SSL and MIME**

## 3. Layer 3, the Session Layer: 
- creates communication channels, called sessions, between source and the destination.
- responsible for opening sessions, ensuring they remain open and functional while data is being transferred, and closing them when communication ends.
- also set checkpoints during a data transfer—if the session is interrupted, devices can resume data transfer from the last checkpoint.
- PPTP, SAP, L2TP and NetBIOS.


## 4. Layer 4, the Transport Layer: 
- takes data transferred in the session layer and breaks it into “segments” on the transmitting end.
- responsible for reassembling the segments on the receiving end, turning it back into data that can be used by the session layer.
- carries out flow control, sending data at a rate that matches the connection speed of the receiving device
- provides error control, checking if data was received incorrectly and if not, requesting it again.
- Transmission Control Protocol **(TCP), UDP, SPX, DCCP and SCTP**.

## 5. Layer 5, the Network Layer: 
- breaking up segments into network packets on sender side and reassembling the packets on the receiving end.
- routing packets by discovering the best path across a physical network.
- **Internet Protocol (IPv4), Internet Protocol (IPv6), IPX, AppleTalk, ICMP, IPSec and IGMP.**

## 6. Layer 6, the Data Link Layer: 
- breaks up packets into frames and sends them from source to destination. two parts...
- Logical Link Control (LLC), which identifies network protocols, **performs error checking and synchronizes frames** by adding headers to data packets.
- Media Access Control (MAC) which **uses MAC addresses to connect devices and define permissions to transmit and receive data**.
- The protocols are used by the Data Link Layer include: ARP, CSLIP, HDLC, IEEE.802.3, PPP, X-25, SLIP, ATM, SDLS and PLIP.

## 7. Layer 7, the Physical Layer: 
- **responsible for the physical cable or wireless connection** between network nodes.
- responsible for transmission of the raw data, which is simply a series of 0s and 1s.
- e.g. **optical fiber, coaxial cable, wireless**, etc.
- major protocols used by this layer include Bluetooth, PON, OTN, DSL, IEEE.802.11, IEEE.802.3, L431 and TIA 449.


## Diagram:
<img width="642" alt="image" src="https://user-images.githubusercontent.com/40174034/216824373-7682eb5a-00b3-4a82-b9ae-db7f377a337f.png">
<img width="391" alt="image" src="https://user-images.githubusercontent.com/40174034/216824781-f5b20236-8e68-496d-aecf-7e95b7403074.png">

[More Defination](https://www.guru99.com/layers-of-osi-model.html)

# TCP/IP vs OSI:
<img width="510" alt="image" src="https://user-images.githubusercontent.com/40174034/216825514-c0fda9b9-41d4-4cb0-8712-09e37c78bc42.png">

