# Recommend Security Controls

Building on the cyber security risk assessment we completed in Step 9, this section is about the security controls that we would recommend for our manufacturing facility network. All of these recommendations come from our Control Catalog and match up with the best possible practices.

## 1. Overview + Security Objectives

In Step 9, our risk assessment showed that our biggest concerns involve:
- ransomware targeting factory machinery (85.10.0.0/24) and our local file server (85.50.0.0/24)
- people stealing engineering designs and intellectual property
- phishing emails sent to office staff (85.20.0.0/24)
- someone gaining unauthorized control of network equipment (85.60.0.0/24)

To address these risks, we have gone through and chosen 8 security controls that fit our network design.

## 2. Our Recommendations
### Control 1: Access Enforcement and Least Privilege
- **NIST SP 800-53 Control**: AC-3 (Access Enforcement)
- **Best Practice Alignment**: ACSC Restrict Administrative Privileges and Access Control
- **Protected Assets**: 
  - A4 (Local File Server)
  - A6 (Engineering Designs)
  - A7 (Financial Records)
- **Threats Addressed**:
  - T4 (Ransomware and Data Loss)
  - T6 (Data Theft or Unauthorized Disclosure)
  - T7 (Unauthorized Access or Data Theft)
- **How it Works**: We will use role-based access control on the Local File Server. Only engineering staff in the office network will be allowed to view or edit engineering files, and financial files will be limited to finance employees. Computers on the factory floor and guest devices will not be able to access file server shares at all.

### Control 2: Multi-Factor Authentication (MFA)
- **NIST SP 800-53 Control**: IA-2 (Identification and Authentication - Organizational Users)
- **Best Practice Alignment**: ACSC Essential Eight (Multi-Factor Authentication)
- **Protected Assets**: 
  - A2 (Office Computers)
  - A5 (Network Infrastructure)
  - A8 (Cloud Services)
- **Threats Addressed**:
  - T2 (Phishing and Malware Infections)
  - T5 (Unauthorized Network Access)
  - T8 (Cloud Account Compromise or Data Breach)
- **How it Works**: Multi-Factor Authentication using an authenticator app will be required for all office workers logging into Microsoft 365, remote VPN connections, cloud portals, and network management screens on the management subnet.

### Control 3: Boundary Protection and Firewall Filtering
- **NIST SP 800-53 Control**: SC-7 (Boundary Protection)
- **Best Practice Alignment**: NIST Cybersecurity Framework (Protect)
- **Protected Assets**: 
  - A1 (Factory Machinery)
  - A4 (Local File Server)
  - A5 (Network Infrastructure)
- **Threats Addressed**:
  - T1 (Ransomware or Malware Attacks)
  - T4 (Ransomware and Data Loss)
  - T6 (Data Theft or Unauthorized Disclosure)
- **How it Works**: The firewall will enforce strict traffic rules between subnets. The factory network will be blocked from direct internet access and cannot talk directly to office devices. The guest Wi-Fi will only allow web browsing to the internet and will block all access to internal servers and factory machinery.


### Control 4: System Backup and Immutable Cloud Storage
- **NIST SP 800-53 Control**: CP-9 (System Backup)
- **Best Practice Alignment**: ACSC Essential Eight (Daily Backups)
- **Protected Assets**: 
  - A4 (Local File Server)
  - A6 (Engineering Designs)
  - A7 (Financial Records)
- **Threats Addressed**:
  - T1 (Ransomware or Malware Attacks)
  - T4 (Ransomware and Data Loss)
- **How it Works**: Based on our backup plan from Step 8, full weekly backups and nightly incremental backups will be saved to the Local Backup NAS. Backups will also be sent offsite to Backblaze B2 using Object Lock for 30 days. This keeps ransomware form deleting or encrypting our saved copies.

