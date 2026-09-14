# Account & Permission Scenarios

This note documents my study and troubleshooting practice involving user accounts, passwords, account lockouts, MFA, group membership, local and organizational permissions, access requests, least privilege, onboarding, offboarding, and common account-related IT support scenarios.

The goal is to use a structured support process to resolve account and permission problems while verifying user identity, protecting access, following authorization requirements, and documenting any changes made.

## Common Account & Permission Problems

Common support issues can include:

- User forgot their password
- Password expired
- Account is locked
- Account is disabled
- User cannot sign in
- MFA is not working
- User changed phones and lost MFA access
- User repeatedly receives sign-in prompts
- User cannot access a shared folder
- User cannot access an application
- User needs access to a new department resource
- User has access they no longer need
- New employee is missing required access
- Employee changed departments
- User requests administrator rights
- Group membership is incorrect
- User can sign in but receives Access Denied
- Account works on one service but not another
- User's permissions differ from coworkers with the same role

## Initial Information Gathering

Before making changes, I would gather information about the issue.

Questions may include:

- What exactly is the user unable to access?
- What error message appears?
- Did access work previously?
- When did the problem begin?
- Was the user's password recently changed?
- Is the account locked or disabled?
- Is MFA involved?
- Is one application affected or everything?
- Did the user recently change roles or departments?
- Is a new permission being requested?
- Has the request been approved?
- Do coworkers in the same role have access?
- Is the user using the correct account?

Account troubleshooting should begin with identifying the user and the exact resource involved.

# Identity Verification

Before performing sensitive account actions, the user's identity should be verified according to organizational policy.

Examples of sensitive actions include:

- Password reset
- MFA reset
- Account unlock
- Permission change
- Administrator access
- Recovery information changes

Identity verification helps prevent unauthorized account takeover.

A technician should not reset credentials simply because someone knows a username.

# Authentication vs Authorization

These concepts are related but different.

**Authentication** answers:

```text
Who are you?
```

Examples:

- Password
- PIN
- Smart card
- Biometrics
- MFA

**Authorization** answers:

```text
What are you allowed to access?
```

Examples:

- Shared-folder permissions
- Application access
- Group membership
- Administrator rights

A user may authenticate successfully but still lack authorization to access a resource.

# Step 1 — Confirm the Correct Account

Users may have multiple accounts.

Examples include:

- Local Windows account
- Work account
- Personal Microsoft account
- Microsoft 365 account
- Administrative account

Confirm the user is attempting to sign in with the correct identity.

Using the wrong account can produce what looks like a permission problem.

# Local Account

A local account exists on a specific Windows computer.

Conceptually:

```text
Computer A
└── Local User
```

The account may not automatically work on another computer.

# Organizational Account

In a managed environment, users may sign in with an organizational identity.

This can provide access to resources such as:

- Windows devices
- Microsoft 365
- Shared folders
- Applications
- VPN
- Internal systems

Account management may be handled by directory or identity-management systems.

# Password Reset Scenario

**Problem:**

A user forgot their password.

Possible process:

1. Verify user identity.
2. Confirm the correct account.
3. Check whether self-service password reset is available.
4. Reset the password only if authorized.
5. Follow password policy.
6. Inform user of any required next steps.
7. Have the user test sign-in.
8. Confirm dependent services work.
9. Document the reset without recording the actual password.

# Temporary Password

Some account systems may provide a temporary password.

The user may be required to change it at next sign-in.

A temporary password should:

- Be handled securely
- Not be placed in public ticket notes
- Follow organizational policy

# Password Policy

Password policies may control requirements such as:

- Minimum length
- Complexity
- Password history
- Expiration
- Lockout behavior

If a password reset fails because the new password does not meet policy, the technician should explain the requirement without revealing unnecessary security details.

# Never Store Passwords in Tickets

Ticket documentation should not contain:

- User passwords
- Temporary passwords
- MFA codes
- Recovery codes

Instead write:

```text
Password reset completed and user successfully signed in.
```

# Account Lockout

An account may lock after repeated failed authentication attempts.

Possible causes include:

- User entering wrong password
- Old password stored on another device
- Mapped drive using old credentials
- Outlook using old credentials
- Mobile device with outdated password
- Background service
- VPN client

Unlocking the account may only fix the symptom if an old credential continues causing failures.

