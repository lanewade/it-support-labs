# Windows Startup & Crash Troubleshooting

This note documents my study and practice of troubleshooting Windows 10/11 startup failures, boot problems, system crashes, blue screens, driver issues, and recovery options.

The goal is to use a structured IT support process to determine whether a problem is caused by Windows, drivers, updates, storage, hardware, startup software, or corrupted system files, then verify that the system starts and operates normally after troubleshooting.

## Common Startup & Crash Problems

Common symptoms can include:

- Windows will not boot
- Computer repeatedly restarts
- Windows freezes during startup
- Black screen after sign-in
- Blue Screen of Death
- Computer crashes randomly
- Automatic Repair loop
- System becomes unstable after an update
- System becomes unstable after a driver installation
- Windows starts but immediately freezes
- Startup takes unusually long
- User cannot reach the Windows desktop
- Error appears before Windows loads

## Initial Information Gathering

Before making changes, I would gather information about the problem.

Questions may include:

- When did the problem begin?
- Did Windows work normally before this?
- Was anything recently installed or changed?
- Were Windows updates recently installed?
- Was a driver recently updated?
- Was new hardware installed?
- Does the system display an error message?
- Is there a stop code?
- Does the issue happen every time?
- Can Windows reach the sign-in screen?
- Can the user sign in?
- Does Safe Mode work?
- Has the computer experienced a sudden power loss?

This helps narrow down whether the issue is related to software, hardware, drivers, updates, or system corruption.

## Step 1 — Restart the Computer

If Windows is still responsive enough to restart normally, start with a regular restart.

A restart can:

- Clear temporary problems
- Complete pending updates
- Restart services
- Release locked files
- Reset some driver states

If Windows starts normally after the restart, continue monitoring for the problem.

## Step 2 — Disconnect Unnecessary Devices

External devices can sometimes interfere with startup.

Temporarily disconnect unnecessary devices such as:

- USB drives
- External hard drives
- Docking stations
- Printers
- USB accessories

Keep essential devices connected.

Example:

```text
Keep:
Keyboard
Mouse
Display
Power

Temporarily disconnect:
External storage
Printer
USB hub
Unnecessary accessories
```

If Windows starts normally afterward, reconnect devices one at a time to identify the possible cause.

## Step 3 — Observe the Startup Process

Determine where the failure occurs.

Possible stages include:

```text
Power On
   |
BIOS / UEFI
   |
Windows Boot
   |
Windows Logo
   |
Sign-In Screen
   |
Desktop
```

Where the failure occurs provides useful clues.

For example:

```text
No vendor logo
→ Possible power or hardware issue

Vendor logo appears but Windows never starts
→ Possible boot, storage, or Windows issue

Windows reaches sign-in but crashes afterward
→ Possible user profile, driver, service, or startup software issue
```

## BIOS / UEFI vs Windows Problem

If the system cannot complete POST or reach BIOS/UEFI, the issue may be below the Windows operating system level.

Possible causes include:

- Power problem
- RAM failure
- Storage failure
- Motherboard issue
- Hardware connection problem

If the system reaches BIOS/UEFI successfully but Windows fails afterward, operating system, boot, driver, or storage troubleshooting may be appropriate.

## Windows Recovery Environment

Windows Recovery Environment is commonly called:

`WinRE`

WinRE provides recovery tools when Windows cannot start normally.

Possible recovery tools include:

- Startup Repair
- Startup Settings
- Safe Mode
- System Restore
- Uninstall Updates
- Command Prompt
- Reset this PC
- UEFI Firmware Settings

Depending on the system, WinRE may appear automatically after repeated startup failures.

It may also be accessed through Windows settings when the operating system is still available.

## Advanced Startup

From a working Windows installation, advanced startup options may be reached through:

```text
Settings
→ System
→ Recovery
→ Advanced startup
```

Then select:

```text
Restart now
```

The exact menu layout may vary by Windows version.

## Startup Repair

Startup Repair attempts to repair certain problems that prevent Windows from loading.

From WinRE:

```text
Troubleshoot
→ Advanced options
→ Startup Repair
```

Startup Repair may help with certain:

- Boot configuration problems
- Startup file issues
- Windows boot failures

If Startup Repair does not resolve the issue, additional troubleshooting is required.

