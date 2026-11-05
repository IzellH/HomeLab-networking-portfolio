04 — Firewall and Network Address Translation (NAT)

Overview

This document covers firewall administration and Network Address Translation (NAT) within the OPNsense lab environment.

The purpose of this section is to understand how OPNsense evaluates network traffic, controls communication between interfaces, and enables connectivity between the isolated lab network and external destinations.

Firewall Fundamentals

A firewall monitors and controls network traffic according to configured security policies.

OPNsense uses firewall rules to determine which traffic is permitted or denied.

Important concepts include:

- Inbound traffic: Traffic entering an interface.
- Outbound traffic: Traffic leaving an interface.
- Source address: The originating IP address.
- Destination address: The target IP address.
- Protocol: The communication protocol, such as TCP, UDP, or ICMP.
- Port: The service-specific communication endpoint.
- Firewall rule: A policy determining whether traffic is allowed or blocked.

WAN and LAN Security

The OPNsense lab uses separate WAN and LAN interfaces.

WAN Interface

The WAN interface connects OPNsense to the upstream network.

Its role is to receive and forward traffic between the firewall and the upstream network, subject to firewall and routing policies.

LAN Interface

The LAN interface provides connectivity to the isolated lab network.

Firewall policies on this interface determine which traffic lab clients may initiate.

Firewall Rule Management

Firewall rules will be reviewed and documented as the lab develops.

Areas of investigation include:

- Default LAN firewall behavior.
- WAN inbound traffic restrictions.
- LAN-to-WAN connectivity.
- Rules permitting or denying specific protocols.
- Rules restricting access to selected destinations.
- Logging and reviewing blocked traffic.

No custom firewall policies are claimed as completed in this document until they have been configured and tested.

Network Address Translation (NAT)

NAT allows multiple devices on a private network to communicate with external networks using translated source addresses.

In this lab, outbound NAT is an important area to investigate because the Ubuntu Desktop client uses the OPNsense LAN interface as its gateway.

Topics to document include:

- Outbound NAT configuration.
- Source address translation.
- Automatic versus manual NAT modes.
- Return traffic handling.
- NAT troubleshooting.

The active NAT mode and configuration still need to be verified.

Planned Firewall and NAT Testing

The following tests will be performed as the lab develops:

- [ ] Review existing LAN firewall rules.
- [ ] Review WAN firewall rules.
- [ ] Inspect outbound NAT configuration.
- [ ] Verify permitted outbound traffic.
- [ ] Test a deliberately restricted destination or service.
- [ ] Review firewall logs for allowed and blocked traffic.
- [ ] Document the results of each test.

Current Validation Status

Initial testing has confirmed that the Ubuntu Desktop client can reach:

- The OPNsense LAN gateway.
- An external IP address at "1.1.1.1".

Both initial ping tests completed with zero packet loss.

These results demonstrate basic connectivity, but they do not independently establish which firewall rules or NAT mode permitted the traffic.

Security Considerations

Firewall rules should follow the principle of least privilege.

Only the traffic required for a particular purpose should be permitted.

Changes should be tested carefully to avoid accidentally exposing internal services or disrupting remote administration.

Future Improvements

- Create documented custom firewall rules.
- Test access restrictions between network segments.
- Investigate logging and traffic monitoring.
- Verify outbound NAT behavior.
- Document firewall policy changes and their results.