# Example — Repeated Account Lockout

**Problem:**

The user's account is unlocked but becomes locked again shortly afterward.

Possible process:

1. Verify the user's identity.
2. Unlock account if authorized.
3. Ask whether password recently changed.
4. Check signed-in devices.
5. Check Outlook or Microsoft 365 applications.
6. Check VPN credentials.
7. Check mapped drives.
8. Review Credential Manager if appropriate.
9. Identify device or application using old password.
10. Update credentials.
11. Confirm account stays unlocked.
12. Document findings.

# Credential Manager

Windows Credential Manager can store credentials used for:

- Network shares
- Applications
- Websites
- Organizational resources

Open:

```text
Control Panel
→ Credential Manager
```

Stale credentials can sometimes cause repeated prompts or account lockouts.

Stored credentials should only be removed when there is a clear troubleshooting reason.

# Account Disabled

A disabled account is different from a locked account.

A disabled account may indicate:

- Employee departure
- Administrative action
- Security concern
- Account lifecycle process

A technician should not re-enable a disabled account without authorization.

# Locked vs Disabled

A simple distinction:

```text
Locked:
Often temporary after failed sign-ins

Disabled:
Account has been administratively turned off
```

The required response can be very different.

# Multi-Factor Authentication

MFA requires an additional authentication factor beyond a password.

Possible factors include:

- Authenticator app
- Security key
- SMS
- Voice call
- Hardware token
- Biometrics

MFA helps protect accounts if passwords are compromised.

# Common MFA Problems

Problems may include:

- User replaced phone
- Authenticator app removed
- Device lost
- Notification never arrives
- Verification number rejected
- User has no access to old method
- New method not registered

MFA changes are security-sensitive and should require identity verification.

# Example — User Replaced Phone

**Problem:**

A user has a new phone and cannot approve MFA prompts.

Possible process:

1. Verify user identity according to policy.
2. Confirm affected account.
3. Determine whether another registered method exists.
4. Use approved MFA recovery process.
5. Reset or update authentication methods only if authorized.
6. Have user register new device.
7. Test sign-in.
8. Confirm MFA works.
9. Document the change without storing MFA secrets.

# MFA Fatigue

Users should not approve unexpected MFA prompts.

Repeated unexpected prompts may indicate someone else is attempting to sign in.

If a user reports unexpected MFA requests:

1. Tell the user not to approve them.
2. Verify account activity if authorized.
3. Reset password when appropriate.
4. Follow security-incident procedures.
5. Escalate suspicious activity.

# Group Membership

Organizations commonly use groups to manage access.

Example:

```text
User
  |
  v
Finance-Users Group
  |
  v
Finance Shared Folder
```

Group-based permissions are easier to manage than assigning individual permissions to every user.

# Example Group Names

Conceptual examples:

```text
HelpDesk-Users
Finance-Read
Finance-Modify
VPN-Users
Remote-Access
Printer-Users
```

Actual group names vary by organization.

# Step 2 — Compare with a Similar User

If one user lacks access, compare their role with another authorized user performing the same job.

Questions may include:

- Are they in the same department?
- Should they have the same application?
- Do they belong to the same groups?
- Is the affected user's access request approved?

This can help identify missing group membership.

Do not automatically copy every permission from another user without verifying business need.

# Least Privilege

Least privilege means users should receive only the access required to perform their job.

Example:

```text
User needs:
Finance shared folder

User does not need:
HR shared folder
Server administration
Domain administration
```

Granting unnecessary access increases risk.

# Administrator Rights

Users may request administrator access because an application or installation requires elevation.

A technician should not automatically add the user to an administrator group.

Possible process:

1. Determine what task requires elevation.
2. Verify software or change is approved.
3. Use authorized administrative credentials if appropriate.
4. Grant temporary or permanent elevated access only when approved.
5. Document the reason.

# Standard User vs Administrator

A standard user can perform normal daily tasks.

An administrator can make broader system changes.

Administrative privileges can allow changes involving:

- Software installation
- System configuration
- Security settings
- User accounts
- Drivers

Least privilege generally favors standard-user access unless elevated rights are required.

# User Account Control

UAC stands for:

**User Account Control**

UAC prompts when an action requires elevated privileges.

A UAC prompt may appear during:

- Software installation
- Driver installation
- System configuration changes

