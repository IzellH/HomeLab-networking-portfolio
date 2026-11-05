02 — Network Architecture

Overview

The OPNsense lab uses Proxmox VE virtual networking to separate the upstream home network from an isolated environment used for networking experiments.

Two Proxmox Linux bridges provide the foundation for this configuration:

- "vmbr0" — Upstream network connection.
- "vmbr1" — Isolated lab network.

OPNsense connects these two networks through separate virtual network interfaces and acts as the gateway for the lab environment.

Network Components

1. Proxmox Virtual Bridge — vmbr0

Purpose: Upstream network connectivity.

- Connected to the physical network interface.
- Bridges virtual machine traffic to the existing upstream network.
- Connected to the OPNsense WAN interface.
- Provides the upstream path toward internet connectivity.

2. Proxmox Virtual Bridge — vmbr1

Purpose: Isolated lab connectivity.

- Provides a separate virtual network.
- Connected to the OPNsense LAN interface.
- Connects lab client virtual machines.
- Allows networking experiments without directly attaching lab clients to the primary physical network.

3. OPNsense Firewall

OPNsense serves as the central routing and firewall device.

WAN Interface

- Connected to "vmbr0".
- Receives upstream network connectivity.
- Provides the external-facing side of the firewall.

LAN Interface

- Connected to "vmbr1".
- Serves as the gateway for the isolated lab network.
- Provides the internal-facing side of the firewall.

4. Ubuntu Desktop Client

An Ubuntu Desktop virtual machine is connected to the isolated lab network through "vmbr1".

It serves as the primary test client for:

- Gateway connectivity.
- External IP connectivity.
- DNS resolution testing.
- Firewall rule validation.
- Network troubleshooting.

Logical Network Layout

The following addressing is illustrative and sanitized for public documentation. It does not represent the actual home network configuration.

- Upstream network example: "192.0.2.0/24"
- Lab network example: "198.51.100.0/24"
- Example OPNsense WAN address: "192.0.2.94"
- Example OPNsense LAN address: "198.51.100.1"
- Example Ubuntu Desktop address: "198.51.100.153"

Traffic Flow

When the Ubuntu Desktop client attempts to reach an external destination, traffic follows this general path:

1. Ubuntu Desktop generates an outbound network request.
2. The request is sent to the OPNsense LAN gateway.
3. OPNsense evaluates the traffic against its firewall policies.
4. If permitted, traffic is routed toward the WAN interface.
5. The traffic passes through "vmbr0" toward the upstream router.
6. Return traffic follows the appropriate routing and NAT behavior back toward the client.

The exact behavior depends on the firewall rules and NAT configuration, which will be documented and verified separately.

Network Segmentation

The use of separate Proxmox bridges provides logical separation between the upstream network and the lab network.

This design creates a controlled environment for experimenting with:

- Firewall policies.
- Routing.
- Network access restrictions.
- Client connectivity.
- Network isolation.

The presence of a separate virtual bridge alone does not prove that all traffic between the lab and home network is blocked. That behavior will be validated through additional testing.

Architecture Validation

Initial testing confirmed:

- The Ubuntu Desktop client could reach the OPNsense LAN gateway.
- The Ubuntu Desktop client could reach an external IP address.
- Both initial ping tests completed with zero packet loss.
- OPNsense displayed inbound and outbound traffic activity.

Further testing is required to verify DNS resolution, firewall restrictions, and isolation between the lab and upstream networks.

Security and Documentation Notes

All published addressing examples are reserved documentation ranges rather than actual operational addresses.

Sensitive information, including private network addresses, public IP addresses, credentials, and authentication keys, must not be included in public documentation.