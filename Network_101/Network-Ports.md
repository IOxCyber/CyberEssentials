## Port:
- Ports are essential components that allow communication between different applications and services on a device or across a network.
- Ports are identified by numbers and are used to direct network traffic to specific processes or services running on a device.

## Port Range:
- 0 to 1023 (Well-Known Ports) eg. Specific Ports for specific usage.
- 1024 to 49151 (Registered Ports) eg. not assigned or controlled, but can be registered to prevent duplication 
- 49152 to 65535 (Dynamic Ports) eg. used for temporary or private ports


> `0 - 65535 (Can be of TCP & UDP separately)`
> `One port can be used by TCP & UDP at the same time.`

## Common Ports & Services:
- `HTTP (Hypertext Transfer Protocol) - Port 80`: for web browsing
- `HTTPS (Hypertext Transfer Protocol Secure) - Port 443`: With an added layer of security using SSL/TLS encryption for secure web browsing and data transfer.
- `SSH (Secure Shell) - Port 22`: provides a secure way to access and manage remote devices or servers over a network.
- `FTP (File Transfer Protocol) - Ports 20 and 21`: Port 21 is used for command and control, while port 20 is used for data transfer.
- `SMTP (Simple Mail Transfer Protocol) - Port 25`: SMTP is used for sending outgoing email messages from an email client to the mail server.
- `POP3 (Post Office Protocol 3) - Port 110`: POP3 is used for retrieving incoming email messages from a mail server to an email client.
- `IMAP (Internet Message Access Protocol) - Port 143 & Secure (993)`: Unlike POP3, IMAP retains messages on the server, making it more suitable for accessing emails from multiple devices.
- `DNS (Domain Name System) - Port 53`: DNS is responsible for translating human-readable domain names into IP addresses. Used for Query & Response.
- `RDP (Remote Desktop Protocol) - Port 3389`: RDP is a proprietary protocol developed by Microsoft that allows users to access and control a remote computer over a network.
- `NTP (Network Time Protocol) - Port 123`: NTP is used for time synchronization between devices on a network, ensuring accurate timekeeping.

## Other Useful Ports:
- `ICMP (Internet Control Message Protocol): ping requests and responses`: Not associated with a specific port number, used for network troubleshooting, error reporting, and diagnostic messages.
- `LDAP (Lightweight Directory Access Protocol) - Port 389`: LDAP is used for accessing and maintaining distributed directory information services, such as a company's directory of users and resources.
- `LDAPS (LDAP Secure) - Port 636`: LDAPS is a secure version of LDAP that uses SSL/TLS encryption for secure communication.
- `SMB (Server Message Block) - Ports 137-139 and 445`: SMB is a file and printer sharing protocol used mainly by Windows devices for accessing shared resources over a network. Ports 137-139 are used for NetBIOS over TCP/IP, and port 445 is used for SMB over TCP.
- `Remote PowerShell - Port 5985`: This port is used for remote PowerShell sessions in Windows environments, allowing administrators to manage remote systems.
- `NFS (Network File System) - Port 2049`: NFS is a protocol used for sharing files and directories between UNIX-like systems over a network.



