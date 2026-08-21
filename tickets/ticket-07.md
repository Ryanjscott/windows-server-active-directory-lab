
### `tickets/ticket-07.md`

```markdown
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
