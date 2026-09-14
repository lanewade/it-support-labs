# Help Desk & Desktop Support Scenarios

This note documents my study and troubleshooting practice across common help desk and desktop support situations involving Windows workstations, user accounts, peripherals, monitors, docking stations, applications, browsers, audio devices, connectivity, and general end-user support.

The goal is to use a consistent troubleshooting process, isolate the source of an issue, verify the resolution, communicate clearly with the user, and document the work performed.

## General Troubleshooting Approach

A structured troubleshooting process can help avoid unnecessary changes.

A basic approach is:

```text
Identify the problem
        |
        v
Gather information
        |
        v
Determine scope
        |
        v
Test likely causes
        |
        v
Apply the safest fix
        |
        v
Verify functionality
        |
        v
Document the result
```

Useful questions include:

- What is the user trying to do?
- What exactly happens?
- What error message appears?
- Did this work previously?
- When did the issue begin?
- What changed recently?
- Is one user affected or multiple users?
- Is one application affected or the entire computer?
- Can the issue be reproduced?
- Has the device already been restarted?

# Scenario 1 — External Monitor Not Detected

## Problem

A user connects an external monitor, but Windows does not display anything on it.

## Possible Causes

- Loose cable
- Monitor powered off
- Wrong monitor input
- Faulty HDMI or DisplayPort cable
- Docking station problem
- Display driver issue
- Windows display mode
- Faulty monitor or port

## Troubleshooting

1. Verify the monitor is powered on.
2. Check the video cable.
3. Confirm the monitor is using the correct input.
4. Disconnect and reconnect the cable.
5. Try a known-good cable if available.
6. Try another monitor or port if available.
7. Open Windows display settings.
8. Select **Detect** if available.
9. Try:

```text
Windows key + P
```

Possible display modes include:

```text
PC screen only
Duplicate
Extend
Second screen only
```

10. Check Device Manager for display-related errors.
11. Restart the workstation if appropriate.
12. Update or reinstall the approved display driver if required.

## Verification

Confirm:

```text
Monitor displays correctly
Correct resolution is selected
User can move windows between displays
```

# Scenario 2 — Monitor Displays the Wrong Resolution

## Problem

The screen appears blurry, stretched, or unusually large.

## Troubleshooting

Open:

```text
Settings
→ System
→ Display
```

Check:

- Display resolution
- Display scaling
- Correct monitor selected
- Refresh rate if relevant

The recommended resolution should normally match the monitor's native resolution.

If the correct resolution is unavailable, check the display driver and connection type.

# Scenario 3 — Docking Station Not Working

## Problem

A laptop connects to a docking station, but monitors, Ethernet, USB devices, or charging do not work correctly.

## Possible Causes

- Dock not powered
- USB-C/Thunderbolt connection problem
- Unsupported cable
- Dock firmware
- Driver issue
- Laptop port problem
- Power adapter issue

## Troubleshooting

1. Verify dock power.
2. Disconnect and reconnect the laptop.
3. Check the USB-C or Thunderbolt cable.
4. Restart the laptop.
5. Test individual peripherals.
6. Check Device Manager.
7. Verify approved docking-station drivers or firmware.
8. Test another dock if available.
9. Test the same dock with another supported laptop if authorized.

## Isolation Example

```text
Monitor fails through dock
Monitor works directly from laptop
```

This suggests the dock, cable, or dock configuration may be involved.

# Scenario 4 — USB Device Not Recognized

## Problem

Windows does not detect a USB device.

Examples include:

- Mouse
- Keyboard
- Flash drive
- Webcam
- Headset
- External drive

## Troubleshooting

1. Disconnect the device.
2. Reconnect it.
3. Try another USB port.
4. Test another known-good device in the same port.
5. Test the affected device on another computer if appropriate.
6. Open Device Manager.
7. Look for warning icons or unknown devices.
8. Restart Windows.
9. Check for approved driver updates.
10. Check power management settings if the issue is intermittent.

