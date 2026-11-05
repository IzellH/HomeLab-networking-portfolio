OPNsense Firewall & Network Segmentation Lab

Project Overview

This project documents the deployment and configuration of OPNsense as a virtualized firewall within a Proxmox VE homelab environment.

The primary objective is to build an isolated networking environment where routing, firewall administration, network segmentation, and connectivity troubleshooting can be practiced safely.

The lab uses a dedicated virtual network bridge to separate test systems from the primary home network.

Project Objectives

- Deploy OPNsense as a virtual machine in Proxmox VE.
- Configure WAN and LAN network interfaces.
- Establish an isolated virtual lab network.
- Connect client virtual machines to the lab network.
- Understand routing and outbound connectivity.
- Explore firewall policies and Network Address Translation (NAT).
- Test network connectivity and segmentation.
- Develop practical network administration and troubleshooting skills.

Lab Environment

- Hypervisor: Proxmox VE
- Firewall: OPNsense
- Client VM: Ubuntu Desktop
- Virtual Networking: Proxmox Linux bridges
- Physical Networking: Gigabit Ethernet
- Upstream Network: Existing home router

Network Architecture

The lab uses two Proxmox virtual bridges:

- vmbr0: Connects the OPNsense WAN interface to the upstream network.
- vmbr1: Provides an isolated virtual network for the OPNsense LAN interface and lab clients.

All network addresses and topology details published in this repository use sanitized documentation examples rather than actual home network values.

Implementation Progress

- [x] Created OPNsense virtual machine.
- [x] Configured WAN and LAN interfaces.
- [x] Connected WAN to the upstream network.
- [x] Connected LAN to an isolated virtual bridge.
- [x] Accessed the OPNsense terminal.
- [x] Established access to the OPNsense web interface.
- [x] Applied system updates and rebooted.
- [x] Connected Ubuntu Desktop to the lab network.
- [x] Verified connectivity to the OPNsense LAN gateway.
- [x] Verified outbound connectivity to an external IP address.
- [ ] Verify DNS resolution.
- [ ] Review firewall rules.
- [ ] Verify NAT configuration.
- [ ] Test network isolation.
- [ ] Document additional firewall policies.

Initial Connectivity Testing

Initial connectivity tests were performed from the Ubuntu Desktop virtual machine.

Test 1 — LAN Gateway Connectivity

- Destination: OPNsense LAN gateway
- Result: Passed
- Packet Loss: 0%

Test 2 — External IP Connectivity

- Destination: "1.1.1.1"
- Result: Passed
- Packet Loss: 0%

Test 3 — Firewall Traffic Monitoring

- OPNsense dashboard displayed inbound and outbound traffic.
- Result: Traffic activity observed.

Pending Tests

- DNS resolution.
- Firewall rule validation.
- NAT verification.
- Network isolation testing.

These initial results confirm basic gateway connectivity and outbound IP routing. DNS resolution and firewall isolation still require separate validation.

Documentation

Detailed implementation notes and test results will be maintained in the following sections:

- "Project Overview" (documentation/01-project-overview.md)
- "Network Architecture" (documentation/02-network-architecture.md)
- "Installation and Configuration" (documentation/03-installation-and-configuration.md)
- "Firewall and NAT" (documentation/04-firewall-and-nat.md)
- "Validation and Testing" (documentation/05-validation-and-testing.md)
- "Network Topology Diagram" (diagrams/network-topology.md)
- "Screenshots and Evidence" (screenshots/README.md)

These supporting documents will be added as the project documentation develops.

Skills Demonstrated

- Virtualization with Proxmox VE
- Firewall deployment and administration
- WAN/LAN interface configuration
- Virtual network segmentation
- Basic routing and connectivity testing
- Network troubleshooting
- Technical documentation

Project Status

Current Phase: Initial deployment and connectivity validation completed.

Next Phase: DNS verification, firewall policy review, NAT validation, and network isolation testing.