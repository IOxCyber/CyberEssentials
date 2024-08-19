
# Option Profile is the setting for scanning a host.

## Perimeter Scan: `Unauth scan for External facing IPs`
- `Full scan setting` for TCP/UDP (All 65535 Ports), non-authenticated for daily scans.
- `Load balancers` are meant to be invisible, can be added additionally. QID: 86192

## On-Prem Scan: `Authenticated Scan of Internal Infrastructure`
- Std UPD/TCP ports
- `Full scan setting` for TCP/UDP (All 65535 Ports), non-authenticated for daily scans.
- `Load balancers` are meant to be invisible, can be added additionally. QID: 86192
- Additional Certificate Detection, adds more time to scan but detect the certificates.
- Enable `Parallel scaling` to boost the performance.
- Dissolve Agent: Build for specific registry keys, removed after scan complete.
- Can add MAX 50 internal scanners.

## Cloud Perimeter Scan: `To scan publically exposed EC2, Azure instances`
- Uses visibility data from Qualys Cloud Conectors.