## Possible Isolation

```text
Device fails on every computer
→ Device may be faulty

Multiple devices fail on one USB port
→ Port may be faulty

Multiple USB ports fail
→ Driver, controller, dock, or hardware issue
```

# Scenario 5 — Mouse or Keyboard Stops Working

## Troubleshooting

For wired devices:

- Check cable
- Try another USB port
- Test known-good keyboard or mouse

For wireless devices:

- Check power switch
- Replace or charge battery
- Reconnect USB receiver
- Re-pair Bluetooth
- Reduce distance from workstation

Also check:

```text
Device Manager
```

and restart Windows if appropriate.

# Scenario 6 — Bluetooth Device Will Not Connect

## Problem

A Bluetooth headset, keyboard, mouse, or other peripheral will not pair.

## Troubleshooting

1. Confirm Bluetooth is enabled.
2. Confirm device is in pairing mode.
3. Remove the old pairing if appropriate.
4. Pair device again.
5. Check battery level.
6. Restart Bluetooth on the workstation.
7. Restart the peripheral.
8. Check Device Manager.
9. Verify Bluetooth driver.
10. Test another Bluetooth device.

Possible path:

```text
Settings
→ Bluetooth & devices
```

# Scenario 7 — No Sound from Speakers or Headset

## Problem

The user cannot hear audio.

## Troubleshooting

1. Check physical volume controls.
2. Confirm Windows is not muted.
3. Verify the correct output device.
4. Disconnect and reconnect headset.
5. Test another audio device.
6. Test sound from another application.
7. Open:

```text
Settings
→ System
→ Sound
```

8. Check Device Manager.
9. Restart application.
10. Restart Windows if appropriate.

A common issue is simply the wrong output device being selected after connecting a dock, monitor, or Bluetooth headset.

# Scenario 8 — Microphone Not Working

## Troubleshooting

Check:

- Physical mute switch
- Correct microphone selected
- Windows microphone permissions
- Application permissions
- Input volume
- Bluetooth connection
- Headset connection

Possible path:

```text
Settings
→ System
→ Sound
→ Input
```

Also check privacy settings, which may vary by Windows version:

```text
Settings
→ Privacy & security
→ Microphone
```

Test the microphone in more than one application when possible.

# Scenario 9 — Webcam Not Working

## Problem

The webcam displays no video or is unavailable.

## Troubleshooting

1. Check for a physical privacy shutter.
2. Verify the camera is enabled.
3. Close other applications that may be using the camera.
4. Check camera privacy permissions.
5. Test the Windows Camera application.
6. Check Device Manager.
7. Restart affected application.
8. Restart Windows.
9. Update approved camera driver if appropriate.

Possible path:

```text
Settings
→ Privacy & security
→ Camera
```

# Scenario 10 — User Cannot Open an Application

## Problem

An application does not launch.

## Troubleshooting

1. Check for an error message.
2. Confirm the application is installed.
3. Restart application.
4. Use Task Manager to check whether the process is already running.
5. End a frozen process only if appropriate.
6. Restart Windows.
7. Check whether other users can open the application.
8. Check recent updates.
9. Run application repair if available.
10. Reinstall only when appropriate and authorized.

# Scenario 11 — Application Is Frozen

## Problem

An application displays:

```text
Not Responding
```

## Troubleshooting

First allow a reasonable amount of time if the application may be processing something.

If it remains frozen:

```text
Ctrl + Shift + Esc
```

opens Task Manager.

Check:

- Application status
- CPU
- Memory
- Disk usage

If necessary:

```text
Task Manager
→ Application
→ End task
```

Before ending an application, consider whether the user may lose unsaved work.

# Scenario 12 — Computer Is Running Slowly

## Possible Causes

- High CPU usage
- High memory usage
- Disk activity
- Too many startup applications
- Low storage
- Windows updates
- Malware
- Failing drive
- Browser overload
- Background applications

## Troubleshooting

