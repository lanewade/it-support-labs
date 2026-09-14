# Storage & Drive Troubleshooting

This note documents my study and practice of troubleshooting storage problems involving SSDs, HDDs, partitions, drive detection, disk space, file-system errors, performance issues, and potential drive failure in Windows 10/11.

The goal is to use a structured IT support process to identify whether a storage issue is caused by hardware, cabling, drivers, partitions, file-system corruption, insufficient disk space, or a failing drive while protecting the user's data.

## Common Storage Problems

Common symptoms can include:

- Drive not detected
- Drive missing from File Explorer
- Windows reports low disk space
- Computer becomes very slow
- Files cannot be opened
- Files become corrupted
- Applications fail to install
- Windows Update fails due to low storage
- Drive appears in BIOS/UEFI but not Windows
- Drive appears in Disk Management but not File Explorer
- External drive disconnects intermittently
- SMART warning appears
- HDD makes unusual noises
- Windows reports file-system errors
- Drive reports incorrect capacity
- Partition is missing
- Drive letter is missing
- System freezes during disk activity

## Initial Information Gathering

Before making changes, I would gather information about the issue.

Questions may include:

- When did the problem begin?
- Is the affected drive internal or external?
- Is it an SSD or HDD?
- Is the drive used for Windows, applications, or user files?
- Does the drive appear in File Explorer?
- Does the drive appear in Disk Management?
- Does BIOS/UEFI detect the drive?
- Was the drive recently installed or replaced?
- Has the computer been dropped or damaged?
- Has there been a recent power outage?
- Are there unusual noises from the drive?
- Is important user data stored on the drive?
- Is there a current backup?

Protecting data is a priority when storage failure is suspected.

# HDD vs SSD

## HDD

HDD stands for:

**Hard Disk Drive**

HDDs store data on spinning magnetic platters.

Common characteristics include:

- Mechanical moving parts
- Larger capacities for lower cost
- Slower than SSDs
- More vulnerable to physical shock

Possible failure symptoms can include:

- Clicking
- Grinding
- Slow access
- Repeated read errors
- Drive disappearing intermittently

Unusual mechanical noises can be a warning sign of hardware failure.

## SSD

SSD stands for:

**Solid-State Drive**

SSDs store data using flash memory.

Common characteristics include:

- No moving parts
- Faster access
- Lower latency
- Lower power consumption

Possible failure symptoms can include:

- Drive disappearing
- Read/write errors
- Sudden read-only behavior
- File corruption
- Failure to boot

SSDs do not usually produce mechanical warning noises before failure.

# SATA Storage

SATA stands for:

**Serial ATA**

SATA is commonly used for:

- HDDs
- 2.5-inch SSDs
- Optical drives

A SATA drive may use:

```text
SATA Data Cable
+
SATA Power Cable
```

A problem with either connection can prevent the drive from working.

# M.2

M.2 is a physical form factor commonly used for SSDs.

M.2 drives may use different interfaces.

Examples include:

- SATA
- NVMe

An M.2 slot does not automatically mean the drive is NVMe.

Compatibility should be verified before installation.

# NVMe

NVMe stands for:

**Non-Volatile Memory Express**

NVMe SSDs commonly use PCIe rather than the SATA interface.

Benefits may include:

- Higher throughput
- Lower latency
- Faster storage performance

The motherboard, slot, and drive must be compatible.

# Step 1 — Determine Whether the Drive Is Detected

Start by determining where the drive appears.

Possible places to check include:

```text
File Explorer
Disk Management
Device Manager
BIOS / UEFI
```

This helps narrow down the problem.

Example:

```text
Drive appears in BIOS
but not Windows
→ Possible Windows, driver, partition, or configuration issue

Drive does not appear in BIOS
→ Possible hardware, cable, power, or drive failure
```

# File Explorer

Open:

```text
File Explorer
→ This PC
```

Check whether the drive appears with a drive letter such as:

```text
C:
D:
E:
```

If the drive is missing from File Explorer, continue checking other tools.

# Disk Management

Disk Management is one of the most useful Windows storage troubleshooting tools.

Open:

```text
diskmgmt.msc
```

Disk Management can show:

- Physical disks
- Partitions
- Drive letters
- File systems
- Unallocated space
- Disk status
- Volume status

A disk may be visible here even when it does not appear in File Explorer.

# Device Manager

Open:

```text
devmgmt.msc
```

Look under:

```text
Disk drives
```

