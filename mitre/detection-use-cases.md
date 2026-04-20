# Detection Use Cases — MITRE ATT&CK / Zero Trust NGO Architecture

## Overview

This document defines high-value security detection use cases for a multi-country NGO operating in high-risk environments.

The use cases are based on:

- MITRE ATT&CK adversary behaviors
- Zero Trust security controls
- NGO threat scenarios
- Cloud-first operations
- Remote workforce risks

The objective is to convert architecture and threat modeling into actionable monitoring logic for a SOC or security operations team.

---

# Detection Strategy

The organization should prioritize detections that identify:

- credential compromise
- suspicious access behavior
- privileged misuse
- data exfiltration
- cloud abuse
- endpoint compromise
- trusted partner misuse

---

# Log Sources Required

| Source | Purpose |
|-------|---------|
| Identity Provider Logs | Login activity, MFA, risky sign-ins |
| Endpoint Telemetry | Malware, device posture, process execution |
| Cloud Audit Logs | IAM changes, admin actions, storage events |
| Email Security Logs | Phishing and malicious attachments |
| Network Logs | Connections, DNS, anomalies |
| SIEM Correlation | Cross-source detections |
| MDM Logs | Device compliance, wipe events |

---

# Priority Detection Use Cases

## 1. Impossible Travel Login

### Threat

Stolen credentials used from distant geographies in short time.

### MITRE Mapping

- Valid Accounts (T1078)

### Detection Logic

- Successful login from Country A
- Second login from Country B within impossible travel timeframe

### Severity

High

### Response

- force re-authentication
- terminate sessions
- investigate source IP

---

## 2. MFA Fatigue / Repeated Push Attempts

### Threat

Attacker attempts repeated MFA prompts until user accepts.

### MITRE Mapping

- Credential Access
- Valid Accounts (T1078)

### Detection Logic

- Excessive MFA prompts in short time
- eventual success after many denies

### Severity

High

### Response

- lock account temporarily
- reset authentication method
- user outreach

---

## 3. Privileged Role Assignment

### Threat

Unexpected admin rights granted.

### MITRE Mapping

- Account Manipulation (T1098)

### Detection Logic

- New privileged role assigned
- outside change window
- unusual actor performs assignment

### Severity

Critical

### Response

- validate change ticket
- revoke if unauthorized
- review actor activity

---

## 4. Disabled Logging / Security Controls

### Threat

Attacker disables logging to hide activity.

### MITRE Mapping

- Impair Defenses (T1562)

### Detection Logic

- CloudTrail disabled
- EDR agent stopped
- SIEM forwarding interrupted

### Severity

Critical

### Response

- restore logging immediately
- isolate affected host/account
- begin investigation

---

## 5. Suspicious Mass File Download

### Threat

User exporting sensitive data.

### MITRE Mapping

- Data from Information Repositories (T1213)
- Exfiltration Over Web Services (T1567)

### Detection Logic

- abnormal file download volume
- sensitive repository access spike
- downloads outside normal hours

### Severity

High

### Response

- suspend download session
- review user intent
- inspect affected data

---

## 6. Partner Federation Abuse

### Threat

Compromised partner tenant used for access.

### MITRE Mapping

- Trusted Relationship (T1199)

### Detection Logic

- partner account accesses new systems
- unusual country / IP for partner login
- excessive failed access attempts

### Severity

High

### Response

- restrict federation trust
- contact partner security team
- review scope of access

---

## 7. BYOD Non-Compliant Device Access Attempt

### Threat

Untrusted device attempting access.

### MITRE Mapping

- Initial Access Support Activity

### Detection Logic

- device fails posture check
- rooted / jailbroken
- outdated OS
- unmanaged device requests sensitive app access

### Severity

Medium / High

### Response

- block access
- notify user
- require remediation

---

## 8. Cloud Storage Public Exposure

### Threat

Misconfigured storage bucket or file share.

### MITRE Mapping

- Data from Cloud Storage (T1530)

### Detection Logic

- storage policy changed to public
- anonymous access enabled
- external share created for restricted data

### Severity

Critical

### Response

- auto-remediate policy
- notify owner
- review access logs

---

## 9. Dormant Account Reactivation

### Threat

Unused account activated for malicious use.

### MITRE Mapping

- Valid Accounts (T1078)

### Detection Logic

- login to account inactive >90 days
- immediate privileged actions
- unusual geo-location

### Severity

High

### Response

- suspend account
- validate owner identity
- investigate session history

---

## 10. Multiple Failed Logins Against Executive Account

### Threat

Password spray / brute force attempt.

### MITRE Mapping

- Password Spraying (T1110.003)

### Detection Logic

- repeated failures
- multiple IPs
- targeting privileged or executive accounts

### Severity

High

### Response

- temporary lockout
- enforce password reset
- IP blocking / rate limiting

---

# SIEM Correlation Examples

## Correlation 1

Impossible Travel + MFA Success + New Device

**Result:** Possible account takeover

---

## Correlation 2

Admin Role Granted + Logging Disabled

**Result:** Possible active compromise

---

## Correlation 3

Mass Downloads + External Sharing Enabled

**Result:** Possible insider exfiltration

---

# Alert Severity Model

| Severity | Meaning |
|---------|--------|
| Critical | Immediate containment required |
| High | High confidence threat activity |
| Medium | Suspicious requires analyst review |
| Low | Informational / baseline anomaly |

---

# Response Workflow

1. Detect event  
2. Enrich with user/device/context data  
3. Assign severity  
4. Trigger containment if needed  
5. Open incident case  
6. Investigate timeline  
7. Recover and document lessons learned  

---

# Automation Opportunities (n8n / SOAR)

- auto-disable risky accounts
- notify security Slack / Teams
- enrich IP with geo data
- create Jira incident ticket
- send executive alert for critical incidents
- trigger remote wipe workflow
- launch user verification workflow

---

# Metrics to Track

| Metric | Target |
|-------|--------|
| Mean Time to Detect | <30 mins |
| Mean Time to Respond | <2 hrs critical |
| False Positive Rate | Continually reduced |
| MFA Attack Blocks | 100% monitored |
| Logging Coverage | 100% critical systems |

---

# Summary

These detection use cases transform Zero Trust architecture into active defense.

They help the NGO:

- identify compromise early
- contain incidents quickly
- protect sensitive data
- detect abuse of trust
- operationalize MITRE ATT&CK intelligence

This is the bridge between architecture and real SOC operations.