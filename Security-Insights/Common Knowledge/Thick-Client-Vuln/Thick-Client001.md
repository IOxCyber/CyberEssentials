## Thick Client: [i](https://www.cyberark.com/resources/threat-research-blog/thick-client-penetration-testing-methodology)
- A thick client (or fat client) is a type of client-server architecture where the client (end-user device) performs the bulk of processing tasks.
- It is typically installed with software that can operate independently of the central server. Common examples include desktop applications like Microsoft Word or Adobe Photoshop.
- Thick client pen-testing involves both local and server-side processing and often uses proprietary protocols for communication. [i](https://wiki.owasp.org/index.php/OWASP_Windows_Binary_Executable_Files_Security_Checks_Project)
- ![image](https://github.com/user-attachments/assets/ad1715b7-dca3-4eb0-8173-9cc00c2c88da)

## Common Architectures:
1. Two-Tier architecture: `Client App <-> Database Server`
- The application is installed on the client computer and will need to communicate with a database server.
- ![image](https://github.com/user-attachments/assets/6203a3ea-e246-4aeb-9385-5e937516e656)


2. Three-Tier architecture: `Client App <-> Application Server <-> Database Server`
- Three-tier architecture has a security advantage over two-tier architecture because it prevents the end-user from communicating directly with the database server.
- ![image](https://github.com/user-attachments/assets/93ce601a-394a-4bf5-989d-fdd1a6d3e0ed)

> Web Server: Serves Static Contents && App Server: Serves Dynamic Contents, interacts with DB Server. && DB Server: Serves DB content. `Web Server <-> App Server <-> DB Server`

## How to test thick client applications:
- `Thick client applications are generally more complicated and customized than web or mobile applications`
```XML
Discovering what technologies are being used on both the client and the server sides.
Figuring out the application’s functionality and behavior.
Identifying all of the different entry points for user input.
Understanding the core security mechanisms used by the application.
Identifying common vulnerabilities like languages and frameworks.
```

1. Information Gathering: Application Architecture and Identifying the Languages and Frameworks Used.
- ![image](https://github.com/user-attachments/assets/ee5d28e8-ab9c-429f-8be5-7f8265ce90a9)
- NET decompilers and deobfuscators tools:
- ![image](https://github.com/user-attachments/assets/254d8304-40b6-4c37-9816-1f26be761730)

2. Network Communication Between the Client and the Server
- ![image](https://github.com/user-attachments/assets/8e6319db-6b09-48c3-9e4f-db139577e4bc)
- Proxy Tools:
- ![image](https://github.com/user-attachments/assets/9d0775e1-e137-4b57-97c2-4e34de33402d)


# DVTA [Vulnerable Thick Client Application for testing](https://github.com/srini0x00/dvta)
# DVJA [Java Based](https://github.com/appsecco/dvja)
