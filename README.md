# Cisco Enterprise Networking Lab

A hands-on enterprise networking project built in Cisco Packet Tracer to demonstrate core networking concepts, Layer 2 and Layer 3 switching, VLAN segmentation, DHCP deployment, and enterprise network documentation.

---

# Project Overview

This lab simulates a small enterprise environment with multiple departments connected through a hierarchical network design.

The project focuses on implementing enterprise networking best practices while documenting every phase of deployment, verification, and troubleshooting.

---

# Technologies Used

- Cisco Packet Tracer
- Cisco Catalyst 3560 Layer 3 Switch
- Cisco Catalyst 2960 Access Switches
- Cisco 2911 Router
- VLANs
- 802.1Q Trunking
- Inter-VLAN Routing
- Static IP Addressing
- DHCP
- DHCP Relay (`ip helper-address`)
- Draw.io
- Git
- GitHub
- VS Code

---

# Enterprise Network Topology

## Physical Topology

![Physical Topology](images/topology/enterprise-network-physical-topology.png)

---

## Inter-VLAN Routing

![Inter-VLAN Routing](images/vlan/inter-vlan-routing.png)

---

# Network Design

The enterprise network consists of:

- 1 Cisco 2911 Edge Router
- 1 Cisco Catalyst 3560 Layer 3 Core Switch
- 3 Cisco Catalyst 2960 Access Switches
- Windows Server (Packet Tracer Server)
- Multiple department PCs and laptops

Departments include:

- Human Resources
- Finance
- Information Technology
- Management
- Servers

---

# VLAN Design

| VLAN | Department | Network | Gateway |
|------:|------------|----------------|----------------|
| 10 | HR | 192.168.10.0/24 | 192.168.10.1 |
| 20 | Finance | 192.168.20.0/24 | 192.168.20.1 |
| 30 | IT | 192.168.30.0/24 | 192.168.30.1 |
| 40 | Management | 192.168.40.0/24 | 192.168.40.1 |
| 50 | Servers | 192.168.50.0/24 | 192.168.50.1 |

---

# Current Features

✅ Physical Enterprise Topology

✅ Layer 2 Switching

✅ Layer 3 Switching

✅ VLAN Segmentation

✅ Access Port Configuration

✅ 802.1Q Trunk Links

✅ Interface Descriptions

✅ Inter-VLAN Routing

✅ Static IP Addressing

✅ DHCP Server Configuration

✅ DHCP Relay (`ip helper-address`)

✅ End-to-End Network Verification

---

# Documentation

| File | Description |
|------|-------------|
| 01-Lab-Overview.md | Project overview and objectives |
| 02-Networking-Design.md | Enterprise network architecture |
| 03-IP-Addressing.md | IP addressing plan |
| 04-VLAN-Configuration.md | VLAN creation and access ports |
| 05-InterVLAN-Routing.md | Layer 3 switching and routing |
| 06-DHCP.md | DHCP server and relay configuration |
| 10-Network-Verification.md | Connectivity and verification testing |

---

# Repository Structure

```
Cisco-networking-lab/
│
├── configurations/
├── diagrams/
├── images/
├── packet-tracer/
├── documentation/
└── README.md
```

---

# Verification Completed

- Successful DHCP lease assignment
- Successful Inter-VLAN Routing
- Cross-VLAN connectivity
- DHCP Relay functionality
- Gateway verification
- DNS assignment verification

---

# Project Status

| Phase | Status |
|--------|--------|
| Enterprise Topology | ✅ Complete |
| VLAN Configuration | ✅ Complete |
| Inter-VLAN Routing | ✅ Complete |
| Static IP Addressing | ✅ Complete |
| DHCP Deployment | ✅ Complete |
| Network Verification | ✅ Complete |
| Network Security | ⏳ Upcoming |
| ACL Implementation | ⏳ Upcoming |
| Final Validation | ⏳ Upcoming |

---

# Future Enhancements

- SSH Remote Management
- Switch Hardening
- Port Security
- Access Control Lists (ACLs)
- DNS Services
- Active Directory
- Windows Server Integration
- Enterprise Security Best Practices

---

# Author

Eric Robinson

Networking Portfolio Project

Built to demonstrate enterprise networking skills using Cisco technologies, GitHub documentation, and infrastructure design.