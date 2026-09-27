# Validation Record

Tests below reflect the observed Packet Tracer results during project validation. Repeat them after any configuration changes.

| Test | Observed result | Notes |
|---|---|---|
| Edge-Router serial to ISP `192.0.2.1` | Pass | Serial interfaces were `up/up`; 5/5 router pings succeeded. |
| Lab PC to ISP `192.0.2.1` | Pass | 4/4 pings succeeded. |
| Lab PC to simulated external `203.0.113.1` | Pass | 4/4 pings succeeded. |
| NAT translation | Pass | Dynamic ICMP translations appeared; NAT statistics showed hits. |
| CSE PC to own gateway `192.168.10.1` | Pass | 4/4 replies. |
| CSE PC to CSN PC `192.168.20.51` | Blocked | Core returned `Destination host unreachable`; CSE ACL deny counter increased. |
| Lab PC to Servers `172.16.10.0` | Pass | 4/4 replies. |
| Lab PC to Office server `192.168.99.10` | No ICMP reply | 4 timeouts, consistent with the configured ping restriction. |
| ISP router to Lab PC `192.168.20.51` | Blocked | `UUUUU`; Edge-Router `OUTSIDE_IN` deny counter increased. |

![Image](./Network%20Configuration%20Validation%20Results.png)

## Useful verification commands

### Edge-Router

```cisco
show ip interface brief
show ip route
show access-lists
show ip nat translations
show ip nat statistics
```

### Multilayer switch

```cisco
show ip interface brief
show ip route
show vlan brief
show interfaces trunk
show access-lists
```

### End devices

```text
ipconfig /all
ping <destination-ip>
```
