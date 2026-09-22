---
type: container
stack: uptime-kuma
category: monitoring
status: running
port: 3001
---

[[Docker]]

---
### Details
Self-hosted uptime monitoring dashboard. Tracks the availability of all running services and sends alerts when something goes down.

#### Monitors
- **Service Uptime** — HTTP monitors for all running containers
- **RAID Health** — Push monitor (60s heartbeat interval) receiving status from `/home/jeremyalston7/raid-health-check.sh`. Sends "RAID Healthy" when `/proc/mdstat` shows `[UU]` (both drives active), "RAID DEGRADED" when a drive has dropped out. See [[RAID Health Check]].
- **Server Heartbeat** — Receives a ping every minute from the [[Uptime Kuma Heartbeat]] cron job to verify the server is reachable.

### Access
Home: http://192.168.86.201:3001
Remote: http://100.74.166.10:3001

### Works With
- [[Uptime Kuma Heartbeat]]
- [[RAID Health Check]]
