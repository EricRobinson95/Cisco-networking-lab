# Network Design

## Objective

Design a scalable enterprise network using a hierarchical architecture that supports departmental segmentation, centralized services, and future expansion.

## Network Architecture

The network consists of the following devices:

- ISP Cloud
- Cisco 2911 Router (RTR1)
- Cisco Catalyst 3560 Layer 3 Core Switch (CORE-SW1)
- Three Cisco Catalyst 2960 Access Switches
- Windows Server 2022 (SRV-DC01)
- Department workstations and laptops

## Hierarchical Design

The network follows a hierarchical enterprise design consisting of:

- Edge Router
- Core Layer Switch
- Access Layer Switches

This architecture simplifies management, improves scalability, and supports efficient traffic forwarding throughout the enterprise.

## Departments

The enterprise network is organized into the following departments:

- Human Resources (HR)
- Finance
- Information Technology (IT)
- Management
- Server Infrastructure

Each department will later be assigned its own VLAN and IP subnet to improve security and network organization.

## Device Naming Convention

| Device Type | Naming Convention |
|-------------|-------------------|
| Router | RTR1 |
| Core Switch | CORE-SW1 |
| Access Switches | ACC-SW1, ACC-SW2, ACC-SW3 |
| Domain Controller | SRV-DC01 |
| Human Resources | HR-PC01, HR-LT01 |
| Finance | FIN-PC01, FIN-LT01 |
| Information Technology | IT-PC01, IT-PC02, IT-LT01 |
| Management | MGMT-PC01, MGMT-LT01 |

## Current Status

The physical topology has been designed, and all Cisco networking devices have received a baseline configuration including hostnames, administrative security settings, console and VTY access, and saved startup configurations. The next phase of the project is IP address planning and VLAN implementation.
