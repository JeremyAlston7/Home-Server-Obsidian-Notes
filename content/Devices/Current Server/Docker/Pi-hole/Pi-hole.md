---
type: container
stack: pihole
category: networking
status: running
port: 80
---

[[Docker]]

---
### Details
Network-wide ad blocking DNS server. Routes DNS queries through a blocklist to filter ads and trackers for all devices on the network.

### Access
Home: http://192.168.86.201/admin
Remote: http://100.74.166.10/admin

### Notes
Pi-hole going down may cause internet to go down for all devices on the network. If this happens, restart the server to resolve the issue.

### Container
- pihole
