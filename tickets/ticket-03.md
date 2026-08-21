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
