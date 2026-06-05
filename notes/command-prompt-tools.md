# Command Prompt Tools

This file documents common Windows Command Prompt tools used for IT support troubleshooting.

## Purpose

The goal of this lab is to practice basic Windows command-line tools used for network troubleshooting, system repair, and support documentation.

## Why Command Prompt Matters

Command Prompt is useful in IT support because it allows technicians to quickly check network settings, test connectivity, troubleshoot DNS issues, and run basic system repair commands.

## Networking Commands

### ipconfig

Shows IP address, subnet mask, default gateway, and network adapter information.

```cmd
ipconfig
```

### ipconfig /all

Shows detailed network configuration information.

```cmd
ipconfig /all
```

### ping

Tests network connectivity.

```cmd
ping 8.8.8.8
```

```cmd
ping google.com
```

### tracert

Shows the path network traffic takes to reach a destination.

```cmd
tracert google.com
```

### nslookup

Checks DNS name resolution.

```cmd
nslookup google.com
```

## System Repair Commands

### sfc /scannow

Scans protected Windows system files and attempts to repair issues.

```cmd
sfc /scannow
```

### chkdsk

Checks a disk for file system errors.

```cmd
chkdsk
```

## Policy and Network Commands

### gpupdate /force

Forces Group Policy updates on a Windows device.

```cmd
gpupdate /force
```

### net use

Used to view or connect to shared network resources.

```cmd
net use
```

## Practice Lab

Commands practiced:

```cmd
ipconfig
ipconfig /all
ping 8.8.8.8
ping google.com
tracert google.com
nslookup google.com
sfc /scannow
chkdsk
gpupdate /force
net use
```

## Example Troubleshooting Scenario

### Problem

A user says they are connected to the network but cannot access websites.

### Steps to Check

1. Run `ipconfig` to check IP address information.
2. Ping `8.8.8.8` to test internet connectivity by IP address.
3. Ping `google.com` to test DNS/name resolution.
4. Run `nslookup google.com` to check DNS results.
5. Run `tracert google.com` if the connection path needs to be checked.
6. Document the results and escalate if needed.

## What I Am Learning

I am learning how command-line tools can help narrow down Windows support issues. These commands help identify whether a problem may be related to IP configuration, DNS, internet connectivity, system files, or network resources.

## IT Support Notes

When using Command Prompt for troubleshooting, I should document:

* The command used
* The result or error message
* Whether the issue affected one user or multiple users
* Any changes made
* Whether the issue was resolved or escalated

## Safety Note

I should avoid posting screenshots or command outputs that show private IP addresses, usernames, computer names, domains, or sensitive network information.
