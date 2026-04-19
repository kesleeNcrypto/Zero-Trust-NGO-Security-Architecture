# Designing a Zero Trust Security Architecture for a Multi-Country NGO Operating in High-Risk Environments

## Overview

This project presents a Zero Trust security architecture designed for a donor-funded NGO operating across multiple countries in high-risk environments. The organization supports remote staff, field operations, cloud collaboration, third-party consultants, and sensitive donor / beneficiary data.

Traditional perimeter-based security models are no longer sufficient for modern distributed organizations. This project applies a Zero Trust model based on the principle:

> Never Trust. Always Verify.

The objective is to reduce risk, improve resilience, strengthen governance, and secure access across users, devices, applications, and data.

---

## Project Scenario

The NGO operates across three countries with:

- Headquarters staff
- Country offices
- Field officers in remote areas
- Finance and HR teams
- Third-party consultants
- Cloud-hosted productivity tools
- Legacy internal systems

### Operational Constraints

- Weak or inconsistent connectivity
- Shared or unmanaged devices
- High phishing exposure
- Insider risk
- Urgent operational access needs
- Donor compliance expectations

---

## Security Objectives

- Protect donor and beneficiary data
- Secure remote and hybrid workforce access
- Enforce least privilege
- Prevent lateral movement
- Improve visibility and monitoring
- Strengthen incident response readiness
- Increase donor confidence and audit readiness

---

# Zero Trust Core Principles

This architecture is built around the following principles:

1. Never trust by default  
2. Verify every user and device  
3. Grant least-privilege access  
4. Use continuous monitoring  
5. Assume breach scenarios  
6. Limit blast radius through segmentation  
7. Protect data wherever it resides

---

# Architecture Layers

## 1. Identity Layer

Identity becomes the primary security perimeter.

Controls:

- Single Sign-On (SSO)
- Multi-Factor Authentication (MFA)
- Role-Based Access Control (RBAC)
- Conditional Access Policies
- Privileged Access Management (PAM)

---

## 2. Device Trust Layer

Only trusted or compliant devices receive appropriate access.

Controls:

- Device registration
- Endpoint posture checks
- Patch compliance validation
- Disk encryption checks
- Restricted unmanaged device access

---

## 3. Access Control Layer

Access is granted per application, not broad network trust.

Controls:

- Secure access gateway
- Risk-based session decisions
- Re-authentication for sensitive systems
- Temporary privileged access
- Time-bound consultant access

---

## 4. Network Segmentation Layer

Limits attacker movement and reduces internal exposure.

Controls:

- Finance network separation
- HR system isolation
- Admin zone segregation
- East-West traffic restrictions
- Microsegmentation policies

---

## 5. Data Protection Layer

Protects sensitive information at all times.

Controls:

- Encryption at rest
- Encryption in transit
- Data classification
- Controlled downloads
- Secure backups
- Access logging

---

## 6. Monitoring & Detection Layer

Visibility is essential to Zero Trust.

Controls:

- Centralized SIEM logging
- Identity telemetry
- Endpoint telemetry
- Cloud audit logs
- Alert triage workflows
- Incident response playbooks

---

# High-Level Architecture Flow

```text
Users
 ↓
Devices
 ↓
Device Validation
 ↓
Identity Provider (SSO / MFA / RBAC)
 ↓
Policy Engine / Secure Gateway
 ↓
Applications & Data
 ↓
Central Logging / SIEM
 ↓
SOC / Incident Response
