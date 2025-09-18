# Risk Assessment Report — SePurity, Inc.

**Date:** September 17th, 2025 
**Prepared by:** Justin Min  

---

## Executive Summary  

SePurity, Inc. is a cybersecurity SaaS company that provides small and mid-sized businesses with compliance and risk management tools. To deliver its product, SePurity relies on three vendors: AWS, Salesforce, and Dropbox. Each vendor plays a different role, from hosting the platform itself to managing customer data and supporting internal collaboration.  

This assessment reviews the risks tied to each vendor. I considered the type of data they handle, their importance to SePurity’s daily operations, and the potential regulatory impact. After evaluating vendor controls, I assigned residual risk levels and created remediation actions along with monitoring steps to ensure risks stay manageable.  

---

## Company Profile  

- **Name:** SePurity, Inc.  
- **Headquarters:** Atlanta, Georgia  
- **Founded:** 2025  
- **Employees:** 250 total, with a main presence in the US, a remote team in Canada, and a small support group in the UK  
- **Mission:** Provide simple, effective, and affordable cloud-based security solutions that help businesses protect data, stay compliant, and lower cyber risk  

**Core Product: SePurity Security Suite**  
- Automated vulnerability scanning for web apps and systems  
- Security awareness training for employees  
- Compliance dashboards that track frameworks like SOC 2, ISO 27001, GDPR, and CCPA  
- Vendor risk tracking module  

---

## Vendors in Scope  

- **AWS (Critical Tier):** Hosts the SePurity platform and stores sensitive customer data, including vulnerability scan results. A failure here would bring the product offline.  
- **Salesforce (High Tier):** Used for CRM. Manages customer contact information, deal history, and support records. Important for sales and service but not tied to uptime of the SePurity platform.  
- **Dropbox (Low Tier):** Used for internal file sharing. Stores non-sensitive documents such as templates, training material, and marketing content.  

---

## Inherent Risk Scoring  

Each vendor was scored from 1 to 4 in the following categories: data sensitivity, data volume, criticality to operations, system integration, and regulatory impact.  

- **AWS:** 20 (Critical)  
- **Salesforce:** 14 (High)  
- **Dropbox:** 6 (Low)  

---

## Control Evaluation and Residual Risk  

Controls were evaluated across governance, encryption, access, monitoring, continuity, and oversight.  

- **AWS:** Strong compliance certifications and encryption practices. Shared responsibility creates monitoring gaps. Residual Risk: **Moderate**  
- **Salesforce:** Solid protections around compliance and access. Gaps remain in monitoring and subprocessor transparency. Residual Risk: **Medium**  
- **Dropbox:** Acceptable for internal docs. Weak monitoring and short log retention, but the data stored is low sensitivity. Residual Risk: **Low**  

---

## Risk Register (Sample)  

| Risk ID | Vendor     | Risk Description                                   | Inherent Risk | Controls in Place              | Residual Risk | Treatment Plan |
|---------|------------|----------------------------------------------------|---------------|--------------------------------|---------------|----------------|
| VR-001  | AWS        | Misconfigured S3 bucket could expose scan results  | Critical (20) | S3 encryption, IAM with MFA    | Moderate      | Mitigate       |
| VR-004  | Salesforce | Excessive access granted to temporary staff        | High (14)     | RBAC, MFA, SSO                 | Medium        | Mitigate       |
| VR-007  | Dropbox    | Accidental oversharing of internal documents       | Low (6)       | MFA, admin controls, SSO       | Low           | Accept         |

---

## Remediation Plan (Highlights)  

- **AWS:** Run quarterly audits of S3 permissions, enforce MFA for all IAM users, and test disaster recovery plans.  
- **Salesforce:** Review roles quarterly, restrict CSV exports to admins, and set up DLP alerts.  
- **Dropbox:** Enforce business-only sync policies, document retention limits, and formally accept the low sensitivity exposure.  

---

## Monitoring SOP  

To make sure risks stay under control, SePurity will:  
- Review the Risk Register every quarter  
- Track remediation progress quarterly  
- Collect updated SOC 2, ISO 27001, and FedRAMP certifications annually  
- Review vendor subprocessors each year  
- Subscribe to vendor Trust Centers and monitor news sources for security incidents  

---

## Conclusion  

The assessment shows that AWS carries the highest risk because the entire platform runs on it. Even with strong controls, some monitoring responsibility remains on SePurity, which means risks stay moderate. Salesforce presents medium risk, mainly tied to access management and integrations. Dropbox remains low risk since it only handles internal documents.  

By following the remediation plan and maintaining the monitoring process, SePurity can keep vendor risks at acceptable levels while continuing to provide secure services to its customers.  
