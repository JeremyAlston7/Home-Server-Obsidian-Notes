[[Cron Jobs]]

---
### Schedule
Every other Sunday at 2am (even-numbered weeks only)

### Command
```bash
0 2 * * 0 [ $(( $(date +\%W) \% 2 )) -eq 0 ] && sudo smartctl -t long -d sat /dev/sda
0 2 * * 0 [ $(( $(date +\%W) \% 2 )) -eq 0 ] && sudo smartctl -t long -d sat /dev/sdb
0 2 * * 0 [ $(( $(date +\%W) \% 2 )) -eq 0 ] && sudo smartctl -t long -d sat /dev/sdc
```

### Details
Performs a full comprehensive S.M.A.R.T. test on all three IronWolf drives. Takes 6-10 hours per drive to complete and provides the most thorough picture of drive health. The modulo check on the week number (`%W % 2 == 0`) limits it to even-numbered weeks, so it runs every two weeks rather than every Sunday. Covers the 6TB drive (`/dev/sda`) and both 8TB RAID drives (`/dev/sdb`, `/dev/sdc`). Results are visible in Scrutiny after the next data collection run.

### Works With
- [[Scrutiny]]
- [[Scrutiny SMART Data Collection]]
