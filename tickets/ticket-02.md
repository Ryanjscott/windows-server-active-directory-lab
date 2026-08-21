# Ticket 02: Join CLIENT01 to the CONTOSO Domain

## Request

Join the Windows 11 workstation CLIENT01 to the CONTOSO.local domain and prepare it for use by Emily Carter.

## Environment

- Workstation: CLIENT01
- Operating system: Windows 11 Enterprise
- Domain: CONTOSO.local
- Domain controller: DC01
- DNS server: 192.168.50.10

## Actions Taken

1. Confirmed CLIENT01 received a valid DHCP address.
2. Confirmed the workstation used DC01 for DNS.
3. Verified that `dc01.contoso.local` resolved successfully.
4. Joined CLIENT01 to `CONTOSO.local`.
5. Restarted the workstation.
6. Moved the CLIENT01 computer account into the Workstations OU.
7. Signed in using `CONTOSO\ecarter`.
8. Completed the required first-sign-in password change.

## Verification

The following were confirmed:

- CLIENT01 was a member of CONTOSO.local.
- The computer object was located in the Workstations OU.
- Emily authenticated using her domain account.
- The active user was `CONTOSO\ecarter`.

## Resolution

CLIENT01 was joined successfully to the CONTOSO.local domain and assigned to the correct Workstations OU. Emily Carter successfully authenticated using her domain account.

## Skills Demonstrated

- Windows domain joining
- DNS validation
- DHCP validation
- Active Directory computer administration
- Domain authentication
- Workstation deployment

## Evidence

- [Successful domain join](../Screenshots/Ticket%2002%20-%20Join%20CLIENT01%20to%20CONTOSO%20Domain/ticket-002-domain-join-success.png)
- [Computer account in Workstations OU](../Screenshots/Ticket%2002%20-%20Join%20CLIENT01%20to%20CONTOSO%20Domain/ticket-002-computer-ou.png)
- [Domain login verification](../Screenshots/Ticket%2002%20-%20Join%20CLIENT01%20to%20CONTOSO%20Domain/ticket-002-domain-login-verification.png)
- [Resolved Jira ticket](../Screenshots/Ticket%2002%20-%20Join%20CLIENT01%20to%20CONTOSO%20Domain/ticket-002-jira-resolved.png)
