# Conduct Cyber Security Risk Assessment

To evaluate the security posture of the manufacturing facility network, a risk assessment was conducted focusing on key digital and physical assets, potential threat sources, vulnerabilities, and high-level risk ratings.


---------------------------------------------------------------------------------------------------------------------------------------------------------------

# Conduct Cyber Security Risk Assessment

## 1. Introduction
---------------------------------------------------------------------------------------------------------------------------------------------------------------
To evaluate the security posture of the manufacturing facility network, a risk assessment was conducted focusing on key digital and physical assets, potential threat sources, vulnerabilities, and high-level risk ratings.

The purpose of this assessment is to identify potential cybersecurity risks that could affect the company's daily operations, compromise sensitive business information, or disrupt manufacturing activities. Particular attention is given to the network-connected factory machinery, office computers, local servers, IP security cameras, network infrastructure, and cloud services.

The assessment considers the company's network segmentation, which separates factory equipment, office devices, security cameras, guest Wi-Fi, local servers, and network management systems into different subnets.

## 2. Risk Assessment Methodology
---------------------------------------------------------------------------------------------------------------------------------------------------------------
A qualitative risk assessment approach was used to evaluate the potential risks associated with the company's network. Each risk was assessed based on two factors: likelihood and impact.

- **Likelihood:** The probability that a particular threat will occur and exploit an existing vulnerability.
- **Impact:** The potential damage or consequences to the company if the threat successfully occurs.

A numerical rating from 1 to 5 was assigned to both likelihood and impact. The overall risk score was calculated by multiplying the two ratings.

**Risk Score = Likelihood × Impact**

### Risk Rating Scale

| Score | Likelihood | Impact |
|---|---|---|
| 1 | Rare | Insignificant |
| 2 | Unlikely | Minor |
| 3 | Possible | Moderate |
| 4 | Likely | Major |
| 5 | Almost Certain | Severe |

### Risk Classification

| Risk Score | Risk Level |
|---|---|
| 1–4 | Low |
| 5–9 | Medium |
| 10–16 | High |
| 17–25 | Critical |

## 3. Identification and Classification of Assets
---------------------------------------------------------------------------------------------------------------------------------------------------------------
The first stage of the assessment involved identifying important assets within the manufacturing company's network. These assets include physical equipment, network infrastructure, computer systems, and confidential company information.

The following assets were identified:

| Asset ID | Asset | Network | Classification | Description |
|---|---|---|---|---|
| A1 | Factory Machinery | Factory (85.10.0.0/24) | Critical | Network-connected machinery, conveyor belts, and monitoring equipment used in manufacturing operations. |
| A2 | Office Computers | Office (85.20.0.0/24) | Internal | Employee computers and laptops used for business operations, communication, and accessing company resources. |
| A3 | Security Cameras | Cameras (85.30.0.0/24) | Internal | IP cameras installed throughout the factory and office buildings for security monitoring. |
| A4 | Local File Server | Servers (85.50.0.0/24) | Confidential | Stores important company documents, engineering designs, and financial records. |
| A5 | Network Infrastructure | Management (85.60.0.0/24) | Critical | Firewalls, switches, and other networking equipment responsible for connecting and managing the network. |
| A6 | Engineering Designs | Office / Servers | Confidential | Sensitive intellectual property containing product designs, technical drawings, and specifications. |
| A7 | Financial Records | Servers (85.50.0.0/24) | Confidential | Important business and financial information belonging to the company. |
| A8 | Cloud Services | External Cloud | Confidential / Public | Cloud-hosted website, email, and backup services used by the company. |

## 4. Identification of Threats and Vulnerabilities
---------------------------------------------------------------------------------------------------------------------------------------------------------------
After identifying the company's assets, potential threats and vulnerabilities were examined.

A threat is a potential event or action that could cause harm to an asset. A vulnerability is a weakness in a system, device, or process that could be exploited by a threat.

The following threats and vulnerabilities were identified:

| ID | Asset | Potential Threat | Vulnerability |
|---|---|---|---|
| T1 | Factory Machinery | Ransomware or malware attacks | Outdated machinery software, insecure configurations, or insufficient network isolation. |
| T2 | Office Computers | Phishing and malware infections | Employees may open malicious email attachments or click fraudulent links. |
| T3 | Security Cameras | Unauthorized access or camera hacking | Default passwords, outdated firmware, or weak authentication. |
| T4 | Local File Server | Ransomware and data loss | Insufficient backup protection, weak access controls, or unpatched server software. |
| T5 | Network Infrastructure | Unauthorized network access | Weak administrator credentials, insecure management interfaces, or misconfigured firewall rules. |
| T6 | Engineering Designs | Data theft or unauthorized disclosure | Excessive employee permissions or insufficient access restrictions. |
| T7 | Financial Records | Unauthorized access or data theft | Weak passwords and insufficient authentication or access controls. |
| T8 | Cloud Services | Cloud account compromise or data breach | Weak authentication, exposed credentials, or improperly configured cloud storage. |

