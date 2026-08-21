# CONTOSO Knowledge Base

This knowledge base records troubleshooting guidance developed from incidents and support tasks completed during the CONTOSO IT Service Desk Lab.

## KB001: Domain Resources Do Not Resolve

### Symptoms

- Workstation has a valid IP address.
- Domain controller is reachable by IP.
- Domain names do not resolve.
- Shared resources cannot be accessed by hostname.
- `nslookup` fails or queries the wrong DNS server.

### Likely Cause

The workstation is using an incorrect DNS server instead of the DNS server hosting the Active Directory domain.

### Diagnosis

```powershell
ipconfig /all
nslookup dc01.contoso.local
Test-NetConnection 192.168.50.10 -Port 53