Device Manager can help determine whether Windows detects the hardware.

It can also provide information about:

- Driver status
- Device errors
- Hardware detection
- Device properties

# BIOS / UEFI

If Windows does not detect the drive, BIOS/UEFI can help determine whether the system hardware sees it.

If the drive does not appear in BIOS/UEFI, possible causes include:

- Loose SATA cable
- Failed power connection
- Failed drive
- Disabled storage controller
- Incorrect M.2 slot
- Hardware compatibility issue

BIOS/UEFI settings should only be changed when the effect is understood.

# Step 2 — Check Physical Connections

For a desktop computer, storage troubleshooting may involve checking:

- SATA data cable
- SATA power cable
- M.2 seating
- Power connector
- External USB cable
- External power supply

Before opening a computer:

- Shut it down
- Disconnect power
- Follow ESD precautions
- Follow organizational procedures

A loose cable can cause intermittent or complete drive failure.

# External Drive Troubleshooting

For USB drives or external storage, possible checks include:

1. Try another USB port.
2. Try another known-good cable.
3. Avoid an unpowered USB hub.
4. Check whether the drive requires external power.
5. Test on another authorized computer.
6. Check Disk Management.
7. Check Device Manager.

If the drive works on another system, the original computer may have a port, driver, or power problem.

# Step 3 — Check Available Disk Space

Low disk space can cause:

- Slow performance
- Failed updates
- Failed application installations
- Temporary file problems
- System instability

Check:

```text
Settings
→ System
→ Storage
```

or:

```text
File Explorer
→ This PC
```

The system drive is commonly:

```text
C:
```

# Storage Settings

Windows Storage settings can help identify space used by:

- Applications
- Temporary files
- Documents
- Downloads
- System files
- Other categories

Before deleting anything, determine whether the files belong to the user or are required by applications.

# Disk Cleanup

Windows can remove certain temporary files.

Search for:

```text
Disk Cleanup
```

Depending on the system, cleanup options may include:

- Temporary files
- Recycle Bin
- Update cleanup
- Temporary internet files

Important user files should not be removed without permission.

# Storage Sense

Windows includes:

`Storage Sense`

Storage Sense can automatically manage some temporary files and storage cleanup.

It should be configured according to user needs and organizational policy.

# Step 4 — Check Drive Letter

A healthy volume may exist without a drive letter.

In Disk Management, a volume might appear without:

```text
D:
E:
F:
```

If appropriate, a drive letter can be assigned.

Conceptually:

```text
Volume
→ Change Drive Letter and Paths
→ Add
```

Changing drive letters can affect applications that rely on an existing path, so this should be done carefully.

# Drive Letter Conflicts

A mapped network drive or another device can sometimes use the same drive letter.

Example:

```text
USB Drive expects E:
Network Drive already uses E:
```

Assigning another available letter may resolve the issue.

# Step 5 — Check Partition Status

Disk Management may show a disk as:

- Online
- Offline
- Healthy
- Unallocated
- Not initialized
- RAW

Each status has a different meaning.

# Unallocated Space

Unallocated space is storage that is not currently part of a partition.

Example:

```text
Disk 1
500 GB

[ 250 GB NTFS ]
[ 250 GB Unallocated ]
```

Creating a new partition modifies the disk and should only be done when appropriate.

If the disk previously contained important data, do not create a new partition before determining why the original partition is missing.

# RAW File System

A volume may sometimes appear as:

`RAW`

This can indicate that Windows does not recognize a valid file system.

Possible causes include:

- File-system corruption
- Damaged partition
- Failing storage device

Formatting a RAW drive destroys existing file-system structures and can make data recovery more difficult.

If important data exists, stop and protect the data before formatting.

# Initializing a Disk

A new disk may need to be initialized before use.

Windows may offer:

- GPT
- MBR

Initialization changes disk metadata.

A disk containing important existing data should not be initialized simply because Windows prompts for it without first confirming the drive's history.

# GPT

GPT stands for:

**GUID Partition Table**

GPT is commonly used on modern systems.

Advantages include:

- Support for large disks
- More partitions
- Compatibility with UEFI systems

# MBR

MBR stands for:

**Master Boot Record**

MBR is an older partitioning method.

It has more limitations than GPT.

Modern Windows systems commonly use GPT for system disks.

# Step 6 — Check File System

Windows commonly uses:

`NTFS`

Other file systems may include:

- FAT32
- exFAT

Different file systems are used for different purposes.

# NTFS

NTFS supports features such as:

