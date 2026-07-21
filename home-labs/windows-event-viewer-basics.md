# Windows Event Viewer Basics

## Objective

Learn how Windows records authentication activity and practice reviewing security events.

## Environment

- Windows 11
- Windows Event Viewer
- Security log

## Steps Completed

1. Opened Event Viewer.
2. Navigated to `Windows Logs > Security`.
3. Used **Filter Current Log**.
4. Filtered for Event IDs `4624` and `4625`.
5. Reviewed a successful logon event.

## Successful Logon Event

- Event ID: 4624
- Result: Successful logon
- Date and time: [REDACTED]
- Account name: System
- Logon type: 5
- Source network address: N/A
- Authentication package: Negotiate
- Computer name: [COMPUTER NAME]
- 
## What I Learned

This event showed that Windows records logons created by background services, not only people signing into the computer.

Event ID 4624 meant the logon succeeded. Logon Type 5 meant a Windows service logged on, and SYSTEM was the built-in account used by that service.