Open Task Manager:

```text
Ctrl + Shift + Esc
```

Review:

```text
CPU
Memory
Disk
Network
```

Also check:

- Available storage
- Startup applications
- Windows updates
- Recent software changes
- System restart history

Avoid randomly disabling services without understanding their purpose.

# Scenario 13 — Computer Has Very Little Free Disk Space

## Problem

The user reports slow performance or cannot save files.

## Troubleshooting

Check:

```text
Settings
→ System
→ Storage
```

Possible items consuming space include:

- Downloads
- Temporary files
- Large applications
- Videos
- OneDrive local files
- Old user data

Do not delete user files without permission.

Storage cleanup should prioritize known temporary or unnecessary data.

# Scenario 14 — Browser Will Not Load a Website

## Troubleshooting

Determine scope.

Ask:

```text
Does one website fail?
Do all websites fail?
Does another browser work?
Can another device access the same site?
```

Possible tests include:

```text
ping
nslookup
ipconfig
```

If one browser fails but another works, the issue may involve:

- Browser cache
- Extension
- Proxy setting
- Browser configuration

If all websites fail, investigate connectivity or DNS.

# Scenario 15 — One Website Works in Another Browser

## Possible Causes

- Browser cache
- Cookies
- Extension
- Browser version
- Saved credentials
- Site-specific settings

Possible process:

1. Try private/incognito mode.
2. Disable problematic extensions if approved.
3. Clear site-specific cache/cookies if appropriate.
4. Update browser.
5. Test again.

Avoid deleting all browser data unless necessary because it can remove useful sessions and saved state.

# Scenario 16 — Browser Keeps Redirecting or Showing Pop-Ups

Possible causes include:

- Malicious extension
- Adware
- Browser notification permissions
- Compromised site
- Malware

If suspicious behavior suggests malware:

```text
Do not install random cleanup tools.
```

Instead:

- Stop interacting with suspicious content
- Document symptoms
- Follow security procedure
- Escalate if required

# Scenario 17 — User Cannot Download a File

Possible causes include:

- Browser restriction
- Antivirus/security control
- Insufficient disk space
- File blocked by policy
- Download location permission issue
- Website problem

Before bypassing a security warning, confirm the file is legitimate and approved.

# Scenario 18 — PDF Will Not Open

## Troubleshooting

1. Verify the file downloaded completely.
2. Try another PDF.
3. Try browser PDF viewer.
4. Restart PDF application.
5. Check default application.
6. Repair or update approved PDF software.
7. Check whether the file itself is corrupted.

If only one PDF fails, the document may be the issue rather than the application.

# Scenario 19 — File Opens with the Wrong Application

## Problem

A file type opens in an unexpected program.

Example:

```text
.pdf opens in browser
```

or:

```text
.jpg opens in unexpected application
```

Check default applications.

Possible path:

```text
Settings
→ Apps
→ Default apps
```

The exact Windows interface may vary by version.

# Scenario 20 — User Cannot Find a Downloaded File

Check common locations:

```text
Downloads
Desktop
Documents
```

Also check the browser's download history.

Useful questions:

- What was the filename?
- When was it downloaded?
- Which browser was used?
- Was the save location changed?

Windows Search may also help locate the file.

# Scenario 21 — Windows Search Is Not Finding a File

Possible troubleshooting:

- Verify correct folder
- Search exact filename
- Search part of filename
- Check file extension
- Verify file was not moved
- Check OneDrive status if applicable

If Windows indexing itself appears broken, further troubleshooting may be required.

# Scenario 22 — User Profile Appears Different

## Problem

The desktop, files, or application settings appear missing after sign-in.

Possible causes include:

- Wrong account
- Temporary profile
- New Windows profile
- OneDrive not signed in
- Domain/account issue

Before assuming data is deleted:

1. Confirm correct user account.
2. Check:

```text
C:\Users
```

