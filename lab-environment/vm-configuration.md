# Virtual Machine Configuration

The CONTOSO lab was built using Oracle VirtualBox.

## Virtual Network

The server and workstations were connected to the same VirtualBox internal network.

| Property | Value |
|---|---|
| Network mode | Internal Network |
| Network name | CONTOSO-LAN |
| Subnet | 192.168.50.0/24 |
| Domain controller | 192.168.50.10 |
| DHCP range | 192.168.50.100 to 192.168.50.199 |
| DNS server | 192.168.50.10 |

The internal network isolated the lab from the host network while allowing the virtual machines to communicate with each other.

## DC01 Configuration

- Windows Server 2022
- 2 virtual CPUs
- 4 GB RAM
- Static IPv4 configuration
- Attached to CONTOSO-LAN
- Active Directory Domain Services installed
- DNS and DHCP hosted locally
- File and print services enabled

## CLIENT01 Configuration

- Windows 11 Enterprise
- 2 virtual CPUs
- 4 GB RAM
- DHCP addressing
- Attached to CONTOSO-LAN
- Joined to CONTOSO.local
- VirtualBox Guest Additions installed

## CLIENT02 Configuration

- Windows 11 Enterprise
- 2 virtual CPUs
- 4 GB RAM
- DHCP addressing
- Attached to CONTOSO-LAN
- Joined to CONTOSO.local
- Virtual TPM enabled
- BitLocker enabled
- VirtualBox Guest Additions installed

## Startup Order

DC01 should be started before either client workstation.

DC01 provides:

- DHCP address allocation
- DNS resolution
- Domain authentication
- Group Policy
- File services
- Print services

Starting a client before DC01 may result in an automatic private address, DNS failure or inability to authenticate against the domain.

## Snapshot Strategy

A VirtualBox snapshot was created before the BitLocker recovery exercise.

Snapshot name:

```text
CLIENT02 Before BitLocker Recovery
