# Software Installation Troubleshooting Ticket

## Ticket Summary

**Issue:** User is unable to install an approved business application.

**User Impact:** User cannot access software required for work.

**Priority:** Normal

**Device:** Windows 11 workstation

## User Report

User reported that an approved business application would not install.

The installer launched successfully but stopped before completion and displayed an installation error.

The user had already restarted the workstation before contacting support.

## Symptoms

- Windows starts normally
- Internet connectivity is working
- Installer opens
- Installation does not complete
- User is signed in with a standard account
- Other applications work normally
- Application is approved for business use

## Troubleshooting Performed

### 1. Confirmed the Software Was Approved

Verified that the requested application was authorized for installation.

Confirmed the installer came from an approved source.

No software was downloaded from an unknown third-party website.

### 2. Verified System Requirements

Reviewed the application's requirements.

Checked:

- Supported Windows version
- 64-bit vs 32-bit compatibility
- Available disk space
- Required memory
- Required dependencies

The workstation met the application's minimum requirements.

### 3. Checked Available Storage

Opened:

```text
Settings
→ System
→ Storage
```

Confirmed there was sufficient free disk space for the installation.

Low storage was ruled out.

### 4. Reviewed the Installer Error

Reproduced the installation attempt.

The installer displayed an error indicating that elevated permissions were required.

Recorded the exact error message rather than documenting only:

```text
Install failed
```

### 5. Confirmed User Permissions

The user was signed in with a standard Windows account.

The application required administrative elevation to install.

The user was not granted permanent administrator rights.

Instead, the approved IT installation process was used.

### 6. Retried Installation with Authorized Elevation

Used authorized administrative credentials to run the approved installer with the required elevation.

The installation began but failed again before completion.

### 7. Checked Windows Installer Service

Opened:

```text
services.msc
```

Located:

```text
Windows Installer
```

Service name:

```text
msiserver
```

Verified the service was available.

The service was started when required by the installation.

### 8. Retried the Installation

Ran the installer again.

The installation progressed further but stopped with another error.

### 9. Reviewed Existing Application Components

Checked whether an older version of the application was already installed.

Opened:

```text
Settings
→ Apps
→ Installed apps
```

An older version of the software was present.

The existing installation appeared damaged and could not update correctly.

### 10. Attempted Application Repair

Used the application's available repair option.

Possible path:

```text
Settings
→ Apps
→ Installed apps
→ Application
→ Modify
```

The exact options may vary depending on the application.

The repair completed, but the newer installer still failed.

### 11. Removed the Damaged Existing Installation

Confirmed user data and required application settings were not stored only inside the application installation directory.

Removed the damaged application using the normal uninstall process.

No application folders or registry entries were manually deleted without evidence or authorization.

### 12. Restarted the Workstation

Restarted Windows after uninstalling the damaged version.

This helped clear:

- Locked installer files
- Pending application state
- Temporary installation processes

### 13. Installed the Approved Application Again

Ran the approved installer with authorized elevation.

The application installed successfully.

### 14. Launched the Application

Opened the application after installation.

The program launched normally.

The user signed in successfully.

## Resolution

The application could not install because an older damaged installation was interfering with the upgrade process.

The previous version was removed using the approved uninstall process.

After restarting Windows, the approved installer completed successfully.

## Verification

Verified that:

- Application installed successfully
- Application appeared under Installed apps
- Application launched normally
- User could sign in
- Required application features opened
- No installation error remained

The user confirmed they could use the software required for work.

## Root Cause

```text
Corrupted or incomplete existing application installation
```

The workstation met system requirements and had sufficient storage.

The user did not require permanent administrator rights.

## Ticket Closure Notes

```text
User reported approved business application would not install.

Verified installer source and application approval.

Confirmed workstation met system requirements and had sufficient storage.

Reproduced installation failure and documented exact error.

Confirmed user was signed in with standard account.

Used authorized administrative elevation for installation.

Checked Windows Installer service.

Identified an older damaged version of the application already installed.

Attempted application repair without success.

Removed damaged installation through approved uninstall process.

Restarted workstation.

Installed current approved application successfully.

Launched application and verified user could sign in and access required features.

Issue resolved.
```

