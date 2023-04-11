## The Metasploit DB:
- Need to start the PostgreSQL database, which Metasploit will use: systemctl start postgresql
- Initialize the Metasploit Database using: msfdb init (need to create non-rrot user to start the msfdb)
- check the database status using: db_status
- The database feature will allow you to create workspaces to isolate different projects: workspace -help
- once Metasploit is launched with a database, the help command, you will show the Database Backends Commands
- Nmap scan using the **db_nmap** will be saved to the database.
- We can check the result **hosts** & **services**
- If there is more than one host saved to the database, all IP addresses will be used when the **hosts -R** command is used.
- 
