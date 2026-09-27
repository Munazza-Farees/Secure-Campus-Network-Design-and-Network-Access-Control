# Secure-Campus-Network-Design-&-Network-Access-Control

A Cisco Packet Tracer project demonstrating a segmented campus network with a DMZ, inter-VLAN routing, edge NAT, and ACL-based access control.

## Topology

- **Core:** Cisco 3560 multilayer switch with inter-VLAN routing.
- **Edge:** Edge-Router providing NAT and edge ACL filtering.
- **Simulated ISP:** ISP-Router connected to Edge-Router over a serial link.
- **DMZ:** Public-facing Web, DNS, and FTP servers.
- **Departments:** CSE, CSN, IT, MECH, and ECE.
- **Office:** Main server in a separate VLAN.

## Addressing

| Segment | VLAN | Subnet | Default gateway |
|---|---:|---|---|
| Office / Main server | 100 | `192.168.99.0/24` | `192.168.99.1` |
| CSE | 110 | `192.168.10.0/24` | `192.168.10.1` |
| CSN | 120 | `192.168.20.0/24` | `192.168.20.1` |
| IT | 130 | `192.168.30.0/24` | `192.168.30.1` |
| MECH | 140 | `192.168.40.0/24` | `192.168.40.1` |
| ECE | 150 | `192.168.50.0/24` | `192.168.50.1` |
| DMZ | — | `172.16.10.0/24` | `172.16.10.1` |
| Edge–Core transit | — | `10.254.254.0/30` | Edge `.1`, Core `.2` |
| Edge–ISP serial | — | `192.0.2.0/30` | Edge `.2`, ISP `.1` |
| Simulated Internet loopback | — | `203.0.113.0/24` | ISP `203.0.113.1` |

### DMZ servers

| Service | Address |
|---|---|
| Web | `172.16.10.10` |
| DNS | `172.16.10.20` |
| FTP | `172.16.10.30` |

Each department has one lab network with a PC, printer, wireless AP, and departmental DHCP server.

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