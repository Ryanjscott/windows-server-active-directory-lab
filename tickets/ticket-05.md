# Ticket 05: Password Reset and Account Unlock

## Request

Restore access for Emily Carter after repeated unsuccessful authentication attempts caused her domain account to become locked.

## Environment

- User: ecarter
- Domain: CONTOSO.local
- Domain controller: DC01
- Workstation: CLIENT01

## Account Lockout Policy

The domain account lockout policy was configured with:

- Lockout threshold: 5 invalid attempts
- Lockout duration: 15 minutes
- Reset counter after: 15 minutes

## Actions Taken

1. Reproduced the issue by entering an incorrect password repeatedly on CLIENT01.
2. Confirmed Emily's domain account became locked.
3. Verified the locked state in Active Directory.
4. Reset the password using a temporary credential.
5. Unlocked the account.
6. Required a password change at the next sign-in.
7. Tested authentication from CLIENT01.
8. Confirmed the temporary password was changed successfully.

## Verification

The account was verified as:

- Enabled
- Not locked
- Able to authenticate successfully
- Configured with a newly changed password

## Resolution

Emily Carter's account was unlocked and the password was reset. Successful authentication from CLIENT01 confirmed access had been restored.

## Skills Demonstrated

- Account lockout troubleshooting
- Active Directory password resets
- Temporary password handling
- Account status validation
- End-user access restoration

## Evidence

- [Locked account message](../Screenshots/Ticket%2005%20-%20Password%20Reset%20and%20Account%20Unlock%20-%20Emily%20Carter/ticket-005-account-locked-client.png)
- [Account locked in Active Directory](../Screenshots/Ticket%2005%20-%20Password%20Reset%20and%20Account%20Unlock%20-%20Emily%20Carter/ticket-005-ad-account-locked.png)
- [Account unlocked](../Screenshots/Ticket%2005%20-%20Password%20Reset%20and%20Account%20Unlock%20-%20Emily%20Carter/ticket-005-account-unlocked.png)
- [Login restored](../Screenshots/Ticket%2005%20-%20Password%20Reset%20and%20Account%20Unlock%20-%20Emily%20Carter/ticket-005-login-restored.png)
- [Resolved Jira ticket](../Screenshots/Ticket%2005%20-%20Password%20Reset%20and%20Account%20Unlock%20-%20Emily%20Carter/ticket-005-jira-resolved.png)
