## Asymmetric Encryption:
```
Private Key: Encrypt
Public Key: Decrypt
```
## Symmetric Encryption: `Same Private Key`

## Cryptography: 
- Cryptography is the study of the conversion of plain text(readable format) to ciphertext(non-readable format) i.e. encryption.
- Encryption algorithms are a specific type of cryptographic mechanism that focuses on transforming plaintext data into ciphertext to protect its confidentiality.

## Cryptographic Mechanism:
- Application, process, module, or device that provides a cryptographic service, such as confidentiality, integrity, source authentication, and access control (e.g., encryption and decryption, and digital signature generation and verification).
> Encryption algorithms are an important component of cryptographic mechanisms

## Mechanism:
> Encryption: `Transforms plaintext data into ciphertext using an encryption algorithm and a cryptographic key` decrypted with decryption key.

## 1. Hash Functions: 
- `Hash functions generate fixed-length hash values from input data.`, one-way functions (can't retrieve the original data from the hash value.)
- eg. Secure Hash Algorithm (SHA-256, SHA-3) and Message Digest Algorithm (MD5).

## 2. Symmetric Encryption: 
- `Symmetric encryption algorithms use the same key for both encryption and decryption.`, faster and more efficient for large amounts of data.
- eg. Encryption Standard (AES), Data Encryption Standard (DES), and Triple Data Encryption Standard (3DES).

## 3. Asymmetric Encryption: 
- `Also known as public key cryptography, uses a pair of mathematically related keys: a public key for encryption and a private key for decryption`
- The `public key can be openly distributed`, while the private key must be kept secret.
- eg. RSA (Rivest-Shamir-Adleman) and Elliptic Curve Cryptography (ECC).

## 4. Digital Signatures: 
- `Provide integrity and authenticity to digital documents or messages.`
- `Created by using the sender's private key` to encrypt a hash value of the data.
- The recipient can `verify the digital signature using the sender's public key`
- eg. RSA-based signatures and Elliptic Curve Digital Signature Algorithm (ECDSA).

## 5. Key Exchange Protocols:
- Establish secure communication channels by enabling two parties to agree on a shared secret key over an insecure network.
- eg. Diffie-Hellman Key Exchange or Elliptic Curve Diffie-Hellman (ECDH).

## 6. Secure Hash Algorithms (SHA):
- Generate fixed-size hash values that provide strong resistance against collisions and are commonly used for password hashing, data integrity checks, and digital certificates.
- eg. SHA-256 or SHA-3, Message Digest Algorithm (MD5).
