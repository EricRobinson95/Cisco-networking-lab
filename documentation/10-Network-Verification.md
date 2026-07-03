# Network Verification

## Overview

After completing the enterprise network implementation, comprehensive verification testing was performed to validate connectivity, Layer 3 routing, VLAN segmentation, and DHCP functionality.

The objective was to ensure that all devices received the correct network configuration and could communicate successfully across VLAN boundaries.

---

# Verification Objectives

- Verify VLAN connectivity
- Verify Inter-VLAN Routing
- Verify DHCP lease assignment
- Verify default gateway configuration
- Verify DNS assignment
- Verify end-to-end connectivity
- Verify Layer 3 switching functionality

---

# VLAN Verification

The following commands were used to verify VLAN configuration on the Layer 3 switch.

```cisco
show vlan brief
```

Verified:

- VLAN 10 – Human Resources
- VLAN 20 – Finance
- VLAN 30 – Information Technology
- VLAN 40 – Management
- VLAN 50 – Servers

---

# Trunk Verification

The trunk links between the Core Switch and Access Switches were verified using:

```cisco
show interfaces trunk
```

Verified:

- 802.1Q trunk encapsulation
- Active trunk ports
- VLAN forwarding across switches

---

# Layer 3 Interface Verification

SVIs were verified using:

```cisco
show ip interface brief
```

Verified Interfaces:

| Interface | IP Address |
|-----------|------------|
| VLAN10 | 192.168.10.1 |
| VLAN20 | 192.168.20.1 |
| VLAN30 | 192.168.30.1 |
| VLAN40 | 192.168.40.1 |
| VLAN50 | 192.168.50.1 |

All interfaces were operational (Up/Up).

---

# DHCP Verification

The centralized DHCP server successfully assigned IPv4 addresses to client devices.

Verification confirmed:

- Automatic IP address assignment
- Correct subnet mask
- Correct default gateway
- Correct DNS server
- Successful DHCP lease acquisition

Example DHCP Client Configuration:

- IP Address: 192.168.10.100
- Subnet Mask: 255.255.255.0
- Default Gateway: 192.168.10.1
- DNS Server: 192.168.50.10

---

# DHCP Relay Verification

DHCP Relay was configured on the Layer 3 switch using:

```cisco
ip helper-address 192.168.50.10
```

Configured on:

- VLAN 10
- VLAN 20
- VLAN 30
- VLAN 40

This allowed DHCP broadcasts from client VLANs to reach the centralized DHCP server located on VLAN 50.

---

# Connectivity Testing

Connectivity testing was performed between multiple VLANs.

Example tests included:

| Source | Destination | Result |
|---------|-------------|--------|
| HR-PC01 | FIN-PC01 | ✅ Success |
| HR-PC01 | IT-PC01 | ✅ Success |
| HR-PC01 | MGMT-PC01 | ✅ Success |
| HR-PC01 | SRV-DC01 | ✅ Success |

Successful replies confirmed:

- Correct routing
- Proper gateway configuration
- Functional DHCP
- End-to-end connectivity

> **Note:** The first ICMP Echo Request timed out during some tests due to ARP resolution. After the destination MAC address was learned, all subsequent ping requests completed successfully. This behavior is expected in Packet Tracer and on Ethernet networks.

---

# Verification Commands

Cisco IOS commands used during validation:

```cisco
show vlan brief
show interfaces trunk
show ip interface brief
show running-config
ping
```

---

# Verification Screenshots

## DHCP Server Configuration

![DHCP Server Configuration](../images/dhcp/dhcp-server-scopes.png)

---

## DHCP Client Configuration

![DHCP Client Configuration](../images/dhcp/dhcp-client-ip-configuration.png)

---

## Inter-VLAN Connectivity Verification

![Inter-VLAN Ping Verification](../images/verification/dhcp-intervlan-ping-test.png)

---

# Results

The enterprise network was successfully validated.

Verified functionality includes:

- ✅ VLAN Segmentation
- ✅ Trunk Links
- ✅ Layer 3 Switching
- ✅ Inter-VLAN Routing
- ✅ Static Infrastructure Addressing
- ✅ DHCP Server
- ✅ DHCP Relay (`ip helper-address`)
- ✅ Automatic Client Address Assignment
- ✅ Cross-VLAN Connectivity
- ✅ End-to-End Network Communication

---

# Conclusion

The enterprise network successfully met all design objectives for this phase.

Client devices automatically obtained network configuration from the centralized DHCP server, while the Layer 3 switch routed traffic between VLANs using Switch Virtual Interfaces (SVIs). DHCP Relay enabled clients on separate VLANs to communicate with the DHCP server located in the Servers VLAN, resulting in reliable, automated IP address management and successful end-to-end connectivity throughout the network.