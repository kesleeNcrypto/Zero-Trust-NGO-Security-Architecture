# Threat Model — Multi-Country NGO Zero Trust Architecture

## Overview

This document defines the threat model for a multi-country NGO operating in high-risk, conflict-affected, and digitally hostile environments.

Unlike traditional enterprise environments, NGOs face:

- nation-state surveillance
- device seizure at borders
- untrusted network infrastructure
- insider and coercion risks
- operational pressure in the field

This threat model informs all Zero Trust architecture decisions.

---

# Threat Modeling Objectives

- Identify high-risk adversaries
- Define critical assets (crown jewels)
- Map realistic attack scenarios
- Prioritize risks based on likelihood and impact
- Align controls with real-world threats

---

# Crown Jewels (Critical Assets)

## 1. Beneficiary Data
- personal identifiable information (PII)
- case records
- health or protection data

## 2. Donor & Financial Data
- funding records
- financial systems
- payroll and vendor payments

## 3. Identity Systems
- SSO accounts
- admin credentials
- service accounts

## 4. Strategic Communications
- internal reports
- program strategy
- sensitive communications

---

# Threat Actor Profiles

## Nation-State (Host Country)
**Capability:** High  
**Targets:**
- field staff devices
- communications metadata
- beneficiary data

---

## Nation-State (Foreign)
**Capability:** High  
**Targets:**
- HQ systems
- donor information
- program intelligence

---

## Cybercriminals
**Capability:** Medium  
**Targets:**
- cloud storage
- email systems
- financial platforms

---

## Insider Threat
**Capability:** Low–Medium  
**Targets:**
- beneficiary databases
- internal systems
- sensitive reports

---

## Physical Adversary
**Capability:** Low-tech  
**Targets:**
- field devices
- laptops and mobile phones

---

## Network-Level Adversary (MITM)
**Capability:** Medium  
**Targets:**
- unencrypted traffic
- login credentials
- DNS queries

---

# High-Risk Environment Definition

A high-risk environment includes:

- state surveillance is active or mandated  
- NGO staff face device seizure or detention  
- ISP infrastructure is monitored or controlled  
- physical security of devices cannot be guaranteed  
- data localization laws conflict with security  

---

# Key Threat Scenarios

## 1. Device Seizure at Border

**Scenario:**  
Field device is seized and data extracted.

**Impact:**  
- exposure of beneficiary data  
- operational compromise  

**Controls:**  
- full-disk encryption  
- remote wipe capability  
- data minimization  
- travel mode activation  

---

## 2. Phishing-Based Credential Compromise

**Scenario:**  
User credentials captured via phishing attack.

**Impact:**  
- account takeover  
- lateral movement  
- data exfiltration  

**Controls:**  
- phishing-resistant MFA (FIDO2)  
- conditional access policies  
- anomaly detection  

---

## 3. State-Level Man-in-the-Middle Attack

**Scenario:**  
Traffic intercepted at ISP level.

**Impact:**  
- credential theft  
- surveillance  
- session hijacking  

**Controls:**  
- mutual TLS  
- DNS-over-HTTPS  
- ZTNA encrypted tunnels  

---

## 4. Privileged Account Compromise

**Scenario:**  
Admin credentials compromised via social engineering.

**Impact:**  
- full system control  
- persistence  
- security bypass  

**Controls:**  
- PAM (Privileged Access Management)  
- Just-In-Time (JIT) access  
- session recording  
- no standing privileges  

---

## 5. Malware on BYOD Device

**Scenario:**  
Compromised personal device used to access systems.

**Impact:**  
- credential theft  
- data exposure  

**Controls:**  
- device posture checks  
- EDR monitoring  
- restricted BYOD access  
- VDI for sensitive systems  

---

## 6. Insider Data Exfiltration

**Scenario:**  
Authorized user exports sensitive data.

**Impact:**  
- PII leakage  
- donor trust loss  

**Controls:**  
- least privilege access  
- data classification  
- DLP enforcement  
- session monitoring  
- behavioral analytics  

---

## 7. Partner Lateral Movement

**Scenario:**  
Compromised partner organization gains access.

**Impact:**  
- internal system exposure  
- trust boundary breach  

**Controls:**  
- separate identity federation  
- microsegmentation  
- scoped access permissions  

---

## 8. Cloud Misconfiguration

**Scenario:**  
Cloud storage exposed due to misconfiguration.

**Impact:**  
- public data exposure  
- compliance violation  

**Controls:**  
- CSPM monitoring  
- automated remediation  
- secure baseline policies  

---

# Risk Table

| Threat Scenario | Likelihood | Impact | Risk Level | Primary Control |
|----------------|-----------|--------|-----------|----------------|
| Device Seizure | High | High | Critical | Encryption + Remote Wipe |
| Phishing | High | High | Critical | MFA + Conditional Access |
| MITM Attack | Medium | High | Critical | mTLS + ZTNA |
| Admin Compromise | Medium | Critical | Critical | PAM + JIT Access |
| BYOD Malware | Medium | High | High | Posture + EDR |
| Insider Threat | Medium | High | High | DLP + Monitoring |
| Partner Risk | Medium | Medium | Medium | Segmentation |
| Misconfiguration | Medium | High | Medium | CSPM |

---

# Threat Modeling Assumptions

- devices may be physically compromised  
- users may be coerced or socially engineered  
- networks are untrusted by default  
- attackers may already be inside the environment  
- detection may be delayed  

---

# Security Priorities

## Priority 1
Protect identity and administrative access

## Priority 2
Protect beneficiary and donor data

## Priority 3
Reduce device-based risk in field operations

## Priority 4
Improve visibility and detection capabilities

## Priority 5
Limit blast radius through segmentation

---

# Summary

This threat model reflects the realities of NGO operations in hostile environments.

It moves beyond traditional enterprise assumptions and ensures that:

- controls are threat-driven  
- architecture decisions are risk-informed  
- Zero Trust is applied to real-world conditions  

This model directly informs the Zero Trust architecture and security control design.
