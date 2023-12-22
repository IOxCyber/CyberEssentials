# Module 12-15:

## Gateway `Default Gateway: Router's IP address`
- Forwarding traffic/packets from the Local network(Instranet) to Remote location `Network`.
- This router IP address can be either statically configured on the host or received dynamically by DHCP.
- The wireless `router serves as the boundary between the local internal network and the external internet.`
![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/c62df6c3-1885-4677-9aba-7012aee7f30d)
![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/5e8321fe-7e65-404d-9afe-409a04fb70f7)

## Network Address Translation:
- `Translate the Private IP address to the Public IP Address` to travel the Packet from the Intranet to the Internet.
- With NAT, a private (local) source IPv4 address is translated to a public (global) address. The process is reversed for incoming packets.

## The ARP Process: `Address Resolution Protocol`
- `ARP Table: IP to MAC Address Mapping`, AKA ARP Cache & learnt from ARP Request.
- Two primary addresses assigned to a device on an Ethernet LAN:
- - Physical address (the MAC address) – Used for NIC-to-NIC communications on the same Ethernet network.
- - Logical address (the IP address) – Used to send the packet from the source device to the destination device. The destination IP address may be on the same IP network as the source, or it may be on a remote network.
- **Note**:
> ARP requests rely on broadcast frames to deliver the requests.
> 
> A host will send an ARP request to determine the MAC address of another device.
> 
```
ARP Process:

1. The sending host creates and sends a frame addressed to a broadcast MAC address. Contained in the frame is a message with the IPv4 address of the intended destination host.
2. Each host on the network receives the broadcast frame and compares the IPv4 address inside the message with its configured IPv4 address. The host with the matching IPv4 address sends its MAC address back to the original sending host.
3. The sending host receives the message and stores the MAC address and IPv4 address information in a table called an ARP table.
```

### To determine the MAC address of a known destination device IP address:
- Address Resolution Protocol (ARP) for known destination device IPv4 address.
- Neighbor Discovery (ND) for known destination device IPv6 address.

## Broadcast Domain:
- Routers are used to divide the network into multiple broadcast domains.
![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/1901370f-1ab8-4af9-8523-32d7c3270e34)
- The destination MAC address for an Ethernet broadcast is `FFFF.FFFF.FFFF`



