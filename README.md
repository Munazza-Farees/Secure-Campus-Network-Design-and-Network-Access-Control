# Secure-Campus-Network-Design-and-Network-Access-Control

A Cisco Packet Tracer project demonstrating a segmented campus network with a DMZ, inter-VLAN routing, edge NAT, and ACL-based access control.

## Topology

- **Core:** Cisco 3560 multilayer switch with inter-VLAN routing.
- **Edge:** Edge-Router providing NAT and edge ACL filtering.
- **Simulated ISP:** ISP-Router connected to Edge-Router over a serial link.
- **DMZ:** Public-facing Web, DNS, and FTP servers.
- **Departments:** CSE, CSN, IT, MECH, and ECE.
- **Office:** Main server in a separate VLAN.

Each department has one lab network with a PC, printer, wireless AP, and departmental DHCP server.

![Image](/docs/Architecture.png)

## Security and networking

- 802.1Q VLAN segmentation and multilayer inter-VLAN routing.
- Edge NAT overload for internal network traffic.
- Edge ACL rules restricting inbound access to internal networks.
- Departmental ACLs restricting routed access between department subnets.
- A separate DMZ subnet for public-facing services.

## Validation

See [docs/validation.md](docs/validation.md) for the tests performed and their observed results.

## Files

- `Campus Network Design.pkt` — add your final Cisco Packet Tracer project file to the repository root.
- `configs/` — reference configuration excerpts.
- `docs/` — topology and validation notes.

Open the `.pkt` file with Cisco Packet Tracer. This project simulates an ISP; it does not provide real Internet access.

---
Just a curious mind [Munazza Farees](https://www.linkedin.com/in/munazza-farees-a983142b7)
