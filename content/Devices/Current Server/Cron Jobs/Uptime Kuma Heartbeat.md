[[Cron Jobs]]

---
### Schedule
Every minute (`* * * * *`)

### Command
```bash
* * * * * curl -s 'http://100.74.166.10:3001/api/push/...' > /dev/null
```

### Details
Sends a ping to Uptime Kuma every minute to confirm the server is alive. If the pings stop arriving, Uptime Kuma marks the server as down and triggers an alert notification.

### Works With
- [[Uptime Kuma]]
