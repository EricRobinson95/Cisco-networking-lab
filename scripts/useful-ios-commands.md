# Useful Cisco IOS Commands

## Overview

This document serves as a quick reference for commonly used Cisco IOS commands throughout the Cisco Enterprise Networking Lab. The commands listed here are used for device configuration, verification, troubleshooting, and network administration. As the project progresses, additional commands will be added to reflect new technologies and features implemented in the lab.

---

## Navigation

```text
enable
configure terminal
exit
end
```

---

## Save Configuration

```text
copy running-config startup-config
write memory
```

---

## Device Information

```text
show running-config
show startup-config
show version
show inventory
show ip interface brief
show interfaces
show interfaces status
```

---

## VLAN Commands

```text
show vlan brief
show interfaces trunk
show spanning-tree
```

---

## Interface Commands

```text
show interfaces
show interfaces description
show cdp neighbors
show cdp neighbors detail
```

---

## Routing Commands

```text
show ip route
show arp
```

---

## DHCP Commands

```text
show ip dhcp binding
show ip dhcp pool
show running-config | section dhcp
```

---

## Access Control Lists (ACLs)

```text
show access-lists
show ip interface
```

---

## Switch Security

```text
show port-security
show port-security interface
show mac address-table
```

---

## Connectivity Testing

```text
ping
traceroute
```

---

## General Troubleshooting

```text
show logging
show processes
show clock
```

---

## Helpful IOS Shortcuts

```text
?
Tab
Ctrl + C
Ctrl + Shift + 6
```

---

## Notes

This document is maintained as a personal Cisco IOS command reference. Commands will be added throughout the project as new configurations, verification procedures, and troubleshooting techniques are introduced.