- File permissions
- Journaling
- Large files
- Encryption features
- Compression

It is commonly used for Windows system and internal data drives.

# FAT32

FAT32 has broad compatibility but limitations.

A major limitation is a maximum single-file size of approximately:

`4 GB`

# exFAT

exFAT is often used for removable storage and supports larger files than FAT32.

# Step 7 — Run CHKDSK

CHKDSK can check the file system for errors.

Basic check:

```text
chkdsk C:
```

To fix file-system errors:

```text
chkdsk C: /f
```

`/f` tells CHKDSK to repair detected file-system errors.

The system drive may require a restart to perform repairs.

# CHKDSK /r

Another option is:

```text
chkdsk C: /r
```

`/r` attempts to locate bad sectors and recover readable information.

This can take a long time and places additional activity on the drive.

If hardware failure is suspected, protecting important data may be more important than running an intensive scan.

# CHKDSK Caution

CHKDSK is not a substitute for a backup.

If a drive is showing signs of physical failure, repeatedly scanning or repairing it can stress the device.

Possible signs of physical failure include:

- Clicking
- Grinding
- Repeated disconnects
- SMART warnings
- Severe read errors

In those situations, stop and consider escalation or data recovery procedures.

# Step 8 — Check SMART Status

SMART stands for:

**Self-Monitoring, Analysis and Reporting Technology**

SMART information can provide health indicators for storage devices.

It may report conditions such as:

- Healthy
- Warning
- Failing

SMART is useful, but it does not guarantee that a drive is healthy.

A drive can fail even without a prior SMART warning.

# PowerShell Storage Information

PowerShell can provide basic disk information.

Example:

```powershell
Get-Disk
```

This may show:

- Disk number
- Friendly name
- Operational status
- Size
- Partition style

Another useful command:

```powershell
Get-PhysicalDisk
```

Depending on the hardware and Windows configuration, this may display health-related information.

# Step 9 — Check Event Viewer

Storage problems may appear in Event Viewer.

Open:

```text
eventvwr.msc
```

Check:

```text
Windows Logs
→ System
```

Look for disk or file-system errors around the time the issue occurred.

Possible sources may relate to:

- Disk
- NTFS
- Storage controller
- File system

Record:

- Event ID
- Source
- Timestamp
- Error message

Do not assume every disk-related warning proves drive failure.

# Step 10 — Check Device Drivers

Storage controllers and drives rely on Windows drivers.

Device Manager can be used to review:

- Disk drives
- Storage controllers
- IDE ATA/ATAPI controllers
- NVMe controllers

A problem beginning after a driver update may require:

- Driver rollback
- Vendor-supported driver
- Windows Update review

Driver changes should be documented.

# Step 11 — Check Performance

Task Manager can help identify whether storage is under heavy load.

Open:

```text
Ctrl + Shift + Esc
```

Check:

```text
Performance
→ Disk
```

Information may include:

- Active time
- Read speed
- Write speed
- Response time

A drive showing sustained 100% active time may contribute to system slowness.

However, high activity does not automatically mean the drive is failing.

# Resource Monitor

Windows Resource Monitor can provide more detail about disk activity.

Open:

```text
resmon
```

The Disk section can show:

- Processes using the disk
- Read activity
- Write activity
- File paths
- Response times

This can help distinguish a storage problem from a program simply using the drive heavily.

# Fragmentation

Traditional HDDs can become fragmented over time.

Windows includes drive optimization tools.

Search for:

```text
Defragment and Optimize Drives
```

For HDDs, optimization may include defragmentation.

For SSDs, Windows uses SSD-appropriate optimization behavior such as TRIM.

An SSD should not be manually treated like an HDD without understanding the tool's behavior.

# TRIM

TRIM helps SSDs manage unused storage blocks efficiently.

Modern Windows systems generally manage TRIM automatically.

It helps maintain SSD performance over time.

# HDD Mechanical Failure

Possible warning signs include:

- Clicking
- Grinding
- Repeated spin-up/spin-down
- Slow reads
- Read errors
- Drive disappearing

If a drive makes abnormal mechanical noises:

1. Minimize unnecessary use.
2. Protect important data.
3. Avoid repeated stress testing.
4. Escalate for replacement or data recovery.

# SSD Failure Signs

Possible SSD failure symptoms include:

- Sudden read-only state
- Drive not detected
- Frequent errors
- Corrupted files
- Repeated freezing during storage access
- SMART warnings

