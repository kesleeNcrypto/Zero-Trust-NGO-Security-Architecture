# Compliance Framework Mapping — Zero Trust NGO Architecture

## Overview

This document maps the Zero Trust security architecture controls for a multi-country NGO to recognized cybersecurity and governance frameworks.

The purpose is to demonstrate that security controls are:

- risk-based  
- measurable  
- aligned to accepted standards  
- suitable for audits, donors, and governance reviews  

This project primarily aligns with:

- NIST Cybersecurity Framework (CSF)
- NIST SP 800-207 Zero Trust Architecture
- ISO/IEC 27001
- CIS Controls v8
- Data protection principles (GDPR-style handling)

---

# Framework Relevance

## NIST Cybersecurity Framework

Used to organize security controls into five functions:

- Identify
- Protect
- Detect
- Respond
- Recover

---

## NIST SP 800-207

Primary reference for Zero Trust Architecture:

- identity-centric access
- continuous verification
- policy decision engine
- least privilege
- no implicit trust

---

## ISO/IEC 27001

Supports governance maturity through:

- access control
- asset management
- incident management
- supplier security
- continuous improvement

---

## CIS Controls v8

Operational best practices for:

- account management
- vulnerability management
- logging
- malware defenses
- data protection

---

## Data Protection Principles

Applied to beneficiary and donor data through:

- minimization
- lawful access
- encryption
- accountability
- retention control

---

# Primary Control Mapping

| Security Control | NIST CSF | NIST 800-207 | ISO 27001 | CIS v8 |
|------------------|----------|-------------|-----------|--------|
| Multi-Factor Authentication | PR.AC | Identity Verification | Access Control | Account Management |
| Single Sign-On (SSO) | PR.AC | Centralized Identity | Access Control | Account Management |
| Least Privilege RBAC | PR.AC | Least Privilege | Access Control | Access Control Mgmt |
| Conditional Access | PR.AC | Context-Aware Policy | Access Control | Secure Configuration |
| Privileged Access Management | PR.AC | Admin Session Control | Privileged Access | Account Management |
| Device Compliance Checks | PR.PT | Device Trust | Endpoint Security | Secure Configuration |
| Full-Disk Encryption | PR.DS | Device Assurance | Cryptography | Data Protection |
| Zero Trust Network Access | PR.AC | Policy Enforcement Point | Network Security | Network Controls |
| DNS-over-HTTPS / TLS | PR.DS | Secure Communications | Cryptography | Network Security |
| Centralized Logging / SIEM | DE.CM | Continuous Monitoring | Logging & Monitoring | Audit Logs |
| Behavioral Analytics | DE.AE | Risk Re-evaluation | Monitoring | Security Monitoring |
| Incident Response Playbooks | RS.RP | Breach Assumption | Incident Mgmt | Incident Response |
| Remote Wipe | RS.MI | Device Revocation | Endpoint Control | Data Recovery |
| Backup & Recovery | RC.RP | Resilience | Business Continuity | Recovery Controls |
| CloudTrail / Audit Logs | DE.CM | Cloud Telemetry | Logging | Audit Logging |
| CSPM Monitoring | ID.RA | Continuous Validation | Risk Assessment | Vulnerability Mgmt |

---

# NIST CSF Functional Alignment

## Identify

Controls:

- asset inventory
- user account inventory
- cloud resource visibility
- risk assessments
- data classification

---

## Protect

Controls:

- MFA
- SSO
- least privilege
- encryption
- ZTNA
- device compliance
- PAM

---

## Detect

Controls:

- SIEM monitoring
- cloud logs
- anomaly detection
- endpoint telemetry
- suspicious login alerts

---

## Respond

Controls:

- incident playbooks
- account lock procedures
- remote wipe
- containment workflows
- escalation process

---

## Recover

Controls:

- backup restoration
- system rebuild procedures
- post-incident review
- business continuity plans

---

# ISO 27001 Domain Alignment

| ISO Domain | Example NGO Controls |
|-----------|----------------------|
| Access Control | MFA, RBAC, PAM |
| Asset Management | Device enrollment, inventory |
| Cryptography | Full-disk encryption, TLS |
| Operations Security | Logging, monitoring, patching |
| Supplier Security | Partner federation controls |
| Incident Management | IR procedures, escalation |
| Business Continuity | Backup and recovery |

---

# NGO / Donor Governance Readiness

This architecture supports governance expectations by providing:

- documented controls  
- measurable security posture  
- audit evidence through logs  
- risk-based access decisions  
- data protection controls  
- continuous improvement roadmap  

---

# Data Protection Mapping

## Beneficiary Data

Required protections:

- restricted classification  
- least privilege access  
- encrypted storage  
- monitored downloads  
- retention controls  

---

## Donor Data

Required protections:

- controlled access  
- audit logging  
- secure communications  
- backup integrity  

---

# Maturity Indicators

| Capability | Current Goal |
|-----------|--------------|
| MFA Coverage | 100% |
| Privileged Session Logging | 100% |
| ZTNA Coverage | All critical apps |
| Device Compliance | >95% |
| Mean Time to Detect | <30 mins |
| Mean Time to Respond | <2 hours |

---

# Residual Risks (Accepted with Controls)

| Risk | Mitigation |
|------|-----------|
| Device seizure | Encryption + wipe |
| User coercion | Duress process + scoped access |
| Metadata surveillance | Secure comms + OPSEC |
| Vendor compromise | Layered architecture |
| Offline access needs | Token controls + minimization |

---

# Summary

This framework mapping demonstrates that the Zero Trust NGO architecture is not theoretical.

It is aligned to internationally recognized cybersecurity standards and can support:

- donor assurance reviews  
- internal governance committees  
- compliance assessments  
- security maturity planning  
- regulated operational environments  

The result is a practical, standards-aligned Zero Trust model for distributed NGO operations.
