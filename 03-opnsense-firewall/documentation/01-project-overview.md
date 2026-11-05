01 — Project Overview

Project Background

This project is part of an ongoing homelab networking environment built using Proxmox VE.

The goal was to deploy OPNsense as a virtualized firewall and use it to create a separate networking environment for hands-on experimentation.

Rather than relying exclusively on theoretical networking exercises,this project provides an opportunity to work with real firewall software, virtual network interfaces, routing, and connected client systems.

Project Goals

The primary goals of this project are:

- Gain practical experience administering a network firewall.
- Understand the relationship between WAN and LAN interfaces.
- Learn how virtual network bridges connect virtual machines.
- Create an isolated environment for networking experiments.
- Understand how traffic moves between separate networks.
- Practice firewall rule configuration and traffic filtering.
- Develop troubleshooting skills through connectivity testing.

Infrastructure Overview

The environment consists of:

- Proxmox VE: Physical virtualization host.
- OPNsense: Virtualized firewall and network gateway.
- Ubuntu Desktop: Client machine used for connectivity testing.
- Proxmox Linux Bridges: Virtual networking infrastructure.
- Upstream Router: Provides connectivity to the existing home network and internet.

OPNsense operates between the upstream network and the isolated lab network.

Learning Objectives

This project is intended to develop practical knowledge in the following areas:

Network Fundamentals

- Private IPv4 addressing.
- Subnetting and network boundaries.
- Default gateways.
- Routing between networks.

Firewall Administration

- WAN and LAN interface configuration.
- Firewall rules and traffic filtering.
- Network Address Translation (NAT).
- Inbound and outbound traffic behavior.

Virtual Networking

- Proxmox Linux bridges.
- Virtual network interfaces.
- Connecting virtual machines to separate networks.
- Network segmentation.

Troubleshooting

- Using "ping" to test connectivity.
- Identifying gateway and routing problems.
- Testing external IP connectivity.
- Diagnosing DNS resolution problems.
- Reviewing firewall traffic and system logs.

Current Project Status

The initial deployment and basic connectivity tests have been completed.

OPNsense is operational, its web administration interface is accessible, and an Ubuntu Desktop virtual machine has successfully communicated with the lab gateway and an external IP address.

Further testing will focus on DNS, firewall policies, NAT behavior, and network isolation.

Expected Outcome

By completing this project, the objective is to demonstrate the ability to deploy, configure, administer, and troubleshoot a virtualized firewall environment.

The project will also serve as a foundation for more advanced networking exercises involving VLANs, inter-network routing, access control, and security monitoring.