## Safe Mode

Safe Mode starts Windows with a limited set of drivers and services.

It is useful for determining whether a startup problem is caused by:

- Driver
- Startup software
- Third-party service
- Recent application
- Configuration change

Conceptually:

```text
Normal Mode:
Windows + drivers + services + startup applications

Safe Mode:
Windows + minimal drivers + minimal services
```

If Windows works in Safe Mode but fails in normal mode, a driver, service, or startup application may be involved.

## Accessing Safe Mode

From WinRE:

```text
Troubleshoot
→ Advanced options
→ Startup Settings
→ Restart
```

Then choose a Safe Mode option.

Possible choices may include:

- Safe Mode
- Safe Mode with Networking
- Safe Mode with Command Prompt

Safe Mode with Networking loads additional networking components.

## Step 4 — Check Recent Changes

Recent changes are especially important when troubleshooting crashes.

Examples include:

- Windows update
- Driver update
- New application
- Antivirus software
- New hardware
- BIOS or firmware update
- Startup software
- System configuration change

If the problem began immediately after a change, that change becomes a strong troubleshooting clue.

## Driver Problems

Drivers allow Windows to communicate with hardware.

A faulty or incompatible driver can cause:

- Startup failures
- Blue screens
- Freezing
- Device failures
- Performance issues

Common driver categories include:

- Graphics
- Network
- Audio
- Storage
- Chipset
- USB
- Bluetooth

## Device Manager

Open Device Manager with:

```text
devmgmt.msc
```

Device Manager can show:

- Device status
- Driver version
- Hardware errors
- Disabled devices
- Warning icons

Possible troubleshooting actions may include:

- Update driver
- Roll back driver
- Disable device temporarily
- Uninstall device and reinstall driver

Driver changes should be made carefully and documented.

## Roll Back Driver

If a problem begins after a driver update, Device Manager may allow the previous driver to be restored.

Conceptually:

```text
Device Manager
→ Device Properties
→ Driver
→ Roll Back Driver
```

If the rollback option is unavailable, another supported driver may need to be installed.

## Windows Update and Startup Problems

If the system becomes unstable immediately after a Windows update, recovery options may include:

```text
WinRE
→ Troubleshoot
→ Advanced options
→ Uninstall Updates
```

Options may include uninstalling:

- Latest quality update
- Latest feature update

Updates should only be removed when troubleshooting evidence supports the update as a likely cause.

## System Restore

System Restore can return Windows system files and configuration to an earlier restore point.

It may help when a problem begins after:

- Driver installation
- Software installation
- System configuration change

System Restore does not normally replace a full user-data backup.

From WinRE:

```text
Troubleshoot
→ Advanced options
→ System Restore
```

A restore point must already exist for this option to work.

## Startup Applications

Too many or malfunctioning startup applications can cause slow or unstable startup.

Open Task Manager:

```text
Ctrl + Shift + Esc
```

Then review:

```text
Startup apps
```

Look for:

- Unnecessary startup programs
- Recently installed applications
- High startup impact

Applications should only be disabled when appropriate.

## Services

A problematic service can sometimes interfere with normal startup.

Open:

```text
services.msc
```

Possible troubleshooting may involve identifying:

- Failed services
- Recently installed services
- Repeated service errors

Core Windows services should not be disabled randomly.

## Clean Boot Concept

A clean boot starts Windows with a reduced set of non-Microsoft services and startup programs.

It can help determine whether a third-party application or service is causing a problem.

Conceptually:

```text
Normal Startup
→ Microsoft services
→ Third-party services
→ Startup programs

Clean Boot
→ Essential Microsoft services
→ Reduced third-party software
```

A clean boot is different from Safe Mode.

Safe Mode uses a minimal Windows environment.

Clean boot troubleshooting isolates third-party services and startup software while using a more normal Windows environment.

## Blue Screen of Death

A Windows blue screen is commonly called:

`BSOD`

It occurs when Windows experiences a serious error that prevents it from safely continuing.

A BSOD may display:

- Stop code
- Error message
- Driver name
- QR code
- Restart status

The exact stop code should be documented.

## Stop Codes

Examples of stop-code formats may include:

