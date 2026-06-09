# DNS Troubleshooting

## Overview

This note documents basic DNS troubleshooting steps for Windows support and help desk environments. DNS stands for Domain Name System. It translates domain names, such as google.com, into IP addresses that computers use to communicate over a network.

DNS issues can cause users to report that websites, email, Microsoft 365, shared resources, or cloud applications are not working.

## Common User Report

A user may report:

* “The internet is not working.”
* “Websites will not load.”
* “I can get to some sites but not others.”
* “Outlook or Teams will not connect.”
* “The shared drive is not opening.”
* “The browser says the site cannot be reached.”

## What DNS Does

DNS allows users to type names instead of IP addresses.

Example:

```text
google.com → IP address
```

If DNS is not working, the computer may still have a network connection but may not be able to resolve names.

## Basic DNS Troubleshooting Steps

### 1. Confirm the Issue

Ask the user what they are trying to access and whether the issue affects one website, multiple websites, or all network resources.

### 2. Check Network Connection

Use:

```cmd
ipconfig
```

Check for:

* Valid IP address
* Subnet mask
* Default gateway
* DNS server address

### 3. Test Basic Connectivity

Ping a public IP address:

```cmd
ping 8.8.8.8
```

If this works, the device may have internet connectivity, and the issue may be DNS-related.

### 4. Test DNS Resolution

Use:

```cmd
nslookup google.com
```

If DNS is working, the command should return an IP address.

### 5. Ping a Domain Name

Use:

```cmd
ping google.com
```

If pinging an IP works but pinging a name fails, DNS may be the issue.

### 6. Flush the DNS Cache

Use:

```cmd
ipconfig /flushdns
```

This clears cached DNS records from the computer.

### 7. Renew the IP Address

Use:

```cmd
ipconfig /release
ipconfig /renew
```

This can refresh the computer’s IP configuration, including DNS settings from DHCP.

### 8. Check for VPN Issues

If the user is connected to a VPN, DNS may be affected by VPN settings. Disconnecting and reconnecting to the VPN may help.

### 9. Test Another Browser or Application

If only one browser or application is affected, the issue may not be DNS. It could be a browser cache, proxy setting, or application issue.

### 10. Check Whether Other Users Are Affected

If multiple users are having the same issue, the problem may be with the DNS server, network equipment, or internet service.

## Useful Commands

```cmd
ipconfig
ipconfig /all
ipconfig /flushdns
ipconfig /release
ipconfig /renew
ping 8.8.8.8
ping google.com
nslookup google.com
tracert google.com
```

## Possible Causes

* Incorrect DNS server
* DNS server unavailable
* Stale DNS cache
* DHCP assigned incorrect DNS settings
* VPN DNS issue
* Browser cache issue
* Network outage
* ISP issue
* Internal DNS record issue

## Escalation Criteria

Escalate the issue if:

* Multiple users are affected
* DNS servers are unreachable
* Internal company resources cannot be resolved
* The issue affects Microsoft 365 or business-critical applications
* DNS settings are controlled by group policy
* Admin access is required
* The problem continues after basic troubleshooting

## Example Ticket Note

User reported that websites would not load, but the computer showed a network connection. Confirmed the device had a valid IP address. Ping to 8.8.8.8 was successful, but nslookup failed. Flushed DNS cache and renewed the IP address. DNS resolution worked after renewal, and the user confirmed websites loaded normally.

## What I Learned

DNS issues can look like general internet problems. Testing both IP connectivity and name resolution helps identify whether the issue is related to DNS, network connectivity, VPN settings, or a specific application.
