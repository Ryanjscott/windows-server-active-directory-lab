# Ticket 07: Deploy the Finance Network Printer

## Request

Deploy a shared Finance printer and connect it to Emily Carter's workstation.

## Environment

- Print server: DC01
- Client workstation: CLIENT01
- Printer name: Finance Printer
- Share name: FinancePrinter
- UNC path: `\\DC01\FinancePrinter`

## Lab Implementation

Because the lab did not contain a physical printer, a simulated printer was created using:

- Windows Print Server
- Generic / Text Only driver
- File-backed local printer port
- Shared print queue

The simulated print output was written to:

```text
C:\PrintOutput\FinancePrinter.prn
```

## Actions Taken

1. Installed the Print Server role and management tools on DC01.
2. Created the print output directory.
3. Installed the Generic / Text Only printer driver.
4. Created a file-backed printer port.
5. Created and shared the Finance Printer.
6. Connected CLIENT01 to `\\DC01\FinancePrinter`.
7. Submitted a test print.
8. Verified the job reached the DC01 print queue.

## Verification

The following were confirmed:

- Finance Printer was shared from DC01.
- CLIENT01 displayed the printer as installed.
- A test document was submitted successfully.
- The print job reached the server queue.

## Resolution

The Finance Printer was deployed successfully and made available to CLIENT01. A completed test print confirmed connectivity between the workstation and print server.

## Skills Demonstrated

- Windows Print Server administration
- Shared printer deployment
- Client printer installation
- Print queue troubleshooting
- Service verification

## Evidence

- [Printer shared](../Screenshots/Ticket%2007%20-%20Deploy%20Finance%20Network%20Printer%20to%20CLIENT01/ticket-007-printer-shared.png)
- [Client printer installed](../Screenshots/Ticket%2007%20-%20Deploy%20Finance%20Network%20Printer%20to%20CLIENT01/ticket-007-client-printer-installed.png)
- [Print job completed](../Screenshots/Ticket%2007%20-%20Deploy%20Finance%20Network%20Printer%20to%20CLIENT01/ticket-007-print-job-completed.png)
- [Resolved Jira ticket](../Screenshots/Ticket%2007%20-%20Deploy%20Finance%20Network%20Printer%20to%20CLIENT01/ticket-007-jira-resolved.png)
