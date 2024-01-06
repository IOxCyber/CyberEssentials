## 3 Way Handshaking: `Process by which two devices establish a connection before they can exchange data using TCP Protocol.`

- ![image](https://github.com/IOxCyber/CyberEssentials/assets/40174034/2fb1fb3f-0864-4142-8d34-eb5d407b9d2f)

## Step 1: SYN (Synchronize)
- Initiator (Client): The client sends a TCP packet with the SYN (synchronize) flag set to the server.
- Purpose: The client initiates the connection request and indicates its intention to establish a connection.

## Step 2: SYN-ACK (Synchronize-Acknowledge)
- Responder (Server): If the server is available and willing to establish a connection, it responds with a TCP packet containing both the SYN and ACK (acknowledge) flags set.
- Purpose: The server acknowledges the client's SYN request and signals its readiness to establish a connection.

## 3. Step 3: ACK (Acknowledge)
- Initiator (Client): The client sends an ACK packet back to the server.
- Purpose: The client acknowledges the server's response, and the connection is established.

## TCP Handshake Summary:
- SYN (Client to Server): Initiate the connection.
- SYN-ACK (Server to Client): Acknowledge the connection request and signal readiness.
- ACK (Client to Server): Confirm acknowledgment, establishing the connection.

```
All the Communication takes place in a TCP Packet:

Client                        Server
  |-------- SYN (Seq=x) ------->|
  |<----SYN(Seq=y) ACK(Y+1)-----|
  |---------- ACK (Y+1)-------->|
  |                             |  Connection Established
```

> Note:  The client sends the first flag (SYN) during the TCP three-way handshake, it shares the initial sequence number, the initial window size, and optionally, the MSS and other TCP options.


