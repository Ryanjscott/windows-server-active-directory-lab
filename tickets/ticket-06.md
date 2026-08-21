# Ticket 06: CLIENT01 DNS Resolution Issue

## Incident

CLIENT01 could not resolve domain resource names or access the Finance share using its domain name.

## Environment

- Workstation: CLIENT01
- Domain controller and DNS server: DC01
- Correct DNS server: 192.168.50.10
- Incorrect DNS server: 192.168.50.99
- Domain: CONTOSO.local

## Symptoms

- CLIENT01 retained a valid DHCP address.
- DC01 remained reachable by IP address.
- DNS queries for `dc01.contoso.local` failed.
- Domain resources could not be accessed by name.

## Investigation

The following tests were performed:

```powershell
ipconfig /all
nslookup dc01.contoso.local
Test-NetConnection 192.168.50.10 -Port 53

# Ticket 06: CLIENT01 DNS Resolution Issue

## Incident

CLIENT01 could not resolve domain resource names or access the Finance share using its domain name.

## Environment

- Workstation: CLIENT01
- Domain controller and DNS server: DC01
- Correct DNS server: 192.168.50.10
- Incorrect DNS server: 192.168.50.99
- Domain: CONTOSO.local

## Symptoms

- CLIENT01 retained a valid DHCP address.
- DC01 remained reachable by IP address.
- DNS queries for `dc01.contoso.local` failed.
- Domain resources could not be accessed by name.

## Investigation

The following tests were performed:

```powershell
ipconfig /all
nslookup dc01.contoso.local
Test-NetConnection 192.168.50.10 -Port 53
```

The results showed that network connectivity to DC01 and the DNS service was available, but CLIENT01 was configured to use the incorrect DNS address `192.168.50.99`.

## Root Cause

A static DNS override had been configured on CLIENT01, causing the workstation to bypass the DNS server supplied through DHCP.

## Resolution

The incorrect static DNS setting was removed and CLIENT01 was returned to DHCP-provided DNS configuration.

The DHCP lease was renewed and the DNS resolver cache was flushed.

```powershell
ipconfig /renew
ipconfig /flushdns
```

## Verification

The following were confirmed:

- CLIENT01 used 192.168.50.10 as its DNS server.
- `dc01.contoso.local` resolved successfully.
- The Finance share was accessible using its domain name.

## Skills Demonstrated

- DNS troubleshooting
- DHCP configuration validation
- PowerShell network diagnostics
- Root-cause analysis
- Service restoration verification

## Evidence

- [Incorrect DNS configuration](../Screenshots/Ticket%2006%20-%20CLIENT01%20Unable%20to%20Resolve%20Domain%20Resources/ticket-006-incorrect-dns-configuration.png)
- [DNS fault diagnosis](../Screenshots/Ticket%2006%20-%20CLIENT01%20Unable%20to%20Resolve%20Domain%20Resources/ticket-006-dns-fault-diagnosis.png)
- [Corrected DNS configuration](../Screenshots/Ticket%2006%20-%20CLIENT01%20Unable%20to%20Resolve%20Domain%20Resources/ticket-006-dns-configuration-corrected.png)
- [DNS resolution restored](../Screenshots/Ticket%2006%20-%20CLIENT01%20Unable%20to%20Resolve%20Domain%20Resources/ticket-006-dns-resolution-restored.png)
- [Resolved Jira ticket](../Screenshots/Ticket%2006%20-%20CLIENT01%20Unable%20to%20Resolve%20Domain%20Resources/ticket-006-jira-resolved.png)
