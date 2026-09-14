# Windows Startup & BSOD Ticket

## Ticket Summary

**Issue:** Windows repeatedly crashes with a blue screen shortly after startup.

**User Impact:** User cannot reliably access the workstation or complete normal work.

**Priority:** High

**Device:** Windows 11 workstation

## User Report

User reported that the workstation began displaying a blue screen shortly after signing into Windows.

The computer restarted automatically and repeated the same behavior.

The user stated that the issue began after a recent device-driver update.

## Symptoms

- Windows powers on normally
- Sign-in screen appears
- User can sign in
- Blue screen occurs shortly afterward
- Workstation automatically restarts
- Issue repeats after normal startup
- Problem began after a recent driver change

## Initial Information Gathering

Before making changes, gathered:

- When the problem started
- Exact BSOD stop code if visible
- Recent hardware or software changes
- Recent Windows updates
- Recent driver updates
- Whether Safe Mode could be reached
- Whether important user data was backed up

The user reported no new hardware installation.

A recently updated device driver was the most significant recent change.

## Step 1 — Document the Stop Code

The blue screen displayed a stop code.

Example:

```text
SYSTEM_THREAD_EXCEPTION_NOT_HANDLED
```

The exact stop code should be recorded rather than writing only:

```text
Computer blue screened
```

A stop code can provide an important troubleshooting clue.

## Step 2 — Attempt Normal Restart

Allowed the workstation to restart normally.

The issue occurred again shortly after sign-in.

Because the crash was repeatable, further troubleshooting was required.

## Step 3 — Enter Windows Recovery Environment

Used Windows Recovery Environment to access advanced startup options.

Possible path:

```text
Troubleshoot
→ Advanced options
→ Startup Settings
→ Restart
```

Then selected Safe Mode.

The exact recovery screens may vary by Windows version.

## Step 4 — Test Safe Mode

Windows successfully started in Safe Mode.

The system remained stable and did not immediately crash.

This suggested that the problem could involve:

- Device driver
- Startup software
- Service
- Recently installed application

Because the issue began after a driver update, the driver became the primary suspect.

## Step 5 — Open Device Manager

Opened:

```text
Device Manager
```

Reviewed the device associated with the recent driver update.

Checked:

- Device status
- Driver provider
- Driver date
- Driver version

The driver had been updated shortly before the crashes began.

## Step 6 — Roll Back the Driver

Opened the affected device properties.

Possible path:

```text
Device Manager
→ Device
→ Properties
→ Driver
→ Roll Back Driver
```

The rollback option was available.

Rolled the driver back to the previous working version.

No driver was downloaded from an untrusted third-party source.

## Step 7 — Restart Windows Normally

Restarted the workstation normally.

Windows reached the desktop without immediately crashing.

Allowed the system to remain running while basic functions were tested.

## Step 8 — Review Reliability Monitor

Opened Reliability Monitor to review recent stability history.

Reliability Monitor showed critical Windows failures beginning around the same time as the driver update.

This supported the suspected driver-related cause.

## Step 9 — Review Event Viewer

Opened:

```text
eventvwr.msc
```

Reviewed relevant events under:

```text
Windows Logs
→ System
```

Looked for events around the time of the crashes.

Recorded relevant timestamps and error information.

Event Viewer can provide supporting evidence, but one event alone should not automatically be treated as the root cause.

## Step 10 — Check Windows Update

Opened:

```text
Settings
→ Windows Update
```

Checked update history for recent changes.

No additional failed Windows updates appeared directly related to the crash.

## Resolution

The repeated BSODs began after a recently updated device driver.

Windows remained stable in Safe Mode.

The affected driver was rolled back to the previous version.

After restarting normally, the workstation stopped crashing.

## Verification

Verified that:

- Windows started normally
- User could sign in
- No BSOD occurred
- Device remained functional
- Network connectivity worked
- Applications opened normally
- Workstation remained stable during testing

The user confirmed they could return to normal work.

## Root Cause

```text
Recently updated device driver
```

The timing of the driver update, Safe Mode stability, and successful driver rollback supported the conclusion that the newer driver was causing the crashes.

## Ticket Closure Notes

