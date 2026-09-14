# Windows Update Troubleshooting Ticket Example

This is a practice help desk ticket documenting a common Windows Update issue and the troubleshooting process used to resolve it.

## Ticket Summary

**Issue:** Windows Update fails to install a cumulative update.

**User Impact:** User is unable to complete required Windows updates.

**Priority:** Normal

**Device:** Windows 11 workstation

## User Report

User reported that Windows Update repeatedly failed while attempting to install a cumulative update.

The update downloaded successfully but failed during installation.

The user had already restarted the workstation before contacting support.

## Symptoms

- Windows Update displayed an installation failure
- Update remained available after restart
- Internet connectivity was working
- Other applications worked normally
- No other major workstation issues were reported

## Troubleshooting Performed

### 1. Verified Network Connectivity

Confirmed the workstation had normal internet access.

Tested access to several websites successfully.

### 2. Checked Windows Update

Opened:

```text
Settings
→ Windows Update
```

Confirmed the cumulative update was still pending and had previously failed.

### 3. Reviewed Update History

Opened:

```text
Settings
→ Windows Update
→ Update history
```

Confirmed the same update had failed multiple times.

Recorded the update and error information for troubleshooting.

### 4. Checked Available Storage

Verified that the system drive had sufficient free space for the update.

Low disk space was ruled out as the cause.

### 5. Checked Date and Time

Verified the workstation had the correct:

- Date
- Time
- Time zone

Incorrect system time can interfere with Windows services and secure connections.

### 6. Restarted Windows Update Services

Checked the Windows Update-related services.

Relevant services included:

```text
Windows Update
Background Intelligent Transfer Service
```

Confirmed the services were available and restarted them where appropriate.

### 7. Retried Windows Update

Returned to:

```text
Settings
→ Windows Update
```

Selected:

```text
Check for updates
```

The update downloaded again but still failed during installation.

### 8. Ran System File Checker

Opened an elevated Command Prompt and ran:

```text
sfc /scannow
```

System File Checker detected and repaired corrupted Windows system files.

### 9. Ran DISM

After SFC completed, ran:

```text
DISM /Online /Cleanup-Image /RestoreHealth
```

DISM completed successfully.

### 10. Restarted the Workstation

Restarted Windows after the repair commands completed.

### 11. Retried the Update

Returned to Windows Update and attempted installation again.

This time the update installed successfully.

## Resolution

Corrupted Windows system files were repaired using:

```text
sfc /scannow
```

and:

```text
DISM /Online /Cleanup-Image /RestoreHealth
```

After restarting the workstation, the Windows cumulative update installed successfully.

## Verification

Verified:

- Windows Update completed successfully
- No pending installation error remained
- Update appeared in update history as successfully installed
- Workstation restarted normally
- User could sign in and use applications normally

## Ticket Closure Notes

```text
User reported Windows cumulative update repeatedly failed to install.

Verified internet connectivity, available disk space, system date/time, and Windows Update services.

Reviewed update history and confirmed repeated failure.

Ran SFC, which repaired corrupted Windows system files.

Ran DISM /Online /Cleanup-Image /RestoreHealth successfully.

Restarted workstation and retried Windows Update.

Update installed successfully.

Verified update history and normal workstation functionality.

Issue resolved.
```

## Skills Demonstrated

- Windows Update troubleshooting
- Windows services
- System File Checker
- DISM
- Windows settings
- Troubleshooting methodology
- Verification
- Help desk documentation