3. Look for the expected profile folder.
4. Check OneDrive sign-in.
5. Review Windows messages about a temporary profile.

Do not delete old user profiles until data has been reviewed and backed up appropriately.

# Scenario 23 — Temporary Windows Profile

Possible symptoms:

- Empty desktop
- Missing personalization
- Missing application settings
- Changes disappear after sign-out

Possible message:

```text
We can't sign into your account
```

Troubleshooting may involve:

- Restarting Windows
- Checking free disk space
- Reviewing Event Viewer
- Checking profile-related errors
- Escalating profile repair if required

User data should be protected before profile replacement.

# Scenario 24 — Desktop Icons or Taskbar Missing

Possible causes include:

- Windows Explorer issue
- Tablet/display mode
- Hidden icons
- Profile issue

One possible troubleshooting action is restarting Windows Explorer through Task Manager.

```text
Task Manager
→ Windows Explorer
→ Restart
```

This refreshes the Windows shell without fully restarting the computer.

# Scenario 25 — Start Menu Not Responding

Possible process:

1. Restart Windows Explorer.
2. Restart workstation.
3. Check Windows Update.
4. Test whether issue affects other user profiles if authorized.
5. Review Event Viewer or Reliability Monitor.
6. Run Windows repair tools if required.
7. Escalate persistent profile or OS corruption.

# Scenario 26 — Taskbar Application Will Not Open

Possible causes include:

- Broken shortcut
- Application not installed
- Application path changed
- User profile issue

Try opening the application from:

```text
Start menu
```

or its installed location.

If that works, repin the application to the taskbar if appropriate.

# Scenario 27 — User Cannot Print from One Application

If the printer works elsewhere:

```text
Windows test page works
Notepad prints
Specific application fails
```

then focus on:

- Application print settings
- Correct printer selection
- Document corruption
- Application updates
- Application repair

This prevents unnecessary printer-driver changes.

# Scenario 28 — Laptop Will Not Charge

## Troubleshooting

1. Check wall outlet.
2. Check power adapter.
3. Check cable and connector.
4. Try known-good approved charger.
5. Check charging indicator.
6. Inspect charging port for obvious damage.
7. Restart laptop.
8. Review battery status.

Possible isolation:

```text
Known-good charger also fails
→ Possible battery, charging port, or system-board issue
```

Escalate hardware repair when required.

# Scenario 29 — Battery Drains Quickly

Possible causes include:

- Battery age
- High screen brightness
- High CPU use
- Background applications
- Battery health deterioration
- Power settings

Check:

```text
Settings
→ System
→ Power & battery
```

Battery replacement may require hardware support.

# Scenario 30 — Laptop Is Overheating

Possible causes include:

- Blocked vents
- Dust buildup
- Heavy CPU usage
- Fan failure
- Poor airflow

Possible support steps:

1. Move laptop to a hard, ventilated surface.
2. Check Task Manager for high CPU usage.
3. Listen for fan operation.
4. Inspect vents.
5. Shut down if the system becomes dangerously hot.
6. Escalate suspected cooling hardware failure.

# Scenario 31 — Computer Will Not Power On

Check:

- Wall power
- Power cable
- Laptop charger
- Dock
- Power button
- Indicator lights

For a desktop:

```text
Wall outlet
→ Power cable
→ Power supply
→ Computer
```

For a laptop:

```text
Wall outlet
→ AC adapter
→ Laptop
```

Use known-good components where appropriate.

If no signs of power remain, escalate to hardware repair.

# Scenario 32 — Computer Powers On but No Display Appears

Possible causes include:

- Monitor power
- Wrong input
- Loose video cable
- Display output setting
- Dock issue
- GPU/display hardware
- Boot failure

Check the display path before assuming the computer itself is dead.

# Scenario 33 — Caps Lock or Num Lock Causes Confusion at Login

Users may report a password suddenly stopped working because:

```text
Caps Lock is enabled
```

or the keyboard layout changed.

Basic checks can prevent unnecessary password resets.

