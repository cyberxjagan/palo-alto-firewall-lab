# Palo Alto Networks Firewall Implementation Lab

## Project Overview

This repository documents a sanitized Palo Alto Networks Firewall implementation lab based on customer-style requirements. The lab uses one ISP connection and subnetting for four internal departments.

The project focuses on enterprise network segmentation, firewall security policies, NAT, DMZ publishing, LDAP integration, URL Filtering, GlobalProtect VPN, Site-to-Site IPsec VPN and firewall validation.

All IP addresses, diagrams and examples in this repository are recreated for public documentation. No real customer data is included.

## Project Objectives

- Design an IPv4 subnetting plan for four departments
- Configure Palo Alto Layer 3 interfaces and security zones
- Configure virtual router and default routing
- Create department-based security policies
- Configure Source NAT for internet access
- Configure Destination NAT for DMZ publishing
- Integrate LDAP / Active Directory authentication
- Configure URL Filtering
- Configure GlobalProtect remote-access VPN
- Configure Site-to-Site IPsec VPN
- Validate traffic using firewall logs

## Sanitized Network Topology

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

## WAN Configuration

The lab uses a single ISP connection.

| Device | Interface | IP Address | Purpose |
|---|---|---|---|
| ISP Router | WAN | `198.51.100.1/30` | ISP gateway |
| Palo Alto Firewall | Untrust | `198.51.100.2/30` | External firewall interface |
| Default Route | — | `0.0.0.0/0` | Internet routing |

The `198.51.100.0/24` range is reserved for documentation and does not represent a real customer network.

## Internal Subnetting Plan

**Base network:** `10.50.10.0/24`

| Department / Service | VLAN | Subnet | Gateway | Usable Hosts |
|---|---:|---|---|---:|
| Administration | 10 | `10.50.10.0/27` | `10.50.10.1` | 30 |
| Accounts | 20 | `10.50.10.32/27` | `10.50.10.33` | 30 |
| Operations | 30 | `10.50.10.64/27` | `10.50.10.65` | 30 |
| IT Department | 40 | `10.50.10.96/27` | `10.50.10.97` | 30 |
| DMZ | 50 | `10.50.10.128/28` | `10.50.10.129` | 14 |
| Management | 60 | `10.50.10.144/28` | `10.50.10.145` | 14 |
| GlobalProtect Pool | — | `10.50.10.160/27` | — | 30 |
| Reserved Range | — | `10.50.10.192/26` | — | 62 |

## Firewall Configuration Scope

### Interfaces and Routing

- Configured Layer 3 interfaces for Trust, Untrust and DMZ zones
- Configured virtual router and default route
- Verified interface status and routing table

### Security Policies

- Created department-based security policies
- Configured inter-zone and internet access rules
- Applied least-privilege access based on project requirements

### Network Address Translation

- Configured Source NAT for outbound internet access
- Configured Destination NAT for publishing services in the DMZ
- Validated NAT translation using firewall traffic logs

### Identity and Web Security

- Practised LDAP / Active Directory integration
- Applied URL Filtering profiles based on security requirements

### VPN Configuration

- Configured GlobalProtect VPN for secure remote access
- Configured Site-to-Site IPsec VPN between Head Office and Branch Office
- Verified VPN tunnel establishment and routing

## Validation and Testing

| Test | Status |
|---|---|
| Layer 3 Interface Status | Passed |
| Default Route | Passed |
| Internet Connectivity | Passed |
| Source NAT | Passed |
| Destination NAT | Passed |
| Security Policy Enforcement | Passed |
| LDAP Authentication | Passed |
| URL Filtering | Passed |
| GlobalProtect VPN | Passed |
| Site-to-Site IPsec VPN | Passed |
| Firewall Log Verification | Passed |

## My Contribution

This project was completed as part of a team-based internship assignment in a controlled lab environment.

My contributions included:

- Designed the IPv4 subnetting plan for multiple departments
- Configured firewall interfaces, zones and virtual router
- Implemented security policies based on department requirements
- Configured Source NAT and Destination NAT
- Assisted with LDAP integration and URL Filtering
- Configured and validated GlobalProtect VPN and Site-to-Site IPsec VPN connectivity in the lab environment
- Verified routing, NAT and VPN connectivity
- Documented the implementation and validation process

## Skills Demonstrated

- IPv4 Addressing and Subnetting
- VLAN-Based Network Segmentation
- Palo Alto Networks Firewall Administration
- Security Zones and Security Policies
- Source NAT and Destination NAT
- DMZ Publishing
- LDAP / Active Directory Integration
- URL Filtering
- GlobalProtect VPN
- Site-to-Site IPsec VPN
- Firewall Traffic Log Review
- Technical Documentation

## Repository Structure

```text
palo-alto-firewall-lab/
│── README.md
│
├── Topology/
│   ├── README.md
│   └── network-topology.md
│
├── Configuration/
│   ├── README.md
│   ├── ip-addressing-plan.md
│   ├── security-zones.md
│   ├── nat-configuration.md
│   ├── security-policies.md
│   ├── globalprotect-vpn.md
│   ├── site-to-site-vpn.md
│   ├── ldap-integration.md
│   └── url-filtering.md
│
├── Documentation/
│   ├── README.md
│   ├── implementation-workflow.md
│   ├── validation-testing.md
│   └── lessons-learned.md
│
└── Screenshots/
    └── README.md
```

## Disclaimer

This repository documents a team-based firewall implementation completed in a controlled lab environment. All diagrams, IP addresses and configuration examples have been sanitized for public documentation.

No real customer IP addresses, credentials, firewall exports, internal diagrams or confidential screenshots are included.
