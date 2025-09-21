# Risk Register // SePurity, Inc.

This Risk Register pulls together everything from the earlier steps.  
It began with the inherent risks in Step 2, then dug into vendor controls in Step 3, and evaluating their effectiveness in Step 4.  
Here, the main risks were compiled into one place so the risks and how they should be handled going forward were clearly displayed.  

---

## How the Register Works

Each risk entry includes:  
1. Risk ID: unique identifier for tracking  
2. Vendor: AWS, Salesforce, or Dropbox  
3. Risk Description: what could go wrong if the risk happened  
4. Inherent Risk: the baseline risk score from Step 2  
5. Controls in Place: what protections I found in Steps 3 and 4  
6. Residual Risk: the level of risk that remains after controls  
7. Risk Owner: the role at SePurity who would be responsible  
8. Treatment Plan: whether to accept, mitigate, monitor, or transfer the risk  

---

## Risk Register Table

| Risk ID | Vendor     | Risk Description                                      | Inherent Risk | Controls in Place                              | Residual Risk | Risk Owner         | Treatment Plan |
|---------|------------|-------------------------------------------------------|---------------|------------------------------------------------|---------------|--------------------|----------------|
| VR-001  | AWS        | Misconfigured S3 bucket could expose vulnerability scan results | Critical (20) | Encryption at rest, TLS in transit, IAM with MFA, restricted policies | Moderate      | Cloud Engineering  | Mitigate: run regular S3 audits and set up alerts |
| VR-002  | AWS        | Weak IAM controls could allow admin compromise        | Critical (20) | IAM with MFA, role-based access                | Moderate      | Security Team      | Mitigate: quarterly access reviews and MFA checks |
| VR-003  | AWS        | Outage of EC2 or RDS could bring platform offline     | Critical (20) | Multi-region redundancy, 99.99% SLA            | Moderate      | Cloud Engineering  | Monitor: test disaster recovery annually |
| VR-004  | Salesforce | Excessive access granted to temporary staff           | High (14)     | Role-based access controls, SSO + MFA          | Medium        | Sales Operations   | Mitigate: quarterly RBAC reviews |
| VR-005  | Salesforce | Third-party app integration could mishandle customer data | High (14)  | Vendor vetting, API permissions restricted     | Medium        | Security Team      | Monitor: approve integrations before use |
| VR-006  | Salesforce | CRM data export could be stored insecurely            | High (14)     | Export logs, breach notifications              | Medium        | Sales Operations   | Mitigate: restrict exports and add DLP alerts |
| VR-007  | Dropbox    | Accidental oversharing of internal documents          | Low (6)       | SSO + MFA available, admin console controls    | Low           | IT Admins          | Accept: limited to internal docs only |
| VR-008  | Dropbox    | Limited log retention makes investigations harder     | Low (6)       | Basic logging with short retention             | Low           | IT Admins          | Monitor: acceptable for low data sensitivity |
| VR-009  | Dropbox    | Staff syncing files to personal accounts              | Low (6)       | Admin restrictions available but not enforced  | Low           | IT Admins          | Mitigate: enforce business-only syncing |

---

## Residual Risk Snapshot

| Vendor       | Residual Risk | Notes                                                                 |
|--------------|---------------|----------------------------------------------------------------------|
| AWS          | Moderate      | Even with strong controls, SePurity has to manage shared responsibility for monitoring. |
| Salesforce   | Medium        | Good coverage on compliance and data protection, but monitoring and integration oversight still leave some exposure. |
| Dropbox      | Low           | Acceptable because it only stores internal documents. Scope must stay limited. |

---

## Key Takeaways

AWS: Remains the biggest risk because the whole platform depends on it. Controls are strong, but I cannot rely only on AWS — SePurity must stay proactive with monitoring and IAM reviews.  

Salesforce: Solid when it comes to compliance and protecting customer data, but less visibility in monitoring means the risk is still medium. RBAC reviews and export restrictions help close the gap.  

Dropbox: Low impact because it is limited to internal docs. Still, enforcing policies like blocking personal syncing keeps this risk from creeping upward.  

---

## Next Steps

- Review each vendor risk on a quarterly basis (frequency depends copmany to copmany)  
- Track remediation tasks like IAM reviews
- Update the register whenever SePurity adds a new vendor or changes how an existing one is used  
