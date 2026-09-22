[[Cron Jobs]]

---
### Schedule
Twice daily at 2am and 2pm (`0 2,14 * * *`)

### Command
```bash
0 2,14 * * * sudo smartctl -t short -d sat /dev/sda
0 2,14 * * * sudo smartctl -t short -d sat /dev/sdb
0 2,14 * * * sudo smartctl -t short -d sat /dev/sdc
```

### Details
Performs a quick S.M.A.R.T. self-test on all three IronWolf drives twice daily. Takes 1-2 minutes per drive and checks the most critical drive functions. Read-only — causes no wear on the drives. Covers the 6TB drive (`/dev/sda`) and both 8TB RAID drives (`/dev/sdb`, `/dev/sdc`). Results are visible in the Scrutiny dashboard after the next data collection run.

### Works With
- [[Scrutiny]]
- [[Scrutiny SMART Data Collection]]
