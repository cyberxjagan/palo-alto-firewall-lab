# Security Zones

## Zone Mapping

| Zone | Purpose |
|---|---|
| Untrust | Internet / ISP-facing zone |
| Trust | Internal department networks |
| DMZ | Published internal services |
| VPN | Remote access and branch connectivity |
| Management | Firewall administration |

## Implementation Notes

- Interfaces were assigned to appropriate security zones.
- Security policies were created based on traffic requirements between zones.
- Unnecessary traffic was restricted using least-privilege policy design.
