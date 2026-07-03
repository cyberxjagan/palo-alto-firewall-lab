# Network Topology

## Overview

The lab simulates an enterprise network using one ISP connection and a Palo Alto Networks Firewall.

The firewall provides segmentation, routing, NAT, security policy enforcement and VPN connectivity for multiple internal departments.

## Logical Topology

```text
                    Internet
                       |
                 One ISP Router
                 198.51.100.1/30
                       |
              Palo Alto Firewall
              198.51.100.2/30
                       |
                 Managed Switch
                       |
      ---------------------------------------
      |          |          |          |
   Admin      Accounts   Operations     IT
   VLAN 10    VLAN 20     VLAN 30     VLAN 40
```

## Network Components

- ISP Router
- Palo Alto Networks Firewall
- Managed Switch
- Department VLANs
- DMZ Network
- Management Network
- GlobalProtect VPN Pool
- Branch Office IPsec VPN Connectivity

## Security Note

This topology is recreated for documentation. It does not represent any real customer network.
