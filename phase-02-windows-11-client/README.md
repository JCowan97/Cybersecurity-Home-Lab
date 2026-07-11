# Phase 02 – Windows 11 Client VM Build

## Overview

In this phase, I built the first endpoint for my cybersecurity home lab: a Windows 11 client virtual machine.

This machine will later be used for:

- Active Directory domain membership
- Windows event log analysis
- Sysmon monitoring
- SIEM log forwarding
- Network traffic capture
- Endpoint investigation
- Controlled attack simulation
- Blue-team detection exercises

The virtual machine was created using VMware Workstation Pro and stored on an external SSD.

---

## Objectives

The objectives of this phase were to:

- Create a Windows 11 virtual machine
- Store the VM on the external SSD
- Install Windows 11
- Configure a local Windows account
- Rename the computer
- Install VMware Tools
- Install core administration and investigation tools
- Apply Windows updates
- Create a clean VMware snapshot
- Document the build for GitHub

---

## Host Environment

The home lab is running on the following host system:

- Host operating system: Windows 11
- Processor: Intel Core i9
- Memory: 32 GB RAM
- Graphics: NVIDIA RTX 4060
- Internal storage: 1 TB SSD
- External lab storage: SanDisk 1 TB portable SSD
- Hypervisor: VMware Workstation Pro

---

## Virtual Machine Configuration

The Windows 11 virtual machine was created with the following configuration:

- Virtual machine name: `WIN11-CLIENT01`
- Guest operating system: Windows 11
- Storage location: External SSD
- Firmware: UEFI
- Virtual TPM: Enabled
- Network connection: VMware NAT during initial setup
- Account type: Local Windows account

The virtual machine files were stored on the external SSD to keep the lab environment separated from the host computer’s internal storage.

![Windows 11 VM configuration](screenshots/figure-09-default-hardware.png)

---

## Windows 11 Installation

Windows 11 was installed using an official Windows installation ISO.

During installation, I chose not to connect the virtual machine to my personal Microsoft account. Instead, I completed the setup using a local Windows account.

This keeps the home lab separate from my personal accounts and prevents unnecessary synchronisation between the virtual machine and my primary computer.

![Windows 11 installation](screenshots/02-windows-installation.png)

![Local account configuration](screenshots/03-local-account.png)

---

## Computer Naming

The Windows computer was renamed to:

`WIN11-CLIENT01`

A consistent naming convention will make it easier to identify systems as the home lab expands to include additional Windows clients, servers, Linux machines, firewalls and monitoring systems.

![Windows computer name](screenshots/04-computer-name.png)

---

## VMware Tools Installation

VMware Tools was installed inside the Windows 11 virtual machine using the Typical installation option.

VMware Tools provides:

- Improved virtual display drivers
- Automatic screen resizing
- Better mouse and keyboard integration
- Improved guest operating system performance
- Clipboard and drag-and-drop integration when enabled
- Better communication between VMware and the guest operating system

The virtual machine was restarted after the installation was completed.

![VMware Tools installation](screenshots/05-vmware-tools.png)

---

## Installed Tools

The following tools were installed or prepared on the Windows 11 client:

| Tool | Purpose |
|---|---|
| VMware Tools | Provides VMware drivers and guest integration |
| Visual Studio Code | Used for scripts, configuration files and documentation |
| Git | Provides version control and GitHub integration |
| 7-Zip | Used to extract compressed files and tool archives |
| Sysinternals Suite | Provides Windows administration and investigation tools |
| Web browser | Used to access documentation and download authorised tools |

---

## Sysinternals Suite

The Microsoft Sysinternals Suite was downloaded and extracted to:

`C:\Tools\Sysinternals`

Sysinternals tools are portable applications and do not require a normal installation process.

The main tools reviewed during this phase were:

### Process Explorer

Process Explorer provides a detailed view of running processes, parent-child relationships, loaded files and system activity.

### Process Monitor

Process Monitor records real-time file system, registry, process and thread activity.

### Autoruns

Autoruns identifies programs, services and scheduled tasks that automatically start with Windows.

### TCPView

TCPView displays active TCP and UDP connections, listening ports and the processes associated with them.

![Sysinternals folder](screenshots/06-sysinternals-folder.png)

![Process Explorer](screenshots/07-process-explorer.png)

---

## Windows Updates

Windows Update was run after the initial installation.

Installing current Windows updates created a more secure and stable baseline before the system is connected to other home-lab machines.

![Windows Update](screenshots/08-windows-update.png)

---

## Clean Snapshot

After the operating system and core tools were installed, the virtual machine was shut down and a clean VMware snapshot was created.

Snapshot name:

`WIN11-CLIENT01 - Clean Build`

This snapshot provides a known-good recovery point before the system is:

- Joined to an Active Directory domain
- Connected to an isolated lab network
- Configured with Sysmon
- Connected to a SIEM
- Used in attack and detection exercises

![VMware clean snapshot](screenshots/09-clean-snapshot.png)

---

## Problems Encountered

### Microsoft Account Setup

Windows encouraged the use of an online Microsoft account during setup.

**Resolution:**  
The network connection was disconnected and the Windows installation was completed using a local account.

### VMware Display and Integration

Before VMware Tools was installed, the virtual display and mouse integration were limited.

**Resolution:**  
VMware Tools was installed using the Typical setup option, followed by a restart of the virtual machine.

### Sysinternals Installation

The Sysinternals Suite did not use a traditional installer.

**Resolution:**  
The downloaded ZIP archive was extracted to `C:\Tools\Sysinternals`, and the required applications were launched directly from that folder.

---

## Security Considerations

The following precautions were used during the build:

- No personal Microsoft account was connected to the VM
- No personal documents were intentionally stored inside the VM
- No personal credentials were added to the VM
- Testing will only be conducted against systems owned and controlled within the home lab
- Snapshots will be created before major configuration changes
- The lab will later be placed behind a dedicated virtual firewall
- Intentionally vulnerable systems will remain isolated from the normal home network

---

## Skills Developed

This phase provided practical experience in:

- Creating a VMware virtual machine
- Installing Windows 11 in a virtual environment
- Configuring a local Windows account
- Naming a system using a consistent lab convention
- Installing VMware guest drivers
- Installing and organising Windows administration tools
- Using Microsoft Sysinternals utilities
- Applying Windows security updates
- Creating VMware recovery snapshots
- Writing technical documentation using Markdown
- Organising screenshots for a GitHub portfolio

---

## Next Phase

The next phase will involve building a Kali Linux virtual machine.

The Kali Linux VM will eventually be used for:

- Network discovery
- Nmap scanning
- Service enumeration
- Vulnerability assessment
- Web application testing
- Controlled penetration-testing exercises
- Generating activity for blue-team investigation

The Kali VM will be used only against authorised systems contained within the home lab.

---

## Build Status

- [x] Windows 11 VM created
- [x] VM stored on external SSD
- [x] Windows 11 installed
- [x] Local Windows account configured
- [x] Computer renamed to `WIN11-CLIENT01`
- [x] VMware Tools installed
- [x] Visual Studio Code installed
- [x] Git installed
- [x] 7-Zip installed
- [x] Sysinternals Suite extracted
- [x] Windows updates completed
- [x] Clean VMware snapshot created
- [ ] Wireshark installed
- [ ] Nmap installed
- [ ] Sysmon configured
- [ ] Active Directory domain joined
- [ ] SIEM agent installed
- [ ] Lab firewall connection configured