Because SSDs have no moving parts, failure may occur without audible warning.

# Bad Sectors

A bad sector is an area of storage that cannot reliably store or retrieve data.

HDDs may develop bad sectors due to:

- Wear
- Physical damage
- Media degradation

Modern drives may automatically remap some failing sectors.

Increasing bad-sector counts can indicate a worsening drive.

# Data Protection First

When storage failure is suspected, data protection becomes more important than aggressive troubleshooting.

Before performing destructive actions, determine whether:

- Important data is backed up
- User files need to be copied
- Encryption is enabled
- Recovery keys are available
- Company policy requires escalation
- Drive replacement is planned

# BitLocker

BitLocker may encrypt the Windows drive.

Before replacing, moving, or troubleshooting an encrypted drive, verify:

- BitLocker status
- Recovery key availability
- Organizational policy

A technician should avoid making changes that could lock the user out of encrypted data.

# Step 12 — Test with a Known-Good Component

When appropriate, hardware isolation can help identify the problem.

Examples include:

- Known-good SATA cable
- Known-good USB cable
- Different USB port
- Different SATA port
- Another compatible drive

Testing with known-good components helps determine whether the fault is in the drive or another part of the system.

# Example Scenario — Drive Missing from File Explorer

**Problem:**

A newly connected secondary drive does not appear in File Explorer.

Possible process:

1. Open Disk Management.
2. Determine whether the disk is detected.
3. Check whether the partition exists.
4. Check whether a drive letter is assigned.
5. Confirm the file system is recognized.
6. Verify hardware connections.
7. Assign a drive letter if appropriate.
8. Test File Explorer.
9. Document the result.

# Example Scenario — Drive Not Detected Anywhere

**Problem:**

A secondary SATA drive is missing from Windows and BIOS/UEFI.

Possible process:

1. Shut down the computer.
2. Disconnect power.
3. Follow ESD precautions.
4. Check SATA data cable.
5. Check SATA power cable.
6. Reseat connections.
7. Try a known-good cable.
8. Try another supported SATA port if appropriate.
9. Check BIOS/UEFI again.
10. Escalate for drive replacement if the device remains undetected.

# Example Scenario — Low Disk Space

**Problem:**

A user's computer reports that the C: drive is almost full.

Possible process:

1. Check available storage.
2. Review Windows Storage settings.
3. Identify large categories.
4. Review temporary files.
5. Empty Recycle Bin if appropriate.
6. Ask before deleting user files.
7. Remove unnecessary software if approved.
8. Recheck available space.
9. Verify affected applications work.
10. Document the cleanup.

# Example Scenario — Drive Appears as RAW

**Problem:**

An external drive that previously contained files now appears as RAW.

Possible process:

1. Stop unnecessary writes to the drive.
2. Confirm whether important data exists.
3. Do not immediately format the drive.
4. Check Disk Management.
5. Check drive health.
6. Review Event Viewer.
7. Determine whether backup exists.
8. Escalate for data recovery if necessary.

# Example Scenario — Slow Computer with 100% Disk Usage

**Problem:**

A user reports that Windows is extremely slow.

Task Manager shows:

```text
Disk: 100%
```

Possible process:

1. Open Task Manager.
2. Identify processes using the disk.
3. Open Resource Monitor if needed.
4. Check available disk space.
5. Review Windows Update activity.
6. Check for antivirus scans.
7. Review Event Viewer.
8. Check drive health.
9. Restart and retest.
10. Escalate if storage hardware problems are suspected.

# Example Scenario — External Drive Disconnects

**Problem:**

A USB drive disconnects intermittently.

Possible process:

1. Try another USB port.
2. Replace the cable.
3. Avoid unpowered hubs.
4. Check Device Manager.
5. Check Event Viewer.
6. Test on another authorized computer.
7. Check drive health.
8. Protect data if instability continues.
9. Document findings.

# Example Scenario — HDD Making Clicking Noise

**Problem:**

A user's hard drive is clicking and the computer is freezing.

Possible process:

1. Stop unnecessary disk activity.
2. Determine whether important data is backed up.
3. Avoid repeated CHKDSK or stress testing.
4. Document the symptoms.
5. Escalate for drive replacement or data recovery.
6. Follow organizational data-protection procedures.

The priority is protecting data, not forcing the failing drive to continue operating.

# Example Scenario — Windows Reports File-System Errors

Possible process:

