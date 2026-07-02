# Network Design

## Overview

This document describes the design of the enterprise network, including the network architecture, physical topology, device placement, departmental segmentation, and design decisions made during implementation.

The network was designed using Cisco's hierarchical network model to provide scalability, simplified management, and efficient traffic flow.

---

# Design Goals

The network was designed to achieve the following objectives:

- Provide a scalable enterprise network architecture
- Separate departments using VLANs
- Support Inter-VLAN communication through Layer 3 switching
- Centralize enterprise services using Windows Server 2022
- Simplify network management and troubleshooting
- Follow Cisco networking best practices

---

# Hierarchical Network Design

The enterprise network is organized into three logical layers.

## Edge Layer

The Edge Layer provides connectivity to the simulated Internet.

### Device

- RTR1

Responsibilities include:

- Internet connectivity
- WAN edge routing
- Future static/default routing

---

## Core Layer

The Core Layer serves as the central switching and routing device for the enterprise network.

### Device

- CORE-SW1

Responsibilities include:

- High-speed switching
- Inter-VLAN Routing
- Default gateway services
- Trunk connections to access switches

---

## Access Layer

The Access Layer provides network connectivity for all end-user devices.

### Devices

- ACC-SW1
- ACC-SW2
- ACC-SW3

Responsibilities include:

- Connecting end-user devices
- VLAN membership
- Access port configuration
- Layer 2 switching

---

# Enterprise Topology

![Enterprise Network Topology](../images/topology/physical-topology.png)

---

# Physical Connections

## Infrastructure Links

| Device | Interface | Connected To | Interface |
|---------|-----------|--------------|-----------|
| RTR1 | GigabitEthernet0/0 | CORE-SW1 | GigabitEthernet0/1 |
| CORE-SW1 | FastEthernet0/1 | ACC-SW1 | FastEthernet0/1 |
| CORE-SW1 | GigabitEthernet0/2 | ACC-SW2 | GigabitEthernet0/1 |
| CORE-SW1 | FastEthernet0/2 | ACC-SW3 | FastEthernet0/1 |

---

# Department Layout

## ACC-SW1

Departments:

- Human Resources
- Finance

Connected Devices:

- HR-PC01
- HR-LT01
- FIN-PC01
- FIN-LT01

---

## ACC-SW2

Departments:

- Management
- Server Infrastructure

Connected Devices:

- MGMT-PC01
- MGMT-LT01
- SRV-DC01

---

## ACC-SW3

Departments:

- Information Technology

Connected Devices:

- IT-PC01
- IT-LT01
- IT-PC02
- IT-LT02

---

# Design Decisions

Several design decisions were made during implementation to improve scalability and simplify future expansion.

## Layer 3 Switching

A Cisco Catalyst 3560 multilayer switch was selected as the core switch to provide:

- Default gateway services
- Inter-VLAN Routing
- Centralized routing between departments

This removes the need for Router-on-a-Stick and provides better performance.

---

## VLAN Segmentation

Each department is separated into its own VLAN to reduce broadcast traffic and improve network security.

Each VLAN represents an independent broadcast domain.

---

## Gigabit Uplinks

Gigabit Ethernet interfaces were used where available for infrastructure connections to improve bandwidth between network devices.

The connection between CORE-SW1 and ACC-SW2 uses Gigabit Ethernet because the Management department and Windows Server are connected through this switch.

---

## Interface Descriptions

Every router and switch interface includes a description identifying the connected device.

This improves:

- Documentation
- Troubleshooting
- Network administration

---

# Device Inventory

| Device | Purpose |
|---------|----------|
| RTR1 | Enterprise Edge Router |
| CORE-SW1 | Core Layer 3 Switch |
| ACC-SW1 | HR & Finance Access Switch |
| ACC-SW2 | Management & Server Access Switch |
| ACC-SW3 | IT Access Switch |
| SRV-DC01 | Windows Server 2022 |
| HR-PC01 | Human Resources Workstation |
| HR-LT01 | Human Resources Laptop |
| FIN-PC01 | Finance Workstation |
| FIN-LT01 | Finance Laptop |
| MGMT-PC01 | Management Workstation |
| MGMT-LT01 | Management Laptop |
| IT-PC01 | IT Workstation |
| IT-PC02 | IT Workstation |
| IT-LT01 | IT Laptop |
| IT-LT02 | IT Laptop |

---

# Verification

The following tasks have been completed and verified:

- Physical topology implemented
- All devices connected
- Interface descriptions configured
- Green link status confirmed
- Enterprise topology documented

---

# Conclusion

The enterprise network design provides a scalable and organized architecture capable of supporting departmental segmentation, centralized services, and future network expansion.

The hierarchical design simplifies management while preparing the network for advanced services including DHCP, ACLs, switch security, and Windows Server integration.