```text
User reported repeated BSOD crashes shortly after Windows sign-in.

Recorded BSOD stop code and reviewed recent system changes.

User reported a recent device-driver update before issue began.

Normal restart reproduced the crash.

Booted workstation into Safe Mode successfully.

System remained stable in Safe Mode.

Reviewed affected device in Device Manager and confirmed recent driver version.

Rolled driver back to previous working version.

Restarted Windows normally.

Reviewed Reliability Monitor and Event Viewer for supporting crash information.

Verified workstation started normally and remained stable.

User opened required applications and resumed normal work.

No additional BSOD occurred during testing.

Issue resolved.
```

## Alternative Troubleshooting Path

If the driver rollback did not resolve the issue, additional troubleshooting could include:

- Startup Repair
- Uninstalling a recent approved update
- Disabling problematic startup software
- Running System File Checker
- Running DISM
- Running memory diagnostics
- Checking storage health
- Reviewing crash dump information
- Testing recently installed hardware
- Checking BIOS/UEFI settings
- Escalating for hardware diagnostics

## System File Checker

If Windows system-file corruption was suspected, an elevated command prompt could be used:

```text
sfc /scannow
```

System File Checker verifies protected Windows system files and attempts to repair corrupted copies.

## DISM

If Windows image corruption was suspected, DISM could be used:

```text
DISM /Online /Cleanup-Image /RestoreHealth
```

A common progression is:

```text
SFC
 |
 v
DISM if needed
 |
 v
Restart
 |
 v
Retest
```

The exact troubleshooting order depends on the symptoms and evidence.

## Windows Memory Diagnostic

Repeated crashes can also be caused by memory problems.

A memory diagnostic may be appropriate if symptoms suggest unstable RAM.

Memory-related troubleshooting may require escalation depending on support scope.

## Storage Health

Startup failures and crashes may also involve:

- SSD failure
- HDD failure
- File-system corruption
- Insufficient storage
- Disk errors

Repeated disk-related errors should be investigated carefully because data loss may be possible.

## Crash Dump Files

Windows may create memory dump files after a system crash.

These can help advanced support teams determine what caused the failure.

Crash dump analysis may exceed first-line help desk scope and can be escalated to desktop engineering or systems support.

## Automatic Repair Loop

A workstation may repeatedly display:

```text
Preparing Automatic Repair
```

or:

```text
Automatic Repair couldn't repair your PC
```

Possible troubleshooting may include:

- Startup Repair
- Safe Mode
- Recent update review
- Driver review
- System file repair
- Recovery options

User data should be protected before performing destructive recovery actions.

## Black Screen Scenario

A Windows startup problem may also appear as a black screen.

Possible causes include:

- Display driver
- Monitor issue
- Docking station
- Windows Explorer failure
- Incomplete startup
- Hardware problem

The technician should determine whether Windows itself failed to start or whether only the display failed.

## BitLocker Consideration

Recovery troubleshooting may sometimes trigger a BitLocker recovery screen.

If a BitLocker recovery key is required:

```text
Do not attempt to bypass encryption.
```

Follow the organization's approved BitLocker recovery process.

## Escalation Alternative

If the workstation continued crashing after reasonable troubleshooting, the ticket could be escalated with notes such as:

```text
Issue:
Windows workstation repeatedly BSODs shortly after startup.

Impact:
User cannot reliably use workstation.

Troubleshooting:
- BSOD stop code documented
- Safe Mode tested
- Recent driver reviewed
- Driver rollback attempted
- Windows Update history reviewed
- SFC completed
- DISM completed
- Reliability Monitor reviewed
- Event Viewer reviewed
- Crash continues during normal startup

Finding:
Issue persists after standard software troubleshooting.

Escalation:
Desktop engineering or hardware support required for crash-dump, memory, storage, or deeper driver analysis.
```

## Data Protection

When troubleshooting serious startup or crash problems:

- Avoid deleting user data
- Avoid formatting the drive prematurely
- Avoid reimaging before recovery needs are reviewed
- Confirm backup status when possible
- Preserve relevant crash information
- Escalate when hardware failure or data loss is suspected

Restoring the workstation quickly is important, but protecting user data is also part of the support process.

## Skills Demonstrated

- Windows startup troubleshooting
- BSOD troubleshooting
- Safe Mode
- Windows Recovery Environment
- Device Manager
- Driver rollback
- Reliability Monitor
- Event Viewer
- Windows Update review
- SFC and DISM concepts
- Root-cause isolation
- Data protection awareness
- Verification
- Ticket documentation
- Escalation awareness
