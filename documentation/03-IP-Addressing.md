# IP Addressing

## Overview

This document describes the IPv4 addressing scheme implemented throughout the enterprise network.

The addressing plan was designed to provide logical separation between departments while simplifying network administration, troubleshooting, and future expansion. Each department is assigned its own VLAN and corresponding IPv4 subnet.

Inter-VLAN communication is provided by the Layer 3 core switch (CORE-SW1), which serves as the default gateway for every VLAN.

---

# Design Objectives

The IPv4 addressing scheme was designed to:

- Provide unique subnets for each department
- Simplify network management
- Support future network growth
- Follow enterprise networking best practices
- Align VLAN IDs with IPv4 network addressing

---

# IPv4 Addressing Plan

| VLAN | Department | Network Address | Subnet Mask | Default Gateway |
|------:|------------|-----------------|-------------|-----------------|
| 10 | Human Resources | 192.168.10.0/24 | 255.255.255.0 | 192.168.10.1 |
| 20 | Finance | 192.168.20.0/24 | 255.255.255.0 | 192.168.20.1 |
| 30 | Information Technology | 192.168.30.0/24 | 255.255.255.0 | 192.168.30.1 |
| 40 | Management | 192.168.40.0/24 | 255.255.255.0 | 192.168.40.1 |
| 50 | Server Infrastructure | 192.168.50.0/24 | 255.255.255.0 | 192.168.50.1 |

---

# Default Gateway Design

The Cisco Catalyst 3560 multilayer switch (CORE-SW1) provides the default gateway for every VLAN using Switch Virtual Interfaces (SVIs).

Each VLAN gateway is configured as follows:

| VLAN | Gateway |
|------:|----------|
| 10 | 192.168.10.1 |
| 20 | 192.168.20.1 |
| 30 | 192.168.30.1 |
| 40 | 192.168.40.1 |
| 50 | 192.168.50.1 |

These gateway addresses allow devices in different VLANs to communicate through Inter-VLAN Routing.

---

# Endpoint Addressing

## Human Resources

| Device | IPv4 Address |
|---------|--------------|
| HR-PC01 | 192.168.10.10 |
| HR-LT01 | 192.168.10.11 |

---

## Finance

| Device | IPv4 Address |
|---------|--------------|
| FIN-PC01 | 192.168.20.10 |
| FIN-LT01 | 192.168.20.11 |

---

## Information Technology

| Device | IPv4 Address |
|---------|--------------|
| IT-PC01 | 192.168.30.10 |
| IT-LT01 | 192.168.30.11 |
| IT-PC02 | 192.168.30.12 |
| IT-LT02 | 192.168.30.13 |

---

## Management

| Device | IPv4 Address |
|---------|--------------|
| MGMT-PC01 | 192.168.40.10 |
| MGMT-LT01 | 192.168.40.11 |

---

## Server Infrastructure

| Device | IPv4 Address |
|---------|--------------|
| SRV-DC01 | 192.168.50.10 |

---

# Address Allocation Strategy

The following addressing convention was adopted throughout the enterprise network.

| Address Range | Purpose |
|---------------|---------|
| .1 | Default Gateway |
| .2 - .9 | Reserved for future infrastructure devices |
| .10 - .49 | Static device assignments |
| .50 - .99 | Reserved |
| .100 - .199 | Future DHCP Scope |
| .200 - .254 | Future expansion |

This structure provides consistency across every subnet and simplifies future network administration.

---

# Configuration Summary

The following configuration tasks were completed:

- IPv4 addressing plan designed
- Default gateways configured on CORE-SW1
- Switch Virtual Interfaces (SVIs) configured
- Static IPv4 addresses assigned to all endpoints
- Default gateways assigned to all end devices
- Inter-VLAN routing verified

---

# Verification

The following Cisco IOS commands were used to verify the addressing configuration.

```cisco
show ip interface brief

show ip route

show running-config
```

End-to-end connectivity was verified using ICMP ping tests between devices located in different VLANs.

Example:

```text
HR-PC01

↓

Ping 192.168.50.10

↓

Successful
```

This confirms:

- Correct IPv4 addressing
- Proper gateway configuration
- Functional Inter-VLAN Routing
- End-to-end connectivity

---

# Network Diagram

![Enterprise Network Topology](../images/topology/physical-topology.png)

---

# Conclusion

The IPv4 addressing plan provides a structured and scalable foundation for the enterprise network.

Each department operates within its own subnet while maintaining connectivity through the Layer 3 core switch. The addressing strategy supports future implementation of DHCP, DNS, Windows Server services, and additional enterprise networking features.
