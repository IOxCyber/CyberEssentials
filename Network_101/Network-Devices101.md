# Network-Devices

## How a packet/text/message flows from a LAN (Ethernet) to another. `Modem > router > Switch`

### 1. Modem: `converts digital data from your computer into analog signals`.
- A Modem (short for Modulator-Demodulator) is a device that modulates and demodulates analog signals, allowing digital devices to transmit and receive data over analog communication lines, such as telephone lines or cable systems.

### 2. Router: `connects different networks together and directs data traffic between them.`
- The router manages the flow of data within your local network and between the local network and the external network (e.g., the internet).
- It uses Network Address Translation (NAT) to map local IP addresses to a single public IP address provided by the ISP.

### 3. Switch: `A device that connects devices within the same local network and uses MAC addresses to forward data only to the intended device.`
- A switch `builds a MAC address table by inspecting incoming Layer 2 frames and recording the source MAC address & incoming Port found in the frame header.
- Every frame that enters a switch is checked for new information to learn. It does this by examining the source MAC address of the frame and port number where the frame entered the switch:
- `If the source MAC address does not exist in the MAC address table, the MAC address and incoming port number are added to the table.`
- When SW1 has an empty MAC address table and receives a frame from PCA to PCC, it broadcasts the frame to all ports (flooding), allowing SW1 to learn PCC's location by updating its table when PCC receives the frame. Future frames to PCC are then efficiently forwarded based on the learned information.

![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/e5d10ded-68d7-41a8-82ea-16e9d0717990)
First, the User sends it > It goes to Switch > then It goes to Router > then another router > then Recived at another User end.

## Other Devices
1. Router: Device that connects two or more packet-switched networks or subnetworks. manage traffic between WAN & LAN by forwarding data packets to intended IP addresses, and allowing multiple devices to use the same Internet connection.
2. Hubs: quick but indiscriminate; when it receives a data packet, it will copy it and send it to every device connected to it.
3. Switches: Slower but responsible; when it receives a data packet, it determines & send the data only to intended devices.
4. Gateway: Default Gateway is router IP.
5. Hop: It refers to the *number of routers* that a packet passes through from its source to its destination, By which we can determine if the device in Same network or not.
