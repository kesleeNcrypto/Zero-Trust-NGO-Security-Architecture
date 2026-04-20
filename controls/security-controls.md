# Security Controls — Zero Trust NGO Architecture

## Overview

This document defines the security controls required to implement the Zero Trust architecture for a multi-country NGO operating in high-risk environments.

Controls are mapped to:

- Zero Trust pillars
- Identified threat scenarios
- Practical implementation requirements

The goal is to translate architecture into **enforceable, operational controls**.

---

# Control Design Principles

- All access must be explicitly verified  
- Controls must be enforceable, not advisory  
- Security must function in low-connectivity environments  
- Controls must account for human behavior and operational pressure  
- High-risk scenarios take priority over convenience  

---

# 1. Identity Controls

## Objectives
- Prevent credential compromise
- Eliminate unauthorized access
- Secure privileged operations

## Controls

### Authentication

- Enforce Multi-Factor Authentication (MFA) for all users  
- Use phishing-resistant MFA (FIDO2) for privileged accounts  
- Disable SMS-based MFA  
- Enforce SSO across all applications  

---

### Access Control

- Implement Role-Based Access Control (RBAC)  
- Enforce least privilege access  
- Conduct quarterly access reviews  
- Automatically remove dormant accounts (>90 days)  

---

### Conditional Access

- Block login attempts from high-risk geographies  
- Require step-up authentication for sensitive applications  
- Detect impossible travel patterns  
- Restrict access based on session risk score  

---

### Privileged Access Management (PAM)

- No standing admin privileges  
- Enforce Just-In-Time (JIT) access  
- Record all privileged sessions  
- Use separate admin accounts  

---

# 2. Device Controls

## Objectives
- Prevent compromised devices from accessing systems
- Protect data in case of physical device loss

## Controls

### Device Trust Model

| Tier | Device Type | Access |
|------|------------|--------|
| Tier 1 | Fully managed | Full access |
| Tier 2 | BYOD (managed apps) | Limited access |
| Tier 3 | Unmanaged | Browser-only |
| Tier 0 | Non-compliant | Blocked |

---

### Device Security

- Enforce full-disk encryption on all managed devices  
- Require device registration (MDM enrollment)  
- Enforce OS version compliance  
- Require screen lock (≤5 minutes)  

---

### Endpoint Protection

- Deploy EDR (Defender / CrowdStrike)  
- Require active agent check-in (<4 hours)  
- Block devices with unresolved threats  

---

### Remote Wipe

- Enable remote wipe for all managed devices  
- Allow wipe without user confirmation (high-risk cases)  
- Configure automatic wipe after failed login attempts  

---

### High-Risk Device Controls

- Activate travel mode for field staff  
- Minimize data stored locally  
- Require integrity check after travel  
- Disable biometric unlock in high-risk regions  

---

# 3. Network Controls

## Objectives
- Eliminate implicit network trust
- Secure all communication channels

## Controls

### Zero Trust Network Access (ZTNA)

- Replace VPN with ZTNA  
- Enforce per-application access  
- Deny network-level access  

---

### Traffic Security

- Enforce TLS encryption for all traffic  
- Implement mutual TLS for sensitive services  
- Use DNS-over-HTTPS  

---

### Network Monitoring

- Log all network activity  
- Detect unusual traffic patterns  
- Monitor east-west traffic  

---

### Geo-Risk Controls

- Apply risk scoring to connection locations  
- Restrict access from high-risk regions  
- Trigger alerts for abnormal access patterns  

---

# 4. Application Controls

## Objectives
- Prevent unauthorized application access
- Reduce application-level attack surface

## Controls

- Enforce identity-aware access to all applications  
- Require authentication per session  
- Apply role-based access restrictions  
- Isolate sensitive applications  
- Route all admin access through secure bastion  

---

# 5. Data Controls

## Objectives
- Protect sensitive NGO data
- Prevent unauthorized data exposure

## Controls

### Data Classification

| Level | Protection |
|------|------------|
| RESTRICTED | Strict access + encryption |
| CONFIDENTIAL | Controlled access |
| INTERNAL | Standard controls |
| PUBLIC | No restriction |

---

### Data Protection

- Encrypt data at rest and in transit  
- Enforce data access logging  
- Restrict downloads for sensitive data  
- Implement Data Loss Prevention (DLP)  

---

### Data Minimization

- Limit data stored on field devices  
- Remove unnecessary sensitive data  
- Enforce short-lived access tokens  

---

# 6. Cloud Security Controls

## Objectives
- Secure cloud infrastructure
- Prevent misconfiguration and abuse

## Controls

- Enforce SSO for all cloud access  
- Disable long-term access keys  
- Enable CloudTrail / audit logging  
- Deploy threat detection (GuardDuty / SCC)  
- Implement CSPM monitoring  
- Enforce secure configuration baselines  

---

# 7. Monitoring & Detection Controls

## Objectives
- Detect threats early
- Enable rapid response

## Controls

- Centralize logs in SIEM (Wazuh / Splunk / Sentinel)  
- Collect identity, endpoint, cloud, and network logs  
- Detect anomalies and suspicious behavior  
- Correlate alerts across systems  

---

# 8. Incident Response Controls

## Objectives
- Contain incidents quickly
- Minimize impact

## Controls

- Maintain incident response playbooks  
- Enable immediate account lock capability  
- Support remote device wipe  
- Preserve logs for investigation  
- Define escalation procedures  

---

# 9. Security Automation Controls

## Objectives
- Reduce manual workload
- Improve response speed

## Controls

- Automate identity posture checks  
- Automate alert triage (SIEM → n8n)  
- Automate access reviews  
- Automate cloud threat detection  
- Automate travel mode activation  

---

# 10. High-Risk Environment Controls

## Objectives
- Protect staff and data in hostile environments

## Controls

- Enable travel mode before entering high-risk areas  
- Enforce device hardening before deployment  
- Use encrypted communication channels  
- Apply geo-based access restrictions  
- Enable emergency remote wipe procedures  

---

# Control Coverage Summary

| Threat | Control |
|------|---------|
| Phishing | MFA + Conditional Access |
| Device Theft | Encryption + Remote Wipe |
| Insider Threat | Least Privilege + Monitoring |
| Admin Abuse | PAM + Session Logging |
| Network Attack | TLS + ZTNA |
| Cloud Misconfig | CSPM + Logging |

---

# Summary

These controls operationalize the Zero Trust architecture.

They ensure that:

- access is continuously verified  
- risk is minimized at every layer  
- sensitive data is protected  
- threats are detected and contained early  

The controls are designed specifically for NGO environments where traditional security assumptions do not hold.