```text
CRITICAL_PROCESS_DIED
MEMORY_MANAGEMENT
SYSTEM_SERVICE_EXCEPTION
IRQL_NOT_LESS_OR_EQUAL
```

The stop code is a troubleshooting clue rather than automatic proof of one specific cause.

Possible causes may include:

- Driver problems
- RAM problems
- Storage issues
- Corrupted system files
- Hardware failure
- Software conflicts

## Record the Exact Error

Useful ticket information may include:

```text
Stop code:
Exact code displayed

Time:
When crash occurred

Recent changes:
Driver, software, hardware, or update

Frequency:
One-time or recurring
```

A photo of the stop code may be useful if organizational policy permits it and no sensitive information is exposed.

## Crash Dumps

Windows can create memory dump files after system crashes.

Common locations may include:

```text
C:\Windows\MEMORY.DMP
```

and:

```text
C:\Windows\Minidump
```

Crash dumps can contain technical information that helps identify:

- Drivers
- Memory addresses
- Faulting components
- System state during crash

Detailed dump analysis may be escalated to a more advanced support team.

## Event Viewer

Event Viewer can provide information about startup and crash problems.

Open:

```text
eventvwr.msc
```

Useful areas include:

```text
Windows Logs
→ System
```

and:

```text
Windows Logs
→ Application
```

Look for events around the time of the failure.

Useful details may include:

- Event ID
- Source
- Timestamp
- Error level
- Device or service involved

Not every warning or error is necessarily the root cause.

## Reliability Monitor

Windows Reliability Monitor provides a timeline of system stability events.

It may show:

- Application crashes
- Windows failures
- Hardware errors
- Update installations
- Software installations

It can be useful for correlating a crash with a recent system change.

One way to open it is by searching Windows for:

```text
View reliability history
```

## System File Checker

Corrupted Windows system files can contribute to instability.

Run from an elevated Command Prompt or PowerShell:

```text
sfc /scannow
```

SFC checks protected Windows system files and attempts to repair corruption.

Possible results may indicate:

- No integrity violations
- Corrupted files repaired
- Files could not be repaired

## DISM

DISM can repair the Windows component store.

Commands may include:

```text
DISM /Online /Cleanup-Image /CheckHealth
```

```text
DISM /Online /Cleanup-Image /ScanHealth
```

```text
DISM /Online /Cleanup-Image /RestoreHealth
```

After DISM completes, SFC may be run again:

```text
sfc /scannow
```

## CHKDSK

CHKDSK checks a Windows file system and storage volume for errors.

Example:

```text
chkdsk C:
```

A repair operation may require administrative privileges and a restart.

Example:

```text
chkdsk C: /f
```

`/f` tells CHKDSK to fix detected file-system errors.

Storage commands should be used carefully, especially on systems with suspected failing drives.

## Storage Problems

Storage problems can cause:

- Slow boot
- Freezing
- File corruption
- Startup failure
- Blue screens
- Repeated repair attempts

Possible signs include:

- Disk-related Event Viewer errors
- SMART warnings
- Clicking or abnormal drive noises
- File-system errors
- Very slow disk access

Important data should be protected before performing risky repair operations on a failing drive.

## Memory Problems

Faulty RAM can cause:

- Random crashes
- BSODs
- Application failures
- Boot failures
- Corrupted data

Windows includes a memory diagnostic tool.

Search for:

```text
Windows Memory Diagnostic
```

A system restart may be required to perform the test.

Hardware diagnostics may also be available from the device manufacturer.

## Overheating

Overheating can cause:

- Unexpected shutdown
- Crashes
- Performance throttling
- Instability

Possible checks include:

- Air vents
- Cooling fans
- Dust buildup
- Environmental temperature

Hardware should be powered down before physical cleaning when appropriate.

## Boot Order

If Windows does not load, BIOS/UEFI boot order may need to be checked.

Example:

```text
1. Windows Boot Manager
2. Internal SSD
3. USB
4. Network
```

A system attempting to boot from the wrong device may fail to load Windows.

BIOS/UEFI settings should not be changed without understanding the effect.

## Windows Boot Manager

Modern Windows systems commonly use Windows Boot Manager.

If Windows Boot Manager is missing or the boot configuration is damaged, Windows may fail before reaching the operating system.

