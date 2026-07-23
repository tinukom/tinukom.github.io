# Portfolio Project: ISO/IEC 27001:2022 Internal Audit Checklist & Gap Analysis
**Author:** Racheal Atinuke Adesoba, ISO 27001 Lead Auditor (Mastermind)
**Frameworks Used:** ISO/IEC 27001:2022 (ISMS Requirements), ISO/IEC 27002:2022 (Security Controls)
**Target Environment:** Corporate Web Infrastructure & Remote Cloud Working Environments

---

## 1. Objective & Audit Scope
This internal audit framework is designed to assess the compliance posture of enterprise operations against the revised ISO/IEC 27001:2022 Information Security Management System (ISMS) standard. 

### Audit Scope
*   **Organizational Units:** IT Security Operations, Infrastructure Management, and Remote Workforce Operations.
*   **Control Domain Focus:** Clause 5 (Organizational Controls), Clause 7 (Physical Controls), and Clause 8 (Technological Controls).

---

## 2. ISO/IEC 27001:2022 Audit & Evidence Checklist

### 📂 Domain A.5: Organizational Controls

| ISO 27001 Control | Control Objective | Compliance Status (Pass/Fail) | Observed Evidence / Audit Notes | Required Corrective Actions |
| :--- | :--- | :---: | :--- | :--- |
| **A.5.15** Access Control | Ensure only authenticated users access corporate network assets. | **PASS** | Validated centralized IAM identity directory config. Multi-factor authentication (MFA) successfully mapped across 100% of tested user profiles. | Maintain monthly credential audits to detect orphan or dormant accounts. |
| **A.5.16** Identity Management | Manage lifecycle of identities to ensure authoritative authentication. | **PASS** | Reviewed onboarding and offboarding workflows. System logs show automatic identity revocation within 24 hours of exit. | None required. |

### 📂 Domain A.8: Technological Controls

| ISO 27001 Control | Control Objective | Compliance Status (Pass/Fail) | Observed Evidence / Audit Notes | Required Corrective Actions |
| :--- | :--- | :---: | :--- | :--- |
| **A.8.8** Management of Technical Vulnerabilities | Prevent exploitation of technical software vulnerabilities. | **FAIL** | Infrastructure vulnerability report from Splunk SIEM showed 3 high-severity unpatched CVE entries on web application servers. | Establish an automated patch cycle program to deploy critical security fixes within 14 days of release. |
| **A.8.20** Network Security | Secure networks and associated network devices from exposure. | **PASS** | Inspected web traffic certificates. Verified enterprise systems enforce TLS 1.3 protocol and modern HTTPS encryption parameters. | Implement continuous expiry monitors for active TLS/SSL domain certificates. |

---

## 3. Executive Gap Analysis Summary
1. **Strong Identity Isolation:** The organization exhibits a highly reliable access control architecture, successfully enforcing single sign-on (SSO) and strict IAM protocols across remote teams.
2. **Patch Remediation Lag:** The primary operational risk stems from a failure to strictly meet patch timelines for core public-facing web infrastructure, exposing the business to potential exploit vectors.
3. **Auditor Action Items:** Remediation activities have been scheduled via automated ServiceNow GRC compliance tracking workflows. A secondary follow-up audit will be conducted to confirm the closure of vulnerability gaps.