## 5. Risk Assessment and Evaluation
---------------------------------------------------------------------------------------------------------------------------------------------------------------
The identified threats were evaluated according to their likelihood of occurring and the potential impact on the manufacturing company.

The risk score for each threat was calculated using the likelihood and impact ratings.

| Risk ID | Risk Description | Likelihood | Impact | Risk Score | Risk Level |
|---|---|---:|---:|---:|---|
| R1 | Ransomware infects factory computers and disrupts machinery operations. | 4 | 5 | 20 | Critical |
| R2 | Attackers gain unauthorized access to engineering designs and steal intellectual property. | 3 | 5 | 15 | High |
| R3 | Unauthorized individuals access confidential financial records. | 3 | 4 | 12 | High |
| R4 | Attackers compromise IP security cameras and gain access to video footage. | 3 | 3 | 9 | Medium |
| R5 | Ransomware encrypts the local file server, making important company files unavailable. | 4 | 5 | 20 | Critical |
| R6 | Attackers compromise network infrastructure and gain access to multiple network segments. | 3 | 5 | 15 | High |
| R7 | Employees fall victim to phishing attacks, resulting in malware infections. | 4 | 4 | 16 | High |
| R8 | Attackers compromise cloud accounts and gain access to company information or backups. | 3 | 5 | 15 | High |

## 6. Analysis of the Highest Risks
---------------------------------------------------------------------------------------------------------------------------------------------------------------
The assessment identified two critical risks and five high risks. These risks require particular attention because of their potential impact on the company's manufacturing operations, confidential information, and overall network security.

### 6.1 Ransomware Attacks on Factory Machinery (Critical)
---------------------------------------------------------------------------------------------------------------------------------------------------------------
The factory relies on network-connected machinery, conveyor belts, and monitoring computers to maintain manufacturing operations. A ransomware attack targeting factory computers could prevent employees from monitoring or controlling machinery.

This could result in manufacturing downtime, delayed production, financial losses, and potential damage to equipment or production processes.

### 6.2 Ransomware Attacks on the Local File Server (Critical)
---------------------------------------------------------------------------------------------------------------------------------------------------------------
The local file server stores important company information, including engineering designs and financial records. If ransomware successfully infects the server, these files could become encrypted and unavailable to employees.

This could significantly disrupt business operations and potentially result in the loss of important company information if reliable backups are unavailable.

### 6.3 Theft of Engineering Designs (High)
---------------------------------------------------------------------------------------------------------------------------------------------------------------
Engineering designs and technical specifications represent valuable intellectual property for the manufacturing company. Unauthorized access to these files could allow attackers or competitors to obtain confidential product information.

This could negatively affect the company's competitive advantage and result in financial losses.

### 6.4 Compromise of Network Infrastructure (High)
---------------------------------------------------------------------------------------------------------------------------------------------------------------
The company's firewall and switches are responsible for managing communication between the different network segments. If an attacker gains administrative access to this infrastructure, they could modify network configurations, bypass security restrictions, or gain access to other parts of the network.

This could expose factory machinery, office computers, servers, and other connected devices to additional attacks.

### 6.5 Phishing and Malware Attacks (High)
---------------------------------------------------------------------------------------------------------------------------------------------------------------
Employees regularly use computers and email for communication and business activities. Attackers could exploit this by sending fraudulent emails containing malicious attachments or links.

If an employee interacts with a malicious email, malware could infect their computer and potentially spread to other connected systems.

## 7. Overall Risk Assessment Findings
---------------------------------------------------------------------------------------------------------------------------------------------------------------
The risk assessment identified ransomware, unauthorized network access, phishing attacks, and data theft as major cybersecurity concerns for the manufacturing company.

The highest risks involve the factory machinery and local file server because these systems support essential business operations. A successful attack against either asset could cause significant operational disruption and financial losses.

Although the company's network is divided into separate subnets, network segmentation alone does not eliminate cybersecurity threats. Additional security measures are required to prevent unauthorized communication between network segments and protect critical systems.

The assessment identified the following priorities:

1. Protect factory machinery and monitoring computers from ransomware and malware.
2. Secure the local file server containing confidential engineering and financial information.
3. Prevent unauthorized access to network infrastructure and administrative interfaces.
4. Improve employee protection against phishing and malware attacks.
5. Secure IP security cameras through stronger authentication and regular firmware updates.
6. Protect cloud services and ensure company backups are securely stored.


The cybersecurity risk assessment highlights several vulnerabilities that could threaten the manufacturing company's network, sensitive information, and daily operations.

Ransomware targeting factory machinery and the local file server represents the greatest potential risk because it could disrupt production and prevent employees from accessing essential business information.

The findings from this assessment will be used to guide the selection of appropriate security controls in Step 10. These controls will focus on reducing the likelihood of identified threats, minimizing their potential impact, and improving the overall security of the company's network.
