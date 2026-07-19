# CONTOSO IT Service Desk Lab

A practical Windows enterprise support lab built to demonstrate common Service Desk, IT Support and junior systems administration tasks.

The project follows a fictional employee, Emily Carter, through onboarding, workstation deployment, access provisioning, troubleshooting, device replacement, BitLocker recovery and eventual offboarding.

Each task was managed as a ticket in Jira Service Management and supported with technical evidence.

## Project Objectives

This project was created to demonstrate practical experience with:

- Active Directory user and computer administration
- Organisational Unit management
- Security group design and group nesting
- Windows domain joins
- DHCP and DNS configuration
- SMB file sharing
- Share and NTFS permissions
- Account lockout and password reset procedures
- Network printer deployment
- Workstation replacement
- Group Policy
- BitLocker recovery
- User offboarding
- PowerShell administration
- Jira Service Management ticket handling

## Lab Environment

| System | Purpose | Configuration |
|---|---|---|
| DC01 | Domain controller and infrastructure server | Windows Server 2022, 192.168.50.10 |
| CLIENT01 | Original user workstation | Windows 11 Enterprise, DHCP |
| CLIENT02 | Replacement user workstation | Windows 11 Enterprise, DHCP, virtual TPM and BitLocker |
| CONTOSO.local | Active Directory domain | NetBIOS name CONTOSO |
| CONTOSO-LAN | VirtualBox internal network | 192.168.50.0/24 |

## Server Roles and Technologies

- Active Directory Domain Services
- DNS Server
- DHCP Server
- Group Policy Management
- File and Storage Services
- Print Management
- BitLocker Drive Encryption
- PowerShell
- Windows 11 Enterprise
- Windows Server 2022
- Oracle VirtualBox
- Jira Service Management

## Completed Tickets

1. [Create a new starter account](tickets/ticket-01)
2. [Join CLIENT01 to the domain](tickets/ticket-02)
3. [Configure the Finance shared folder](tickets/ticket-03)
4. [Add Emily Carter to the Finance Reporting group](tickets/ticket-04)
5. [Reset a password and unlock an account](tickets/ticket-05)
6. [Troubleshoot a DNS resolution issue](tickets/ticket-06)
7. [Deploy a Finance network printer](tickets/ticket-07)
8. [Replace Emily Carter's workstation](tickets/ticket-08)
9. [Complete a BitLocker recovery](tickets/ticket-09)
10. [Offboard Emily Carter](tickets/ticket-10)

A summary of all tickets is available in the [ticket register](ticket-register.md).

## Repository Structure

```text
lab-environment/
    network-diagram.png
    server-specifications.md
    vm-configuration.md

screenshots/
    Technical evidence and resolved Jira tickets

tickets/
    Detailed documentation for Tickets 01 to 10

README.md
assets
diagrams
knowledge-base
procedures
ticket-register.md
