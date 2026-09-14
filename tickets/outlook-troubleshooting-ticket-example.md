# Outlook Troubleshooting Ticket Example

This is a practice help desk ticket documenting a Microsoft Outlook desktop issue involving sign-in, connectivity, Outlook Safe Mode, add-ins, application repair, and verification.

## Ticket Summary

**Issue:** Outlook desktop will not open normally.

**User Impact:** User cannot access work email through the Outlook desktop application.

**Priority:** Normal

**Device:** Windows 11 workstation

## User Report

User reported that Microsoft Outlook stopped opening normally.

When launched, Outlook appeared briefly and then closed.

The user stated that email still worked through Outlook on the web.

## Symptoms

- Outlook desktop fails to stay open
- Outlook on the web works
- Internet connectivity is normal
- Microsoft 365 account is active
- Other Microsoft 365 applications work normally
- Issue appears limited to Outlook desktop

## Troubleshooting Performed

### 1. Verified Internet Connectivity

Confirmed the workstation had normal network access.

Tested access to several websites successfully.

Because Outlook on the web worked normally, a general network outage was unlikely.

### 2. Verified Microsoft 365 Account Access

Opened Outlook on the web and confirmed the user could:

- Sign in successfully
- Open the mailbox
- Read email
- Send email

This helped confirm that the mailbox and account were functioning.

### 3. Restarted Outlook

Closed Outlook completely and checked Task Manager for any remaining Outlook processes.

Opened:

```text
Ctrl + Shift + Esc
```

Confirmed no stuck Outlook process remained.

Tried launching Outlook again.

The issue continued.

### 4. Restarted Windows

Restarted the workstation to clear temporary application and system state.

After restart, Outlook still failed to open normally.

### 5. Tested Outlook Safe Mode

Opened the Run dialog:

```text
Windows key + R
```

Entered:

```text
outlook.exe /safe
```

Outlook opened successfully in Safe Mode.

This suggested the problem was related to Outlook configuration or an add-in rather than the mailbox itself.

### 6. Reviewed Outlook Add-ins

With Outlook open in Safe Mode, reviewed installed add-ins.

Possible path:

```text
File
→ Options
→ Add-ins
```

Checked active COM add-ins.

A recently installed third-party add-in was identified.

### 7. Disabled the Suspected Add-in

Disabled the suspected add-in for testing.

Closed Outlook completely.

Opened Outlook normally.

Outlook launched successfully.

### 8. Tested Normal Outlook Functions

Verified that Outlook could:

- Open mailbox
- Send email
- Receive email
- Open calendar
- Search mailbox
- Open attachments

No further crashing occurred.

## Resolution

A third-party Outlook add-in was causing Outlook to close during normal startup.

Outlook successfully opened in Safe Mode because Safe Mode disabled optional add-ins.

After the problematic add-in was disabled, Outlook opened and functioned normally.

## Verification

Verified:

- Outlook opened normally
- Mailbox synchronized
- User could send and receive email
- Calendar opened successfully
- Search worked
- Outlook remained open without crashing

The user confirmed they could return to normal work.

## Root Cause

```text
Problematic Outlook add-in
```

The Microsoft 365 account, mailbox, network connection, and Outlook web access were functioning normally.

## Ticket Closure Notes

```text
User reported Outlook desktop opened briefly and then closed.

Verified internet connectivity.

Confirmed Microsoft 365 account and mailbox worked normally through Outlook on the web.

Restarted Outlook and workstation with no change.

Launched Outlook using outlook.exe /safe.

Outlook opened successfully in Safe Mode.

Reviewed Outlook add-ins and identified a recently installed third-party add-in.

Disabled the suspected add-in and restarted Outlook normally.

Outlook opened successfully and remained stable.

Verified send/receive, calendar, search, and mailbox access.

User confirmed normal Outlook functionality.

Issue resolved.
```

## Alternative Troubleshooting Path

If Outlook had still failed in Safe Mode, additional steps could include:

- Check Microsoft 365 service health
- Review Outlook profile
- Create a new Outlook profile if appropriate
- Check OST/PST issues
- Check mailbox storage quota
- Review Credential Manager
- Run Microsoft Office repair
- Check Windows updates
- Review Event Viewer
- Review Reliability Monitor
- Reinstall Microsoft 365 only if appropriate and authorized

## Outlook Profile Troubleshooting

If the Outlook profile appeared corrupted, a technician might review:

```text
Control Panel
→ Mail
→ Show Profiles
```

A new profile could be created for testing if organizational policy allows.

The existing profile should not be deleted until the required mailbox and local data are understood.

## Office Repair Option

If Outlook remained unstable, Microsoft 365 repair could be considered.

Possible path:

```text
Settings
→ Apps
→ Installed apps
→ Microsoft 365
→ Modify
```

Available repair options may vary by version.

A common progression is:

```text
Quick Repair
        |
        v
Retest
        |
        v
Online Repair if required
```

Online Repair may require internet access and can take longer.

## Escalation Alternative

If Outlook continued to fail after local troubleshooting, the ticket could be escalated with documentation such as:

```text
Issue:
Outlook desktop crashes during launch.

Impact:
User cannot access work email through Outlook desktop.

Scope:
One user / one workstation.

Troubleshooting:
- Internet connectivity verified
- Outlook web works normally
- Account authentication successful
- Workstation restarted
- Outlook Safe Mode tested
- Add-ins disabled
- Office Quick Repair completed
- Issue persists

Finding:
Mailbox and cloud service appear functional.

Escalation:
Desktop Outlook issue requires deeper Microsoft 365 or endpoint support review.
```

## Skills Demonstrated

- Microsoft Outlook troubleshooting
- Microsoft 365 support
- Application isolation
- Outlook Safe Mode
- Add-in troubleshooting
- Task Manager
- Account verification
- Web vs desktop comparison
- Microsoft Office repair concepts
- Troubleshooting methodology
- Verification
- Help desk documentation
- Escalation awareness
