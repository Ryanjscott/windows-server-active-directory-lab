# CONTOSO IT Support Procedures

This document records the standard procedures followed during the CONTOSO IT Service Desk Lab.

## New User Onboarding

1. Confirm the approved user details.
2. Confirm the department, job title and manager.
3. Create the Active Directory account in the correct departmental OU.
4. Assign a temporary password.
5. Require the user to change the password at the first sign-in.
6. Add the user only to approved security groups.
7. Verify account status and OU placement.
8. Confirm that required resources are accessible.
9. Record the completed work in the service desk ticket.

## Joining a Workstation to the Domain

1. Confirm the workstation has a valid IP address.
2. Confirm that the workstation uses the domain DNS server.
3. Test DNS resolution for the domain controller.
4. Confirm the workstation has a unique hostname.
5. Join the workstation to the domain.
6. Restart the workstation.
7. Move the computer object into the correct OU.
8. Test domain authentication.
9. Confirm Group Policy applies successfully.
10. Record the result in the ticket.

## Shared Folder Provisioning

1. Create the server folder.
2. Create the SMB share.
3. Assign Share permissions to a domain-local security group.
4. Assign NTFS permissions to the same domain-local group.
5. Nest the appropriate global role group into the domain-local resource group.
6. Avoid assigning permissions directly to individual users.
7. Test access using an authorised user.
8. Test denied access using an unauthorised user.
9. Record both results.

## Password Reset and Account Unlock

1. Verify the user's identity.
2. Confirm whether the account is locked.
3. Review the reason for the lockout where possible.
4. Unlock the account.
5. Reset the password using a temporary credential.
6. Require a password change at the next sign-in.
7. Confirm that the account is enabled.
8. Test successful authentication.
9. Do not record passwords in the ticket.

## DNS Troubleshooting

1. Run `ipconfig /all`.
2. Confirm the workstation's IP address, DHCP server and DNS server.
3. Test the destination by IP address.
4. Test DNS resolution using `nslookup`.
5. Confirm TCP port 53 is reachable on the DNS server.
6. Compare configured DNS with the approved domain DNS server.
7. Remove incorrect static DNS entries.
8. Renew the DHCP lease.
9. Flush the DNS resolver cache.
10. Retest name resolution and resource access.

## Network Printer Deployment

1. Confirm the Print Server role is installed.
2. Install the approved printer driver.
3. Create the printer port.
4. Create and share the printer.
5. Assign an appropriate share name.
6. Publish the printer where required.
7. Connect the client workstation.
8. Submit a test print.
9. Confirm the print job reaches the queue.
10. Record successful verification.

## Workstation Replacement

1. Build the replacement device using a fresh operating-system installation.
2. Assign a unique hostname.
3. Install required drivers and integration tools.
4. Connect the workstation to the corporate network.
5. Confirm DHCP and DNS configuration.
6. Join the device to the domain.
7. Move the computer account into the correct OU.
8. Test user authentication.
9. Restore mapped drives, printers and required access.
10. Disable and retain the previous computer account.
11. Record the replacement and retirement details.

## BitLocker Recovery

1. Record the recovery key ID displayed by the workstation.
2. Locate the computer account in Active Directory.
3. Open the BitLocker Recovery information.
4. Match the displayed recovery key ID.
5. Provide only the corresponding recovery password.
6. Unlock the workstation.
7. Investigate why recovery was triggered.
8. Restore the TPM protector where required.
9. Confirm BitLocker protection is enabled.
10. Restart and verify normal startup.

## User Offboarding

1. Confirm the offboarding request is authorised.
2. Record existing group memberships.
3. Export an access record where required.
4. Remove role and resource group memberships.
5. Disable the Active Directory account.
6. Record the offboarding date in the account description.
7. Move the account into the Disabled Objects OU.
8. Retain the account for auditing rather than deleting it immediately.
9. End active sessions where required.
10. Confirm that domain authentication is denied.
11. Record the completed actions in the ticket.
