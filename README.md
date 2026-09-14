# IT Support Labs

This repository documents my practical IT support, help desk, desktop support, and troubleshooting work across Windows 10/11, Microsoft 365, user accounts, printers, networking, command-line tools, PowerShell, and technical documentation.

The focus of this repository is supporting end users, diagnosing common workstation and application issues, following structured troubleshooting methods, and documenting technical work clearly.

## About This Repository

I created this repository to organize IT support concepts, troubleshooting exercises, technical notes, and ticket-style scenarios I have studied and practiced.

The work documented here focuses on areas commonly encountered in help desk and desktop support environments, including:

- Windows 10/11 troubleshooting
- Hardware and software support
- User account and access issues
- Microsoft 365 support
- Outlook, Teams, OneDrive, and SharePoint concepts
- Printer troubleshooting
- Slow computer troubleshooting
- Basic network connectivity
- DNS and DHCP troubleshooting
- Wi-Fi troubleshooting
- Command Prompt and PowerShell
- Ticket documentation
- Troubleshooting methodology
- Escalation and technical documentation

Networking is included where it directly supports end-user troubleshooting. More advanced networking and network security work is documented separately in my Networking & Network Security Labs repository.

## Skills Practiced

- Windows 10/11 troubleshooting
- Desktop support workflows
- Help desk troubleshooting
- Hardware and software support
- Account and access troubleshooting
- Password and login troubleshooting
- Microsoft 365 support concepts
- Printer troubleshooting
- Slow computer troubleshooting
- Network connectivity troubleshooting
- TCP/IP troubleshooting
- DNS troubleshooting
- DHCP troubleshooting
- Wi-Fi troubleshooting
- Basic network cabling
- Command-line diagnostics
- PowerShell
- Ticket documentation
- Technical documentation
- Structured troubleshooting methodology
- Escalation concepts
- End-user communication

## Tools & Technologies

- Windows 10/11
- Command Prompt
- PowerShell
- Microsoft 365
- Outlook
- Microsoft Teams
- OneDrive
- SharePoint
- Device Manager
- Event Viewer
- Task Manager
- Windows Update
- Print Spooler
- TCP/IP
- IPv4 and IPv6
- DNS
- DHCP
- Wi-Fi
- Ethernet
- `ipconfig`
- `ping`
- `tracert`
- `nslookup`
- `arp`
- `netstat`

## Support Notes

### [Windows Troubleshooting Checklist](notes/windows-troubleshooting-checklist.md)

Documents a structured Windows 10/11 troubleshooting process for common desktop support issues.

### [Windows Update Troubleshooting](notes/windows-update-troubleshooting.md)

Documents Windows 10/11 update troubleshooting involving connectivity, disk space, Windows Update and BITS services, update history, error codes, Event Viewer, SFC, DISM, update components, verification, and escalation.

### [Windows Startup & Crash Troubleshooting](notes/windows-startup-crash-troubleshooting.md)

Documents Windows 10/11 startup and crash troubleshooting involving WinRE, Startup Repair, Safe Mode, BSOD stop codes, drivers, Device Manager, Event Viewer, Reliability Monitor, SFC, DISM, storage and memory diagnostics, BitLocker considerations, recovery options, and escalation.

### [Storage & Drive Troubleshooting](notes/storage-drive-troubleshooting.md)

Documents Windows storage troubleshooting involving SSDs, HDDs, Disk Management, drive detection, partitions, drive letters, file systems, SMART health, CHKDSK, Event Viewer, disk performance, BitLocker considerations, data protection, and drive-failure escalation.

### [Command Prompt Tools](notes/command-prompt-tools.md)

Documents common Windows command-line tools used for connectivity testing, DNS troubleshooting, system checks, and support documentation.

### [PowerShell Basics](notes/powershell-basics.md)

Documents PowerShell commands for system information, processes, services, networking, and basic troubleshooting.

### [Microsoft 365 Support Concepts](notes/microsoft-365-support-concepts.md)

Documents Microsoft 365 support concepts involving Outlook, Teams, OneDrive, SharePoint, account access, permissions, and common user issues.

### [Account Access Troubleshooting](notes/account-access-troubleshooting.md)

Documents common login, password, MFA, account lockout, group membership, and permission troubleshooting steps.

### [Printer Troubleshooting](notes/printer-troubleshooting.md)

Documents common printer issues involving offline printers, print queues, network printers, drivers, and the Windows Print Spooler service.

### [Windows Network Troubleshooting](notes/windows-network-troubleshooting.md)

Documents Windows connectivity troubleshooting using tools and commands such as `ipconfig`, `ping`, `nslookup`, `tracert`, `ipconfig /release`, `ipconfig /renew`, and `ipconfig /flushdns`.

### [Network Cabling Basics](notes/network-cabling-basics.md)

Documents Ethernet cabling concepts relevant to IT support, including structured cabling, cable categories, patch panels, patch cords, T568A/T568B standards, common tools, and cabling problems.

### [Slow Computer Troubleshooting](notes/slow-computer-troubleshooting.md)

Documents a Windows troubleshooting process for slow computer performance, including Task Manager, startup applications, disk space, Windows updates, malware checks, and escalation criteria.

### [DNS Troubleshooting](notes/dns-troubleshooting.md)

Documents DNS troubleshooting steps including IP connectivity testing, `nslookup`, DNS cache flushing, and identifying name-resolution problems.

