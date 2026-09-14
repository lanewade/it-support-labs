# Shared Folder Access Ticket

## Ticket Summary

**Issue:** User receives Access Denied when attempting to open a department shared folder.

**User Impact:** User cannot access files required for daily work.

**Priority:** Normal

**Device:** Windows 11 workstation

## User Report

User reported that they could access other network resources normally but could not open their department shared folder.

The user received an Access Denied message when attempting to open:

```text
\\fileserver\Finance
```

The user stated that coworkers in the same department could access the folder successfully.

## Symptoms

- Windows sign-in works normally
- Internet access works
- Other network resources are available
- File server is reachable
- Finance share returns Access Denied
- Other Finance users can access the share
- Issue affects only one user

## Troubleshooting Performed

### 1. Verified Network Connectivity

Confirmed the workstation had normal network access.

Tested connectivity to the file server:

```text
ping fileserver
```

The file server responded successfully.

### 2. Verified Name Resolution

Tested the server hostname:

```text
nslookup fileserver
```

The server name resolved successfully.

This helped rule out a DNS issue.

### 3. Verified the UNC Path

Confirmed the correct network path:

```text
\\fileserver\Finance
```

The path was valid and accessible by other authorized users.

### 4. Tested SMB Connectivity

Used PowerShell:

```powershell
Test-NetConnection fileserver -Port 445
```

TCP port 445 was reachable.

This confirmed the workstation could communicate with the file server using SMB.

### 5. Determined Scope

Confirmed:

```text
Affected:
One user

Not affected:
Other Finance users
```

Because other users could access the same share, a server outage or general network problem was unlikely.

### 6. Reviewed User Access

The user could reach the share but received:

```text
Access Denied
```

This indicated the problem was more likely related to authorization than connectivity.

### 7. Checked Required Group Membership

Reviewed the user's access requirements.

The Finance folder used a department access group.

The user was expected to be a member of:

```text
Finance-Users
```

The affected user was not currently a member of the required group.

### 8. Verified Authorization

Confirmed that an approved access request existed for the user.

No permissions were changed until the authorization was verified.

### 9. Updated Group Membership

The user was added to the approved Finance access group using the authorized account-management process.

No direct permissions were assigned to the individual user.

Using the existing group maintained consistent access control.

### 10. Refreshed the User Session

The user signed out of Windows and signed back in so the updated group membership could be applied.

The user then reopened:

```text
\\fileserver\Finance
```

The folder opened successfully.

## Resolution

The user was missing membership in the required Finance access group.

After the approved group membership was added and the user's session was refreshed, access to the shared folder worked normally.

## Verification

Verified that the user could:

- Open the Finance share
- Browse required folders
- Open files
- Create a test file where authorized
- Save changes
- Reopen the saved file

The user confirmed they could perform their required work.

## Root Cause

```text
Missing group membership
```

The workstation, DNS, SMB connectivity, and file server were functioning normally.

The issue was related to authorization rather than network connectivity.

## Ticket Closure Notes

```text
User reported Access Denied when opening \\fileserver\Finance.

Verified workstation network connectivity.

Confirmed fileserver hostname resolved successfully.

Confirmed TCP 445 connectivity to fileserver.

Verified other Finance users could access the share normally.

Reviewed user's access and found required Finance-Users group membership missing.

Confirmed approved access request before making changes.

User added to approved Finance access group.

User signed out and back in to refresh access.

Verified user could open, edit, save, and reopen authorized files in the Finance share.

Issue resolved.
```

## Escalation Alternative

If the technician did not have permission to modify group membership, the ticket could instead be escalated with documentation similar to:

```text
Issue:
User cannot access \\fileserver\Finance.

Impact:
User cannot access department files required for work.

Troubleshooting:
- Network connectivity verified
- DNS resolution successful
- TCP 445 reachable
- UNC path confirmed
- Other Finance users can access share
- User receives Access Denied
- Required Finance-Users group membership is missing

Finding:
Issue appears authorization-related.

Escalation:
Approved access request exists, but group membership change requires Identity or Systems Administration.
```

## Skills Demonstrated

- Windows shared-folder troubleshooting
- UNC paths
- SMB connectivity
- DNS verification
- TCP port testing
- Authentication vs authorization
- Group-based access control
- Least privilege
- Permission troubleshooting
- Scope determination
- User access verification
- Ticket documentation
- Escalation awareness
