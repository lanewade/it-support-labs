# Wi-Fi Troubleshooting

## Overview

This note documents basic Wi-Fi troubleshooting steps for Windows support and help desk environments. Wi-Fi issues can affect internet access, Microsoft 365 services, shared drives, printers, VPN connections, and other network resources.

Wi-Fi problems may be caused by signal strength, incorrect passwords, disabled wireless adapters, driver issues, DHCP problems, DNS problems, access point issues, or network outages.

## Common User Report

A user may report:

* “I cannot connect to Wi-Fi.”
* “The Wi-Fi keeps disconnecting.”
* “The internet is slow.”
* “My laptop says connected, but nothing loads.”
* “I do not see the company Wi-Fi network.”
* “My Wi-Fi worked yesterday, but now it does not.”

## Initial Questions to Ask

Before troubleshooting, ask the user:

1. When did the issue start?
2. Are they using a laptop, desktop, phone, or tablet?
3. Can they see the Wi-Fi network name?
4. Are other users having the same issue?
5. Are they in the office, at home, or remote?
6. Did they recently change their password?
7. Are they connected to VPN?
8. Does the issue happen in one location or multiple locations?

## Basic Wi-Fi Troubleshooting Steps

### 1. Confirm Wi-Fi Is Enabled

Check that Wi-Fi is turned on and that airplane mode is disabled.

### 2. Confirm the Correct Network

Make sure the user is connecting to the correct SSID, or Wi-Fi network name.

A user may accidentally connect to a guest network, hotspot, or old saved network.

### 3. Check Signal Strength

Weak signal can cause slow speeds, dropped connections, and intermittent issues.

If the signal is weak, ask the user to move closer to the wireless access point if possible.

### 4. Forget and Reconnect to the Network

If the saved Wi-Fi profile is corrupted or has an old password, forget the network and reconnect.

### 5. Restart Wi-Fi

Turn Wi-Fi off and back on.

This can refresh the wireless connection.

### 6. Restart the Computer

Restarting the computer can clear temporary network or driver issues.

### 7. Check IP Configuration

Open Command Prompt and run:

```cmd
ipconfig
```

Check for:

* Valid IP address
* Subnet mask
* Default gateway
* DNS server

### 8. Check for APIPA Address

If the device has an IP address beginning with:

```text
169.254.x.x
```

The device likely did not receive a valid IP address from DHCP.

### 9. Release and Renew the IP Address

Run:

```cmd
ipconfig /release
ipconfig /renew
```

This asks the DHCP server for a new IP address.

### 10. Flush DNS Cache

Run:

```cmd
ipconfig /flushdns
```

This clears cached DNS records.

### 11. Test Network Connectivity

Test connectivity with:

```cmd
ping [default-gateway]
ping 8.8.8.8
ping google.com
nslookup google.com
```

These commands help determine whether the issue is local Wi-Fi, internet connectivity, or DNS.

### 12. Check Network Adapter

Open Device Manager and check the wireless adapter.

Look for:

* Disabled adapter
* Warning icons
* Driver issues
* Missing wireless adapter

### 13. Restart the Wireless Adapter

Disable and re-enable the wireless adapter if allowed.

### 14. Check for VPN Issues

If the user is connected to a VPN, disconnect and reconnect to the VPN.

VPN settings can affect DNS, routing, and access to internal resources.

### 15. Check Whether Other Users Are Affected

If multiple users are having Wi-Fi issues, the problem may be with:

* Wireless access point
* Network switch
* DHCP server
* DNS server
* Internet service
* Authentication server
* Wi-Fi coverage in that area

## Useful Commands

```cmd
ipconfig
ipconfig /all
ipconfig /release
ipconfig /renew
ipconfig /flushdns
ping [default-gateway]
ping 8.8.8.8
ping google.com
nslookup google.com
tracert google.com
```

## Possible Causes

* Wi-Fi disabled
* Airplane mode enabled
* Incorrect Wi-Fi password
* Connected to the wrong SSID
* Weak wireless signal
* Wireless adapter driver issue
* DHCP issue
* DNS issue
* VPN issue
* Access point issue
* Network outage
* Account or authentication issue
* Too many devices connected to the wireless network

## Possible Resolutions

* Enable Wi-Fi
* Disable airplane mode
* Connect to the correct SSID
* Forget and reconnect to the network
* Restart the computer
* Restart the wireless adapter
* Renew the IP address
* Flush DNS cache
* Move closer to the access point
* Update or reinstall the wireless driver if approved
* Escalate if multiple users are affected

## Escalation Criteria

Escalate the issue if:

* Multiple users are affected
* The wireless network is not visible
* The device cannot receive an IP address
* The user cannot authenticate to the Wi-Fi network
* The access point may be down
* The issue affects an entire office area
* Admin permissions are required
* Network infrastructure needs to be checked
* The issue continues after basic troubleshooting

## Example Ticket Note

User reported they could not connect to the company Wi-Fi. Confirmed Wi-Fi was enabled and airplane mode was off. Verified the user was connecting to the correct SSID. The device showed a weak signal and failed to load websites. Ran `ipconfig` and confirmed the workstation had a valid IP address. Moved the user closer to the access point and reconnected to Wi-Fi. User confirmed internet access and Microsoft 365 services were working.

## What I Learned

Wi-Fi troubleshooting requires checking both simple and technical causes. Verifying Wi-Fi status, SSID, signal strength, IP configuration, DNS, and whether other users are affected helps narrow down whether the issue is with the device, wireless signal, or network infrastructure.
