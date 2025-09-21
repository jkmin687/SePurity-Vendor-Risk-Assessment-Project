# Control Evaluation // SePurity, Inc.

This step evaluates how effective each vendor’s controls are in practice.
In Step 2, inherent risk was scored without considering any protections.
In Step 3, information was collected through the Due Diligence Checklists.

The question is: “Do these controls reduce risk enough for SePurity to be comfortable?”
This is where the analysis shifts from inherent risk to residual risk, which is the risk that remains after vendor controls are applied.

---

## How I Evaluated Controls

Six categories were used:  

1. Governance & Compliance: certifications, audits, policies  
2. Data Protection: encryption, retention, residency  
3. Access & Authentication: MFA, SSO, role-based access  
4. Monitoring & Response: logging, IR plan, breach notifications  
5. Continuity & Recovery: SLA, redundancy, disaster recovery  
6. Third-Party Oversight: subprocessor management, transparency  

Ratings are kept simple:  
- Strong = control fully addresses the risk  
- Partial = control exists but has gaps  
- Weak = control is missing or not effective  

---

## AWS (Critical Vendor)

| Control Category        | What AWS Does                                    | Effectiveness |
|--------------------------|--------------------------------------------------|---------------|
| Governance & Compliance | SOC 2, ISO 27001, FedRAMP certified              | Strong        |
| Data Protection         | Encryption at rest (KMS), TLS in transit, regions | Strong        |
| Access & Authentication | IAM with MFA, fine-grained policies, SSO support | Strong        |
| Monitoring & Response   | CloudTrail + GuardDuty, but shared responsibility | Partial       |
| Continuity & Recovery   | Multi-region redundancy, 99.99% SLA              | Strong        |
| Third-Party Oversight   | Publishes subprocessors in AWS Artifact          | Partial       |

**Observation:** AWS is the backbone of SePurity. Their controls are mature and reliable, but the shared responsibility model means SePurity has to handle some monitoring on its own. Residual risk is moderate.  

---

## Salesforce (High Vendor)

| Control Category        | What Salesforce Does                             | Effectiveness |
|--------------------------|--------------------------------------------------|---------------|
| Governance & Compliance | SOC 2 and ISO 27001 certified                    | Strong        |
| Data Protection         | Encryption at rest and in transit, GDPR/CCPA     | Strong        |
| Access & Authentication | SSO + MFA options                                | Strong        |
| Monitoring & Response   | Breach notifications, but less transparency      | Partial       |
| Continuity & Recovery   | Redundant data centers, published SLA            | Strong        |
| Third-Party Oversight   | Subprocessors published on trust portal          | Partial       |

**Observation:** Salesforce is strong on compliance and customer data protection. Where they fall short is giving full visibility into monitoring and subprocessor activity. Residual risk is medium.  

---

## Dropbox (Low Vendor)

| Control Category        | What Dropbox Does                                | Effectiveness |
|--------------------------|--------------------------------------------------|---------------|
| Governance & Compliance | SOC 2 and ISO 27001 certified                    | Partial       |
| Data Protection         | Encryption at rest and in transit                | Strong        |
| Access & Authentication | MFA + SSO, but not always enforced               | Partial       |
| Monitoring & Response   | IR plan exists, logs are short-term only         | Weak          |
| Continuity & Recovery   | Standard SLA, not much detail on DR              | Partial       |
| Third-Party Oversight   | Publishes subprocessors                          | Strong        |

**Observation:** Dropbox is fine for internal docs but not something I would trust with sensitive customer data. Weaknesses in monitoring and continuity are acceptable here only because of its limited scope. Residual risk is low.  

---

## Side-by-Side Summary

| Vendor       | Governance | Data Protection | Access & Auth | Monitoring | Continuity | Third-Party Oversight | Residual Risk |
|--------------|------------|-----------------|---------------|------------|------------|-----------------------|----------------|
| **AWS**      | Strong     | Strong          | Strong        | Partial    | Strong     | Partial               | Moderate       |
| **Salesforce** | Strong   | Strong          | Strong        | Partial    | Strong     | Partial               | Medium         |
| **Dropbox**  | Partial    | Strong          | Partial       | Weak       | Partial    | Strong                | Low            |

---

## Residual Risk Explained

**Inherent Risk** = the raw danger a vendor (or process) brings if no controls exist (Step 2).  

**Controls** = the protections the vendor puts in place (certifications, encryption, MFA, monitoring, etc.) (Step 3 and 4).  

**Residual Risk** = the leftover risk after you account for those controls.  

Residual risk is basically:  

**Residual Risk = Inherent Risk – Control Effectiveness**  

It answers: *“Even with all these protections, what risk do we still have to live with?”*  

## Residual Risk Scale

- **Low**: Residual risk is minimal. Vendor’s role is limited or controls are strong enough that the remaining exposure is not a big issue.  
- **Medium**: Some gaps are present. Vendor is important to operations but controls reduce most (but not all) of the danger.  
- **Moderate**: Vendor is critical and controls are strong, but SePurity must still be on their toes since completely eliminating the risk is impossible.  
- **High**: Significant risks even after controls. The business may need remediation or consider changing vendors.

## Example with SePurity Vendors
- **AWS**  
  Inherent risk: Critical (20)  
  Controls: Strong across compliance, encryption, access. Partial in monitoring (shared responsibility)  
  Residual risk: Moderate. AWS is excellent, but you can never reduce Critical to zero because SePurity depends on it.  

- **Salesforce**  
  Inherent risk: High (14)  
  Controls: Strong in compliance and access. Partial in transparency and subprocessors  
  Residual risk: Medium. Salesforce reduces a lot of the inherent risk, but it cannot be considered low because SePurity does not control their monitoring.  

- **Dropbox**  
  Inherent risk: Low (6)  
  Controls: Basic coverage but weak monitoring  
  Residual risk: Low. Since SePurity only uses it for non-sensitive docs, the risk stays low even with weak spots.  

---

## Why It Matters
- You can never get risk to zero  
- Residual risk tells you whether current controls are enough or if remediation is needed  
- If residual risk is too high, you either:  
  - Push the vendor for stronger controls  
  - Limit or end your use of that vendor  