UAC should not be disabled simply because prompts are inconvenient.

# Access Requests

A request for new access should include:

- User
- Resource
- Required access level
- Business reason
- Approval when required

Example:

```text
User:
Employee A

Resource:
\\fileserver\Finance

Requested:
Modify

Approval:
Finance manager
```

# Read vs Modify Access

A user may need different permission levels.

**Read** may allow:

- View files
- Open documents

**Modify** may allow:

- Create
- Edit
- Rename
- Delete

The requested level should match the user's job requirements.

# Role Changes

When an employee changes departments, their access may need to change.

Example:

```text
Old Role:
Sales

New Role:
Finance
```

Possible process:

1. Confirm role change.
2. Review access requirements.
3. Remove unnecessary old access.
4. Add approved new access.
5. Verify required systems.
6. Document changes.

Leaving unnecessary old permissions in place can violate least-privilege principles.

# Joiner, Mover, Leaver Concept

Account lifecycle management is sometimes described as:

```text
Joiner
Mover
Leaver
```

**Joiner:** New employee

**Mover:** Employee changes role

**Leaver:** Employee leaves organization

Each stage may require access changes.

# New Employee Onboarding

Possible account-related onboarding tasks include:

- Create or activate account
- Assign Microsoft 365 license
- Add approved groups
- Provide shared-folder access
- Configure email
- Configure MFA
- Provide required applications
- Confirm sign-in

These actions should follow approved onboarding procedures.

# Example — New Employee Missing Access

**Problem:**

A new employee can sign in but cannot access the department shared folder.

Possible process:

1. Verify onboarding request.
2. Confirm employee department.
3. Compare required role access.
4. Check group membership.
5. Add approved group if authorized.
6. Allow changes to apply.
7. Have user sign out/in if needed.
8. Test folder.
9. Document resolution.

# Employee Offboarding

Offboarding may involve:

- Disable account
- Revoke sign-in
- Remove group membership
- Revoke sessions
- Preserve business data
- Transfer ownership
- Remove application access

Offboarding is sensitive and should follow organizational procedures.

A technician should not delete account data without authorization.

# Example — Former Employee Account

If an employee leaves:

```text
Do not simply delete everything.
```

Business data, mailbox content, and files may need to be preserved.

Follow the organization's retention and offboarding process.

# Shared Mailbox Access

A user may require access to a shared mailbox.

Permissions can include concepts such as:

- Full Access
- Send As
- Send on Behalf

Having permission to open a mailbox does not automatically mean the user can send from it.

These permissions may require Microsoft 365 administrator support.

# Application Access

A user may sign into Windows successfully but still be unable to access an application.

Possible causes include:

- License missing
- Group membership missing
- Application-specific role
- Account not provisioned
- MFA policy
- Conditional access
- Application outage

This is an authorization issue rather than necessarily a Windows login problem.

# Licensing

Some applications require a license assignment.

Examples may include:

- Microsoft 365
- Specialized business software
- Cloud applications

If the user's account exists but the service is unavailable, licensing should be checked.

# Microsoft 365 Access

Possible Microsoft 365 access problems include:

- License missing
- Account disabled
- MFA failure
- Password issue
- Conditional access
- Service outage

Comparing access across:

```text
Outlook
Teams
OneDrive
Browser sign-in
```

can help determine scope.

# File Permissions

Windows file access may depend on:

- NTFS permissions
- Share permissions
- Group membership
- Inheritance
- Ownership

These should be changed only with proper authorization.

# Permission Inheritance

A child folder may inherit permissions from its parent.

Example:

```text
Finance
  |
  └── Reports
```

If Reports inherits permissions from Finance, changing the parent may affect the child.

Breaking inheritance can create unexpected access differences.

# Explicit Deny

A Deny permission can override expected access in many Windows permission scenarios.

Because Deny entries complicate troubleshooting, they should be used carefully.

# User Can Open but Cannot Modify

Possible causes include:

- Read-only permission
- Missing Modify permission
- File locked
- Application restriction
- Share permission more restrictive than NTFS

Possible process:

1. Confirm required access.
2. Check group membership.
3. Check NTFS permissions.
4. Check share permissions.
5. Check file lock.
6. Verify approved permission level.
7. Retest.
8. Document findings.

# User Cannot Install Software

Possible causes include:

