# Module 15-17:

## TCP & UDP:
- Transmission Control Protocol: Ack of the receipt of packets & their sequence.
- User Datagram Protocol: No Ack & Sequence Number.

> Note: The transport layer in both the TCP/IP and OSI models is responsible for ensuring packets are sent reliably and any missing packets are resent.

## Port Number:
- Every message that a host sends contains both a source and destination port.
![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/475298f8-7610-43db-b54a-af4447cecbab)
- Ports are assigned and managed by an organization known as the Internet Corporation for Assigned Names and Numbers (ICANN).
- Port numbers help distinguish different services or applications running on a device. 
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
 
## Client-Server:
1. Server: `a host running a software application that provides information` or services to other hosts that are connected to the network.
2. Client: client software is a web browser, like Chrome or Firefox, Gmail, Spotify etc

## URL,URI, URN:
- URL: Uniform Resource Locator.
- URI: Uniform Resource Identifier.
- URN: Uniform Resource Name (URN)
![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/6431199a-009f-46b5-9648-8ffb27b0868b)

## Types of the Servers:
![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/bc66f337-0435-4d89-a65b-a52de8781de7)

## Application Protocols:
![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/53c6b505-c797-4d23-a452-7f85b89a6fae)
- Email clients connect to SMTP servers over port 25 to send email.
- POP and IMAP are used by clients to receive email.
- IMAP is a protocol for clients to retrieve copies of email messages from an IMAP server. The original messages remain on the server until manually deleted.

```
SMTP (Simple Mail Transfer Protocol):
Port Number: 25 (unencrypted), 587 (encrypted/TLS)

POP3 (Post Office Protocol version 3):
Port Number: 110 (unencrypted), 995 (encrypted/SSL)

IMAP (Internet Message Access Protocol):
Port Number: 143 (unencrypted), 993 (encrypted/SSL)
```
- The ping command is used to test connectivity from one network device to another network device.
- The tracert command is used to trace a route from the source network device to another network device.
- ipconfig/all can be used to display the IP configuration, gateway address and MAC address on a PC.
- The command ipconfig /renew will cause the computer to request a new IP address from the DHCP server.
- The command ipconfig /release will remove the current IP address but will not request a new address.
![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/98115c9c-227e-46e4-b047-460d64888af2)



## Addressing:
- Logical addresses/IP addresses are added at the network layer. 
- Physical addresses are added at the data link layer. 
- Port addresses are added at the transport layer.













