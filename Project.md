# IS355 Networking and Cyber Security

## Group Members

| Student Name      | Student ID | Student Email                                           |
| ----------------- | ---------: | ------------------------------------------------------- |
| Zane Schutzman    |    1924285 | [zwschutzman@loyola.edu](mailto:zwschutzman@loyola.edu) |
| Owen Steinetz     |    1928302 | [omsteinetz@loyola.edu](mailto:omsteinetz@loyola.edu)   |
| Gbemiro Omokayode |    1904384 | [gdomokayode@loyola.edu](mailto:gdomokayode@loyola.edu) |
| Charlie DiNapoli  |    1906216 | [cjdinapoli@loyola.edu](mailto:cjdinapoli@loyola.edu)   |

---

## Communication Plan

We will use an iMessage group chat, which we have already created, to communicate throughout the project.

We will communicate every week to discuss:

* What we have completed
* What still needs to be done
* What we will work on next

We will aim to complete one or two tasks each week.

---

## Tasks

| Task                                            | Name | Status |
| ----------------------------------------------- | ---- | ---- |
| Form project group and create GitHub repository | All | complete |
| Create project plan and communication schedule  | All | complete |
| Identify assumptions and requirements           | Zane | complete |
| Design the network                              | Zane | complete |
| Create network diagram                          | Zane | complete |
| Develop IP addressing plan                      | Zane | complete |
| Recommend network hardware                      | Zane | complete |
| Research cloud providers                        | Charlie | complete |
| Complete cloud service pricing comparison       | Charlie | complete |
| Compare backup strategies                       | Charlie | complete |
| Conduct cyber security risk assessment          | Gbemiro | incomplete |
| Recommend security controls                     | Owen | incomplete |
| Review and improve network design               | Owen | incomplete |
| Complete final report                           | Owen | incomplete |
| Prepare final submission                        | Gbemiro | incomplete |

---

## Project Timeline

### Week 4

- [X] Form group
- [X] Create GitHub repository
- [X] Create project plan

### Week 5

- [X] Assumptions
- [X] Requirements
- [X] Begin network design

### Week 6

- [X] Network design
- [X] IP addressing

### Week 7

- [X] Network diagram
- [X] Hardware recommendations

### Week 8

- [ ] Upload draft network design to GitHub

### Week 9

- [ ] Cloud provider research
- [ ] Pricing

---

# Assumptions and Requirements

## Requirements

* The company has two attached buildings: a factory and an office building.
* The factory normally has 20 to 25 workers.
* The office normally has 30 to 40 staff.
* The factory contains network-controlled machinery and conveyor belts.
* Factory machinery can use wired LAN or wireless Wi-Fi connections.
* Factory computers monitor and control the machinery.
* Office and factory users have both wired and wireless devices.
* The company has general-purpose office printers.
* The company has specialized printers, including large engineering printers and 3D printers.
* The company will use IP-based security cameras throughout the buildings.
* Security cameras will send video to a local server in the office.
* The company will use some cloud services, including a public website and email.
* Important information such as engineering designs and financial information will remain on local office servers.
* The network must contain at least three IP subnets: factory, office, and security cameras.
* Only `/24` and `/16` network masks may be used.
* Every IP address used in the network design must begin with the last two digits of one of the group members' student IDs.

## Assumptions

* The company will have one primary internet connection.
* A firewall will be placed between the company's internal network and the internet.
* Managed network switches will be used to support network segmentation.
* Separate networks will be used for factory devices, office devices, security cameras, and other specialized devices where appropriate.
* Wireless access points will be used to provide Wi-Fi throughout the office and factory.
* Guest wireless devices will be separated from the company's internal networks.
* The company will use local servers for important engineering and financial information.
* A local server will be used to store security camera footage.
* Network equipment and servers will be located in secure areas with restricted physical access.
* The network will use security controls such as firewalls, network segmentation, access controls, and regular backups.

---

# Network Design

## IP Addressing

The network will be divided into six separate `/24` subnets. Network segmentation will separate factory equipment, office devices, security cameras, guest devices, servers, and network management traffic.

| Network            | IP Address Range | Purpose                                                  |
| ------------------ | ---------------- | -------------------------------------------------------- |
| Factory            | 85.10.0.0/24     | Factory machinery, conveyor belts, and factory computers |
| Office             | 85.20.0.0/24     | Office computers, laptops, and printers                  |
| Security Cameras   | 85.30.0.0/24     | IP security cameras                                      |
| Guest Wi-Fi        | 85.40.0.0/24     | Guest wireless devices                                   |
| Servers            | 85.50.0.0/24     | Local company servers                                    |
| Network Management | 85.60.0.0/24     | Management of network equipment                          |

