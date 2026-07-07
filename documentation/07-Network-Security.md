
# 08 - Network Security

## Overview

Network security is a critical component of any enterprise infrastructure. Beyond providing connectivity, network devices must protect administrative access, prevent unauthorized devices from joining the network, and secure communications between administrators and infrastructure.

This phase focuses on implementing fundamental Cisco security features across the enterprise network.

---

# Objectives

The following security measures were implemented:

- Secure Shell (SSH) Version 2
- Local User Authentication
- RSA Key Generation
- Password Encryption
- Enable Secret
- Message of the Day (MOTD) Banner
- Port Security
- Sticky MAC Address Learning
- Port Security Verification

---

# Secure Remote Management

Telnet transmits data in plain text, making it vulnerable to interception. To provide secure remote administration, all network devices were configured to use SSH Version 2.

SSH encrypts management traffic, ensuring usernames, passwords, and configuration commands remain protected during remote sessions.

Each device was configured with:

- Hostname
- Domain Name
- Local Administrator Account
- RSA Encryption Keys
- SSH Version 2
- VTY Line Configuration

Example:

```cisco
hostname ACC-SW1

ip domain-name robinson.local

username admin secret Cisco123!

crypto key generate rsa
2048

ip ssh version 2

line vty 0 15
 login local
 transport input ssh
 exec-timeout 10 0
 logging synchronous
```

---

# Local User Authentication

Remote access uses locally configured administrator credentials instead of a shared VTY password.

Configuration:

```cisco
username admin secret Cisco123!
```

VTY lines authenticate using:

```cisco
login local
```

Benefits include:

- Individual administrator authentication
- Encrypted password storage
- Improved administrative security

---

# Password Protection

Administrative access is protected using an encrypted enable secret.

```cisco
enable secret ********
```

Additionally, service password encryption was enabled to prevent plaintext passwords from appearing in configuration files.

```cisco
service password-encryption
```

---

# Login Banner

A Message of the Day (MOTD) banner was configured to display a security warning before authentication.

Example:

```text
WARNING: Authorized personnel only.
Unauthorized access is prohibited.
```

This provides users with a clear notification that access is restricted to authorized personnel.

---

# Port Security

Port Security was implemented on all access ports connected to end devices.

Each access port was configured to:

- Allow only one MAC address
- Automatically learn the first connected device
- Shut down the port if an unauthorized device is connected

Configuration example:

```cisco
switchport mode access
switchport port-security
switchport port-security maximum 1
switchport port-security mac-address sticky
switchport port-security violation shutdown
```

Port Security was intentionally **not** applied to trunk links connecting network switches.

---

# Sticky MAC Address Learning

Sticky MAC dynamically learns the MAC address of the first authorized device connected to an access port.

Once learned, the MAC address is written into the running configuration and becomes the only authorized device allowed to use that port.

This approach simplifies deployment while protecting against unauthorized devices.

---

# Security Testing

After configuring Port Security, the implementation was validated by connecting an unauthorized workstation to a secured switch port.

The switch detected the unknown MAC address and automatically placed the interface into a Secure-Shutdown state.

Verification confirmed:

- Port Security enabled
- Sticky MAC successfully learned
- Security violation detected
- Port transitioned to Secure-Shutdown
- Unauthorized device denied network access

---

# Verification Commands

Verify SSH

```cisco
show ip ssh
```

Verify Port Security

```cisco
show port-security interface FastEthernet0/2
```

Display Secure MAC Addresses

```cisco
show port-security address
```

View Running Configuration

```cisco
show running-config
```

---

# Verification Images

## SSH Remote Management

![SSH Verification](../images/security/ssh-remote-management-verification.png)

---

## Port Security Topology Test

![Port Security Topology](../images/security/port-security-violation-topology.png)

---

## Port Security CLI Verification

![Port Security CLI](../images/security/port-security-violation-cli.png)

---

# Technologies Used

- Cisco IOS
- SSH Version 2
- RSA Encryption
- Local User Authentication
- Port Security
- Sticky MAC Address Learning
- Cisco Catalyst 2960 Switches
- Cisco Catalyst 3560 Layer 3 Switch

---

# Key Skills Demonstrated

- Network Device Hardening
- Secure Remote Administration
- Enterprise Switch Security
- Access Layer Security
- Port Security Configuration
- SSH Deployment
- Cisco IOS Security
- Security Validation and Troubleshooting

---

# Conclusion

The enterprise network was successfully secured using industry-standard Cisco security features. Administrative access is protected through SSH and local user authentication, while access-layer security prevents unauthorized devices from connecting to the network. Validation testing confirmed that the implemented controls function as expected, providing a more secure and resilient enterprise infrastructure.