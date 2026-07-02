# VLAN Configuration

## Overview

This document describes the implementation of Virtual Local Area Networks (VLANs) within the enterprise network.

VLANs were implemented to logically separate departments into independent broadcast domains while sharing the same physical switching infrastructure. This design improves network performance, security, and scalability.

Communication between VLANs is provided by the Layer 3 core switch (CORE-SW1) through Switch Virtual Interfaces (SVIs).

---

# Objectives

The VLAN implementation was designed to:

- Separate departments into individual broadcast domains
- Improve network security
- Reduce unnecessary broadcast traffic
- Simplify network administration
- Support future network growth
- Prepare the network for Inter-VLAN Routing

---

# VLAN Design

Each department was assigned its own VLAN.

| VLAN ID | VLAN Name | Department |
|---------:|-----------|------------|
| 10 | HR | Human Resources |
| 20 | FINANCE | Finance |
| 30 | IT | Information Technology |
| 40 | MANAGEMENT | Management |
| 50 | SERVERS | Server Infrastructure |

---

# VLAN Implementation

The VLANs were created on:

- CORE-SW1
- ACC-SW1
- ACC-SW2
- ACC-SW3

Creating identical VLAN databases on every switch ensures consistent VLAN operation throughout the enterprise network.

---

# Access Port Assignments

## ACC-SW1

| Interface | Device | VLAN |
|------------|--------|------|
| Fa0/2 | HR-PC01 | VLAN 10 |
| Fa0/3 | HR-LT01 | VLAN 10 |
| Fa0/4 | FIN-PC01 | VLAN 20 |
| Fa0/5 | FIN-LT01 | VLAN 20 |

---

## ACC-SW2

| Interface | Device | VLAN |
|------------|--------|------|
| Fa0/2 | MGMT-PC01 | VLAN 40 |
| Fa0/3 | MGMT-LT01 | VLAN 40 |
| Fa0/4 | SRV-DC01 | VLAN 50 |

---

## ACC-SW3

| Interface | Device | VLAN |
|------------|--------|------|
| Fa0/2 | IT-PC01 | VLAN 30 |
| Fa0/3 | IT-LT01 | VLAN 30 |
| Fa0/4 | IT-PC02 | VLAN 30 |
| Fa0/5 | IT-LT02 | VLAN 30 |

---

# Trunk Configuration

Trunk links were configured between the core switch and each access switch to transport traffic for multiple VLANs across a single physical connection.

## Trunk Links

| Device | Interface | Connected To | Interface |
|---------|-----------|--------------|-----------|
| CORE-SW1 | Fa0/1 | ACC-SW1 | Fa0/1 |
| CORE-SW1 | Gi0/2 | ACC-SW2 | Gi0/1 |
| CORE-SW1 | Fa0/2 | ACC-SW3 | Fa0/1 |

The trunk links use IEEE 802.1Q encapsulation to identify VLAN traffic between switches.

---

# Layer 3 Integration

The Cisco Catalyst 3560 multilayer switch provides Layer 3 functionality for all VLANs.

Each VLAN is assigned a Switch Virtual Interface (SVI), allowing the switch to perform Inter-VLAN Routing.

This design eliminates the need for Router-on-a-Stick while providing improved performance and scalability.

---

# Verification

The following Cisco IOS commands were used to verify the VLAN configuration.

```cisco
show vlan brief

show interfaces trunk

show running-config
```

Verification confirmed:

- VLANs successfully created
- Correct VLAN names
- Access ports assigned to the proper VLANs
- Trunk links operational
- Successful VLAN propagation across all switches

---

# Verification Screenshot

Add a screenshot of:

```cisco
show vlan brief
```

Example:

```text
images/vlans/show-vlan-brief.png
```

Markdown:

```markdown
![VLAN Verification](../images/vlans/show-vlan-brief.png)
```

---

# Design Benefits

Implementing VLANs provides several enterprise networking advantages.

- Departmental isolation
- Reduced broadcast domains
- Improved security
- Better traffic management
- Simplified troubleshooting
- Easier network expansion
- Logical separation without additional physical switches

---

# Summary

The enterprise network was successfully segmented using VLANs, creating separate broadcast domains for each department.

Access ports were assigned according to departmental requirements, while trunk links between switches allow VLAN traffic to traverse the network. This implementation establishes the Layer 2 foundation required for Inter-VLAN Routing, DHCP, and future enterprise network services.
