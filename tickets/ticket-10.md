# Ticket 10: Offboard Emily Carter

## Request

Remove Emily Carter's access following the end of her employment while retaining the Active Directory account for auditing.

## Environment

- User: Emily Carter
- Username: ecarter
- Domain: CONTOSO.local
- Domain controller: DC01
- Workstation: CLIENT02

## Actions Taken

1. Signed Emily out of CLIENT02.
2. Recorded her existing group memberships.
3. Exported her group memberships for auditing.
4. Removed Emily from `GG_Finance_Users`.
5. Removed Emily from `GG_Finance_Reporting`.
6. Disabled the Active Directory account.
7. Added an offboarding date and description.
8. Moved the account into the Disabled Objects OU.
9. Verified the Finance access groups had been removed.
10. Tested authentication from CLIENT02.

## Cached Logon Finding

The first sign-in test succeeded because CLIENT02 used cached domain credentials.

Cached domain logons were disabled for the verification test so that CLIENT02 was required to contact the domain controller. The subsequent authentication attempt was denied because the Active Directory account was disabled.

This demonstrated the distinction between disabling a domain account and cached workstation authentication.

## Verification

The following were confirmed:

- The Active Directory account was disabled.
- Finance and reporting access groups were removed.
- The account was located in the Disabled Objects OU.
- Domain authentication was denied.

## Resolution

Emily Carter's access was removed successfully. The account was disabled and retained in the Disabled Objects OU for auditing rather than deleted.

## Skills Demonstrated

- User offboarding
- Access revocation
- Group-membership auditing
- Active Directory account disabling
- OU management
- Cached credential troubleshooting
- Authentication testing

## Evidence

- [Access before removal](../Screenshots/Ticket%2010%20-%20User%20Offboarding%20-%20Emily%20Carter/ticket-010-access-before-removal.png)
- [Access after removal](../Screenshots/Ticket%2010%20-%20User%20Offboarding%20-%20Emily%20Carter/ticket-010-access-after-removal.png)
- [Account disabled and moved](../Screenshots/Ticket%2010%20-%20User%20Offboarding%20-%20Emily%20Carter/ticket-010-account-disabled-and-moved.png)
- [Login denied](../Screenshots/Ticket%2010%20-%20User%20Offboarding%20-%20Emily%20Carter/ticket-010-login-denied.png)
- [Resolved Jira ticket](../Screenshots/Ticket%2010%20-%20User%20Offboarding%20-%20Emily%20Carter/ticket-010-jira-resolved.png)
