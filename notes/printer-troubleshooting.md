# Printer Troubleshooting

This file documents common printer troubleshooting steps for IT support practice.

## Purpose

The goal of this lab is to understand how IT support technicians troubleshoot common printer issues in Windows and office environments.

## Common Printer Issues

Users may report issues such as:

* Printer is not printing
* Printer shows offline
* Print job is stuck in the queue
* Printer is printing slowly
* Printer is printing blank pages
* User cannot find the printer
* Printer has a paper jam
* Printer needs toner or ink
* Printer driver is missing or outdated
* User cannot print to a network printer

## Basic Troubleshooting Process

1. Confirm the printer is powered on.
2. Check for error lights or messages.
3. Confirm the printer has paper, toner, or ink.
4. Check for paper jams.
5. Confirm the computer is connected to the network.
6. Check whether other users can print.
7. Check the print queue.
8. Restart the printer if needed.
9. Restart the Print Spooler service if needed.
10. Document the issue, steps taken, and resolution.

## Windows Tools to Check

### Settings

Used to check installed printers and default printer settings.

### Control Panel

Used to view devices and printers.

### Print Queue

Used to check stuck print jobs.

### Device Manager

Used to check printer drivers and device errors.

### Services

Used to check or restart the Print Spooler service.

## Command Prompt Commands

### View network connectivity

```cmd
ping printer-ip-address
```

### Check IP configuration

```cmd
ipconfig
```

## PowerShell Commands

### Check the Print Spooler service

```powershell
Get-Service -Name Spooler
```

### Restart the Print Spooler service

```powershell
Restart-Service -Name Spooler
```

## Example Scenario

### Problem

A user says their printer is not printing, but the printer is powered on.

### Steps to Check

1. Ask if the issue affects only one user or multiple users.
2. Check if the printer shows offline.
3. Check the print queue for stuck jobs.
4. Confirm the printer has paper and toner.
5. Restart the printer if needed.
6. Restart the Print Spooler service if appropriate.
7. Test printing again.
8. Document the final result.

## Documentation Notes

When documenting a printer issue, I should include:

* User affected
* Printer name or location
* Error message
* Whether the issue affects one user or multiple users
* Whether the printer is local or networked
* Troubleshooting steps taken
* Commands or tools used
* Final resolution or escalation notes

## What I Am Learning

I am learning how printer issues can involve hardware, network connectivity, drivers, print queues, services, and user settings. This is useful for help desk, desktop support, and IT support roles.

## Safety Note

I should avoid uploading screenshots or notes that show printer IP addresses, company printer names, internal network details, usernames, or private documents.
