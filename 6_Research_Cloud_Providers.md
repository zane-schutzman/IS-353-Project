# Research Cloud Providers

The company will use cloud services for its public website and email, and cloud storage for offsite backups. As stated in the requirements, important engineering designs and financial information will remain on the local file server. Cloud storage will only hold encrypted backup copies of that data.

| Service Needed | Providers Compared | Purpose |
|---|---|---|
| Email and productivity | Microsoft 365, Google Workspace | Business email, calendars, office apps, and video meetings |
| Public website | Squarespace, Wix | Hosting the company's public website |
| Backup storage | Backblaze B2, Amazon S3, Microsoft Azure Blob Storage, Google Cloud Storage | Offsite copy of local server backups |

## Email and Productivity

| Feature | Microsoft 365 | Google Workspace |
|---|---|---|
| Entry plan | Business Basic | Business Starter |
| Standard plan | Business Standard | Business Standard |
| Email | Exchange / Outlook | Gmail |
| Office apps | Word, Excel, PowerPoint (desktop apps on Standard and above) | Docs, Sheets, Slides (web-based) |
| Cloud storage | 1 TB per user | 30 GB per user (Starter), 2 TB per user (Standard) |
| Meetings | Microsoft Teams | Google Meet |
| Security upgrade path | Business Premium adds device management and advanced threat protection | Business Plus adds Vault and additional security controls |

**Recommendation: Microsoft 365.** Engineering and finance staff are likely to rely on desktop Excel and Word, and most business software is designed to work with Microsoft Office. Microsoft 365 also has a clear upgrade path to Business Premium, which adds device management and security features that support the company's security controls. Licenses can be mixed, so office staff can receive Business Standard while factory workers who only need email and web apps can receive Business Basic.

## Public Website

The public website will be hosted by a managed website provider instead of on a server inside the company network. This means the firewall does not need to allow inbound internet traffic to an internal web server, which reduces the company's attack surface. The provider also handles web server updates, uptime, and SSL certificates.

| Feature | Squarespace | Wix |
|---|---|---|
| Free plan | No (14-day trial) | Yes (with Wix branding, no custom domain) |
| Entry paid plan | Basic | Light |
| Hosting and SSL | Included | Included |
| Strengths | Professional templates, simple editing | More apps and customization options |

**Recommendation: Squarespace.** The company needs a professional informational website rather than an online store, and Squarespace's entry plan with a custom domain fully meets that need.

## Backup Storage

| Provider | Standard Storage Price | Notes |
|---|---|---|
| Backblaze B2 | $6.95 per TB/month | No minimum storage time, free egress up to 3x stored data, supports Object Lock (immutable backups) |
| Microsoft Azure Blob (Hot) | About $18 per TB/month | Integrates with Microsoft services |
| Google Cloud Storage (Regional) | About $20 per TB/month | Integrates with Google services |
| Amazon S3 Standard | About $23 per TB/month | Largest feature set |
| Amazon S3 Glacier | About $1–3.60 per TB/month | Very cheap storage, but restores are slow and retrieval fees apply |

**Recommendation: Backblaze B2.** It has the lowest standard storage price, works with most backup software through its S3-compatible API, and supports Object Lock, which prevents backups from being deleted or encrypted by ransomware for a set retention period. Glacier is cheaper to store but would be slow and costly to restore from during an emergency.
