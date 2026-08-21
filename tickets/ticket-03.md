# Ticket 03: Configure the Finance Shared Folder

## Request

Create a secure departmental file share for Finance staff and confirm that users outside Finance cannot access it.

## Environment

- Server: DC01
- Folder path: `C:\Shares\Finance`
- Share path: `\\DC01\Finance`
- Authorised group: `DL_Finance_Share_RW`
- Finance user: Emily Carter
- Negative-test user: Daniel Reed

## Access Model

Finance access was assigned using nested groups:

```text
ecarter
  → GG_Finance_Users
    → DL_Finance_Share_RW
      → Finance folder permissions

# Ticket 03: Configure the Finance Shared Folder

## Request

Create a secure departmental file share for Finance staff and confirm that users outside Finance cannot access it.

## Environment

- Server: DC01
- Folder path: `C:\Shares\Finance`
- Share path: `\\DC01\Finance`
- Authorised group: `DL_Finance_Share_RW`
- Finance user: Emily Carter
- Negative-test user: Daniel Reed

## Access Model

Finance access was assigned using nested groups:

```text
ecarter
  → GG_Finance_Users
    → DL_Finance_Share_RW
      → Finance folder permissions
```

## Actions Taken

1. Created `C:\Shares\Finance`.
2. Shared the folder as `\\DC01\Finance`.
3. Assigned Share-level Change and Read access to `DL_Finance_Share_RW`.
4. Assigned NTFS Modify access to `DL_Finance_Share_RW`.
5. Retained Full Control for SYSTEM and Administrators.
6. Nested `GG_Finance_Users` into `DL_Finance_Share_RW`.
7. Added a sample Finance file.
8. Tested access using Emily Carter's Finance account.
9. Tested denied access using Daniel Reed's Sales account.

## Verification

Emily Carter successfully accessed the Finance share and created a test file.

Daniel Reed received an Access Denied response because he was not a member of the Finance access groups.

## Resolution

The Finance share was created successfully with Share and NTFS permissions controlled through nested Active Directory security groups.

Positive and negative access tests confirmed that the permissions worked as intended.

## Skills Demonstrated

- SMB file sharing
- NTFS permissions
- Share permissions
- Active Directory security-group nesting
- Role-based access control
- Positive and negative access testing

## Evidence

- [Finance share created](../Screenshots/Ticket%2003%20-%20Finance%20Shared%20Folder%20Access%20for%20Emily%20Carter/ticket-003-finance-share-created.png)
- [Share permissions](../Screenshots/Ticket%2003%20-%20Finance%20Shared%20Folder%20Access%20for%20Emily%20Carter/ticket-003-share-permissions.png)
- [NTFS permissions](../Screenshots/Ticket%2003%20-%20Finance%20Shared%20Folder%20Access%20for%20Emily%20Carter/ticket-003-ntfs-permissions.png)
- [Nested group permissions](../Screenshots/Ticket%2003%20-%20Finance%20Shared%20Folder%20Access%20for%20Emily%20Carter/ticket-003-nested-group-permissions.png)
- [Finance access verified](../Screenshots/Ticket%2003%20-%20Finance%20Shared%20Folder%20Access%20for%20Emily%20Carter/ticket-003-finance-access-verified.png)
- [Non-Finance access denied](../Screenshots/Ticket%2003%20-%20Finance%20Shared%20Folder%20Access%20for%20Emily%20Carter/ticket-003-nonfinance-access-denied.png)
- [Resolved Jira ticket](../Screenshots/Ticket%2003%20-%20Finance%20Shared%20Folder%20Access%20for%20Emily%20Carter/ticket-003-jira-resolved.png)
