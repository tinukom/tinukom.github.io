# Portfolio Project: Enterprise NIST SP 800-30 Rev. 1 Risk Assessment Report
**Author:** Racheal Atinuke Adesoba, CGRC (Candidate)
**Frameworks Used:** NIST SP 800-30 Rev 1, NIST SP 800-53 Rev 5, NIST CSF 2.0
**Target Environment:** Cloud-Hosted Web Infrastructure & Remote Working Systems

---

## 1. Executive Summary
This assessment identifies, analyzes, and evaluates information security risks to the enterprise web infrastructure and remote workforce data systems. The objective is to align organizational controls with NIST SP 800-53 Rev. 5 baselines to mitigate operational vulnerabilities and ensure compliance with PIPEDA/GDPR requirements.

---

## 2. Assessment Methodology & Scope
Following the **NIST SP 800-30 Rev. 1** standard, this assessment implements a four-step risk management process:
1. **Prepare for Assessment:** Define scope, assumptions, and threat sources.
2. **Conduct Assessment:** Identify vulnerabilities, predisposing conditions, and likelihood.
3. **Communicate Results:** Document risk findings for executive stakeholder review.
4. **Maintain Assessment:** Establish continuous monitoring protocols.

### System Boundary & Scope
*   **Assets:** Corporate Web Infrastructure, Customer-Facing Web Applications, Remote Endpoint Infrastructure (Microsoft 365, AWS Cloud Environment).
*   **Data Types:** Personally Identifiable Information (PII), Authentication Credentials, Transaction Logs.

---

## 3. Risk Assessment Matrix (NIST SP 800-30 Scale)

| Threat Source / Event | Vulnerability / Predisposing Condition | Likelihood (1-5) | Impact (1-5) | Risk Score (L x I) | NIST SP 800-53 Control Mapping |
| :--- | :--- | :---: | :---: | :---: | :--- |
| **TE-01: Credential Stuffing / Phishing** | Absence of enforced Multi-Factor Authentication (MFA) on remote endpoints. | 5 (High) | 4 (High) | **20 (Critical)** | AC-2, IA-2, IA-8 |
| **TE-02: Ransomware / Malware Injection** | Outdated patch levels on cloud web servers hosting customer apps. | 4 (Mod) | 5 (High) | **20 (Critical)** | SI-2, SI-3, CM-3 |
| **TE-03: Data Exfiltration via Insider** | Broad, unrestricted database read/write access permissions across IT teams. | 3 (Mod) | 4 (High) | **12 (Medium)** | AC-3, AC-6 (Least Privilege) |
| **TE-04: API Layer Interception (Man-in-the-Middle)** | Misconfigured TLS/SSL protocols or expired web infrastructure certificates. | 3 (Mod) | 3 (Mod) | **9 (Low)** | SC-8, SC-13, IA-5 |

---

## 4. Detailed Finding & Remediation Plan

### 🚨 Finding Reference: TE-01 (Critical Risk)
*   **Threat Description:** Malicious actors exploit weak password policies via automated credential stuffing to gain unauthorized access to remote administrative environments.
*   **Vulnerability:** Core remote endpoint systems lack mandatory multi-factor authentication (MFA).
*   **NIST SP 800-53 Rev 5 Alignment:** 
    *   **IA-2 (Identification and Authentication):** Requires organizational systems to uniquely identify and authenticate users.
    *   **AC-2 (Account Management):** Mandates account monitoring and restrictive access privileges.
*   **Recommended Mitigation Actions:**
    1. Implement mandatory Phishing-Resistant MFA (e.g., FIDO2 keys or authenticator apps) across 100% of corporate identity profiles.
    2. Deploy automated conditional access policies inside Azure AD/M365 Compliance Center to flag and block anomalous login geographic locations.
*   **Residual Risk Post-Mitigation:** **Low (Score: 4)** — Enforcing MFA reduces likelihood from 5 to 1.

---

## 5. Continuous Monitoring Strategy (NIST CSF Alignment)
To maintain compliance and risk awareness, the following continuous monitoring guardrails are configured:
*   **Detect (DE.CM):** Splunk SIEM dashboards configured to alert on consecutive failed authentication tokens exceeding 5 attempts within 2 minutes.
*   **Respond (RS.RP):** ServiceNow GRC automated ticketing workflows triggered natively upon any high-severity vulnerability flag detected during automated monthly infrastructure scans.
