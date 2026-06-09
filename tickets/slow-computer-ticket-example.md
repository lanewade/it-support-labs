# Ticket Example: Slow Computer Issue

## Ticket Summary

User reports that their Windows computer is running slowly and applications are freezing.

## User Impact

The user is having difficulty completing normal work tasks because applications take a long time to open, the system freezes, and performance is inconsistent.

## Initial User Report

The user stated that their computer has been slow since the morning. They reported that Outlook, Teams, and the web browser take longer than usual to open.

## Troubleshooting Steps

1. Confirmed when the issue started.
2. Asked whether the issue affected all applications or only one application.
3. Asked whether the computer had recently been restarted.
4. Restarted the computer to clear temporary issues.
5. Opened Task Manager and checked CPU, memory, disk, and network usage.
6. Reviewed startup applications for unnecessary programs.
7. Checked available disk space.
8. Checked for pending Windows updates.
9. Verified that the user was connected to the correct network.
10. Tested basic network connectivity using:

```cmd
ipconfig
ping 8.8.8.8
nslookup google.com
```

11. Checked Device Manager for warning icons.
12. Reviewed Event Viewer for repeated errors or warnings.
13. Confirmed whether other users were experiencing similar issues.
14. Documented all findings in the ticket.

## Possible Causes

* Too many applications running
* High CPU usage
* High memory usage
* High disk usage
* Low storage space
* Pending Windows updates
* Failed updates
* Unnecessary startup programs
* Malware or unwanted software
* Network or VPN issue
* Application-specific issue
* Failing hardware

## Resolution

Task Manager showed high disk usage and several unnecessary startup applications. The computer was restarted, pending Windows updates were completed, and unnecessary startup applications were disabled according to policy. After the restart, the user confirmed that performance improved.

## Ticket Notes

The user confirmed that Outlook, Teams, and the browser opened normally after troubleshooting. No additional issues were reported.

## Escalation Criteria

This issue would be escalated to Tier 2 or desktop support if:

* The computer continued to run slowly after basic troubleshooting
* Hardware failure was suspected
* The computer showed repeated blue screen errors
* Malware was suspected
* Admin permissions were required
* The issue affected multiple users
* Event Viewer showed repeated critical errors
* The hard drive or memory needed diagnostic testing

## What I Learned

This ticket helped reinforce the importance of checking simple causes first, such as restarting the computer, reviewing Task Manager, checking disk space, and looking for pending updates before escalating the issue.
