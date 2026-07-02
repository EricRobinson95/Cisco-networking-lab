# Lab Overview

## Project Summary

The Cisco Enterprise Networking Lab is a hands-on networking project designed to simulate the implementation of a small enterprise network using Cisco Packet Tracer. The project follows industry best practices by documenting each stage of the network deployment, from initial design through verification and troubleshooting.

The lab is intended to strengthen practical networking skills while reinforcing Cisco CCNA concepts including Layer 2 switching, Layer 3 routing, VLAN implementation, IPv4 addressing, network security, and enterprise network documentation.

---

# Objectives

The primary objectives of this project are to:

- Design a scalable enterprise network
- Implement a hierarchical network architecture
- Configure Cisco routers and switches using Cisco IOS
- Segment departments using VLANs
- Configure Inter-VLAN Routing using a Layer 3 switch
- Implement static and dynamic IP addressing
- Configure Windows Server 2022 network services
- Secure the network using ACLs and switch security features
- Verify end-to-end network connectivity
- Document every phase of the implementation

---

# Business Scenario

Robinson Technology Solutions is a fictional small business requiring a reliable and scalable enterprise network capable of supporting multiple departments and centralized IT services.

The network must provide secure communication between departments while allowing controlled access to shared resources hosted on a centralized Windows Server 2022 system.

The enterprise consists of the following departments:

- Human Resources
- Finance
- Information Technology
- Management
- Server Infrastructure

Each department is isolated using Virtual Local Area Networks (VLANs) while maintaining communication through Inter-VLAN Routing performed by the core Layer 3 switch.

---

# Network Topology

The enterprise network consists of the following infrastructure components:

- ISP Connection
- Edge Router (RTR1)
- Core Layer 3 Switch (CORE-SW1)
- Access Switch 1 (ACC-SW1)
- Access Switch 2 (ACC-SW2)
- Access Switch 3 (ACC-SW3)
- Windows Server 2022
- Departmental PCs and Laptops

---

## Enterprise Topology

![Enterprise Network Topology](../images/topology/physical-topology.png)

---

# Network Architecture

The network follows Cisco's hierarchical design model consisting of three logical layers.

## Edge Layer

Provides connectivity to the simulated Internet through the enterprise edge router.

Components:

- RTR1

---

## Core Layer

Acts as the central switching and routing device for the enterprise.

Responsibilities include:

- VLAN Routing
- Default Gateway Services
- High-speed switching
- Inter-switch connectivity

Components:

- CORE-SW1

---

## Access Layer

Provides network connectivity for end-user devices within each department.

Components:

- ACC-SW1
- ACC-SW2
- ACC-SW3

---

# Enterprise Services

The completed network will provide the following services:

- VLAN Segmentation
- Inter-VLAN Routing
- DHCP
- DNS
- Windows Active Directory
- Access Control Lists (ACLs)
- Switch Security
- Static Routing

---

# Technologies Used

- Cisco Packet Tracer
- Cisco IOS
- Layer 2 Switching
- Layer 3 Switching
- VLANs
- IEEE 802.1Q Trunking
- IPv4
- Inter-VLAN Routing
- DHCP
- ACLs
- Static Routing
- Git
- GitHub
- Markdown

---

# Project Status

## Completed

- Enterprise topology designed
- Physical network deployment
- Cisco IOS baseline configuration
- Interface descriptions
- VLAN implementation
- Access port assignments
- Trunk configuration
- Layer 3 gateway configuration
- Inter-VLAN Routing
- Static IP Addressing
- End-to-end connectivity verification

---

## Upcoming Phases

- Windows Server 2022 Configuration
- DHCP
- Access Control Lists
- Switch Security
- Static Routing
- Final Network Verification
- Troubleshooting Documentation

---

# Learning Outcomes

This project demonstrates practical experience with:

- Enterprise network design
- Cisco IOS administration
- VLAN deployment
- Layer 2 switching
- Layer 3 switching
- IPv4 addressing
- Inter-VLAN Routing
- Enterprise documentation
- Network verification
- Version control using Git and GitHub

---

# Conclusion

This project serves as a practical implementation of enterprise networking concepts commonly encountered in production environments. By documenting each phase of the deployment, the repository demonstrates not only configuration skills but also the planning, verification, and documentation practices expected of network engineers.