### [DHCP Troubleshooting](notes/dhcp-troubleshooting.md)

Documents DHCP troubleshooting steps including checking IP configuration, identifying APIPA addresses, and using `ipconfig /release` and `ipconfig /renew`.

### [Wi-Fi Troubleshooting](notes/wi-fi-troubleshooting.md)

Documents Wi-Fi troubleshooting involving wireless status, SSIDs, signal strength, IP configuration, DNS, DHCP, wireless adapter issues, and escalation criteria.

### [Ticket Documentation Examples](notes/ticket-documentation-examples.md)

Documents examples of clear help desk ticket notes, troubleshooting steps, resolutions, escalation information, and user-facing technical documentation.

## Ticket Examples

### [Network Connectivity Ticket Example](tickets/network-connectivity-ticket-example.md)

Provides a ticket-style example for troubleshooting a user who cannot connect to the network.

### [Microsoft 365 Login Ticket Example](tickets/microsoft-365-login-ticket-example.md)

Provides a ticket-style example for troubleshooting a user who cannot sign in to Microsoft 365 services.

### [Printer Offline Ticket Example](tickets/printer-offline-ticket-example.md)

Provides a ticket-style example for troubleshooting a printer that appears offline.

### [Slow Computer Ticket Example](tickets/slow-computer-ticket-example.md)

Provides a ticket-style example for a user reporting slow Windows computer performance.

### [DNS Troubleshooting Ticket Example](tickets/dns-troubleshooting-ticket-example.md)

Provides a ticket-style example for a user who has network connectivity but cannot access websites or resources by hostname.

### [DHCP Troubleshooting Ticket Example](tickets/dhcp-troubleshooting-ticket-example.md)

Provides a ticket-style example for a workstation that did not receive a valid IP address from DHCP.

### [Wi-Fi Troubleshooting Ticket Example](tickets/wi-fi-troubleshooting-ticket-example.md)

Provides a ticket-style example for a user who cannot connect to Wi-Fi or experiences intermittent wireless connectivity.

## Troubleshooting Approach

When working through an IT support issue, I use a structured process:

1. Identify the user's problem and gather symptoms.
2. Determine the scope and impact.
3. Ask about recent changes.
4. Check simple and likely causes first.
5. Establish a theory of probable cause.
6. Test the theory before making unnecessary changes.
7. Apply an appropriate solution.
8. Verify that the original issue is resolved.
9. Confirm that no additional problems were introduced.
10. Document the issue, troubleshooting steps, resolution, and escalation details when necessary.

This approach helps keep troubleshooting organized, repeatable, and easier for another technician to follow.

## Ticket Documentation

Good ticket documentation should clearly explain:

- What the user reported
- Who or what was affected
- Important symptoms
- Troubleshooting performed
- Commands or tools used
- Changes made
- Root cause when known
- Final resolution
- Verification performed
- Escalation information when applicable

The goal is for another technician to understand what happened without needing to repeat the entire troubleshooting process.

## Current Repository Structure

```text
it-support-labs/
├── README.md
├── notes/
│   ├── account-access-troubleshooting.md
│   ├── command-prompt-tools.md
│   ├── dhcp-troubleshooting.md
│   ├── dns-troubleshooting.md
│   ├── microsoft-365-support-concepts.md
│   ├── network-cabling-basics.md
│   ├── powershell-basics.md
│   ├── printer-troubleshooting.md
│   ├── slow-computer-troubleshooting.md
│   ├── storage-drive-troubleshooting.md
│   ├── ticket-documentation-examples.md
│   ├── wi-fi-troubleshooting.md
│   ├── windows-network-troubleshooting.md
│   ├── windows-startup-crash-troubleshooting.md
│   ├── windows-troubleshooting-checklist.md
│   └── windows-update-troubleshooting.md
└── tickets/
    ├── dhcp-troubleshooting-ticket-example.md
    ├── dns-troubleshooting-ticket-example.md
    ├── microsoft-365-login-ticket-example.md
    ├── network-connectivity-ticket-example.md
    ├── printer-offline-ticket-example.md
    ├── slow-computer-ticket-example.md
    └── wi-fi-troubleshooting-ticket-example.md
```

## Areas to Continue Building

As I continue practicing IT support, I plan to expand this repository with additional work in areas such as:

- Software installation and removal issues
- Device and driver troubleshooting
- Outlook troubleshooting
- OneDrive synchronization troubleshooting
- Microsoft Teams audio and video troubleshooting
- Print Spooler and printer driver troubleshooting
- Shared folder and file-access troubleshooting
- Additional account and permission scenarios
- Ticket escalation examples
- Additional help desk and desktop support scenarios

New documentation will be added as I study and practice these topics.

## Current Focus

My goal for this repository is to continue strengthening practical IT support skills involving Windows, Microsoft 365, user support, troubleshooting, ticket documentation, and desktop support workflows.

I want the repository to demonstrate not only technical knowledge, but also the ability to approach problems methodically, communicate clearly, document work, and know when an issue should be escalated.

## Certifications

- CompTIA A+
- CompTIA Network+
- CompTIA Tech+

## Safety & Privacy

All examples in this repository are intended for educational practice, personal lab environments, and authorized systems.

I avoid uploading sensitive or confidential information such as passwords, MFA codes, personal files, private company information, internal system details, or screenshots containing confidential data.
