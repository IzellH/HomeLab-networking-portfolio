03 — Installation and Configuration

Overview

This document describes the deployment of OPNsense as a virtual machine within Proxmox VE.

The installation was completed as part of a larger homelab networking project focused on virtualization, firewall administration, and network segmentation.

Deployment Environment

Hypervisor: Proxmox VE

Virtual Machine: OPNsense-Lab

Network Infrastructure:

- "vmbr0" — Upstream network bridge.
- "vmbr1" — Isolated lab network bridge.

Connected Client: Ubuntu Desktop virtual machine.

Virtual Machine Deployment

OPNsense was deployed as a virtual machine within the Proxmox environment.

The deployment involved:

- Creating a dedicated virtual machine.
- Attaching virtual network interfaces.
- Connecting the WAN interface to "vmbr0".
- Connecting the LAN interface to "vmbr1".
- Installing and initializing OPNsense.
- Assigning WAN and LAN interfaces.

The virtual network interfaces provide OPNsense with separate connections to the upstream network and isolated lab network.

Interface Configuration

WAN Interface

The WAN interface was connected to the Proxmox "vmbr0" bridge.

Its purpose is to provide upstream connectivity through the existing home network.

LAN Interface

The LAN interface was connected to the Proxmox "vmbr1" bridge.

Its purpose is to provide gateway connectivity for virtual machines connected to the isolated lab network.

Interface Status

After configuration, the OPNsense dashboard displayed both WAN and LAN interfaces as operational.

Administrative Access

Access to the OPNsense administration environment was established through:

- The Proxmox virtual machine console.
- The OPNsense command-line interface.
- The OPNsense web administration interface.

Both terminal and web interface access were successfully restored during initial troubleshooting.

System Updates

Following initial deployment:

1. Administrative access was established.
2. System updates were initiated.
3. OPNsense was rebooted.
4. The web administration interface was accessed again.
5. Interface status and traffic activity were reviewed.

The dashboard subsequently displayed inbound and outbound traffic activity.

Initial Verification

The following deployment checks were completed:

- [x] OPNsense virtual machine deployed.
- [x] WAN interface connected to "vmbr0".
- [x] LAN interface connected to "vmbr1".
- [x] Terminal access established.
- [x] Web administration access established.
- [x] System updates applied.
- [x] System reboot completed.
- [x] WAN and LAN interface status reviewed.
- [x] Ubuntu Desktop connected to the lab network.

Outstanding Configuration Details

The following items will be documented as they are verified:

- Virtual machine CPU and memory allocation.
- Virtual disk configuration.
- Network adapter models.
- Exact OPNsense version.
- DHCP configuration.
- Firewall rule configuration.
- NAT behavior.

These details are intentionally left open rather than assuming configuration values that have not yet been recorded.

Lessons Learned

This deployment provided practical experience with:

- Virtual machine deployment in Proxmox VE.
- Assigning virtual network interfaces.
- Connecting virtual machines through Linux bridges.
- Configuring WAN and LAN interfaces.
- Accessing a firewall through both CLI and web administration.
- Applying system updates and verifying service availability.