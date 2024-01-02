# Digital Signature & Public Key Infrastructure (PKI) Concepts: 

## Digital Signature:
- A Mathematical technique to validate the Authenticity and integrity of a Digital Document.
- Digital Document: a Message, Software, etc.

- `Digital signature = Hash value of the Original Data + The Signing algorithm`

### Note:
- Signature Key: The Signing Algorithm encrypts the `Hash Value` by Private Key AKa Signature Key.
- Signing Algorithm: Agreed upon on Industries Practices on Connection Initialization i.e. by CA aka Certification Authority or at TLS/SSL Handshaking.

### Process of Creating & Verification:
1. Signing: The Signer applies the `Hash function to the original data, Encrypt it with its Private Key, and generates a Digital Signature.`
2. Transmission: `Digital Signature + Original Data` transmitted to the recipient.
3. Verification: The Recipient `generates the Hash value of the Received Original Data.` by using the Public Key.
4. Comparision: `Compare the Hash value with Received Original Data.`

## SSL/TLC Digital Certificate: `An electronic document Containing..`
- Certificate holder's name
- Serial Number
- Certificate Signing Algorithm
- Issuer Name (the entity (CA Authority) that issued the certificate)
- Copy of Public Key Information
- Certificate Authority (CA) Information

### Usage:
- Issued by a Certificate Authority CA used for Authenticity, Integrity, and Non-Repudiation.
- In HTTPS, Emails, User authentication, VPNs, Code Signing, Document Integrity, Secure File Transfer etc.

## CA Certificate Authority: `A trusted entity to verify the identity of entities`
- Used to verify the identity of entities (individuals, organizations, or servers) and bind their identity to a public key.
- CA issues the digital certificates to verify the identity of entities. 
- CA acts as a trusted third party, facilitating secure communication, authentication, and data integrity in various online transactions.
- CAs maintain Certificate Revocation Lists (CRLs) to invalidate compromised or expired certificates.
- Can be Internal CA (Managed by the Organization) or External CA (Third-Party CA)

