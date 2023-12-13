## Module 8-10:

1.  IPv4 addresses:
- 32-bit (4 octets) long.
- IPv4 addresses are logical addresses and are assigned to host network interfaces as needed.
- IPv4 addressing is hierarchical and each IPv4 address is made up of two parts, the network number (or network address) and the host number.
- IPv4 addresses are used both on local networks and on the internet.

2. IPv4 Unicast, Broadcast, and Multicast:
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

3. 
