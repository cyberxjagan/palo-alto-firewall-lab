# IPv4 Addressing Plan

## WAN Network

| Device | Interface | IP Address | Purpose |
|---|---|---|---|
| ISP Router | WAN | `198.51.100.1/30` | ISP Gateway |
| Palo Alto Firewall | Untrust | `198.51.100.2/30` | External Interface |

## Internal Base Network

```text
10.50.10.0/24
```

## VLAN Allocation

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

## Notes

- The internal network was divided using subnetting based on department requirements.
- The addressing plan is sanitized and does not represent a real customer network.