1. Back up important data.
2. Review Event Viewer.
3. Check drive health.
4. Run CHKDSK when appropriate.
5. Restart if required.
6. Verify the file system.
7. Monitor for recurring errors.
8. Escalate if errors return.

# Replacing a Drive

Drive replacement may be necessary when:

- Hardware failure is confirmed
- SMART reports failure
- Drive disappears repeatedly
- Bad sectors continue increasing
- Mechanical failure is suspected
- Performance is severely degraded
- Manufacturer diagnostics fail

Before replacement:

- Back up user data
- Confirm encryption status
- Record required applications
- Follow asset procedures
- Confirm recovery media or imaging process

# Cloning

Drive cloning copies data from one drive to another.

It may be useful during an upgrade or replacement.

However, cloning a failing drive can be risky.

If the source drive is physically failing, professional or specialized recovery methods may be safer.

# Imaging

Organizations may use a standard system image to deploy Windows.

A replacement drive may be:

```text
Installed
→ Imaged
→ Updated
→ Applications installed
→ User data restored
```

Imaging procedures should follow organizational standards.

# Storage Troubleshooting and Backups

Storage troubleshooting highlights why backups are important.

A backup protects against:

- Drive failure
- Accidental deletion
- File corruption
- Malware
- Hardware loss

Redundancy and backups are not the same thing.

A second drive does not automatically mean important files are backed up.

# Escalation

Storage problems should be escalated when:

- Drive failure is suspected
- Important data is at risk
- SMART reports failure
- Drive makes abnormal mechanical noises
- Drive contains confidential or business-critical data
- BitLocker recovery is required
- File-system corruption cannot be repaired
- Partition recovery is required
- Data recovery is required
- Hardware replacement is needed
- RAID or enterprise storage is involved

# Example Escalation Notes

```text
Issue:
User reports workstation freezing and extremely slow file access.

Symptoms:
- Disk activity remains near 100%
- HDD produces intermittent clicking noise
- File access frequently hangs

Troubleshooting:
- Task Manager reviewed
- Resource Monitor reviewed
- Disk space verified
- Event Viewer contains disk-related errors
- Important user data identified

Action:
Stopped unnecessary disk activity to reduce risk.

Escalation:
Suspected physical drive failure. Requires data backup/recovery and drive replacement.
```

# Ticket Documentation Example

```text
User reported secondary drive missing from File Explorer.

Opened Disk Management and confirmed the disk was detected.

Verified the volume was healthy but had no drive letter assigned.

Assigned an available drive letter.

Confirmed the drive appeared in File Explorer.

Opened several files successfully to verify access.

Documented the change and resolution in the ticket.
```

# Storage Troubleshooting Checklist

When troubleshooting storage problems, I can follow this process:

1. Gather symptoms.
2. Determine whether important data is at risk.
3. Confirm whether a backup exists.
4. Check File Explorer.
5. Check Disk Management.
6. Check Device Manager.
7. Check BIOS/UEFI if necessary.
8. Inspect physical connections.
9. Check free disk space.
10. Verify partitions.
11. Verify drive letters.
12. Check the file system.
13. Review SMART information where available.
14. Review Event Viewer.
15. Check storage performance.
16. Run CHKDSK when appropriate.
17. Test known-good cables or ports if needed.
18. Protect data before destructive actions.
19. Verify the repair.
20. Monitor for recurring errors.
21. Document findings.
22. Escalate suspected hardware failure.

# Key Takeaways

Some of the most important storage troubleshooting concepts include:

- Determine whether the problem is hardware, Windows, partition, file system, or available space.
- Disk Management is one of the most useful Windows storage tools.
- A drive can exist without appearing in File Explorer.
- Missing drive letters can prevent a volume from appearing normally.
- RAW file systems should not be formatted automatically when important data may exist.
- CHKDSK checks and repairs file-system problems.
- SMART provides useful health information but cannot predict every drive failure.
- Event Viewer can provide evidence of disk and file-system problems.
- Task Manager and Resource Monitor help investigate high disk activity.
- HDDs and SSDs can fail in different ways.
- Clicking or grinding HDDs should be treated as possible hardware failures.
- Protecting user data comes before aggressive troubleshooting.
- BitLocker recovery information should be considered before major storage changes.
- Known-good cables and ports can help isolate hardware problems.
- Drive replacement, reimaging, and data recovery may require escalation.
- A successful fix should always be verified and documented.

Storage troubleshooting combines hardware awareness, Windows administration, data protection, performance analysis, file-system troubleshooting, and careful escalation.