# Scenario 34 — Keyboard Layout Is Wrong

Possible symptoms:

```text
@ becomes "
```

or characters do not match the keyboard.

Check Windows keyboard/language settings.

A changed input language can make passwords appear incorrect.

# Scenario 35 — User Cannot Copy or Paste

Determine scope:

```text
One application?
All applications?
Remote session?
```

Try:

```text
Ctrl + C
Ctrl + V
```

Test with simple text between applications.

If copying works elsewhere, the problem is likely application-specific.

# Scenario 36 — Screenshot Tool Not Working

Possible alternatives include:

```text
Print Screen
Windows key + Shift + S
Snipping Tool
```

If one method fails, test another before troubleshooting the whole system.

# Scenario 37 — Time Is Incorrect

Incorrect system time can cause problems with:

- Authentication
- Websites
- Certificates
- Microsoft 365
- Domain services

Check:

```text
Settings
→ Time & language
→ Date & time
```

In managed environments, time synchronization may be controlled centrally.

Do not manually force incorrect time settings around organizational policies.

# Scenario 38 — User Cannot Connect to Wi-Fi

Possible process:

1. Confirm Wi-Fi is enabled.
2. Verify airplane mode is off.
3. Confirm correct SSID.
4. Reconnect to wireless network.
5. Check password if appropriate.
6. Run:

```text
ipconfig /all
```

7. Check IP addressing.
8. Test gateway.
9. Test DNS.
10. Compare with other users.

If multiple users are affected, consider an infrastructure issue.

# Scenario 39 — Wired Network Not Working

Check:

- Ethernet cable
- Link light
- Docking station
- Wall jack
- Network adapter
- IP configuration

Useful commands include:

```text
ipconfig /all
```

```text
ping
```

```text
tracert
```

```text
nslookup
```

# Scenario 40 — User Receives a 169.254 Address

An address in:

```text
169.254.0.0/16
```

is an APIPA address.

This often means Windows could not obtain an IPv4 address from DHCP.

Possible causes include:

- DHCP server unavailable
- Network link issue
- VLAN issue
- Wireless problem
- Switch problem

The presence of APIPA does not automatically mean the DHCP server itself is broken.

# Scenario 41 — VPN Connects but Internal Resources Do Not Work

Possible causes include:

- DNS
- Routing
- Split tunneling configuration
- Access permissions
- VPN policy
- Internal resource outage

Possible tests include:

```text
ping internal-host
nslookup internal-host
```

if permitted.

Determine whether:

```text
VPN connection itself fails
```

or:

```text
VPN connects but resources fail
```

These are different problems.

# Scenario 42 — User Cannot Access Shared Folder Remotely

Check:

```text
VPN connected?
Server reachable?
UNC path correct?
Credentials valid?
Permissions correct?
```

Example:

```text
\\fileserver\Shared
```

If the same share works while the user is in the office but not remotely, investigate VPN/network access before changing folder permissions.

# Scenario 43 — User Receives Repeated Password Prompts

Possible sources include:

- Outlook
- OneDrive
- Teams
- VPN
- Mapped drives
- Old saved credentials

If the password recently changed, stale credentials may still exist.

Check:

```text
Credential Manager
```

when appropriate.

# Scenario 44 — User Is Locked Out Repeatedly

Unlocking the account may not resolve the root cause.

Look for:

- Old phone
- Old laptop
- Saved mapped-drive credentials
- Outlook
- VPN
- Scheduled tasks

The goal is to identify what continues sending the old password.

# Scenario 45 — User Requests Administrator Access

The first response should not automatically be:

```text
Add user as local administrator
```

Instead determine:

- What task requires elevation?
- Is the software approved?
- Can IT perform the task?
- Is temporary elevation available?
- Has the request been authorized?

Follow least privilege.

# Scenario 46 — New User Missing an Application

Possible process:

