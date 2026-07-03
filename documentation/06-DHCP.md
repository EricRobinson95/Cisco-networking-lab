# DHCP Configuration

## Overview

Dynamic Host Configuration Protocol (DHCP) was implemented to automate IPv4 address assignment for all client devices within the enterprise network.

Instead of manually configuring IP addresses on every workstation, the DHCP server dynamically assigns:

- IPv4 Address
- Subnet Mask
- Default Gateway
- DNS Server

The DHCP service is hosted on **SRV-DC01** within the **Servers VLAN (VLAN 50)**.

---

# Objectives

- Configure a centralized DHCP server
- Create separate DHCP scopes for each department
- Automatically assign IP addresses to client devices
- Configure DHCP Relay using `ip helper-address`
- Verify successful DHCP lease assignment
- Maintain static addressing for infrastructure devices

---

# DHCP Server

Device:

```text
SRV-DC01
```

Server VLAN:

```text
VLAN 50
```

Static IP Address:

```text
192.168.50.10
```

Default Gateway:

```text
192.168.50.1
```

---

# DHCP Scopes

| Department | VLAN | Network | Gateway | DHCP Range |
|------------|------|----------------|----------------|----------------|
| HR | 10 | 192.168.10.0/24 | 192.168.10.1 | 192.168.10.100 - 192.168.10.199 |
| Finance | 20 | 192.168.20.0/24 | 192.168.20.1 | 192.168.20.100 - 192.168.20.199 |
| IT | 30 | 192.168.30.0/24 | 192.168.30.1 | 192.168.30.100 - 192.168.30.199 |
| Management | 40 | 192.168.40.0/24 | 192.168.40.1 | 192.168.40.100 - 192.168.40.199 |

---

# Addressing Strategy

Lower IP addresses were reserved for infrastructure devices requiring static addresses.

Example:

| Address Range | Purpose |
|----------------|---------------------------|
| .1 | Default Gateway |
| .2 - .9 | Future Infrastructure |
| .10 - .99 | Static Devices |
| .100 - .199 | DHCP Clients |
| .200 - .254 | Future Expansion |

This approach prevents IP conflicts while keeping the addressing scheme organized and scalable.

---

# DHCP Relay Configuration

Because the DHCP server resides on VLAN 50 while clients exist on separate VLANs, DHCP broadcasts cannot cross VLAN boundaries.

To allow DHCP requests to reach the server, **DHCP Relay** was configured on the Layer 3 switch using the `ip helper-address` command.

Configured on:

- VLAN 10
- VLAN 20
- VLAN 30
- VLAN 40

Example configuration:

```cisco
interface Vlan10
 ip helper-address 192.168.50.10
```

---

# DHCP Process (DORA)

The DHCP lease process follows four steps:

1. **Discover**
   - Client broadcasts a DHCP Discover message.

2. **Offer**
   - DHCP server offers an available IP address.

3. **Request**
   - Client requests the offered address.

4. **Acknowledge**
   - Server confirms the lease and sends complete network configuration.

---

# Verification

Successful verification included:

- DHCP Server operational
- DHCP scopes created successfully
- DHCP Relay configured
- Client devices automatically received IP addresses
- Correct default gateway assigned
- Correct DNS server assigned
- Successful inter-VLAN communication

---

# Verification Screenshots

## DHCP Server Configuration

![DHCP Server](../images/dhcp/dhcp-server-scopes.png)

---

## DHCP Client Lease

![DHCP Client](../images/dhcp/dhcp-client-ip-configuration.png)

---

## Inter-VLAN Connectivity

![DHCP Verification](../images/verification/dhcp-intervlan-ping-test.png)

---

# Results

All client devices successfully obtained IP addresses through DHCP.

The Layer 3 switch forwarded DHCP broadcasts to the centralized DHCP server using `ip helper-address`, allowing devices on different VLANs to receive network configuration automatically.

Inter-VLAN routing continued to function correctly after migrating clients from static addressing to DHCP.

---

# Key Concepts Learned

- Dynamic Host Configuration Protocol (DHCP)
- DHCP Scopes
- DHCP Lease Assignment
- DORA Process
- Static vs Dynamic Addressing
- DHCP Relay (`ip helper-address`)
- Enterprise IP Address Management
- Centralized Network Services
