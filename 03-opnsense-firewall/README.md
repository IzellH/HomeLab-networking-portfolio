# OPNsense Firewall Lab

Documentation for deploying and configuring OPNsense as a virtualized firewall in Proxmox.

## Project Goals

- Deploy OPNsense as a virtual machine.
- Configure WAN and LAN interfaces.
- Create an isolated networking lab.
- Connect client VMs to the lab network.
- Practice firewall rules, routing, NAT, and network troubleshooting.

## Current Progress

- [x] OPNsense VM deployed.
- [x] WAN and LAN interfaces configured.
- [x] Web interface access established.
- [x] System updates applied.
- [x] Lab gateway connectivity verified.
- [x] Outbound IP connectivity verified.
- [ ] DNS resolution testing.
- [ ] Firewall policy testing.
- [ ] Network isolation testing.

## Network Architecture

Network addressing and topology details will be documented using sanitized examples to protect the private home network.

## Testing

Initial connectivity tests from the Ubuntu Desktop lab VM confirmed:

- Successful communication with the OPNsense LAN gateway.
- Successful outbound connectivity to `1.1.1.1`.
- Zero packet loss during both tests.

DNS resolution and firewall policy behavior have not yet been fully tested.

## Future Improvements

- Configure and document firewall rules.
- Verify NAT behavior.
- Test DNS resolution.
- Validate isolation between the lab and home networks.
- Add a sanitized network topology diagram.