# Reverse Shell vs. Bind Shell in Metasploit

## Reverse Shell: Attacker's VM opens Ports & Listen
- Type of `shell where the target machine connects back to the attacker's machine.`
- The target machine executes the payload and initiates a connection to the attacker's machine.
- The attacker listens for incoming connections on a specific port.
- Commonly `used when the target machine is behind a firewall or NAT`, making it difficult to connect directly to it.

## Bind Shell: Target's VM opens Ports & Listen
- Type of `shell where the target machine opens up a port and waits for the attacker to connect to it.`
- The target machine executes the payload and listens on a specific port.
- The attacker connects to the target machine’s listening port.
- Commonly `Useful when the attacker cannot set up a listener or if the target machine allows inbound connections.`

# Interview QnA:

