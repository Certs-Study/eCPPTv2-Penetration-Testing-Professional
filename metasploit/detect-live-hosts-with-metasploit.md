---
description: How to detect live hosts with Metasploit inside a corporate network.
---

# 🟢 Detect Live Hosts with Metasploit

After we are inside the box through our metasploit shell&#x20;

### Detect Live Hosts with Metasploit

#### Discover Live Hosts sending ARP Requests

```
auxiliary/scanner/discovery/arp_sweep
```

#### Discover Live Hosts sending IPv6 Neighbor solicitations

```
auxiliary/scanner/discovery/ipv6_neighbor
```
