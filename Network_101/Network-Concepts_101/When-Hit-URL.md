## What excly happens:

1. **Local DNS Cache**: 1st > The Computer checks its local DNS cache first to see if it already has the IP address for the requested domain name. If the TTL (Time to Live) of the cached record has expired, it may need to be refreshed.

2. **DNS Resolver Query**: 2nd >  If the domain name is not found in the local DNS cache or if the cached record has expired, your computer sends a DNS query to a DNS resolver. This resolver is often provided by your Internet Service Provider (ISP) or a third-party DNS service.

3. **Root DNS Servers**: 3rd > The DNS resolver starts the resolution process by querying the root DNS servers to find the IP addresses of the TLD (Top-Level Domain) servers responsible for the domain's extension (like ".com", ".org", etc.).

4. **TLD Servers**: 4th > The DNS resolver then queries the TLD servers for the IP addresses of the authoritative name servers responsible for the specific domain. These authoritative name servers are the ultimate source of DNS information for the domain.

5. **Authoritative Name Servers**: 5th > Once the TLD servers provide the IP addresses of the authoritative name servers for the domain, the DNS resolver queries these authoritative name servers directly to obtain the IP address(es) associated with the requested domain name.

6. **IP Address Response**: 6th > The authoritative name servers respond to the DNS resolver with the IP address(es) associated with the domain.

7. **Connection**: 7th > Finally, your computer receives the IP address(es) from the resolver and establishes a connection to one of the servers associated with the domain to access the website.

## Authoritative name servers are DNS servers that store the authoritative DNS records for a specific domain. These servers are responsible for providing authoritative answers to DNS queries for the domain they are authoritative for. In other words, they are the ultimate source of truth for DNS information for a particular domain. When the DNS resolver queries authoritative name servers for a domain, it expects accurate and definitive answers.
