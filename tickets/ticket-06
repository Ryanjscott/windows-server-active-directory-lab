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