- Standard user account
- Application requires elevation
- Application not approved
- Endpoint-management policy
- Software deployment restrictions

The solution is not automatically:

```text
Make user administrator
```

Instead determine the approved installation process.

# Example — User Requests Local Admin

**Problem:**

A user asks for administrator rights to install an application.

Possible process:

1. Identify the software.
2. Confirm business requirement.
3. Confirm software is approved.
4. Determine whether IT can install it using elevated credentials.
5. Avoid granting permanent admin access unless approved.
6. Complete installation through authorized process.
7. Verify application works.
8. Document the action.

# Access Denied After Department Transfer

Possible process:

1. Confirm new role.
2. Check required access.
3. Review current group membership.
4. Remove obsolete old-role groups.
5. Add approved new-role groups.
6. Have user sign out/in if necessary.
7. Verify access.
8. Document changes.

# Permission Changes May Take Time

Some access changes are not immediately visible.

Depending on the system, the user may need to:

- Sign out and back in
- Restart application
- Reconnect network resource
- Refresh authentication token

This should be considered before assuming the change failed.

# Cached Authentication

Users may retain old access information temporarily because of cached tokens or sessions.

Possible examples include:

- Microsoft 365 session
- Mapped drive
- VPN
- Application token

Signing out and back in can sometimes refresh access.

# Active Sessions

Changing a password or disabling an account does not always immediately terminate every existing session.

Organizations may have tools to revoke sessions when security requires it.

Session revocation is typically an administrative action.

# Service Accounts

Service accounts are used by applications or services rather than normal interactive users.

They may be used for:

- Windows services
- Scheduled tasks
- Applications

Service-account credentials should not be changed casually because doing so can break dependent systems.

# Shared Accounts

Shared user accounts reduce accountability and should generally be avoided unless specifically required by a system and organizational policy.

Individual accounts provide better:

- Auditing
- Accountability
- Access control

# Account Naming

Organizations may use naming conventions.

Conceptual examples:

```text
first.last
firstinitiallastname
employeeID
```

Technicians should follow established naming standards rather than creating inconsistent accounts.

# Security Questions and Recovery Information

Recovery information can provide account access and should be treated as sensitive.

Changes should require identity verification.

Do not place security answers or recovery secrets in tickets.

# Phishing and Account Access

A user reporting an unexpected login page or repeated MFA prompts may be experiencing a phishing attempt.

Possible warning signs include:

- Unexpected password prompt
- Suspicious URL
- Unexpected MFA request
- Email asking user to verify credentials

If phishing is suspected:

1. Tell user not to enter credentials.
2. Follow security-reporting procedure.
3. Escalate appropriately.
4. Reset credentials if compromise is suspected and authorized.

# Account Compromise Indicators

Possible signs include:

- Password suddenly stops working
- Unexpected MFA requests
- Unknown sign-ins
- Sent emails user did not send
- Changed account settings

These issues should be treated as potential security incidents rather than ordinary password problems.

# Scenario — User Forgot Password

Possible process:

1. Verify identity.
2. Confirm account.
3. Use self-service reset if available.
4. Reset if authorized.
5. Require password change if appropriate.
6. Test sign-in.
7. Confirm Microsoft 365 or other services.
8. Document the reset.

# Scenario — Account Locked

Possible process:

1. Verify identity.
2. Confirm lockout.
3. Unlock if authorized.
4. Ask about recent password change.
5. Check stored credentials.
6. Test sign-in.
7. Monitor whether lockout returns.
8. Document result.

# Scenario — MFA Phone Lost

Possible process:

1. Verify user identity.
2. Confirm no alternate method is available.
3. Follow approved MFA recovery procedure.
4. Remove old method if authorized.
5. Register new method.
6. Test sign-in.
7. Document change without storing secrets.

# Scenario — User Needs Shared Folder Access

Possible process:

1. Identify folder.
2. Confirm required access level.
3. Confirm manager or owner approval.
4. Check approved group.
5. Add user if authorized.
6. Refresh sign-in if needed.
7. Test folder access.
8. Verify required task.
9. Document approval and change.

# Scenario — User Has Too Much Access

**Problem:**

A user changed roles but can still access their former department files.

Possible process:

1. Verify role change.
2. Review old group membership.
3. Confirm access is no longer required.
4. Remove old membership if authorized.
5. Verify access is removed.
6. Check current-role access remains correct.
7. Document change.

