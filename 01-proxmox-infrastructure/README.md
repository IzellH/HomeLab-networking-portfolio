🖥️ Project 01 — Proxmox Infrastructure

Building and managing a virtualized home lab environment

---

📌 Project Overview

This project documents the design, installation, and ongoing development of my Proxmox VE home lab.

The goal is to build a flexible virtualization environment where I can deploy virtual machines, experiment with networking, manage storage, and host services.

This infrastructure also serves as the foundation for my networking and systems administration learning projects.

🎯 Project Objectives

- Install and configure Proxmox VE.
- Understand hypervisors and virtualization.
- Create and manage virtual machines.
- Configure virtual networking and Linux bridges.
- Explore network isolation.
- Configure shared storage between systems.
- Deploy and manage self-hosted services.
- Practice Linux administration and troubleshooting.

---

🧰 Hardware Specifications

Component| Specification
CPU| AMD Ryzen 5 3600
RAM| 32 GB DDR4-3600
GPU| NVIDIA GTX 1650 Super
Primary Storage| 256 GB SSD
Secondary Storage| 1 TB HDD

⚙️ Software & Technologies

- Proxmox VE
- Ubuntu Server
- Ubuntu Desktop
- OPNsense
- Pi-hole
- Docker
- Portainer
- NFS
- Tailscale

---

🌐 Virtual Networking

The Proxmox host uses Linux bridges to connect virtual machines to different network environments.

Current Bridge Configuration

Bridge| Purpose| Configuration
"vmbr0"| Primary network| Connected to physical Ethernet interface
"vmbr1"| Isolated lab network| Virtual switch without a physical uplink

Networking Concepts Practiced

- Linux bridges
- Virtual network interfaces
- DHCP addressing
- Network isolation
- Virtual machine connectivity
- Routing through OPNsense

Private network details and actual device addresses are intentionally excluded from this public documentation.

---

🗄️ Storage Infrastructure

The lab uses local storage and network file sharing.

Storage Concepts Practiced

- Proxmox storage management
- Directory-based storage
- Linux filesystem permissions
- Shared directories
- Network File System (NFS)
- Mounting remote filesystems

An NFS share provides shared storage between the Proxmox host and Ubuntu Server environment.

---

🖥️ Virtual Machines & Services

System| Purpose
Ubuntu Server| Docker and self-hosted services
OPNsense| Firewall and routing laboratory
Pi-hole| DNS filtering and DNS learning
Ubuntu Desktop| Client machine for network testing

Additional services are hosted through Docker and managed using Portainer.

---

🔍 Skills Developed

- Hypervisor installation and management
- Virtual machine deployment
- Linux system administration
- Virtual networking
- Storage management
- NFS configuration
- Docker container management
- Network troubleshooting

---

🧠 Challenges & Lessons Learned

This section will document real problems encountered during development, the troubleshooting process, and the solutions implemented.

Examples include:

- Troubleshooting virtual machine network connectivity.
- Configuring shared storage and filesystem permissions.
- Deploying services through Docker and Portainer.
- Understanding the differences between physical and virtual networking.

Detailed troubleshooting reports will be added as individual experiences are documented.

---

📈 Future Improvements

- Expand network monitoring capabilities.
- Introduce managed switching and VLANs.
- Improve infrastructure documentation.
- Explore automated backups.
- Experiment with additional virtual network topologies.
- Evaluate additional hardware as lab requirements grow.

---

📚 Project Status

Status: Active Development

This project is an ongoing learning environment. Documentation will be updated as the infrastructure evolves and new skills are developed.

---

Part of my Homelab & Networking Portfolio.