1. Confirm the application is required.
2. Check licensing.
3. Check software portal or deployment system.
4. Verify user/account assignment.
5. Install only if approved.
6. Test application.
7. Document the change.

# Scenario 47 — User Has an Application but No License

An installed application may still require account licensing.

Possible symptoms include:

- Activation prompt
- Read-only mode
- Sign-in required
- Feature unavailable

This is different from a broken installation.

# Scenario 48 — Software Installation Requires Admin Rights

Do not give permanent administrator access just to complete installation.

Possible approach:

```text
Verify software
→ Confirm approval
→ Use authorized installation method
→ Test application
→ Document
```

# Scenario 49 — Windows Update Is Pending a Restart

A user may report strange behavior after updates partially install.

Check:

```text
Settings
→ Windows Update
```

If a restart is pending, schedule or perform it when appropriate.

A restart can complete:

- Windows updates
- Driver changes
- Application updates

# Scenario 50 — Restart vs Shut Down

Restarting Windows can clear temporary system state and reload services and drivers.

When troubleshooting, a restart is often more useful than simply closing the laptop lid or allowing it to sleep.

# Scenario 51 — User Has Too Many Startup Applications

Too many startup programs can slow sign-in.

Check:

```text
Task Manager
→ Startup apps
```

Do not disable unknown business or security software without understanding what it does.

# Scenario 52 — High CPU Usage

Task Manager can identify processes using large amounts of CPU.

Possible causes include:

- Application processing
- Windows Update
- Browser tabs
- Security scan
- Software malfunction

High CPU usage is a symptom, not automatically the root cause.

# Scenario 53 — High Memory Usage

Possible causes include:

- Many browser tabs
- Large applications
- Memory leak
- Insufficient RAM
- Multiple background applications

Compare:

```text
Memory usage
```

with the applications currently running.

# Scenario 54 — High Disk Usage

Possible causes include:

- Windows Update
- Antivirus scan
- Search indexing
- Low RAM causing paging
- Storage failure

If disk usage stays high with poor performance, investigate the process responsible and review drive health.

# Scenario 55 — User Deleted a File

First determine where the file was stored.

Check:

```text
Recycle Bin
```

For cloud-managed files, also consider:

```text
OneDrive recycle bin
SharePoint recycle bin
Version history
```

Do not immediately install recovery software on a business device without authorization.

# Scenario 56 — User Overwrote a File

Possible recovery sources may include:

- Version history
- OneDrive
- SharePoint
- Backup
- Previous versions

Preserve the current file before attempting recovery when appropriate.

# Scenario 57 — User Cannot Save a File

Possible causes include:

- Read-only file
- Missing permissions
- Full disk
- Full network share
- File locked
- Invalid filename
- Application issue

Determine whether the user can save:

```text
Another file
To another folder
From another application
```

This helps isolate the cause.

# Scenario 58 — File Name Is Invalid

Windows and cloud platforms may restrict certain characters, reserved names, or path lengths.

If one file refuses to save or sync, check the filename and path before troubleshooting the entire application.

# Scenario 59 — User Reports “Internet Is Down”

This statement can mean many things.

Clarify:

```text
Can they reach any website?
Can they reach internal resources?
Is Wi-Fi connected?
Do other users have internet?
Does DNS work?
```

A website outage is not the same as an internet outage.

# Scenario 60 — User Reports “The Computer Is Broken”

Ask specific questions.

For example:

```text
Does it power on?
Can you sign in?
Can you open applications?
Is there an error?
Is the screen blank?
Is it slow?
```

Turning a vague complaint into an observable symptom is an important help desk skill.

# Scenario 61 — User Is Frustrated

Technical support also involves communication.

Useful approaches include:

- Let the user explain the problem
- Avoid unnecessary jargon
- Explain what you are checking
- Confirm before making disruptive changes
- Avoid blaming the user
- Give clear next steps
- Verify the user can continue working

A calm explanation can improve the support experience even when the issue requires escalation.

# Scenario 62 — Remote Support Session

