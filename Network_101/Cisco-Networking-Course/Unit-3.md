## Module 8-10:

### 1.  IPv4 addresses:
- 32-bit (4 octets x 8 bits) long.
- IPv4 addresses are logical addresses and are assigned to host network interfaces as needed.
- IPv4 addressing is hierarchical and each IPv4 address is made up of two parts, the network number (or network address) and the host number.
- IPv4 addresses are used both on local networks and on the internet.

## 2. IPv4 Unicast, Broadcast, and Multicast:
> Unicast is one-to-one communication, Broadcast is one-to-all, and Multicast is one-to-a-group.
- `Unicast: from one sender to one specific receiver.` eg. 192.168.1.1
- `Broadcast: from one sender to all possible receivers within the network.` eg. 192.168.1.0/24: 192.168.1.255 (all the Host Bits = 1)
- `Multicast: from one sender to a selected group of receivers.` eg. `224.0. 0.0 through 239.255. 255.255.`

## Note:
```
Unicast communication can occur within the local network or across different networks if routers are involved.
Broadcast communication is confined to the local network and is not typically forwarded by routers to other networks.
Multicast communication may be contained within a network or may be routed across networks if multicast routing is configured.
```

## 3. Private IPv4 Addresses and Network Address Translation (NAT):
- Most internal networks, from large enterprises to home networks, use `private IPv4 addresses for addressing all internal devices (intranet)` including hosts and routers. However, private addresses are not globally routable.
- Packets with a private address must be filtered (discarded) or translated to a public address before forwarding the packet to an ISP.
> NAT is used to translate between private IPv4 and public IPv4 addresses. This is usually done on the router.
- Private IPs `10.x.x.x // 172.16.x.x // 192.168.x.x`
- ![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/a0d8ddd9-db96-4b02-84d2-21cca75cc183)

## 4. Loopback addresses: `(127.0.0.0 /8 or 127.0.0.1 to 127.255.255.254) `
- More commonly identified as only 127.0.0.1. These are special addresses `used by a host to direct traffic to itself.`
- Link-local addresses (169.254.0.0 /16 or 169.254.0.1 to 169.254.255.254) are more commonly known as the Automatic Private IP Addressing (APIPA) addresses or self-assigned addresses.

## 5: Assignment of IP Addresses:
- Both IPv4 and IPv6 addresses are managed by the Internet Assigned Numbers Authority (IANA).
- The IANA manages and allocates blocks of IP addresses to the Regional Internet Registries (RIRs). 
```
AfriNIC (African Network Information Centre) - Africa Region
APNIC (Asia Pacific Network Information Centre) - Asia/Pacific Region
ARIN (American Registry for Internet Numbers) - North America Region
LACNIC (Regional Latin-American and Caribbean IP Address Registry) - Latin America and some Caribbean Islands
RIPE NCC (Réseaux IP Européens Network Coordination Centre) - Europe, the Middle East, and Central Asia
```

## 6: Broadcast, ARP:
- Broadcast messages will be communicated to all the Devices connected to the same network, `Routers don't forward broadcast packets to other networks & devices.`
- In an Ethernet LAN, devices use broadcasts and the Address Resolution Protocol (ARP) to locate other devices.


## 7: Dynamic Host Configuration Protocol (DHCP):
- `Automatically assigning IP addresses and other network configuration information to the new device` as soon as they connect to the network.
- `DHCP client: A new device joins a network`
- `DHCP server responds with an IP address` and related configuration details.
- The DHCP client sends a DHCP Discover message to the network to find a DHCP server.
```
DHCP servers are often implemented on network servers or dedicated networking equipment such as routers, switches, or specialized DHCP server devices.

DHCP clients are the end devices (computers, smartphones, printers, etc.) that request network configuration information from DHCP servers.
```

> when DHCP fails: Range: 169.254.0.1 to 169.254.255.254, Assigned automatically by the device.

## 8: Subnet AKA network in an IP address (Network & Host).
- In CIDR notation, 10.

## 9:  Other Info:
- All of the five RIRs, ARIN, APNIC, LACNIC, AfriNIC, and RIPE NCC have exhausted their IPv4 address pools.
- Only dual stack uses native IPv6 connectivity.

## 10: IPv6: `128 bits` `16 x 8 = 128 Bits`
- IPv6 addresses are represented using hexadecimal numbers eg. `0 1 2 3 4 5 6 7 8 9 A B C D E F`
- 16-bit Segments or Hextets & Every four bits is represented by a single hexadecimal digit; for a total of 32 hexadecimal values
- IPv6 addresses are not case-sensitive and can be written in either lowercase or uppercase.
- The tunneling migration technique encapsulates an IPv6 packet inside an IPv4 packet.
- 

 
> Rules:
> Leading Zero can be removed eg. 0001 can be written as 1
> Two consecutive Zeros can be represented as :: but contiguous string of hextets containing all zeroes with a double colon, which can only be used one time.

![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/2ef30f7f-bf34-46a5-9b93-4236a8786426)
![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/e9c340ec-1c32-4e30-b8c2-10111be223ea)

Eg:
- ![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/c1251839-15d3-4ede-b323-eadaf8e030e3)


## 11: Static and Dynamic Addressing:
### Static IPv4 Address Assignment:
- IPv4 addresses can be assigned either statically or dynamically, It requires IP Address, Subnet Mask, Default Gateway.
### Dynamic IPv4 Address Assignment:
- DHCP automatically assigns addressing information such as IPv4 address, subnet mask, default gateway, and other configuration information.
- Preferred method of assigning IPv4 addresses to hosts on large networks because it reduces the burden on network support staff and virtually eliminates entry errors.

> Note: Which destination IPv4 address does a DHCPv4 client use to send the initial DHCP Discover packet when the client is looking for a DHCP server? - Broadcast IP Address (255.255.255.255) because Client doesn't know the DHCP Server.

### DHCP Packets:
- ![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/f7ac4d34-8852-4299-bea4-b521bba7ed0c)

### Working:
1. A client initiating a message to find a DHCP server.	`DHCPDISCOVER`
2. A DHCP server responding to the initial request by a client.	`DHCPOFFER`
3. The Client accepts the IP address provided by the DHCP server.	`DHCPREQUEST` broadcast message.
4. The DHCP server confirms that the address lease has been accepted	`DHCPACK` unicast message.


## 12: 







