05 — Validation and Testing

Overview

This document records the tests performed to validate the OPNsense firewall deployment and basic network connectivity.

Testing is performed from an Ubuntu Desktop virtual machine connected to the isolated lab network.

The objective is to verify gateway communication, outbound connectivity, DNS resolution, and firewall behavior.

Test Environment

Firewall: OPNsense

Hypervisor: Proxmox VE

Test Client: Ubuntu Desktop virtual machine

Network Connection: Isolated Proxmox virtual bridge connected to the OPNsense LAN interface.

Test 1 — LAN Gateway Connectivity

Objective: Verify that the Ubuntu Desktop client can communicate with the OPNsense LAN interface.

Command:

ping -c 4 <OPNSENSE_LAN_GATEWAY>

Expected Result: Successful replies from the OPNsense LAN gateway.

Actual Result:

- Test completed successfully.
- Packet loss: 0%.

<badge>Passed</badge>

Test 2 — External IP Connectivity

Objective: Verify that the Ubuntu Desktop client can reach an external IP address through the OPNsense firewall.

Command:

ping -c 4 1.1.1.1

Actual Result:

- Test completed successfully.
- Packet loss: 0%.

<badge>Passed</badge>

This confirms basic outbound IP connectivity from the lab client.

Test 3 — Firewall Traffic Monitoring

Objective: Confirm that OPNsense is observing network activity.

Verification Method:

Reviewed the OPNsense dashboard and traffic graph.

Actual Result:

- Inbound traffic activity observed.
- Outbound traffic activity observed.

<badge>Observed</badge>

Pending Test 4 — DNS Resolution

Objective: Verify that the Ubuntu Desktop client can resolve domain names.

Command:

ping -c 4 google.com

Expected Result: Successful hostname resolution followed by ping replies.

Status: Not yet tested.

Pending Test 5 — Firewall Policy Validation

Objective: Verify that firewall policies correctly permit and restrict network traffic.

Planned activities:

- Review existing LAN firewall rules.
- Review WAN firewall rules.
- Test permitted traffic.
- Test restricted traffic.
- Review firewall logs.

Status: Not yet tested.

Pending Test 6 — Network Isolation

Objective: Verify the intended separation between the isolated lab network and the upstream home network.

Planned activities:

- Test connectivity between lab and upstream network devices.
- Review firewall policies governing inter-network communication.
- Verify that unauthorized access is blocked.
- Document permitted and denied traffic.

Status: Not yet tested.

Test Results Summary

Completed Tests

- [x] OPNsense LAN gateway connectivity.
- [x] External IP connectivity.
- [x] Zero packet loss during initial ping tests.
- [x] Inbound and outbound traffic activity observed.

Outstanding Tests

- [ ] DNS resolution.
- [ ] Firewall rule validation.
- [ ] NAT configuration verification.
- [ ] Network isolation testing.
- [ ] Firewall logging review.

Conclusion

Initial testing confirms that the OPNsense firewall is operational and that the Ubuntu Desktop client can communicate with its default gateway and reach an external IP address.

Additional testing is required to validate DNS resolution, firewall policy enforcement, NAT configuration, and network isolation.

This testing process provides a foundation for more advanced networking exercises and security validation.