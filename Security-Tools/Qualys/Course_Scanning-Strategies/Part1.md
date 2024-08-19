1. We can deploy more than 1 Appliances in a subscription to reduce scan time.

2. Adding Scannable Hosts:
- `VM > Assets > New > Select the required Tracking Method`
- If the Tracking method changes, Purge the Asset first then rescan the assets.
- A Manager can limit IPs for a Unit Manager: VM > Users > Set Up (Settings) > Business Units > enable Check Box Option > Business Units meanu > Select Business Unit name to limit the IPs.

3. Best Practices:
- Schedules can be set to run daily, weekly, or monthly, and can be paused for the maintenance period.
-![image](https://github.com/user-attachments/assets/247c6bd7-3e11-44c7-b5a1-a789f295e38c)
- Internal Assets/Perimeter: Weekly, External Assets: Daily

4. Auth Scans Set-Up:
- For Internal/On-prem Assets

### For Win: 
- NTLM (default), Kerberos(If both selected, Kerberos trigger first)
- Kerberos relies (DNS, Time Sync, Encryption)
- Remote Registry Disabled Info: QID 90194
- ![image](https://github.com/user-attachments/assets/8594f038-bd3c-4efa-8865-906138bfbf4f)

## Note: Local win & linux auth records needs assets assigned by IPs (Manually or by Asset Groups/Tags)
![image](https://github.com/user-attachments/assets/869fda85-d8dd-40b4-85fb-4291cd2ace6b)

### For Linux:
- Not to use root user, `Use Root delegation(Sudo) for a normal user for elevated options.`
- Use Private/Public Key(Type: RSA/DSA)
- Openssh, ssh-keygen (to gen keys on the system locally)
- A scanner account must be added to the host & the public key goes into the authorized keys file locally.
- For large org, 3rd party password vaults can be used. (CyberArk, Azure Key, BeyondTrust etc)
- [image](https://github.com/user-attachments/assets/3f19fff4-576f-41a0-aa7b-2a14fa4a2caa)


5. Monitoring Auth Scans:
- Make Specific Option Profile for Auth Testing: `Test Authentication testing`
- `Run the scan to test the Auth before` the normal vuln scan.
- Use the `Qualys Subscription Health` dashboard to monitor the completed scans.

