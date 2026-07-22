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
5. Reviewed successful logon events.

## Successful Service Logon Event

- Event ID: 4624
- Result: Successful logon
- Date and time: [REDACTED]
- Account name: SYSTEM
- Logon type: 5
- Source network address: N/A
- Authentication package: Negotiate
- Computer name: [COMPUTER NAME]

## What I Learned From This Event

This event showed that Windows records logons created by background services, not only people signing into the computer.

Event ID 4624 meant the logon succeeded. Logon Type 5 meant a Windows service logged on, and SYSTEM was the built-in account used by that service.

## Workstation Unlock Event

- Event ID: 4624
- Result: Successful logon
- Account name: [USERNAME]
- Logon type: 7
- Authentication package: Negotiate
- Source network address: N/A
- Computer name: [COMPUTER NAME]

## What I Learned From This Event

- Event ID 4624 means the logon was successful.
- Logon Type 7 means the computer was unlocked.
- This usually happens when a user unlocks a locked computer using a password, PIN, or another sign-in method.
- The account name identifies the user who unlocked the computer.
- `Negotiate` means Windows automatically selected an available authentication protocol.
- This event is different from Logon Type 5, which represents a Windows service logging on.

## Cached Interactive Logon Event

- Event ID: 4624
- Result: Successful logon
- Account name: [USERNAME]
- Logon type: 11
- Authentication package: Negotiate
- Source network address: N/A
- Computer name: [COMPUTER NAME]

## What I Learned From This Event

- Event ID 4624 means the logon succeeded.
- Logon Type 11 is a cached interactive logon.
- Windows used sign-in information previously stored on the computer.
- This can allow a user to sign in when a domain controller is unavailable.
- `Negotiate` means Windows automatically selected an available authentication protocol.
- This differs from Logon Type 7, which represents unlocking an existing session.
