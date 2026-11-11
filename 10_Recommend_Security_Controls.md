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
- **How it Works**: 

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
- **How it Works**: 

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
- **How it Works**: 


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
- **How it Works**: 

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
- **How it Works**: 

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
- **How it Works**: 

### Control 7: Secure Baseline Configuration
- **NIST SP 800-53 Control**: CM-2 (Baseline Configuration
- **Best Practice Alignment**: ACSC Hardening Guidance and NIST Cybersecurity Framework (Protect)
- **Protected Assets**: 
  - A3 (Security Cameras)
  - A5 (Network Infrastructure)
- **Threats Addressed**:
  - T3 (Unauthorized Access or Camera Hacking)
  - T5 (Unauthorized Network Access)
- **How it Works**: 

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
- **How it Works**: 

