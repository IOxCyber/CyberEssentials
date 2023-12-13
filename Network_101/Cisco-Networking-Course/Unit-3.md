## Module 8-10:

### 1.  IPv4 addresses:
- 32-bit (4 octets) long.
- IPv4 addresses are logical addresses and are assigned to host network interfaces as needed.
- IPv4 addressing is hierarchical and each IPv4 address is made up of two parts, the network number (or network address) and the host number.
- IPv4 addresses are used both on local networks and on the internet.

## 2. IPv4 Unicast, Broadcast, and Multicast:
> Unicast is one-to-one communication, Broadcast is one-to-all, and Multicast is one-to-a-group.
- `Unicast: from one sender to one specific receiver.` eg. 192.168.1.1
- `Broadcast: from one sender to all possible receivers within the network.` eg. 192.168.1.0/24: 192.168.1.255 (all the Host Bits = 1)
- `Multicast: from one sender to a selected group of receivers.` eg. `224.0.1.1`

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

## 6: 






