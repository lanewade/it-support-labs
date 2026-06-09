# Ticket Example: Network Connectivity Issue

## Ticket Summary

User reports they are unable to connect to the network from their workstation.

## User Impact

The user cannot access the internet, shared resources, email, or cloud-based applications needed for daily work.

## Initial User Report

The user stated that their computer shows no internet connection and they are unable to access websites or Microsoft 365 services.

## Troubleshooting Steps

1. Confirmed the issue with the user and asked when the problem started.
2. Checked whether other users in the same area were experiencing similar issues.
3. Verified that the Ethernet cable was connected securely to the workstation and wall port.
4. Checked for link lights on the workstation network port.
5. Restarted the workstation to rule out a temporary software issue.
6. Opened Command Prompt and ran:

```cmd
ipconfig
```

7. Checked whether the workstation had a valid IP address, subnet mask, default gateway, and DNS server.
8. Ran a loopback test:

```cmd
ping 127.0.0.1
```

9. Tested local network connectivity by pinging the default gateway:

```cmd
ping [default-gateway]
```

10. Tested external connectivity:

```cmd
ping 8.8.8.8
```

11. Tested DNS resolution:

```cmd
nslookup google.com
```

12. Released and renewed the IP address:

```cmd
ipconfig /release
ipconfig /renew
```

13. Flushed the DNS cache:

```cmd
ipconfig /flushdns
```

14. Tested the connection again after each step.

## Possible Causes

* Loose or damaged Ethernet cable
* Bad wall port
* Switch port issue
* DHCP issue
* DNS issue
* Incorrect IP configuration
* Network adapter problem
* Local workstation issue

## Resolution

After reseating the Ethernet cable and renewing the IP address, the workstation received a valid IP address and network connectivity was restored.

## Ticket Notes

The issue appeared to be related to the workstation not receiving a valid IP address. The user was able to access the internet and Microsoft 365 services after troubleshooting.

## Escalation Criteria

This issue would be escalated to Tier 2 or the network team if:

* Multiple users were affected
* The switch port was down
* The wall jack appeared damaged
* DHCP was not assigning addresses
* The workstation could not reach the default gateway
* The issue continued after replacing the cable and testing another port

## What I Learned

This ticket helped reinforce the importance of checking physical connections first, then using command-line tools to narrow down whether the issue is related to the workstation, IP addressing, DNS, or the network infrastructure.
