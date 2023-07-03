## Authentication protocol:
- Azure `AD supports` SAML 2.0[^1] , OpenID Connect[^2], OAuth 2.0[^3], and WS-Federation protocols `for authentication and authorization.`
- OpenID is an authentication protocol that allows users to use a single set of credentials to authenticate themselves across multiple websites or applications.
- OAuth (Open Authorization) is an authorization framework.
- Single Sign-On (SSO) granting you seamless access without requiring multiple logins.
- SAML 2.0 focuses on enterprise integration, while OpenID is more consumer-centric.

[^1]: SAML 2.0, which stands for Security Assertion Markup Language 2.0, is a protocol used for exchanging authentication and authorization information between different systems. Used in SSO, Federation (To build trust between 2 orgs), Azure AD.
[^2]: OpenID, verifies the user from an identity provider (like Google or Facebook) & allows access/login to the site. OpenID Connect: OpenID Connect is an authentication layer built on top of OAuth 2.0.
[^3]: OAuth 2.0, allows applications to obtain limited access to a user's resources on another system (referred to as the resource server) without sharing the user's credentials.
