[[Cron Jobs]]

---
### Schedule
Every 6 hours at midnight, 6am, noon, and 6pm (`0 */6 * * *`)

### Command
```bash
0 */6 * * * docker exec scrutiny scrutiny-collector-metrics run
```

### Details
Polls S.M.A.R.T. health data from all connected drives and pushes the results to the Scrutiny dashboard. Runs inside the Scrutiny Docker container via `docker exec`. Keeps drive health data current so the dashboard always reflects the latest state of each drive.

### Works With
- [[Scrutiny]]