## Alternative Scenario — Installer Will Not Open

If an installer does not launch at all, troubleshooting could include:

- Verify installer finished downloading
- Verify file is from an approved source
- Check file extension
- Check Windows security warnings
- Check available storage
- Restart Windows
- Download a fresh approved installer
- Check whether security software blocked the file
- Review Event Viewer if appropriate

Do not disable antivirus or endpoint security simply to force an installer to run.

## EXE vs MSI

Windows application installers commonly use formats such as:

```text
.exe
```

and:

```text
.msi
```

MSI packages commonly use the Windows Installer service.

A failed MSI installation may produce useful installer error information.

## MSIEXEC

Windows includes:

```text
msiexec
```

for Windows Installer packages.

Example syntax:

```text
msiexec /i application.msi
```

Advanced switches should only be used when understood and appropriate.

For troubleshooting, installer logging may also be used in some environments.

## Windows Installer Service

The Windows Installer service is commonly associated with:

```text
msiserver
```

It supports installation, modification, and removal of MSI-based applications.

If the service is unavailable, some installers may fail.

## Dependencies

Applications may require supporting components such as:

- .NET
- Microsoft Visual C++ Redistributables
- Runtime libraries
- Browser components
- Device drivers

Missing dependencies can cause installation failures.

Required dependencies should come from trusted and approved sources.

## Compatibility

Older applications may not fully support newer versions of Windows.

Possible indicators include:

- Installer refuses to run
- Application installs but crashes
- Missing legacy dependency
- Unsupported operating system warning

Compatibility settings may be appropriate in limited situations, but they should not be used to bypass security or organizational requirements.

## Application Repair

Some applications provide repair options.

A repair may:

- Replace damaged files
- Restore required components
- Re-register application features

Repair can be less disruptive than completely uninstalling the application.

## Reinstallation

Reinstallation may be appropriate when:

- Application files are corrupted
- Repair fails
- Upgrade cannot complete
- Application configuration is damaged

Before uninstalling:

- Protect user data
- Verify licensing
- Check whether local application data must be preserved
- Confirm installer is available
- Follow organizational policy

## Security Software

Endpoint protection may block suspicious or unauthorized installers.

If an installer is blocked:

```text
Do not simply disable security software.
```

Instead:

1. Verify the software is legitimate.
2. Verify the source.
3. Follow approved security process.
4. Escalate false-positive concerns if necessary.

## SmartScreen

Windows SmartScreen may warn about unfamiliar software.

A warning does not automatically mean the application is malicious, but it should not be bypassed casually.

Verify:

- Publisher
- Source
- Organizational approval

before proceeding.

## Application Licensing

An application may install successfully but still fail to function without a license.

Possible symptoms include:

- Activation prompt
- Trial mode
- Read-only mode
- Feature restrictions

Installation and licensing are separate troubleshooting areas.

## Managed Software Deployment

In organizational environments, applications may be delivered through:

- Microsoft Intune
- Microsoft Configuration Manager
- Company Portal
- Group Policy
- Endpoint-management platforms
- Internal software repositories

If an application is centrally managed, manual installation may not be appropriate.

## Example Escalation

If installation continued to fail after standard troubleshooting, the ticket could be escalated with documentation such as:

```text
Issue:
Approved business application fails during installation.

Impact:
User cannot access required application.

Troubleshooting:
- Application approval verified
- Trusted installer source confirmed
- System requirements met
- Disk space verified
- Authorized elevation used
- Windows Installer service checked
- Existing version removed
- Workstation restarted
- Fresh approved installer tested
- Installation still fails

Finding:
Standard workstation troubleshooting did not resolve the installer failure.

Escalation:
Desktop engineering or application support required for deeper installer, dependency, packaging, or compatibility analysis.
```

## Skills Demonstrated

- Windows software installation troubleshooting
- Application requirements
- User permissions
- UAC concepts
- Windows Installer service
- Software repair
- Application uninstall/reinstall
- System compatibility
- Software dependencies
- Data protection
- Security awareness
- Verification
- Help desk documentation
- Escalation awareness