### IP Addressing Plan

All internal networks use a /24 subnet mask (255.255.255.0). The first octet of the IP addresses is 85, which corresponds to the last two digits of a group member's student ID.

| Device / Device Group | IP Address / Range | Network | Purpose |
|---|---|---|---|
| Factory Gateway | 85.10.0.1 | Factory | Default gateway for factory devices |
| Office Gateway | 85.20.0.1 | Office | Default gateway for office devices |
| Camera Gateway | 85.30.0.1 | Cameras | Default gateway for security cameras |
| Guest Gateway | 85.40.0.1 | Guest Wi-Fi | Default gateway for guest devices |
| Server Gateway | 85.50.0.1 | Servers | Default gateway for local servers |
| Management Gateway | 85.60.0.1 | Management | Default gateway for network equipment |
| Factory Switch | 85.60.0.2 | Management | Management address for factory switch |
| Office Switch | 85.60.0.3 | Management | Management address for office switch |
| Camera Switch | 85.60.0.4 | Management | Management address for camera switch |
| Server Switch | 85.60.0.5 | Management | Management address for server switch |
| Factory PCs | 85.10.0.10–85.10.0.34 | Factory | Factory employee computers |
| Office Computers | 85.20.0.10–85.20.0.49 | Office | Employee computers |
| IP Cameras | 85.30.0.10–85.30.0.59 | Cameras | Security cameras |
| Guest Devices | 85.40.0.10–85.40.0.99 | Guest Wi-Fi | Temporary/guest devices |
| File Server | 85.50.0.10 | Servers | Engineering and financial files |
| Camera Server | 85.50.0.11 | Servers | Stores security camera footage |

### Network Design Decisions

The network is divided into separate subnets to improve organization, security, and network management. The factory, office, security cameras, guest Wi-Fi, servers, and network management equipment each have their own subnet.

The factory network is separated from the office network because it contains network-controlled machinery and conveyor belts. This helps limit unnecessary traffic between factory equipment and office devices.

The security camera network is separate from the other networks so that camera traffic does not interfere with normal business traffic. The cameras connect to a dedicated camera switch and send their footage to the local camera server.

The guest Wi-Fi network is separated from the company's internal networks. Guest devices should not have direct access to company computers, servers, machinery, or security cameras.

The server network contains the local file server and camera server. The file server stores important engineering and financial information, while the camera server stores security camera footage.

A separate management network is used for managing switches and other network equipment. This keeps management traffic separate from normal user traffic.

The firewall is placed between the internet and the internal network. It provides traffic filtering and helps protect the company's internal systems from unauthorized internet traffic.

### Device IP Addresses

| Device | IP Address | Network |
|---|---|---|
| Firewall | 85.10.0.1 | Network Gateway |
| Core Switch | 85.60.0.1 | Management |
| Factory Switch | 85.60.0.2 | Management |
| Office Switch | 85.60.0.3 | Management |
| Camera Switch | 85.60.0.4 | Management |
| Server Switch | 85.60.0.5 | Management |
| Factory PCs | 85.10.0.10–85.10.0.34 | Factory |
| Office Computers | 85.20.0.10–85.20.0.49 | Office |
| IP Cameras | 85.30.0.10–85.30.0.59 | Cameras |
| Guest Devices | 85.40.0.10–85.40.0.99 | Guest |
| File Server | 85.50.0.10 | Servers |
| Camera Server | 85.50.0.11 | Servers |

### Recommended Network Hardware

