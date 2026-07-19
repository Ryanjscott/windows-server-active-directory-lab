
---

# `ticket-register.md`

```markdown
# Ticket Register

This register summarises the ten service desk tickets completed during the CONTOSO IT Service Desk Lab.

| Ticket | Summary | Category | Systems | Status |
|---|---|---|---|---|
| 01 | Create a new starter account for Emily Carter | Identity and Access Management | DC01, Active Directory | Resolved |
| 02 | Join CLIENT01 to CONTOSO.local | Device Management | CLIENT01, DC01 | Resolved |
| 03 | Configure the Finance shared folder | File Services | DC01, CLIENT01 | Resolved |
| 04 | Add Emily Carter to the Finance Reporting group | Access Management | Active Directory | Resolved |
| 05 | Reset Emily Carter's password and unlock the account | Identity and Access Management | DC01, CLIENT01 | Resolved |
| 06 | Resolve domain resource name resolution failure | Networking and DNS | CLIENT01, DC01 | Resolved |
| 07 | Deploy the Finance network printer | Print Services | DC01, CLIENT01 | Resolved |
| 08 | Replace Emily Carter's workstation | Device Management | CLIENT01, CLIENT02, DC01 | Resolved |
| 09 | Recover CLIENT02 using a BitLocker recovery password | Security and Encryption | CLIENT02, DC01 | Resolved |
| 10 | Offboard Emily Carter | Identity and Access Management | DC01, CLIENT02 | Resolved |

## Ticket Lifecycle

Each ticket followed a basic service desk workflow:

1. Request or incident recorded in Jira Service Management.
2. Initial response and triage completed.
3. Ticket moved to In Progress.
4. Technical work performed.
5. Results verified.
6. Evidence captured.
7. Resolution response added.
8. Ticket moved to Resolved.