# Scenario — User Cannot Access Application

Possible process:

1. Confirm application.
2. Verify user sign-in.
3. Check whether coworkers can access it.
4. Check licensing.
5. Check group membership or application role.
6. Check MFA.
7. Test browser access if appropriate.
8. Escalate provisioning issue if required.
9. Document findings.

# Scenario — Admin Rights Requested

Possible process:

1. Ask why admin rights are needed.
2. Identify task or application.
3. Verify approval.
4. Determine whether IT can perform the elevated task instead.
5. Follow least privilege.
6. Grant elevation only if required and approved.
7. Document reason and approval.

# Scenario — Repeated Microsoft 365 Sign-In Prompts

Possible process:

1. Confirm internet connectivity.
2. Verify password.
3. Test browser sign-in.
4. Check MFA.
5. Check account lockout.
6. Review Credential Manager if appropriate.
7. Restart application.
8. Restart Windows.
9. Escalate identity issue if needed.
10. Document findings.

# Escalation

Account and permission issues may require escalation when:

- Identity verification cannot be completed
- Account is disabled for an unknown reason
- Manager approval is required
- Permission changes exceed support scope
- Microsoft 365 administration is required
- MFA reset requires higher privileges
- Licensing needs adjustment
- Conditional access is involved
- Security compromise is suspected
- Administrator rights are requested
- Service accounts are involved
- Offboarding or legal hold requirements apply
- Access involves sensitive or regulated data

# Example Escalation Notes

```text
Issue:
User cannot access Finance shared folder.

Symptoms:
- Windows sign-in successful
- Network connectivity verified
- Finance share path reachable
- User receives Access Denied
- Other Finance users can access normally

Troubleshooting:
- User identity verified
- Correct share confirmed
- Credentials verified
- Group membership reviewed
- User is not a member of approved Finance access group

Escalation:
Access requires Finance manager approval and directory group update.
```

# Ticket Documentation Example

```text
User reported inability to access department shared folder after transferring teams.

Verified user identity and confirmed approved access request.

Reviewed account group membership and found required department access group missing.

Added user to approved access group according to request.

User signed out and back in.

Confirmed user could open, edit, and save files in required folder.

Verified old department access had already been removed.

Documented group change and approval in ticket.
```

# Account & Permission Troubleshooting Checklist

When troubleshooting account or permission problems, I can follow this process:

1. Gather symptoms and exact error messages.
2. Verify user identity.
3. Confirm the correct account.
4. Determine whether the problem is authentication or authorization.
5. Check account lockout or disabled status.
6. Check password status.
7. Check MFA if applicable.
8. Test access to other services.
9. Identify the exact resource.
10. Confirm required access level.
11. Check group membership.
12. Check permissions when authorized.
13. Compare with an equivalent approved user if useful.
14. Review recent role changes.
15. Check licensing if applicable.
16. Review cached credentials when appropriate.
17. Obtain required approval before changing access.
18. Apply least privilege.
19. Have the user refresh their session if needed.
20. Verify the required task works.
21. Confirm no unnecessary access was granted.
22. Document the change.
23. Escalate when approval, security, or administrative scope requires it.

# Key Takeaways

Some of the most important account and permission concepts include:

- Authentication proves identity while authorization controls access.
- User identity should be verified before sensitive account changes.
- Passwords and MFA codes should never be recorded in tickets.
- Account lockouts may return if old credentials remain stored on another device or application.
- Disabled accounts should not be re-enabled without authorization.
- MFA changes require careful identity verification.
- Group-based permissions make access easier to manage.
- Least privilege means users should receive only the access required for their role.
- Administrator rights should not be granted simply because a user requests them.
- Role changes should include both adding new access and removing obsolete access.
- Onboarding, role changes, and offboarding all require account lifecycle management.
- Licensing can affect access even when an account exists.
- Permission changes should have appropriate approval.
- Suspicious login activity or unexpected MFA prompts may require security escalation.
- A successful change should be verified using the user's actual required task.
- Clear ticket documentation should record what changed and why without exposing secrets.

Account and permission troubleshooting combines identity verification, authentication, authorization, access control, Microsoft 365 support, Windows permissions, security awareness, user communication, verification, and documentation.
