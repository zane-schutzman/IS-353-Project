# Compare Backup Strategies

## Backup Types

| Backup Type | How It Works | Advantages | Disadvantages |
|---|---|---|---|
| Full | Copies all data every time | Fastest and simplest restore | Uses the most storage and takes the longest to run |
| Incremental | Copies only data changed since the last backup of any type | Fastest backups, uses the least storage | Slower restore; needs the last full backup plus every incremental since |
| Differential | Copies all data changed since the last full backup | Faster restore than incremental; needs only the full backup plus the latest differential | Each differential grows larger until the next full backup |

## Backup Locations

| Strategy | Advantages | Disadvantages |
|---|---|---|
| Local only (backup server or NAS) | Fast backups and restores, no ongoing cloud costs | Lost along with the original data in a fire, flood, theft, or ransomware attack |
| Cloud only | Stored offsite and protected from local disasters | Large restores are slow over the internet connection; ongoing monthly costs |
| Hybrid (local + cloud) | Fast local restores plus offsite protection | Highest cost and complexity |

## Recommended Backup Strategy

The company will follow the **3-2-1 backup rule**: keep 3 copies of important data, on 2 different types of storage, with 1 copy offsite.

1. **Original data** is stored on the file server (85.50.0.10), which uses RAID. RAID protects against a single drive failure but is not a backup.
2. **Local backup:** A backup NAS on the server network (85.50.0.12) receives a full backup every weekend and an incremental backup every night. This allows quick restores of deleted or damaged files.
3. **Offsite backup:** Each night, an encrypted copy of the backup is sent to Backblaze B2. Object Lock makes these copies unchangeable for 30 days, so ransomware or an attacker cannot delete or encrypt them.

| Data | Backup Method | Frequency | Retention |
|---|---|---|---|
| Engineering and financial files | Local NAS + Backblaze B2 | Weekly full, nightly incremental | 30 daily, 12 monthly versions |
| Security camera footage | Stored on camera server RAID; important clips copied to the file server | Continuous recording | 30 days of footage |
| Switch and firewall configurations | Exported to the file server after every change | After each change | Last 10 versions |
| Microsoft 365 email and files | Microsoft 365 retention policies (a third-party Microsoft 365 backup service is optional) | Continuous | As set by policy |

Security camera footage is not fully backed up to the cloud because 24/7 video from many cameras would use too much storage and internet bandwidth. Instead, footage is kept on the camera server's RAID storage, and clips of important events are saved to the file server, where they are included in normal backups.

Restores will be tested every three months to make sure the backups actually work. With nightly backups, the company would lose at most one day of file changes in a worst-case event.

## Additional Hardware and IP Address

| Hardware | Quantity | Minimum Specifications | Purpose |
|---|---:|---|---|
| Backup NAS | 1 | Business NAS with RAID, at least 2x the file server's storage capacity, and encryption support | Stores local backups of the file server |

| Device | IP Address | Network | Purpose |
|---|---|---|---|
| Backup NAS | 85.50.0.12 | Servers | Local backup storage |

### Sources

* Microsoft 365 pricing: https://o365hq.com/blog/microsoft-365-business-basic-vs-standard-vs-premium-which-plan-for-10-50-and-200-users
* Google Workspace pricing: https://www.flamingo.run/blog/google-workspace-pricing
* Backblaze B2 pricing: https://www.backblaze.com/cloud-storage/pricing
* Cloud storage comparison: https://tech-insider.org/backblaze-b2-vs-google-cloud-vs-azure-blob-2026/
* Wix and Squarespace pricing: https://helpcompare.com/wix-vs-squarespace/
