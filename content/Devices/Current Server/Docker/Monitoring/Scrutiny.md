---
type: container
stack: monitoring
category: monitoring
status: running
port: 8082
---

[[Monitoring]]

---
### Details
S.M.A.R.T. drive health monitoring dashboard. Collects and visualizes SMART data for all connected drives, tracking health over time and alerting on attribute changes. Configured via `/home/jeremyalston7/docker/scrutiny/collector.yaml` using `type: sat` for USB-connected drives through the TR-004 enclosure.

#### Monitored Drives
| Drive | Device | Type |
|-------|--------|------|
| 1TB NVMe Crucial P2 | `/dev/nvme0n1` | NVMe |
| 6TB IronWolf HDD | `/dev/sda` | SAT |
| 8TB IronWolf HDD (RAID) | `/dev/sdb` | SAT |
| 8TB IronWolf HDD (RAID) | `/dev/sdc` | SAT |

The container has `/dev/sda`, `/dev/sdb`, `/dev/sdc`, and `/dev/nvme0n1` passed through as devices. SMART data is collected every 6 hours via the [[Scrutiny SMART Data Collection]] cron job.

### Access
Home: http://192.168.86.201:8082
Remote: http://100.74.166.10:8082

### Works With
- [[Short SMART Test]]
- [[Long SMART Test]]
- [[Scrutiny SMART Data Collection]]
