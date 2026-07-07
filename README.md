# Enterprise Cisco Networking Lab

A comprehensive enterprise networking lab built in Cisco Packet Tracer that demonstrates core networking concepts, Layer 2 and Layer 3 switching, network segmentation, DHCP, secure remote management, and enterprise security.

This project simulates a small business environment with multiple departments connected through a Layer 3 core switch, providing secure communication, centralized network services, and enterprise-grade security features.

---

# Project Objectives

- Design a scalable enterprise network
- Implement VLAN segmentation
- Configure trunk links between switches
- Configure Inter-VLAN Routing using a Layer 3 switch
- Deploy centralized DHCP services
- Secure remote device management using SSH
- Secure access-layer ports using Port Security
- Verify enterprise network connectivity
- Document configurations and verification procedures

---

# Network Topology

The lab consists of:

- 1 Edge Router (RTR1)
- 1 Layer 3 Core Switch (CORE-SW1)
- 3 Access Layer Switches
- Multiple Department VLANs
- DHCP/DNS Server
- Department Workstations and Laptops

Department VLANs:

| Department | VLAN | Network |
|------------|------|----------------|
| HR | 10 | 192.168.10.0/24 |
| Finance | 20 | 192.168.20.0/24 |
| IT | 30 | 192.168.30.0/24 |
| Management | 40 | 192.168.40.0/24 |
| Servers | 50 | 192.168.50.0/24 |

---

# Features

### Enterprise Network Design

- Hierarchical network topology
- Layer 2 Access Layer
- Layer 3 Core Layer
- Structured VLAN design
- Department segmentation

### Layer 2 Switching

- VLAN Configuration
- Access Ports
- 802.1Q Trunking
- MAC Address Learning

### Layer 3 Switching

- Switched Virtual Interfaces (SVIs)
- Inter-VLAN Routing
- Default Gateway Configuration
- Routing Verification

### Network Services

- Centralized DHCP Server
- DHCP Address Pools
- DHCP Relay
- DNS Configuration
- Automatic Client Address Assignment

### Network Security

- SSH Version 2
- RSA Key Generation
- Local User Authentication
- Enable Secret
- Password Encryption
- Login Banner (MOTD)
- Port Security
- Sticky MAC Address Learning
- Secure Remote Management

### Verification & Testing

- VLAN Verification
- Trunk Verification
- DHCP Verification
- Inter-VLAN Connectivity Testing
- SSH Verification
- Port Security Violation Testing

---

# Project Structure

```
Cisco-networking-lab/
│
├── configurations/
│   ├── router/
│   └── switches/
│
├── diagrams/
│
├── documentation/
│   ├── 01-Lab-Overview.md
│   ├── 02-Network-Design.md
│   ├── 03-IP-Addressing.md
│   ├── 04-VLAN-Configuration.md
│   ├── 05-InterVLAN-Routing.md
│   ├── 06-DHCP.md
│   ├── 07-Static-Routing.md
│   ├── 08-Network-Security.md
│   ├── 09-Access-Control-Lists.md
│   └── 10-Network-Verification.md
│
├── images/
│   ├── topology/
│   ├── vlan/
│   ├── dhcp/
│   ├── security/
│   └── verification/
│
├── packet-tracer/
│
├── README.md
└── LICENSE
```

---

# Technologies Used

- Cisco Packet Tracer
- Cisco IOS
- Layer 2 Switching
- Layer 3 Switching
- VLANs
- 802.1Q Trunking
- Inter-VLAN Routing
- DHCP
- DHCP Relay
- SSH Version 2
- RSA Encryption
- Port Security
- Sticky MAC Address Learning

---

# Skills Demonstrated

- Enterprise Network Design
- VLAN Segmentation
- Layer 2 Switching
- Layer 3 Switching
- Inter-VLAN Routing
- DHCP Configuration
- DHCP Relay Configuration
- Network Security
- Secure Remote Administration
- Cisco IOS Configuration
- Network Verification
- Network Troubleshooting
- Enterprise Documentation

---

# Verification

The following functionality has been successfully tested:

- VLAN communication
- Inter-VLAN Routing
- DHCP address assignment
- DHCP relay forwarding
- SSH remote administration
- Secure login authentication
- Port Security
- Sticky MAC learning
- Unauthorized device detection
- Automatic Secure-Shutdown during Port Security violations

---

# Documentation

Detailed implementation guides are included for every major phase of the project:

- Lab Overview
- Network Design
- IP Addressing
- VLAN Configuration
- Inter-VLAN Routing
- DHCP Configuration
- Static Routing
- Network Security
- Access Control Lists *(planned)*
- Network Verification

---

# Future Improvements

Planned enhancements include:

- Standard and Extended ACLs
- NAT/PAT
- Internet Connectivity
- Syslog
- NTP
- SNMP
- EtherChannel
- HSRP
- Dynamic Routing (OSPF)
- IPv6
- Network Monitoring

---

# License

This project is licensed under the MIT License.