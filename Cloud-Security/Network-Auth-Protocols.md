# Network Authentication Protocols:
- `specifically address the authentication needs within a network` for verifying the identity of entities (users or devices) attempting `to access network resources or services.`
- `Authentication Process involves mechanisms such as challenge-response, digital certificates, or tokens.`
- Have Network Scope such LAN, WAN etc.
- eg. Kerberos, RADIUS, TACACS+, EAP (used in wireless networks), and CHAP (used in PPP connections)

> Authentication protocols (broader sense) `authenticate entities beyond network environments, including web applications, APIs, operating systems, and distributed systems`.

### 1. Kerberos:
- a `network authentication protocol` that uses `symmetric key cryptography` and operates based on the concept of `trusted third-party authentication`.
- Kerberos Server or Key Distribution Center - KDC is a `central server that stores authentication information (database)`, two components: `the Authentication Server (AS) and the Ticket-Granting Server (TGS).`
- An `admin creates user accounts in the Kerberos database` for each user & typically specifies the `user's username, password, and other relevant attributes.`
- used by Microsoft Active Directory (AD), Apache Hadoop

### 2. RADIUS (Remote Authentication Dial-In User Service):
- authentication, authorization, and accounting `AAA protocol commonly used for remote access authentication in network systems.`
- used by VPN solutions and wireless access points, NAC( eg. Cisco Identity Services Engine (ISE) and Aruba ClearPass), ISPs.

### 3. TACACS+ (Terminal Access Controller Access Control System Plus):
- `an authentication, authorization, and accounting protocol used for network device administration.`
- authorize access to network devices like `routers, switches, and firewalls`
- used by Cisco ASA firewalls and F5 BIG-IP load balancers.

### 4. EAP (Extensible Authentication Protocol):
- commonly used in `wireless networks and Point-to-Point Protocol (PPP) connections.`

### 5. CHAP (Challenge-Handshake Authentication Protocol):
- used primarily for Point-to-Point Protocol (PPP).
- use a challenge-response mechanism.
  
### 6. LDAP (Lightweight Directory Access Protocol): 
- While primarily a directory access protocol, LDAP also supports authentication.