| Hardware | Quantity | Minimum Specifications | Purpose |
|---|---:|---|---|
| Firewall | 1 | Enterprise firewall, VLAN support, VPN support, traffic filtering, and at least 1 Gbps throughput | Protects the internal network and controls internet traffic |
| Core Switch | 1 | Managed Layer 3 switch, VLAN support, Gigabit Ethernet, and enough ports for all network connections | Connects the company's different network segments |
| Factory Switch | 1+ | Managed Gigabit switch, VLAN support, and industrial/environmental suitability | Connects factory machinery, conveyor belts, and factory PCs |
| Office Switch | 1+ | Managed Gigabit switch with VLAN support and sufficient Ethernet ports | Connects office computers, printers, and access points |
| Camera Switch | 1+ | Managed PoE switch with Gigabit Ethernet and enough PoE ports | Connects and powers IP security cameras |
| Server Switch | 1 | Managed Gigabit switch with VLAN support | Connects the local servers |
| Wireless Access Points | 4+ | Wi-Fi 6 or newer, VLAN support, WPA3, and business/enterprise management | Provides wireless connectivity throughout the buildings |
| File Server | 1 | Business-class server, redundant storage/RAID, and sufficient storage for company files | Stores engineering designs and financial information |
| Camera Server | 1 | Business-class server with high-capacity storage and RAID | Stores security camera footage |
| UPS | 2+ | Battery backup with surge protection and sufficient capacity for network/server equipment | Keeps critical network equipment running during short power interruptions |

### Hardware Recommendations

The recommended hardware supports the size and requirements of the company's factory and office networks. Managed switches are used so that the different network subnets can be separated and managed. A PoE switch is recommended for the security cameras because IP cameras can receive both network connectivity and power through Ethernet.

Wireless access points will provide Wi-Fi throughout the factory and office while supporting the network segmentation used in the design. The company will also use local servers for important engineering and financial information and for storing security camera footage.

A firewall will be placed between the internet and the internal network to provide traffic filtering and network protection. UPS devices are recommended for critical network and server equipment to reduce disruption caused by short power outages.

### Research cloud providers

The company will use cloud services for its public website and email, and cloud storage for offsite backups. As stated in the requirements, important engineering designs and financial information will remain on the local file server. Cloud storage will only hold encrypted backup copies of that data.

| Service Needed | Providers Compared | Purpose |
|---|---|---|
| Email and productivity | Microsoft 365, Google Workspace | Business email, calendars, office apps, and video meetings |
| Public website | Squarespace, Wix | Hosting the company's public website |
| Backup storage | Backblaze B2, Amazon S3, Microsoft Azure Blob Storage, Google Cloud Storage | Offsite copy of local server backups |

#### Email and Productivity

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

#### Public Website

The public website will be hosted by a managed website provider instead of on a server inside the company network. This means the firewall does not need to allow inbound internet traffic to an internal web server, which reduces the company's attack surface. The provider also handles web server updates, uptime, and SSL certificates.

| Feature | Squarespace | Wix |
|---|---|---|
| Free plan | No (14-day trial) | Yes (with Wix branding, no custom domain) |
| Entry paid plan | Basic | Light |
| Hosting and SSL | Included | Included |
| Strengths | Professional templates, simple editing | More apps and customization options |

**Recommendation: Squarespace.** The company needs a professional informational website rather than an online store, and Squarespace's entry plan with a custom domain fully meets that need.

#### Backup Storage

| Provider | Standard Storage Price | Notes |
|---|---|---|
| Backblaze B2 | $6.95 per TB/month | No minimum storage time, free egress up to 3x stored data, supports Object Lock (immutable backups) |
| Microsoft Azure Blob (Hot) | About $18 per TB/month | Integrates with Microsoft services |
| Google Cloud Storage (Regional) | About $20 per TB/month | Integrates with Google services |
| Amazon S3 Standard | About $23 per TB/month | Largest feature set |
| Amazon S3 Glacier | About $1–3.60 per TB/month | Very cheap storage, but restores are slow and retrieval fees apply |

**Recommendation: Backblaze B2.** It has the lowest standard storage price, works with most backup software through its S3-compatible API, and supports Object Lock, which prevents backups from being deleted or encrypted by ransomware for a set retention period. Glacier is cheaper to store but would be slow and costly to restore from during an emergency.

### Complete cloud service pricing comparison

#### Pricing Assumptions

* Up to 65 users: 40 office staff and 25 factory workers (the maximum staff numbers in the requirements).
* Office staff need desktop Office apps; factory workers need email and web apps only.
* All prices are U.S. list prices on annual commitment, as of September–October 2026.
* About 2 TB of engineering and financial files, stored as about 4 TB in the cloud once backup versions are included.

#### Email and Productivity Costs

