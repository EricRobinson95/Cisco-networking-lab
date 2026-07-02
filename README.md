# Cisco Enterprise Networking Lab

## Overview

This project demonstrates the design, implementation, and documentation of a simulated enterprise network using Cisco Packet Tracer. The objective is to build a secure and scalable small business network while applying networking concepts commonly found in enterprise environments.

The project is being developed as both a CCNA learning lab and a professional networking portfolio. Each phase is documented to explain the design decisions, Cisco IOS configurations, verification procedures, and troubleshooting process.

---

## Business Scenario

Robinson Technology Solutions is a fictional small business that requires a reliable and secure network infrastructure to support multiple departments and centralized services.

The network is designed to provide:

- Departmental network segmentation using VLANs
- Layer 3 switching with Inter-VLAN Routing
- Centralized Windows Server 2022 services
- Dynamic IP addressing (DHCP)
- Network security using ACLs and switch security
- Enterprise-style documentation and verification

---

## Enterprise Network Topology

![Enterprise Network Topology](images/topology/physical-topology.png)

---

## Network Architecture

The network follows a hierarchical enterprise design consisting of:

- ISP Connection
- Edge Router (RTR1)
- Core Layer 3 Switch (CORE-SW1)
- Three Access Layer Switches
- Windows Server 2022
- Departmental End Devices

Departments include:

- Human Resources
- Finance
- Information Technology
- Management
- Server Infrastructure

---

## Technologies Used

- Cisco Packet Tracer
- Cisco IOS
- Layer 2 Switching
- Layer 3 Switching
- VLANs
- 802.1Q Trunking
- Inter-VLAN Routing
- Static IPv4 Addressing
- DHCP (Planned)
- Access Control Lists (ACLs)
- Switch Security
- Static Routing
- Git
- GitHub
- Markdown

---

## Project Progress

### ✅ Completed

- Enterprise network topology designed
- Physical network cabling completed
- Cisco IOS baseline device configuration
- Interface descriptions configured
- VLAN implementation
- Access port assignments
- 802.1Q trunk configuration
- Switch Virtual Interfaces (SVIs)
- Inter-VLAN Routing
- Static IP Addressing
- End-to-end connectivity verification

### 🚧 In Progress

- Documentation
- Windows Server 2022 Integration

### 📅 Planned

- DHCP Configuration
- Access Control Lists (ACLs)
- Switch Security
- Static Routing
- Final Network Verification
- Troubleshooting Documentation

---

## Repository Structure

```text
Cisco-networking-lab/
│
├── configurations/
├── documentation/
├── diagrams/
├── images/
├── packet-tracer/
└── scripts/
```

### Folder Description

| Folder | Description |
|---------|-------------|
| configurations | Cisco router and switch running configurations |
| documentation | Step-by-step implementation and technical documentation |
| diagrams | Network diagrams and topology files |
| images | Project screenshots and verification images |
| packet-tracer | Cisco Packet Tracer project files |
| scripts | Useful Cisco IOS commands and reference material |

---

## Documentation

| Document | Description |
|----------|-------------|
| 01-Lab-Overview.md | Project overview and objectives |
| 02-Networking-Design.md | Enterprise network design and topology |
| 03-IP-Addressing.md | IPv4 addressing plan and gateway design |
| 04-VLAN-Configuration.md | VLAN creation, access ports, and trunking |
| 05-InterVLAN-Routing.md | Layer 3 switching and routing between VLANs |
| 06-DHCP.md | DHCP implementation |
| 07-Access-Control-Lists.md | Network security using ACLs |
| 08-Switch-Security.md | Layer 2 security features |
| 09-Static-Routing.md | Static routing configuration |
| 10-Network-Verification.md | Connectivity testing and verification |
| 11-Troubleshooting.md | Troubleshooting process and resolutions |

---

## Skills Demonstrated

- Enterprise Network Design
- Cisco IOS Administration
- Layer 2 Switching
- Layer 3 Switching
- VLAN Configuration
- 802.1Q Trunking
- Inter-VLAN Routing
- IPv4 Addressing
- Network Verification
- Configuration Documentation
- Version Control with Git & GitHub

---

## Current Status

**Status:** 🟡 In Progress

The core enterprise network has been successfully implemented with VLAN segmentation, trunking, Layer 3 switching, static IP addressing, and verified end-to-end connectivity.

The next phase of the project focuses on implementing Windows Server 2022 services, DHCP, network security, and final validation.

---

## Author

**Eric Robinson**

Enterprise Networking Portfolio Project

Built using Cisco Packet Tracer as part of CCNA preparation and hands-on networking practice.