### Control 5: Malicious Code Protection and Endpoint Protection
- **NIST SP 800-53 Control**: SI-3 (Malicious Code Protection)
- **Best Practice Alignment**: ACSC Essential Eight (Patch Applications and Endpoint Protection)
- **Protected Assets**: 
  - A1 (Factory Machinery)
  - A2 (Office Computers)
- **Threats Addressed**:
  - T1 (Ransomware or Malware Attacks)
  - T2 (Phishing and Malware Infections)
  - T7 (Unauthorized Access or Data Theft)
- **How it Works**: Anti-malware software will be installed on all office computers, factory monitoring PCs, and local servers. The software will update automatically every day and run weekly scans to catch malicious files.

### Control 6: Continuous System Monitoring and Logging
- **NIST SP 800-53 Control**: SI-4 (Information System Monitoring)
- **Best Practice Alignment**: ACSC Essential Eight and NIST Cybersecurity Framework (Detect)
- **Protected Assets**: 
  - A3 (Security Cameras)
  - A5 (Network Infrastructure)
  - A8 (Cloud Services)
- **Threats Addressed**:
  - T3 (Unauthorized Access or Camera Hacking)
  - T5 (Unauthorized Network Access)
  - T8 (Cloud Account Compromise or Data Breach)
- **How it Works**: Network switches, the main firewall, and local servers will send log data to a server on the management network. System alerts will notify administrators about unusual network activity, multiple failed login attempts, or unexpected settings changes.

### Control 7: Secure Baseline Configuration
- **NIST SP 800-53 Control**: CM-2 (Baseline Configuration
- **Best Practice Alignment**: ACSC Hardening Guidance and NIST Cybersecurity Framework (Protect)
- **Protected Assets**: 
  - A3 (Security Cameras)
  - A5 (Network Infrastructure)
- **Threats Addressed**:
  - T3 (Unauthorized Access or Camera Hacking)
  - T5 (Unauthorized Network Access)
- **How it Works**: Before placing hardware on the network, default passwords will be changed on all switches, firewalls, and security cameras. Unnecessary features like HTTP management and Telnet will be turned off, and management will only be allowed through SSH or HTTPS over the management subnet.

### Control 8: Protection of Information at Rest
- **NIST SP 800-53 Control**: SC-28 (Protection of Information at Rest)
- **Best Practice Alignment**: Data Encryption Best Practices
- **Protected Assets**: 
  - A4 (Local File Server)
  - A6 (Engineering Designs)
  - A7 (Financial Records)
- **Threats Addressed**:
  - T4 (Ransomware and Data Loss)
  - T6 (Data Theft or Unauthorized Disclosure)
  - T8 (Cloud Account Compromise or Data Breach)
- **How it Works**: Full-disk encryption will be turned on for both the Local File Server and the Backup NAS. In addition, all backups will be encrypted before they leave our local network so that no one can read the data stored in the cloud.

## 3. Summary Table of Security Controls

| Control ID | NIST SP 800-53 Control | Target Asset / Risk | Implementation Location / Mechanism |
|---|---|---|---|
| SC-1 | AC-3 (Access Enforcement) |  |  |
| SC-2 | IA-2 (Identification and Authentication) |  |  |
| SC-3 | SC-7 (Boundary Protection) |  |  |
| SC-4 | CP-9 (System Backup) |  |  |
| SC-5 | SI-3 (Malicious Code Protection) |  |  |
| SC-6 | SI-4 (Information System Monitoring) |  |  |
| SC-7 | CM-2 (Baseline Configuration |  |  |
| SC-8 | SC-28 (Protection of Information at Rest) |  |  |


## 4. Updates to Network Design
Adding these security controls helps keep our network organized in two main ways:
- **Management Subnet (85.60.0.0/24)**
  - keeps switch, firewall, and admin controls on a separate network so regular users can't reach them
- **Camera Subnet (85.30.0.0/24)**
  - keeps security camera video streams on their own separate network so they don't slow down other computers or expose camera web pages
