[[Cron Jobs]]

---
### Schedule
Every minute (`* * * * *`)

### Command
```bash
* * * * * /home/jeremyalston7/raid-health-check.sh
```

### Script
Located at `/home/jeremyalston7/raid-health-check.sh`. Reads `/proc/mdstat` and checks for `[UU]` to confirm both RAID drives are active. Uses full binary paths (`/bin/grep`, `/usr/bin/curl`) to avoid cron environment issues.

- **Healthy** → pushes "RAID Healthy" to Uptime Kuma push monitor
- **Degraded** → pushes "RAID DEGRADED" when a drive has dropped out of the array

### Details
Monitors the software RAID array (`/dev/sdb` + `/dev/sdc`) for drive failures. The `[UU]` pattern in `/proc/mdstat` indicates both drives are active and the array is healthy; any other pattern (e.g. `[U_]`) signals a degraded array. The Uptime Kuma push monitor is configured with a 60-second heartbeat interval so a missed push triggers an alert quickly.

### Works With
- [[Uptime Kuma]]
