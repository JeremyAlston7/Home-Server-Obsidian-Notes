[[Cron Jobs]]

---
### Schedule
Every 5 minutes (`*/5 * * * *`)

### Command
```bash
*/5 * * * * /home/jeremyalston7/.local/bin/vdirsyncer sync >> ~/vdirsyncer.log 2>&1
```

### Details
Bidirectionally syncs Google Calendar with Nextcloud CalDAV using vdirsyncer. Keeps calendar events in sync between Google and Nextcloud in near real-time. All output is logged to `~/vdirsyncer.log` for troubleshooting if sync issues arise.

### Works With
- [[Nextcloud App]]