Before taking control of a user's workstation:

- Follow organizational remote-support policy
- Verify the correct user and device
- Explain what you are doing
- Avoid opening unrelated personal information
- Do not enter or request passwords unnecessarily
- End the remote session when troubleshooting is complete

# Scenario 63 — User Must Restart but Has Unsaved Work

Before restarting:

1. Tell the user why a restart is needed.
2. Ask them to save their work.
3. Close important applications.
4. Confirm it is safe to restart.

This avoids creating a second problem while fixing the first one.

# Scenario 64 — Issue Cannot Be Reproduced

If the issue is intermittent:

Document:

```text
When it happens
What the user is doing
Error message
Application
Network location
Frequency
Recent changes
```

Ask the user to capture the exact error or screenshot if organizational policy allows.

Intermittent issues often require pattern recognition rather than immediate changes.

# Scenario 65 — Issue Returns After Being Fixed

If the same problem keeps returning:

```text
Do not only repeat the temporary fix.
```

Investigate the underlying cause.

Example:

```text
Mapped drive repeatedly disconnects
```

Possible deeper causes:

- VPN timing
- Login script
- Group Policy
- DNS
- Server availability

# Scenario 66 — Multiple Users Report the Same Problem

If multiple users suddenly report the same issue, stop treating every ticket as an isolated workstation problem.

Consider:

- Service outage
- Server issue
- Network problem
- Microsoft 365 outage
- Application outage
- Recent deployment or update

Scope is a major troubleshooting clue.

# Scenario 67 — One User Is Affected

If everyone else can use the same service, focus on:

- User account
- Permissions
- Device
- Profile
- Local application
- Credentials
- Local network configuration

# Scenario 68 — Problem Began After a Change

Recent changes are strong clues.

Examples include:

- Windows update
- Driver update
- Password change
- New dock
- New monitor
- Application update
- Department transfer
- New VPN client

Ask:

```text
What changed immediately before the problem started?
```

# Scenario 69 — Hardware or Software?

Useful isolation questions include:

```text
Does the device work on another computer?
Does another device work on this computer?
Does the application work for another user?
Does the problem follow the user or the workstation?
```

This helps separate:

```text
Hardware
Software
User account
Network
```

# Scenario 70 — Verify the Fix

A troubleshooting task is not complete just because the error disappeared.

Verification should match the user's original problem.

Examples:

```text
User couldn't print
→ Print original document

User couldn't access share
→ Open, edit, and save required file

User had no sound
→ Play audio through intended device

User couldn't sign in
→ Sign in and open required application
```

# Ticket Documentation

A useful help desk ticket should include:

```text
Issue
Symptoms
Scope
Troubleshooting performed
Results
Resolution
Verification
Escalation if required
```

# Example Ticket — External Monitor

```text
Issue:
User reported second monitor was not detected.

Troubleshooting:
- Verified monitor power
- Confirmed DisplayPort cable connected
- Monitor was set to HDMI input instead of DisplayPort
- Changed monitor input to DisplayPort

Resolution:
Second monitor detected immediately.

Verification:
Confirmed user could extend Windows desktop across both displays.
```

# Example Ticket — USB Headset

```text
Issue:
User could not hear audio through USB headset.

Troubleshooting:
- Headset detected by Windows
- Windows audio was playing through monitor speakers
- Changed default output device to USB headset
- Tested audio

Resolution:
Audio played normally through headset.

Verification:
User confirmed both system audio and meeting audio worked.
```

# Example Ticket — Slow Computer

```text
Issue:
User reported workstation was unusually slow.

Troubleshooting:
- Opened Task Manager
- CPU normal
- Memory normal
- Disk usage remained near 100%
- Windows Update was actively installing updates

Resolution:
Allowed updates to finish and restarted workstation.

Verification:
Disk usage returned to normal and user confirmed expected performance.
```

# Example Ticket — Application Frozen