| Option | Office Users (40) | Factory Users (25) | Monthly Cost | Annual Cost |
|---|---|---|---:|---:|
| Microsoft 365: Standard (office) + Basic (factory) | 40 × $14 | 25 × $7 | $735 | $8,820 |
| Microsoft 365: Standard for everyone | 40 × $14 | 25 × $14 | $910 | $10,920 |
| Google Workspace: Standard (office) + Starter (factory) | 40 × $14 | 25 × $7 | $735 | $8,820 |
| Google Workspace: Starter for everyone | 40 × $7 | 25 × $7 | $455 | $5,460 |

Microsoft 365 and Google Workspace now have the same list prices, so the decision comes down to features. The Google Workspace Starter-only option is the cheapest, but office staff would not have desktop Office apps and would only have 30 GB of storage each.

#### Website Costs

| Option | Monthly Cost | Annual Cost |
|---|---:|---:|
| Squarespace Basic | About $16–19 | About $192–228 |
| Wix Light | $17 | $204 |
| Wix Core | $29 | $348 |

#### Backup Storage Costs (4 TB)

| Provider | Monthly Cost | Annual Cost |
|---|---:|---:|
| Backblaze B2 | $27.80 | $333.60 |
| Microsoft Azure Blob (Hot) | About $72 | About $864 |
| Google Cloud Storage | About $80 | About $960 |
| Amazon S3 Standard | About $92 | About $1,104 |
| Amazon S3 Glacier | About $4–15 (plus retrieval fees) | About $48–173 (plus retrieval fees) |

#### Recommended Cloud Services Total

| Service | Recommended Option | Estimated Annual Cost |
|---|---|---:|
| Email and productivity | Microsoft 365 (Standard + Basic) | $8,820 |
| Website | Squarespace Basic | About $228 |
| Backup storage | Backblaze B2 (4 TB) | About $334 |
| **Total** | | **About $9,382 per year** |

Prices change often, so they should be confirmed with each provider before purchase.

### Compare backup strategies

#### Backup Types

| Backup Type | How It Works | Advantages | Disadvantages |
|---|---|---|---|
| Full | Copies all data every time | Fastest and simplest restore | Uses the most storage and takes the longest to run |
| Incremental | Copies only data changed since the last backup of any type | Fastest backups, uses the least storage | Slower restore; needs the last full backup plus every incremental since |
| Differential | Copies all data changed since the last full backup | Faster restore than incremental; needs only the full backup plus the latest differential | Each differential grows larger until the next full backup |

#### Backup Locations

| Strategy | Advantages | Disadvantages |
|---|---|---|
| Local only (backup server or NAS) | Fast backups and restores, no ongoing cloud costs | Lost along with the original data in a fire, flood, theft, or ransomware attack |
| Cloud only | Stored offsite and protected from local disasters | Large restores are slow over the internet connection; ongoing monthly costs |
| Hybrid (local + cloud) | Fast local restores plus offsite protection | Highest cost and complexity |

#### Recommended Backup Strategy

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

#### Additional Hardware and IP Address

| Hardware | Quantity | Minimum Specifications | Purpose |
|---|---:|---|---|
| Backup NAS | 1 | Business NAS with RAID, at least 2x the file server's storage capacity, and encryption support | Stores local backups of the file server |

| Device | IP Address | Network | Purpose |
|---|---|---|---|
| Backup NAS | 85.50.0.12 | Servers | Local backup storage |

#### Sources

* Microsoft 365 pricing: https://o365hq.com/blog/microsoft-365-business-basic-vs-standard-vs-premium-which-plan-for-10-50-and-200-users
* Google Workspace pricing: https://www.flamingo.run/blog/google-workspace-pricing
* Backblaze B2 pricing: https://www.backblaze.com/cloud-storage/pricing
* Cloud storage comparison: https://tech-insider.org/backblaze-b2-vs-google-cloud-vs-azure-blob-2026/
* Wix and Squarespace pricing: https://helpcompare.com/wix-vs-squarespace/
### Network Design Explanation

The network is divided into separate subnets for the factory, office, security cameras, guest Wi-Fi, servers, and network management. This separation allows different types of devices and users to be managed independently.

The factory network contains the company's network-controlled machinery, conveyor belts, and factory PCs. The office network contains employee computers, printers, and wireless access points. The security camera network is separated from the other networks because the cameras continuously send video to the local camera server.

The guest network provides wireless access for visitors without placing guest devices directly on the company's internal networks. The server network contains the local file and camera servers. A separate management network is used for managing network infrastructure.

A firewall is positioned between the internet and the internal network. The core switch connects the different network segments and allows the network to be centrally connected.
![Network Diagram](images/diagramproj.png)
