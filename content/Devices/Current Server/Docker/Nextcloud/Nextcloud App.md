---
type: container
stack: nextcloud
category: storage
status: running
port: 8081
---

[[Nextcloud]]

---
### Details
The main Nextcloud application container. Self-hosted cloud storage integrated with Jellyfin. Handles the web interface, file syncing, and all Nextcloud functionality.

#### External Storage
| Name | Container Path | Host Path |
|------|---------------|-----------|
| Movies | `/media/raid/movies` | `/mnt/raid/movies` |
| TV Shows | `/media/raid/tvshows` | `/mnt/raid/tvshows` |

Both entries point to the RAID array (`/dev/sdb` + `/dev/sdc`) mounted at `/mnt/raid` on the host. Old entries pointing to the 6TB IronWolf have been removed.

### Access
Home: http://192.168.86.201:8081
Remote: http://100.74.166.10:8081

### Login
Username: jeremyalston7
Password: Kylie00415

### Works With
- [[Nextcloud DB]]
- [[Vdirsyncer Calendar Sync]]
