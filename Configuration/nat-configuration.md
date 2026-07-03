# NAT Configuration

## Source NAT

Source NAT was configured to allow internal VLANs to access the Internet using the firewall's external interface.

### Example Rule Purpose

| Source Zone | Destination Zone | Translation Type | Purpose |
|---|---|---|---|
| Trust | Untrust | Source NAT | Internal users to Internet |

## Destination NAT

Destination NAT was configured to publish selected DMZ services securely.

### Example Rule Purpose

| Source Zone | Destination Zone | Translation Type | Purpose |
|---|---|---|---|
| Untrust | DMZ | Destination NAT | Publish DMZ service |

## Validation

- Verified NAT rule matching
- Tested internal Internet access
- Tested DMZ service reachability
- Reviewed firewall traffic logs
