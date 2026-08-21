# CONTOSO Knowledge Base

This knowledge base records troubleshooting guidance developed from incidents and support tasks completed during the CONTOSO IT Service Desk Lab.

## KB001: Domain Resources Do Not Resolve

### Symptoms

- Workstation has a valid IP address.
- Domain controller is reachable by IP.
- Domain names do not resolve.
- Shared resources cannot be accessed by hostname.
- `nslookup` fails or queries the wrong DNS server.

### Likely Cause

The workstation is using an incorrect DNS server instead of the DNS server hosting the Active Directory domain.

### Diagnosis

```powershell
ipconfig /all
nslookup dc01.contoso.local
Test-NetConnection 192.168.50.10 -Port 53
```

Confirm that the configured DNS server is `192.168.50.10`.

### Resolution

Return the client to the approved DNS configuration, renew the DHCP lease and flush the resolver cache.

```powershell
ipconfig /renew
ipconfig /flushdns
```

### Verification

```powershell
nslookup dc01.contoso.local
Test-Path "\\dc01.contoso.local\Finance"
```

---

## KB002: Shared Folder Access Denied

### Checks

1. Confirm the user is a member of the correct global role group.
2. Confirm the global group is nested into the correct domain-local resource group.
3. Verify Share permissions.
4. Verify NTFS permissions.
5. Check for explicit Deny permissions.
6. Confirm the user has signed out and back in after any group-membership change.
7. Retest access using the UNC path.

### Example Access Model

```text
User
  → Global role group
    → Domain-local resource group
      → Folder permissions
```

---

## KB003: Group Membership Change Has Not Taken Effect

### Cause

The user's current Windows logon token may have been created before the Active Directory group membership was changed.

### Resolution

1. Save the user's work.
2. Sign the user out completely.
3. Sign back in using the domain account.
4. Retest access.

Locking and unlocking the workstation does not create a new logon token.

---

## KB004: Disabled Domain User Can Still Sign In

### Possible Cause

The workstation may be using cached domain credentials instead of contacting a domain controller.

### Diagnosis

```powershell
nslookup dc01.contoso.local
Test-NetConnection 192.168.50.10 -Port 389
nltest /dsgetdc:contoso.local
```

A disabled domain account should be rejected when the workstation authenticates directly with the domain controller.

Cached logon configuration should only be changed in accordance with organisational security policy.

---

## KB005: BitLocker Recovery Information Cannot Be Stored in Active Directory

### Symptom

BitLocker recovery information cannot be backed up to Active Directory.

### Cause

The required BitLocker recovery Group Policy has not been configured.

### Resolution

Configure the following policy:

```text
Computer Configuration
→ Policies
→ Administrative Templates
→ Windows Components
→ BitLocker Drive Encryption
→ Operating System Drives
→ Choose how BitLocker-protected operating system drives can be recovered
```

Enable Active Directory backup of recovery information and apply Group Policy.

```powershell
gpupdate /force
```

Then back up the recovery protector to Active Directory.

---

## KB006: VirtualBox Guest Integration Stops Working

### Symptoms

- Bidirectional clipboard does not work.
- Mouse integration is unavailable.
- Guest integration features behave unexpectedly.

### Resolution

1. Confirm VirtualBox Guest Additions is installed.
2. Repair or reinstall Guest Additions if required.
3. Restart the virtual machine.
4. Confirm the Guest Additions service is running.

```powershell
Get-Service VBoxService
```

---

## KB007: Client Receives an Unexpected IP Address

| Address | Meaning |
|---|---|
| 192.168.50.100 to 192.168.50.199 | Correct CONTOSO DHCP range |
| 10.0.2.x | VirtualBox NAT is likely configured |
| 169.254.x.x | DHCP is unavailable |
| 192.168.50.x with incorrect DNS | IP connectivity may work while domain resolution fails |

### Checks

1. Confirm DC01 is running.
2. Confirm the DHCP Server service is running.
3. Confirm the client is attached to `CONTOSO-LAN`.
4. Confirm the virtual network adapter is connected.
5. Renew the DHCP lease.

```powershell
ipconfig /release
ipconfig /renew
```
