# Security Policies

## Policy Scope

Security policies were created to control traffic between internal departments, the Internet, DMZ services and VPN users.

## Example Policy Types

| Source Zone | Destination Zone | Purpose |
|---|---|---|
| Trust | Untrust | Internet access |
| Trust | DMZ | Internal access to hosted services |
| VPN | Trust | Remote user access |
| Trust | VPN | Required return traffic |
| Untrust | DMZ | Published service access |

## Validation

- Verified security rule order
- Tested allowed and blocked traffic
- Reviewed traffic logs for rule matching
- Confirmed required access only