Advanced repair of boot configuration may require escalation or use of recovery tools.

## BitLocker Considerations

BitLocker may protect the Windows drive.

Certain recovery actions can trigger a BitLocker recovery prompt.

Before making major boot, firmware, or recovery changes, confirm whether:

- BitLocker is enabled
- Recovery key is available
- Organizational policy permits the change

A technician should not proceed with changes that could lock the user out of encrypted data without appropriate recovery information.

## Automatic Repair Loop

A system may repeatedly display:

```text
Preparing Automatic Repair
```

or repeatedly return to recovery options.

Possible causes include:

- Failed update
- Corrupted Windows files
- Storage problems
- Boot configuration issue
- Driver problem

Possible troubleshooting may include:

1. Try Startup Repair.
2. Try Safe Mode.
3. Review recent changes.
4. Uninstall recent update if appropriate.
5. Use System Restore if available.
6. Run system repair tools.
7. Check storage health.
8. Escalate if Windows cannot be recovered safely.

## Black Screen After Sign-In

A black screen after sign-in may involve:

- Display driver
- Windows Explorer
- Startup application
- External monitor configuration
- Graphics hardware
- User profile

Possible checks include:

1. Verify monitor power and input.
2. Disconnect unnecessary displays.
3. Try `Ctrl + Shift + Esc`.
4. Check whether Task Manager opens.
5. Test Safe Mode.
6. Review graphics driver.
7. Review startup applications.
8. Check Event Viewer.
9. Escalate if the issue continues.

## Windows Explorer

If the desktop does not appear but Task Manager works, Windows Explorer may not have started correctly.

The Windows shell process is:

```text
explorer.exe
```

This can be useful when troubleshooting a missing desktop, taskbar, or Start menu.

## Repeated Restart Loop

A restart loop may occur when Windows repeatedly:

```text
Starts
→ Fails
→ Restarts
→ Starts
→ Fails
```

Possible causes include:

- Failed update
- Driver issue
- Boot problem
- Hardware failure
- System corruption

Safe Mode or WinRE can help interrupt the cycle and allow troubleshooting.

## Example Scenario — BSOD After Driver Update

**Problem:**

A user reports that the computer began crashing after a graphics driver update.

Possible process:

1. Record the stop code.
2. Confirm when the driver was updated.
3. Boot into Safe Mode if normal mode is unstable.
4. Open Device Manager.
5. Review the graphics driver.
6. Roll back the driver if appropriate.
7. Restart normally.
8. Verify stability.
9. Review Event Viewer.
10. Document the resolution.

## Example Scenario — Windows Will Not Boot After Update

**Problem:**

A workstation installed updates and now cannot reach the desktop.

Possible process:

1. Enter WinRE.
2. Try Startup Repair.
3. Attempt Safe Mode.
4. Review recent update history if accessible.
5. Use **Uninstall Updates** if the update is strongly suspected.
6. Try System Restore if an appropriate restore point exists.
7. Run repair tools if needed.
8. Verify Windows starts.
9. Recheck Windows Update.
10. Document findings.

## Example Scenario — System Starts Only in Safe Mode

**Problem:**

Windows crashes during normal startup but works in Safe Mode.

This suggests that the core Windows environment can start.

Possible causes may include:

- Third-party driver
- Startup application
- Third-party service
- Recently installed software

Possible process:

1. Review recent changes.
2. Check Device Manager.
3. Review startup applications.
4. Review third-party services.
5. Check Event Viewer.
6. Remove or roll back the suspected change.
7. Restart normally.
8. Verify stability.
9. Document findings.

## Example Scenario — Random System Crashes

**Problem:**

A user reports several unexplained crashes during the week.

Possible process:

1. Ask when each crash occurs.
2. Record any stop codes.
3. Check Reliability Monitor.
4. Review Event Viewer.
5. Check recent drivers and updates.
6. Run system-file checks.
7. Check storage health.
8. Run memory diagnostics if appropriate.
9. Check overheating or hardware symptoms.
10. Escalate if the cause remains unclear.

## Example Scenario — Slow Startup

**Problem:**

Windows eventually starts but takes much longer than normal.

Possible process:

