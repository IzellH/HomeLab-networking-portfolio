OPNsense Lab Network Topology

Overview

This diagram illustrates the logical network layout of the OPNsense virtual firewall lab running within Proxmox VE.

The topology uses two virtual bridges to connect the upstream network and the isolated lab environment.

All addressing shown is illustrative and sanitized for public documentation.

Network Diagram

flowchart TB
    Internet((Internet))
    Router["Upstream Home Router<br/>Example: 192.0.2.1"]
    
    subgraph Proxmox["Proxmox VE Host"]
        vmbr0["vmbr0<br/>Upstream Bridge"]
        vmbr1["vmbr1<br/>Isolated Lab Bridge"]
        
        subgraph Firewall["OPNsense Virtual Machine"]
            WAN["WAN Interface<br/>192.0.2.94"]
            LAN["LAN Interface<br/>198.51.100.1"]
        end
        
        Ubuntu["Ubuntu Desktop VM<br/>198.51.100.153"]
    end

    Internet --- Router
    Router --- vmbr0
    vmbr0 --- WAN
    WAN --- LAN
    LAN --- vmbr1
    vmbr1 --- Ubuntu

    classDef external fill:#64748b,color:#fff,stroke:#334155
    classDef firewall fill:#2563eb,color:#fff,stroke:#1e40af
    classDef network fill:#0f766e,color:#fff,stroke:#115e59
    classDef client fill:#7c3aed,color:#fff,stroke:#5b21b6

    class Internet,Router external
    class WAN,LAN firewall
    class vmbr0,vmbr1 network
    class Ubuntu client

Component Descriptions

- Internet: External destinations reached through the upstream network.
- Upstream Router: Provides connectivity between the home network and internet.
- vmbr0: Proxmox bridge connecting the OPNsense WAN interface to the upstream network.
- OPNsense WAN: Receives upstream connectivity.
- OPNsense LAN: Provides gateway and firewall services to the lab network.
- vmbr1: Isolated Proxmox virtual bridge for lab clients.
- Ubuntu Desktop: Client virtual machine used for connectivity and firewall testing.

Traffic Flow

Outbound traffic from Ubuntu Desktop follows this general path:

1. Ubuntu Desktop sends traffic to its default gateway.
2. OPNsense evaluates the traffic against its firewall rules.
3. Permitted traffic is routed toward the WAN interface.
4. Traffic exits through "vmbr0" toward the upstream router.
5. Return traffic is handled through the appropriate routing and NAT configuration.

Addressing Note

The IP addresses in this diagram are documentation-only examples. They do not represent the actual operational network addresses.

The diagram represents the intended logical architecture, not proof that all inter-network isolation policies have been tested.