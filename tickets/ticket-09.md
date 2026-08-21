# Ticket 09: BitLocker Recovery

## Incident

CLIENT02 was placed into BitLocker recovery mode during a controlled recovery exercise.

## Environment

- Workstation: CLIENT02
- Operating system: Windows 11 Enterprise
- Encryption: BitLocker
- Key protectors: TPM and recovery password
- Recovery-key storage: Active Directory
- Domain controller: DC01

## Preparation

CLIENT02 was confirmed as:

- Fully encrypted
- Protection enabled
- Protected using TPM and recovery-password protectors

A VirtualBox snapshot was created before forcing recovery.

## Group Policy Configuration

A Group Policy Object named `CONTOSO BitLocker Recovery` was created and linked to the Workstations OU.

The policy allowed operating-system-drive recovery information to be stored in Active Directory and required BitLocker recovery information to be backed up.

## Actions Taken

1. Confirmed the virtual TPM was present and ready.
2. Added TPM and recovery-password protectors.
3. Enabled BitLocker protection.
4. Applied the BitLocker recovery Group Policy.
5. Backed up the recovery password to Active Directory.
6. Verified the recovery information on the CLIENT02 computer account.
7. Forced CLIENT02 into BitLocker recovery mode.
8. Matched the displayed recovery key ID with the Active Directory record.
9. Entered the corresponding recovery password.
10. Restored TPM protection.
11. Confirmed BitLocker protection was enabled.
12. Completed a normal restart.

## Verification

The following were confirmed:

- CLIENT02 remained fully encrypted.
- BitLocker protection was enabled.
- Recovery information was stored in Active Directory.
- The stored recovery password successfully unlocked CLIENT02.
- TPM protection was restored.

## Resolution

CLIENT02 was recovered successfully using BitLocker recovery information stored in Active Directory. Normal TPM protection was restored after recovery.

## Skills Demonstrated

- BitLocker administration
- TPM key protection
- Active Directory recovery-key storage
- Group Policy configuration
- Recovery-key identification
- Secure workstation recovery

## Evidence

- [Recovery information stored in Active Directory](../Screenshots/Ticket%2009%20-%20BitLocker%20Recovery%20Assistance%20-%20Emily%20Carter/ticket-009-recovery-key-in-ad.png)
- [BitLocker recovery prompt](../Screenshots/Ticket%2009%20-%20BitLocker%20Recovery%20Assistance%20-%20Emily%20Carter/ticket-009-recovery-prompt.png)
- [Resolved Jira ticket](../Screenshots/Ticket%2009%20-%20BitLocker%20Recovery%20Assistance%20-%20Emily%20Carter/ticket-009-jira-resolved.png)
