# Botium Toys: Internal IT Audit & Risk Assessment Report

## 1. Project Overview

**Company Profile:**  
Botium Toys is a U.S.-based retailer with a single physical location (storefront/warehouse) and a rapidly growing international online presence.

**Objective:** Conduct an internal IT audit to establish a security baseline, ensure compliance with global regulations (GDPR, PCI DSS), and align with the NIST Cybersecurity Framework (NIST CSF).

## 2. Scope & Goals

- **Scope:** All internal IT infrastructure, physical security of the storefront/warehouse, and data processing systems for online payments.
- **Goals:**
  - Identify vulnerabilities in current data handling.
  - Assess compliance with PCI DSS and GDPR.
  - Provide a risk-based roadmap for infrastructure hardening.

## 3. Internal IT Audit: Controls Checklist

| Control Category | Control Name                  | Implemented (Yes/No) | Priority | Notes |
|------------------|-------------------------------|----------------------|----------|-------|
| Administrative   | Least Privilege Access        | No                   | High     | All employees currently access all data. |
| Administrative   | Disaster Recovery Plans       | No                   | High     | No plan currently exists for business continuity. |
| Administrative   | Password Policies             | No                   | Medium   | Current policies are nominal and weak. |
| Administrative   | Separation of Duties          | N                    | High     | Critical for reducing internal fraud/errors. |
| Technical        | Firewall                      | Yes                  | High     | Rules are defined and traffic is filtered. |
| Technical        | IDS/IPS                       | No                   | High     | No system in place to detect active intrusions. |
| Technical        | Encryption (At Rest/Transit)  | No                   | High     | PII/SPII and credit card data are unencrypted. |
| Technical        | Data Backups                  | No                   | High     | No secondary copies of critical business data. |
| Technical        | Antivirus (AV) Software    | Yes                  | Medium   | Installed and regularly monitored. |
| Physical         | CCTV Surveillance          | Yes                  | Low      | Functioning system covers storefront/warehouse. |
| Physical         | Physical Locks             | Yes                  | Low      | Doors and assets are physically secured. |
| Physical         | Fire Detection/Prevention  | Yes                  | Low      | Alarms and sprinklers are up to date. |

## 4. Compliance Checklist

### PCI DSS (Payment Card Industry Data Security Standard)

| Requirement                          | Status  | Action Needed |
|--------------------------------------|---------|---------------|
| Authorized user access to card data  | Failed  | Implement RBAC (Role-Based Access Control) |
| Secure storage/transmission of data  | Failed  | Implement TLS for transit and AES for storage. |
| Encryption procedures                | Failed  | Encrypt all primary account numbers (PAN). |
| Secure password management           | Failed  | Enforce complexity and rotation requirements. |

### GDPR (General Data Protection Regulation)

| Requirement                        | Status  | Action Needed |
|------------------------------------|---------|---------------|
| Privacy of E.U. customer data      | Failed  | Access controls and encryption required. |
| 72-hour breach notification plan   | Passed  | Plan is currently documented and ready. |
| Data classification and inventory  | Failed  | Create an asset/data inventory log. |
| Enforcement of privacy policies    | Passed  | Policies exist (though technical controls lag). |

## 5. Risk Analysis Summary

**Current Risk Score: 8/10 (Critical)**

The primary risks identified during this audit involve the **confidentiality** and **availability** of data. While Botium Toys has strong physical security and basic perimeter defenses (Firewall/AV), the “soft interior” of the network poses significant threats:

- **Financial Risk:** Failure to comply with PCI DSS and GDPR could result in massive fines (up to 4% of global turnover) and the loss of the ability to process credit card payments.
- **Operational Risk:** The lack of backups and a Disaster Recovery plan means a single ransomware event or hardware failure could permanently shutter the business.
- **Internal Threat:** The “everyone-has-access” model for data increases the risk of both accidental data loss and intentional insider threats.

## 6. Recommendations & Roadmap (NIST CSF Alignment)

1. **Identify (High Priority):** Complete a full asset inventory to categorize PII, SPII, and financial data.
2. **Protect (Immediate Action):** Enable Encryption for all customer data at rest.
   - Establish a Back-up policy.
3. **Detect (Mid-Term):** Deploy an Intrusion Detection System (IDS) to monitor the growing global traffic.
4. **Recover (Long-Term):** Develop and test a formal Disaster Recovery and Business Continuity Plan.

---
