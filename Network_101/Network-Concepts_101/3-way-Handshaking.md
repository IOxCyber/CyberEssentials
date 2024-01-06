## 3 Way Handshaking:

## Step 1: SYN (Synchronize)
- Initiator (Client): The client sends a TCP packet with the SYN (synchronize) flag set to the server.
- Purpose: The client initiates the connection request and indicates its intention to establish a connection.

## Step 2: SYN-ACK (Synchronize-Acknowledge)
- Responder (Server): If the server is available and willing to establish a connection, it responds with a TCP packet containing both the SYN and ACK (acknowledge) flags set.
- Purpose: The server acknowledges the client's SYN request and signals its readiness to establish a connection.

## 3. Step 3: ACK (Acknowledge)
- Initiator (Client): The client sends an ACK packet back to the server.
- Purpose: The client acknowledges the server's response, and the connection is established.

