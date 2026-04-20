# MITRE ATT&CK Mapping — Zero Trust NGO Architecture

## Overview

This document maps realistic threats facing a multi-country NGO operating in high-risk environments to the MITRE ATT&CK framework.

MITRE ATT&CK is a globally recognized knowledge base of adversary tactics and techniques used in real-world intrusions.

This mapping helps the organization:

- understand attacker behavior
- build detections
- prioritize monitoring
- align controls to threats
- improve incident response readiness

---

# Why MITRE ATT&CK Matters

Traditional security often focuses on tools.

MITRE ATT&CK focuses on:

> **How attackers actually operate**

It gives defenders a common language to describe malicious behavior.

Example:

Instead of saying:

> suspicious login activity

You can say:

> Potential abuse of Valid Accounts (**T1078**)

That improves communication across SOC, IR, and leadership teams.

---

# NGO Threat Context

This NGO environment includes:

- remote workforce
- field staff in hostile regions
- cloud-first applications
- donor and beneficiary data
- third-party partner access
- elevated phishing risk
- device seizure risk

These conditions make ATT&CK mapping highly relevant.

---

# Key Tactics Relevant to This Project

| Tactic | Purpose |
|-------|---------|
| Initial Access | Gain first entry |
| Execution | Run malicious code |
| Persistence | Maintain access |
| Privilege Escalation | Gain higher rights |
| Defense Evasion | Avoid detection |
| Credential Access | Steal credentials |
| Discovery | Learn environment |
| Lateral Movement | Move between systems |
| Collection | Gather sensitive data |
| Exfiltration | Remove data |
| Impact | Disrupt operations |

---

# Threat Scenario Mapping

## 1. Phishing Staff Credentials

### Scenario

Attacker sends fake NGO / donor login page to capture credentials.

### ATT&CK Mapping

| Tactic | Technique | ID |
|-------|-----------|----|
| Initial Access | Phishing | T1566 |
| Credential Access | Steal Web Session Cookie / Credentials | T1539 / T1056 |
| Persistence | Valid Accounts | T1078 |

### Recommended Controls

- phishing-resistant MFA
- conditional access
- impossible travel detection
- user awareness training

---

## 2. Compromised Valid Account Access

### Scenario

Attacker logs in using stolen credentials.

### ATT&CK Mapping

| Tactic | Technique | ID |
|-------|-----------|----|
| Defense Evasion | Use Trusted Identity | T1078 |
| Persistence | Valid Accounts | T1078 |
| Discovery | Account Discovery | T1087 |

### Recommended Controls

- session risk scoring
- re-authentication
- login anomaly detection
- access revocation workflows

---

## 3. Privileged Admin Abuse

### Scenario

Attacker gains cloud or admin rights.

### ATT&CK Mapping

| Tactic | Technique | ID |
|-------|-----------|----|
| Privilege Escalation | Account Manipulation | T1098 |
| Persistence | Additional Cloud Roles | T1098 |
| Defense Evasion | Disable Security Tools | T1562 |

### Recommended Controls

- PAM
- JIT admin access
- admin session recording
- separate privileged identities

---

## 4. Internal Reconnaissance

### Scenario

Compromised account explores systems and users.

### ATT&CK Mapping

| Tactic | Technique | ID |
|-------|-----------|----|
| Discovery | Network Service Scanning | T1046 |
| Discovery | File and Directory Discovery | T1083 |
| Discovery | Account Discovery | T1087 |

### Recommended Controls

- segmentation
- alert on excessive enumeration
- restrict internal visibility

---

## 5. Data Theft from Beneficiary Systems

### Scenario

Sensitive records exported or copied.

### ATT&CK Mapping

| Tactic | Technique | ID |
|-------|-----------|----|
| Collection | Data from Information Repositories | T1213 |
| Exfiltration | Exfiltration Over Web Services | T1567 |
| Collection | Archive Collected Data | T1560 |

### Recommended Controls

- DLP controls
- restricted exports
- audit logging
- unusual download detection

---

## 6. Partner Organization Abuse

### Scenario

Trusted partner account used as attack path.

### ATT&CK Mapping

| Tactic | Technique | ID |
|-------|-----------|----|
| Initial Access | Trusted Relationship | T1199 |
| Lateral Movement | External Remote Services | T1133 |

### Recommended Controls

- separate federation trust
- scoped permissions
- partner monitoring
- periodic access review

---

## 7. Malware on BYOD Device

### Scenario

Personal device infected before accessing NGO resources.

### ATT&CK Mapping

| Tactic | Technique | ID |
|-------|-----------|----|
| Execution | User Execution | T1204 |
| Credential Access | Input Capture | T1056 |
| Persistence | Startup Items / Login Items | T1547 |

### Recommended Controls

- device posture checks
- EDR
- browser isolation
- limited BYOD access

---

## 8. Cloud Misconfiguration Exploitation

### Scenario

Attacker discovers exposed storage or weak IAM.

### ATT&CK Mapping

| Tactic | Technique | ID |
|-------|-----------|----|
| Discovery | Cloud Service Discovery | T1526 |
| Collection | Data from Cloud Storage | T1530 |
| Exfiltration | Exfiltration to Cloud Account | T1537 |

### Recommended Controls

- CSPM monitoring
- least privilege IAM
- cloud audit logging
- automated remediation

---

# Detection Priorities

High-value ATT&CK techniques to monitor first:

| Technique | ID | Priority |
|----------|----|---------|
| Phishing | T1566 | Critical |
| Valid Accounts | T1078 | Critical |
| Disable Security Tools | T1562 | High |
| Account Discovery | T1087 | High |
| Data from Repositories | T1213 | High |
| Trusted Relationship | T1199 | Medium |
| Cloud Service Discovery | T1526 | High |

---

# Zero Trust + ATT&CK Relationship

Zero Trust helps prevent and contain ATT&CK techniques by:

| ATT&CK Behavior | Zero Trust Control |
|----------------|-------------------|
| Stolen Credentials | MFA + Conditional Access |
| Lateral Movement | Segmentation |
| Privilege Escalation | PAM + JIT Access |
| Data Exfiltration | DLP + Logging |
| Trusted Relationship Abuse | Scoped Federation |
| Persistent Sessions | Continuous Verification |

---

# SOC Use Cases

This mapping can support:

- SIEM detection rules
- Wazuh alert tuning
- Splunk use cases
- Incident response playbooks
- Purple team exercises
- Executive risk reporting

---

# Summary

MITRE ATT&CK converts generic threats into measurable attacker behaviors.

For this NGO Zero Trust project, it enables:

- stronger detections
- clearer threat communication
- better monitoring priorities
- more mature incident response
- real-world adversary alignment

This turns the architecture from static design into an operational defense model.