```text
Issue:
User reported application stopped responding.

Troubleshooting:
- Confirmed application showed Not Responding
- User confirmed work had been saved
- Ended application through Task Manager
- Restarted application

Resolution:
Application launched normally.

Verification:
User reopened required file and resumed work successfully.
```

# Example Ticket — Browser Issue

```text
Issue:
User could not load an internal site in primary browser.

Troubleshooting:
- Network connectivity verified
- Site worked in alternate browser
- Tested private browsing mode
- Site loaded successfully
- Identified browser extension conflict

Resolution:
Disabled approved problematic extension.

Verification:
Site loaded normally in primary browser.
```

# Example Ticket — Laptop Not Charging

```text
Issue:
Laptop would not charge.

Troubleshooting:
- Verified wall outlet
- Reseated power adapter
- Tested known-good approved charger
- Laptop still did not detect power
- Charging port appeared loose

Resolution:
No software resolution available.

Escalation:
Escalated to hardware repair for charging-port evaluation.
```

# Example Ticket — Missing Mapped Drive

```text
Issue:
User reported department drive missing.

Troubleshooting:
- Network connectivity verified
- VPN connected
- UNC path accessible
- net use showed no mapping
- Recreated approved drive mapping

Resolution:
Mapped drive restored.

Verification:
User successfully opened and saved department files.
```

# Desktop Support Safety

Before making significant changes:

- Protect user data
- Confirm backups when necessary
- Avoid deleting profiles prematurely
- Avoid disabling security controls
- Avoid installing unapproved software
- Avoid changing permissions without authorization
- Avoid sharing passwords
- Avoid bypassing MFA
- Avoid making infrastructure changes outside support scope

# When to Escalate

Escalation may be appropriate when:

- Hardware repair is required
- Administrator permissions exceed support scope
- Multiple users are affected
- Server or network infrastructure is involved
- Security incident is suspected
- Data loss is possible
- User access requires approval
- Application backend is unavailable
- Issue persists after reasonable troubleshooting

# Help Desk & Desktop Support Checklist

When working through a user issue, I can follow this process:

1. Confirm the user's goal.
2. Gather exact symptoms.
3. Record error messages.
4. Determine the scope.
5. Ask about recent changes.
6. Check physical connections.
7. Check power.
8. Verify network connectivity if relevant.
9. Reproduce the issue when possible.
10. Test one change at a time.
11. Use known-good components when useful.
12. Check Windows settings.
13. Check Device Manager if hardware is involved.
14. Check Task Manager for performance or application problems.
15. Check Event Viewer or Reliability Monitor when needed.
16. Protect user data.
17. Stay within support permissions.
18. Avoid unnecessary changes.
19. Verify the original user task.
20. Document the resolution.
21. Escalate when appropriate.

# Key Takeaways

Some of the most important help desk and desktop support concepts include:

- Clarifying the user's actual problem is often the first troubleshooting step.
- Scope helps distinguish local problems from shared service problems.
- Physical connections should be checked before complicated software changes.
- Testing with known-good hardware can isolate failed components.
- Device Manager is useful for driver and hardware troubleshooting.
- Task Manager helps investigate frozen applications and resource usage.
- User profiles, credentials, permissions, and device configuration can all affect workstation behavior.
- A working application in another browser or profile can help isolate the source.
- Recent changes are valuable troubleshooting clues.
- Security controls should not be disabled simply to make a problem disappear.
- Administrator privileges should only be used when authorized and necessary.
- User data should be protected before profile resets, reinstalls, or storage work.
- A temporary workaround is not always the same as solving the root cause.
- The final verification should reproduce the user's original task successfully.
- Clear ticket documentation helps prevent repeated troubleshooting.
- Good technical support combines troubleshooting, communication, documentation, judgment, and escalation.

Help desk and desktop support troubleshooting involves more than fixing individual devices. It requires isolating problems across hardware, Windows, applications, accounts, peripherals, networking, and user workflows while protecting data and maintaining a clear support process.
