# Authentication protocol:
- An authentication protocol is a set of rules and procedures that define how entities, such as users or devices, can prove their identity to gain access to a system, network, or resource.

## Authentication protocols Types:
1. OAuth 2.0: `Log-in with`
- Allows users to `grant limited` access to their resources on one website to another website `without sharing/entering their credentials`.
- eg. Log-in by `Facebook Login, Google Sign-In, and GitHub OAuth.`

2. OpenID Connect: `Auth by an IDP`
- OpenID Connect is an `identity layer built on top of the OAuth 2.0 framework.`
- Standardized way for websites/app to authenticate users using an identity provider.
- eg. `Apple ID, Azure AD` supports SAML 2.0[^1], OpenID Connect[^2], OAuth 2.0[^3], and WS-Federation protocols `for authentication and authorization.`


3. SAML (Security Assertion Markup Language): `SSO`
- `XML-based protocol` used for single sign-on (SSO) authentication.
- Enables users to `log in once and access multiple` applications without re-entering their credentials. 
- eg. `Salesforce` and Microsoft Azure `Active Directory`

4. JWT (JSON Web Tokens):
- JWT is a compact, URL-safe means of representing claims between two parties.
- used for stateless authentication and authorization in web applications.
- often `used with OAuth 2.0 for securing APIs.`
- eg. `services like Auth0, Firebase, or Okta.`

5. OpenID:
- `Open standard for decentralized authentication and single sign-on (SSO).`
- `Predecessor to OpenID Connect.`

6. LDAP (Lightweight Directory Access Protocol):
- used for accessing and maintaining directory services as:
  - Bind: `Authenticates` the client to the server.
  - `Search`: Retrieves information from the directory.
  - `Add`: Creates a new entry in the directory.
  - `Modify`: Modifies existing entries.
  - Delete: `Removes` entries from the directory.
- operates over `TCP/IP and typically uses port 389` (or 636 for secure communication using SSL/TLS).
- Eg. Enterprise Authentication and Authorization (Azure AD), to query user address books or global address lists within Corporate Directory, Joomla and Drupal CMS platforms etc.

## Actual Working:
> Request for Authentication > Credential Verification > Authentication Token Generation > Token Exchange > Subsequent Requests > Token Validation > Access Granting

## Notes: 
- OpenID is an authentication protocol that allows users to use a single set of credentials to authenticate themselves across multiple websites or applications.
- OAuth (Open Authorization) is an authorization framework.
- Single Sign-On (SSO) granting you seamless access without requiring multiple logins.
- SAML 2.0 focuses on enterprise integration, while OpenID is more consumer-centric.
- Kerberos is primarily an authentication protocol focused on secure authentication and single sign-on, while LDAP is a protocol for accessing and managing directory services.

[^1]: SAML 2.0, which stands for Security Assertion Markup Language 2.0, is a protocol used for exchanging authentication and authorization information between different systems. Used in SSO, Federation (To build trust between 2 orgs), Azure AD.
[^2]: OpenID, verifies the user from an identity provider (like Google or Facebook) & allows access/login to the site. OpenID Connect: OpenID Connect is an authentication layer built on top of OAuth 2.0.
[^3]: OAuth 2.0, allows applications to obtain limited access to a user's resources on another system (referred to as the resource server) without sharing the user's credentials.
