# Microsoft Teams Audio & Video Ticket

## Ticket Summary

**Issue:** User can join Microsoft Teams meetings but microphone and camera do not work.

**User Impact:** User cannot participate normally in Teams meetings.

**Priority:** Normal

**Device:** Windows 11 laptop

## User Report

User reported that Microsoft Teams opened normally and meetings could be joined, but other participants could not hear or see them.

The user stated that the built-in microphone and webcam had worked previously.

## Symptoms

- Teams launches successfully
- User can join meetings
- Speakers work normally
- Microphone does not transmit audio
- Camera does not display video
- Internet connectivity is working
- No Microsoft 365 sign-in errors

## Troubleshooting Performed

### 1. Verified Physical Controls

Checked the laptop for:

- Microphone mute key
- Webcam privacy shutter
- Hardware privacy switches

The microphone was not physically muted.

The webcam privacy shutter was partially closed.

Opened the privacy shutter completely.

The camera became visible to Windows, but Teams still did not display video.

### 2. Checked Teams Device Settings

Opened Microsoft Teams settings and reviewed the selected devices.

Checked:

```text
Teams
→ Settings
→ Devices
```

Verified:

- Correct speaker
- Correct microphone
- Correct camera

Teams had selected a connected monitor as the audio input device instead of the laptop microphone.

Changed the microphone to the correct built-in microphone.

### 3. Tested the Microphone

Used the available Teams test-call/device-testing option where supported.

The microphone still did not record audio.

This indicated that another Windows setting might be blocking microphone access.

### 4. Checked Windows Sound Settings

Opened:

```text
Settings
→ System
→ Sound
```

Under input devices, confirmed that the built-in microphone was detected.

Selected the microphone and tested input.

Windows detected microphone activity successfully.

This confirmed that the microphone hardware itself was functioning.

### 5. Checked Microphone Privacy Permissions

Opened:

```text
Settings
→ Privacy & security
→ Microphone
```

Confirmed microphone access was enabled.

However, application access to the microphone had been disabled.

Enabled the appropriate microphone access setting.

Restarted Teams.

### 6. Checked Camera Privacy Permissions

Opened:

```text
Settings
→ Privacy & security
→ Camera
```

Confirmed camera access was enabled.

Verified applications were permitted to use the camera.

### 7. Tested the Camera Outside Teams

Opened the Windows Camera application.

The webcam displayed video normally.

This confirmed:

```text
Camera hardware
+
Windows driver
+
Windows permissions
```

were functioning.

### 8. Restarted Microsoft Teams

Closed Teams completely.

Checked Task Manager to ensure no Teams processes remained running.

Opened:

```text
Ctrl + Shift + Esc
```

Confirmed Teams had closed.

Restarted Teams and rejoined a test meeting.

### 9. Retested Teams Devices

Returned to:

```text
Teams
→ Settings
→ Devices
```

Verified:

```text
Microphone:
Built-in microphone

Speaker:
User's preferred output device

Camera:
Integrated webcam
```

The microphone input meter responded normally.

The webcam preview also displayed correctly.

## Resolution

The issue had two causes:

```text
Incorrect microphone selected in Teams
```

and:

```text
Windows application microphone access disabled
```

The camera was also initially blocked by the laptop's physical privacy shutter.

After correcting device selection, enabling microphone permissions, opening the webcam privacy shutter, and restarting Teams, both audio and video worked normally.

## Verification

Verified that the user could:

- Join a Teams meeting
- Hear other participants
- Speak through the intended microphone
- See microphone input activity
- Enable the camera
- Display webcam video
- Mute and unmute successfully

The user confirmed normal Teams functionality.

## Root Cause

```text
Incorrect Teams input-device selection
+
Windows microphone privacy setting
+
Webcam privacy shutter
```

The Microsoft 365 account, Teams service, network connection, microphone hardware, and camera hardware were otherwise functioning normally.

## Ticket Closure Notes

```text
User reported microphone and camera were not working in Microsoft Teams.

Verified Teams launched and user could join meetings successfully.

Checked physical controls and found webcam privacy shutter partially closed.

Opened webcam shutter.

Reviewed Teams device settings and found incorrect microphone selected.

Selected built-in microphone.

Windows Sound settings confirmed microphone hardware detected and functional.

Reviewed Windows microphone privacy settings and found application microphone access disabled.

Enabled microphone access and verified camera permissions.

Tested webcam successfully in Windows Camera application.

Restarted Microsoft Teams.

Verified correct microphone, speaker, and camera selections.

Joined test meeting and confirmed microphone and camera worked normally.

User confirmed issue resolved.
```

## Alternative Troubleshooting Path

If audio or video still failed, additional troubleshooting could include:

- Restart Windows
- Test Teams in a browser
- Check browser microphone and camera permissions
- Check Device Manager
- Update or reinstall approved audio/video drivers
- Disconnect and reconnect USB or Bluetooth devices
- Test without docking station
- Check whether another application is using the camera
- Update Microsoft Teams
- Sign out and back into Teams
- Check Microsoft 365 service health
- Review VPN or network quality
- Escalate if account or meeting-policy restrictions are suspected

## Device Manager Check

If Windows did not detect the microphone or camera, Device Manager could be reviewed.

Possible categories include:

```text
Audio inputs and outputs
Cameras
Sound, video and game controllers
```

Look for:

- Missing devices
- Warning icons
- Disabled devices
- Driver errors

Driver changes should use approved vendor or organizational sources.

## Bluetooth Headset Alternative

If the issue involved a Bluetooth headset, additional checks could include:

```text
Settings
→ Bluetooth & devices
```

Verify:

- Headset connected
- Battery charged
- Correct input/output selected
- Device paired successfully

If necessary:

1. Disconnect headset.
2. Reconnect it.
3. Test Teams again.
4. Test with built-in microphone and speakers.

This helps determine whether the issue is specific to the headset.

## Network Quality Considerations

Poor network performance may cause:

- Audio cutting out
- Frozen video
- Delayed speech
- Low video quality
- Meeting disconnects

Possible factors include:

- Weak Wi-Fi
- Packet loss
- High latency
- Jitter
- Congested network
- VPN performance

These symptoms are different from a microphone or camera that is completely unavailable.

## Escalation Alternative

If Teams still failed after local troubleshooting, the ticket could be escalated with documentation such as:

```text
Issue:
Teams microphone and camera unavailable during meetings.

Impact:
User cannot participate with audio or video.

Troubleshooting:
- Physical mute/privacy controls checked
- Correct Teams devices selected
- Windows microphone and camera permissions verified
- Microphone works in Windows Sound settings
- Webcam works in Windows Camera
- Teams restarted
- Teams updated
- Browser Teams test completed
- Issue persists only in Teams desktop client

Finding:
Audio/video hardware and Windows permissions appear functional.

Escalation:
Requires Microsoft 365 or application-support review.
```

## Skills Demonstrated

- Microsoft Teams troubleshooting
- Microsoft 365 support
- Audio-device troubleshooting
- Webcam troubleshooting
- Windows privacy permissions
- Device selection
- Hardware isolation
- Task Manager
- Device Manager concepts
- Application troubleshooting
- User verification
- Ticket documentation
- Escalation awareness
