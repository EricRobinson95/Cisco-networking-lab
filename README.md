# Cisco Enterprise Networking Lab

## Overview

This project documents the design, implementation, and validation of a simulated enterprise network using Cisco Packet Tracer. The goal is to build a secure and scalable business network while reinforcing networking concepts covered in the Cisco Certified Network Associate (CCNA) certification.

The project is being developed in phases, with each implementation step documented using Git and GitHub.

---

## Business Scenario

Robinson Technology Solutions is a fictional small business that requires a secure, scalable, and well-organized network infrastructure. The network is designed to support multiple departments while providing centralized network services through a Windows Server 2022 domain controller.

Departments include:

- Management
- Human Resources
- Finance
- Information Technology
- Server Infrastructure

---

## Enterprise Network Topology

![Enterprise Network Topology](images/topology/physical-topology.png)

---

## Skills Demonstrated

- Enterprise Network Design
- Cisco IOS Administration
- Cisco Router and Switch Configuration
- Layer 2 Switching
- Layer 3 Switching
- Network Documentation
- Git Version Control
- GitHub Project Management

> Additional skills including VLANs, Inter-VLAN Routing, DHCP, ACLs, Static Routing, and Switch Security will be implemented throughout the project.

---

## Technologies Used

- Cisco Packet Tracer
- Cisco IOS
- Windows Server 2022
- Git
- GitHub
- Visual Studio Code

---

## Repository Structure

```text
Cisco-networking-lab/
│
├── configurations/
├── diagrams/
├── documentation/
├── images/
├── packet-tracer/
├── scripts/
├── README.md
└── LICENSE
```

---

## Project Progress

### ✅ Completed

- Designed the enterprise network topology
- Implemented a hierarchical network architecture
- Added the enterprise router, Layer 3 core switch, access switches, and Windows Server
- Organized departmental endpoints
- Configured baseline Cisco device settings
  - Hostnames
  - Enable secret
  - Service password encryption
  - Disable DNS lookup
  - MOTD banner
  - Console access
  - VTY access
  - Saved startup configurations
- Created and organized the GitHub repository
- Exported baseline device configurations
- Began project documentation

### 🚧 In Progress

- Physical network cabling
- IP addressing design

### 📋 Planned

- VLAN implementation
- Inter-VLAN routing
- DHCP configuration
- Static routing
- Access Control Lists (ACLs)
- Switch port security
- Network verification
- Troubleshooting

---

## Documentation

Detailed implementation documentation for each phase of the project can be found in the `documentation/` directory.

Current documentation includes:

- Lab Overview
- Network Design

Additional documentation will be added as each implementation phase is completed.

---

## License

This project is licensed under the MIT License.