# Due Diligence Checklist // SePurity, Inc.

These checklists are designed to evaluate the security and compliance posture of SePurity’s third-party vendors.  
Through these checklists, the goal is to verify whether vendors have the means necessary (controls, certifications, etc.) to manage risks identified during the previous *Inherent Risk Questionnaire* step.  

The *Master Checklist* is one that pertains to all vendors and acts as a baseline, while the *Vendor-Specefic Due Diligence Questionnaires* are tailored to each vendor.
---

## Master Checklist

### 1. General Information
- [ ] Vendor provides company HQ, ownership structure, and number of employees  
- [ ] Vendor provides dedicated security or compliance contact  

### 2. Governance & Compliance
- [ ] Vendor maintains at least one major certification (SOC 2 Type II, ISO 27001, etc.)  
- [ ] Vendor conducts regular risk assessments (annually or more frequent)  
- [ ] Vendor maintains documented security policies and procedures  
- [ ] Vendor provides audit reports or summaries upon request  

### 3. Data Protection
- [ ] Data encrypted at rest  
- [ ] Data encrypted in transit  
- [ ] Data logically or physically segregated from other tenants  
- [ ] Data residency options for compliance (e.g., GDPR, CCPA)  
- [ ] Vendor maintains clear data retention and deletion policies  

### 4. Access & Authentication
- [ ] Multi-factor authentication (MFA) enforced for admins  
- [ ] Single Sign-On (SSO) integration available  
- [ ] Role-based access controls (least privilege) enforced  
- [ ] Privileged access logged and monitored  

### 5. Incident Response
- [ ] Documented incident response plan exists  
- [ ] Breach notification guaranteed within 72 hours  
- [ ] Regular incident response testing performed  
- [ ] Dedicated incident response team available  

### 6. Business Continuity
- [ ] Documented disaster recovery (DR) plan  
- [ ] Regular backup and restore testing performed  
- [ ] Vendor maintains defined uptime SLA  
- [ ] Failover capabilities tested in the last 12 months  

### 7. Third-Party Risk Management
- [ ] Vendor performs due diligence on its own subprocessors  
- [ ] Vendor maintains a list of subprocessors  
- [ ] Vendor notifies customers of subprocessor changes  

---

## Vendor-Specific Due Diligence

### AWS (Critical Tier Vendor)
AWS is the backbone of SePurity’s entire platform and is classified as **Critical**.  
The focus here is on validating AWS’s infrastructure security and shared responsibility model.

- [ ] SOC 2 Type II, ISO 27001 certified  
- [ ] Dedicated Trust & Safety or Security team with published documentation  
- [ ] Data encrypted at rest (KMS) and in transit (TLS)  
- [ ] IAM with MFA for all privileged accounts  
- [ ] AWS CloudTrail and GuardDuty logs enabled  
- [ ] Documented breach notification process  
- [ ] Regional data hosting options (US/EU)  
- [ ] Service uptime SLA (99.9%+)  

**Notes:** AWS typically publishes compliance reports in the [AWS Artifact portal](https://aws.amazon.com/artifact/).  

---

### Salesforce (High Tier Vendor)
Salesforce is **High** because it processes sensitive CRM data but does not directly host SePurity’s SaaS platform.  

- [ ] SOC 2 and ISO 27001 certified  
- [ ] GDPR and CCPA compliance program in place  
- [ ] Customer data encrypted at rest and in transit  
- [ ] Supports SSO (SAML, OIDC) for enterprise integration  
- [ ] Role-based access control for accounts (Sales, Support, Admin)  
- [ ] Data export logging and monitoring  
- [ ] Breach notification within 72 hours  
- [ ] Redundant data centers for availability  

**Notes:** Salesforce maintains a public [Trust and Compliance page](https://trust.salesforce.com/) with uptime and compliance details.  
### Why Salesforce Includes GDPR and CCPA

Salesforce processes personal data that falls under data protection laws such as GDPR (for customers in the UK/EU) and CCPA (for customers in California). Since SePurity uses Salesforce to manage customer contact information, deal history, and support records, this data qualifies as Personally Identifiable Information (PII).  

- **GDPR impact**: Any mishandling of EU/UK customer information, such as unauthorized access or data export misuse, could trigger GDPR obligations around breach notification, lawful processing, and data minimization.  
- **CCPA impact**: For California residents, CCPA requires transparency on what personal information is collected, stored, and shared. A breach or misuse of Salesforce records could lead to consumer claims or regulatory penalties under this law.  

Because of this, Salesforce is not only important for operations but also carries regulatory exposure that must be considered in SePurity’s risk evaluation. Controls such as access management, encryption, and audit logging directly support compliance with these laws.

---

### Dropbox (Low Tier Vendor)
Dropbox is **Low** because it primarily holds internal SePurity documents, not customer-facing data.  
Due diligence still ensures that even “low tier” vendors don’t create avoidable risks.  

- [ ] Basic certifications (SOC 2, ISO 27001)  
- [ ] MFA available for user accounts  
- [ ] SSO support for business accounts  
- [ ] Data encrypted at rest and in transit  
- [ ] Breach notification policies documented  
- [ ] Short log retention periods documented  
- [ ] Regular uptime SLA and incident transparency  

**Notes:** Dropbox’s [Trust Center](https://www.dropbox.com/trust) provides details on security certifications and practices.  

---

## Vendor Comparison at a Glance

| Control Area            | **AWS (Critical)** | **Salesforce (High)** | **Dropbox (Low)** |
|--------------------------|--------------------|------------------------|-------------------|
| **Certifications**       | SOC 2, ISO 27001, | SOC 2, ISO 27001 | SOC 2, ISO 27001 |
| **Data Encryption**      | At rest & in transit (KMS, TLS) | At rest & in transit | At rest & in transit |
| **SSO / MFA**            | Full SSO (SAML, OIDC), MFA for all admins | Full SSO, MFA supported | SSO available, MFA optional |
| **Access Controls**      | Fine-grained IAM policies, least privilege | Role-based access for CRM users | Basic access roles, less granular |
| **Incident Response**    | Documented IR plan, 24/7 support, breach notifications | Documented IR plan, 72-hour breach notice | Documented IR plan, breach notice available |
| **Business Continuity**  | Global redundancy, 99.9%+ SLA | Redundant data centers, defined SLAs | Standard uptime SLA, basic transparency |
| **Data Residency**       | Multiple region hosting (US/EU) | Regional hosting options (GDPR/CCPA) | Limited options, global hosting |
| **Subprocessor Mgmt.**   | Publishes subprocessor list in AWS Artifact | Publishes subprocessor list | Publishes subprocessor list |
| **Overall Risk Tier**    | **Critical** (20) | **High** (14) | **Low** (6) |

---

## Key Points
- **AWS** is rock-solid with certifications and global infrastructure, but its inherent risk is highest because SePurity fully depends on it.  
- **Salesforce** is strong in compliance and customer data handling, but less critical to uptime than AWS.  
- **Dropbox** covers the basics but is designed for collaboration, not heavy compliance workloads, which is fine since SePurity only uses it for internal docs.  
  

---