1. Check Task Manager startup applications.
2. Check available disk space.
3. Check disk utilization.
4. Review Windows Update status.
5. Check Event Viewer.
6. Review recently installed software.
7. Check drive health.
8. Disable unnecessary startup applications if appropriate.
9. Restart and compare startup performance.
10. Document findings.

## Reset This PC

Windows includes:

```text
Reset this PC
```

This is a more significant recovery option.

Depending on the selected option, Windows may allow:

- Keep my files
- Remove everything

A reset can remove applications and settings.

Before using it:

- Back up important data
- Confirm organizational policy
- Confirm BitLocker recovery information
- Document installed applications
- Verify account access
- Obtain appropriate approval

Resetting Windows should not be the first troubleshooting step.

## Reinstallation / Reimaging

If Windows cannot be repaired, an organization may choose to:

- Reimage the workstation
- Reinstall Windows
- Replace the device

This should normally happen after appropriate troubleshooting and data-protection steps.

Before reimaging:

- Protect user data
- Confirm backups
- Confirm encryption status
- Record applications
- Confirm required licenses
- Follow company imaging procedures

## Escalation

Startup and crash issues may require escalation when:

- Windows cannot boot after standard recovery
- Startup Repair fails
- System Restore fails
- SFC or DISM cannot repair corruption
- Storage failure is suspected
- Memory failure is suspected
- Hardware replacement is required
- BitLocker recovery is required
- BIOS or firmware changes are necessary
- Crash-dump analysis is needed
- The system contains critical business data
- Reimaging or replacement is required

## Example Escalation Notes

```text
Issue:
Workstation repeatedly crashes during startup.

Symptoms:
Windows displays a BSOD before reaching the desktop.

Troubleshooting:
- Exact stop code documented
- External devices disconnected
- Safe Mode tested successfully
- Recent driver update identified
- Driver rollback attempted
- SFC completed
- Event Viewer reviewed
- Crash continues during normal startup

Escalation:
Requires advanced operating system or driver investigation.
```

## Ticket Documentation Example

```text
User reported Windows crashing immediately after sign-in.

Confirmed issue occurs during normal startup.

Booted successfully into Safe Mode.

Reviewed recent system changes and identified a recently updated display driver.

Rolled back the display driver and restarted the workstation.

Windows started normally.

Tested sign-in and normal desktop operation.

No additional crashes observed during verification.

Documented driver version and resolution in ticket.
```

## Troubleshooting Checklist

When troubleshooting Windows startup and crash problems, I can follow this order:

1. Gather symptoms and exact errors.
2. Determine where startup fails.
3. Ask about recent changes.
4. Disconnect unnecessary external devices.
5. Try a normal restart when possible.
6. Use WinRE if Windows cannot start.
7. Try Startup Repair.
8. Test Safe Mode.
9. Review recent drivers, updates, and software.
10. Check Device Manager.
11. Review Event Viewer.
12. Review Reliability Monitor.
13. Run SFC if corruption is suspected.
14. Run DISM when Windows image repair is needed.
15. Check storage health.
16. Run memory diagnostics when appropriate.
17. Check for overheating or hardware symptoms.
18. Verify BitLocker considerations before major recovery work.
19. Test normal startup after changes.
20. Verify system stability.
21. Document findings and resolution.
22. Escalate when the issue exceeds support scope.

## Key Takeaways

Some of the most important startup and crash troubleshooting concepts include:

- Determine where in the startup process the failure occurs.
- Recent changes are important clues.
- Safe Mode helps isolate driver, service, and startup-software problems.
- Startup Repair can address some Windows boot problems.
- WinRE provides several recovery options when Windows cannot start normally.
- Driver problems can cause startup failures and blue screens.
- Exact BSOD stop codes should be documented.
- Event Viewer and Reliability Monitor can provide useful evidence.
- SFC checks protected Windows system files.
- DISM can repair the Windows component store.
- Storage and memory problems can cause crashes that appear to be software issues.
- BitLocker recovery must be considered before major boot or firmware changes.
- Resetting or reimaging Windows should come after less disruptive troubleshooting.
- A successful repair should always be verified through normal startup and system use.
- Clear documentation makes escalation more effective.

Windows startup and crash troubleshooting combines operating system recovery, driver troubleshooting, hardware awareness, Windows diagnostic tools, user communication, verification, and careful escalation.
