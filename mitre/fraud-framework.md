# Fraud Threat Framework — NGO Zero Trust Architecture

## Overview

This document applies a fraud-focused threat modeling approach inspired by the MITRE Fight Fraud Framework to a multi-country NGO operating in high-risk environments.

While traditional cybersecurity focuses on system compromise, NGOs face equally critical risks from:

- financial fraud
- identity abuse
- insider collusion
- grant manipulation
- vendor exploitation

This framework complements MITRE ATT&CK by addressing **human-driven and financially motivated threats**.

---

# Why Fraud Modeling Matters for NGOs

NGOs operate with:

- distributed financial operations  
- remote staff and field agents  
- third-party vendors and partners  
- donor-funded programs  
- beneficiary identity systems  

These create opportunities for fraud that may not involve malware or technical exploits.

---

# Core Fraud Categories

## 1. Account Takeover (ATO)

### Scenario

Attacker gains access to NGO user account to:

- redirect payments  
- access financial data  
- impersonate staff  

### Risk

High

### Controls

- MFA enforcement  
- login anomaly detection  
- session monitoring  
- rapid account lock  

---

## 2. Payroll Fraud

### Scenario

Employee or insider manipulates payroll records to:

- inflate salary  
- add ghost employees  
- redirect payments  

### Risk

High

### Controls

- dual approval workflows  
- separation of duties  
- payroll audit logs  
- periodic reconciliation  

---

## 3. Vendor / Procurement Fraud

### Scenario

Fake vendor created or legitimate vendor account compromised.

Used to:

- submit fraudulent invoices  
- redirect payments  

### Risk

High

### Controls

- vendor verification procedures  
- payment validation checks  
- invoice anomaly detection  
- approved vendor registry  

---

## 4. Grant / Fund Diversion

### Scenario

Funds allocated to programs are misused or redirected.

### Risk

High

### Controls

- fund tracking systems  
- approval chains  
- audit trails  
- periodic financial review  

---

## 5. Beneficiary Identity Fraud

### Scenario

Fake or duplicated identities used to:

- claim benefits  
- manipulate program data  

### Risk

Medium / High

### Controls

- identity verification processes  
- duplicate detection systems  
- data validation checks  
- restricted data modification access  

---

## 6. Insider Collusion

### Scenario

Multiple insiders collaborate to bypass controls.

### Risk

High

### Controls

- segregation of duties  
- cross-checking workflows  
- independent audits  
- monitoring of privileged actions  

---

## 7. Expense Reimbursement Fraud

### Scenario

Employees submit false or inflated expenses.

### Risk

Medium

### Controls

- receipt verification  
- expense policy enforcement  
- anomaly detection  
- approval workflows  

---

## 8. Donation / Payment Redirection

### Scenario

Attacker manipulates communication to redirect donor funds.

### Risk

Critical

### Controls

- verified communication channels  
- payment confirmation processes  
- email security controls  
- domain spoofing protection  

---

# Fraud Behavior Indicators

| Indicator | Possible Fraud |
|----------|----------------|
| Unusual payment changes | Vendor fraud |
| Sudden account activity | Account takeover |
| Duplicate beneficiary records | Identity fraud |
| Frequent manual overrides | Insider abuse |
| After-hours financial actions | Unauthorized access |
| Multiple approvals by same user | Control bypass |

---

# Detection Opportunities

Fraud detection relies on:

- behavioral monitoring  
- financial anomaly detection  
- access pattern analysis  
- cross-system correlation  

---

## Example Detection Use Cases

### Suspicious Payment Change

- vendor bank account updated  
- followed by immediate payment  

→ flag as high-risk event  

---

### Duplicate Beneficiary Records

- similar identity data  
- multiple claims  

→ flag for review  

---

### Unusual Expense Patterns

- repeated high-value claims  
- outside normal behavior  

→ trigger audit  

---

# Fraud + Zero Trust Integration

Zero Trust principles help reduce fraud risk:

| Fraud Risk | Zero Trust Control |
|-----------|-------------------|
| Account takeover | MFA + Conditional Access |
| Insider abuse | Least privilege |
| Vendor fraud | Scoped access |
| Data manipulation | Logging + monitoring |
| Payment fraud | Verification workflows |

---

# Governance and Compliance Impact

Fraud controls support:

- donor trust  
- financial accountability  
- audit readiness  
- regulatory compliance  

---

# Risk Management Approach

Fraud risk cannot be eliminated entirely.

Instead:

- reduce likelihood  
- detect early  
- respond quickly  
- document incidents  

---

# Metrics to Track

| Metric | Target |
|-------|--------|
| Fraud detection rate | Increasing over time |
| False positives | Decreasing |
| Time to detect fraud | <24 hours |
| Time to respond | <48 hours |
| Audit findings | Reduced annually |

---

# Summary

This fraud framework extends cybersecurity into **financial and operational risk management**.

For NGO environments, this is critical because:

- not all threats are technical  
- insider and financial abuse are common risks  
- trust-based operations can be exploited  

Combining:

- Zero Trust Architecture  
- MITRE ATT&CK  
- Fraud Modeling  

creates a **holistic security posture** covering both technical and human threats.