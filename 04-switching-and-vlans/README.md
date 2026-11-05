# Switching and VLANs

Documentation for Ethernet switching, network segmentation, and VLAN configuration experiments.

## Lab Equipment

- TP-Link TL-SG1005D unmanaged 5-port Gigabit Ethernet switch.
- Proxmox VE host.
- OPNsense virtual firewall.
- Virtual network bridges.

## Current Knowledge and Setup

- Basic Ethernet switching.
- Physical and virtual network connections.
- Proxmox Linux bridges.
- WAN and LAN interface separation using OPNsense.

## VLAN Learning Objectives

- Understand VLANs and 802.1Q tagging.
- Learn access ports and trunk ports.
- Understand inter-VLAN routing.
- Explore firewall rules between VLANs.
- Practice network segmentation.

## Important Hardware Limitation

The TP-Link TL-SG1005D is an unmanaged switch and does not support configurable VLANs.

Future VLAN experiments will require VLAN-capable hardware or virtual networking configurations.

## Future Labs

- [ ] Study VLAN tagging.
- [ ] Build a virtual VLAN lab.
- [ ] Configure inter-VLAN routing.
- [ ] Test communication between segmented networks.
- [ ] Document firewall policies between networks.