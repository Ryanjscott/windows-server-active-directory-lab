# Server and Workstation Specifications

## DC01

| Property | Configuration |
|---|---|
| Operating system | Windows Server 2022 |
| Hostname | DC01 |
| Domain | CONTOSO.local |
| NetBIOS domain | CONTOSO |
| IPv4 address | 192.168.50.10 |
| Subnet mask | 255.255.255.0 |
| DNS server | 192.168.50.10 |
| Addressing | Static |
| Virtual CPUs | 2 |
| Memory | 4 GB |
| Hypervisor | Oracle VirtualBox |

### Installed Roles and Features

- Active Directory Domain Services
- DNS Server
- DHCP Server
- Group Policy Management
- File and Storage Services
- Print Server
- BitLocker recovery administration tools

### DHCP Configuration

| Property | Value |
|---|---|
| Scope | 192.168.50.0/24 |
| Address range | 192.168.50.100 to 192.168.50.199 |
| DNS server option | 192.168.50.10 |
| Default gateway | Not configured |
| Scope state | Active |

## CLIENT01

| Property | Configuration |
|---|---|
| Operating system | Windows 11 Enterprise |
| Hostname | CLIENT01 |
| Domain | CONTOSO.local |
| Addressing | DHCP |
| DNS | Supplied by DC01 |
| Virtual CPUs | 2 |
| Memory | 4 GB |
| Final state | Disabled and moved to Disabled Objects |

CLIENT01 was used as Emily Carter's original workstation. It was later replaced by CLIENT02 during the workstation replacement ticket.

## CLIENT02

| Property | Configuration |
|---|---|
| Operating system | Windows 11 Enterprise |
| Hostname | CLIENT02 |
| Domain | CONTOSO.local |
| Addressing | DHCP |
| DNS | Supplied by DC01 |
| Virtual CPUs | 2 |
| Memory | 4 GB |
| Virtual TPM | Enabled |
| Drive encryption | BitLocker |
| Recovery storage | Active Directory |

CLIENT02 replaced CLIENT01 and was used for the BitLocker recovery and offboarding tickets.
