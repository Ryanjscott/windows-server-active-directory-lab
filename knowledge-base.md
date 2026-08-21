# CONTOSO Knowledge Base

## KB001: Domain Resources Do Not Resolve

### Symptoms

- The workstation has a valid IP address.
- The domain controller is reachable by IP.
- Domain names do not resolve.
- Shared folders cannot be accessed by hostname.
- `nslookup` times out or queries the wrong server.

### Likely Cause

The workstation is using an incorrect DNS server instead of the Active Directory DNS server.

Domain-joined Windows workstations should use the DNS server hosting the Active Directory domain zone.

### Diagnosis

Run:

```powershell
ipconfig /all
nslookup dc01.contoso.local
Test-NetConnection 192.168.50.10 -Port 53
