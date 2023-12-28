# Module 15-17:

## TCP & UDP:
- Transmission Control Protocol: Ack of the receipt of packets & their sequence.
- User Datagram Protocol: No Ack & Sequence Number.

> Note: The transport layer in both the TCP/IP and OSI models is responsible for ensuring packets are sent reliably and any missing packets are resent.

## Port Number:
- Every message that a host sends contains both a source and destination port.
![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/475298f8-7610-43db-b54a-af4447cecbab)
- Ports are assigned and managed by an organization known as the Internet Corporation for Assigned Names and Numbers (ICANN).
- Ports are broken into three categories and range in number from `1 to 65,535:`
- `Well-Known Ports` - `Destination ports` that are used with common network applications are identified as well-known ports. These ports are in the range of 1 to 1023.
- `Registered Ports` - Ports 1024 through 49151 can be `used as either source or destination ports`. These can be used by organizations to register specific applications such as IM applications.
- `Private Ports` - Ports 49152 through 65535 are often `used as source ports`. These ports can be used by any application.

## Sockets:
- The combination of the source IP address and source port number, or the destination IP address and destination port number is known as a socket.
- The socket is used to identify the server and service being requested by the client.
- A client socket might look like this, with 1099 representing
- - the source port number: 192.168.1.5:1099
- - The socket on a web server might be 192.168.1.7:80
 
## 
