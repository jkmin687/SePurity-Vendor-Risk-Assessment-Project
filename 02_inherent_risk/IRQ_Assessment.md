# Inherent Risk Questionnaire // SePurity, Inc.

This section outlines how SePurity’s vendors were tiered by **inherent risk**.  
Inherent risk represents the *raw level of risk a vendor introduces* if no security controls were put into place. In other words: *How risky could this vendor be simply based on the type of data they handle, the volume of it, and their importance to business operations?*  

---

## Scoring Model

Each vendor was assessed across five key categories:  

1. **Data Sensitivity**: The type of data handled (customer, internal, or regulated).  
2. **Data Volume**: The scale or amount of data stored or processed.  
3. **Criticality to Operations**: Whether SePurity could continue to function if the vendor failed.  
4. **System Integration**: How deeply the vendor is embedded into SePurity’s systems.  
5. **Regulatory Impact**: The extent to which a breach could trigger GDPR, CCPA, or other compliance issues.  

### Scale Used  
- **1 = Low**  
- **2 = Medium**  
- **3 = High**  
- **4 = Critical**  

### Tier Ranges  
- **Low:** 5–8 (minimal risk if things go wrong)  
- **Medium:** 9–12 (important, but not business-critical)  
- **High:** 13–16 (serious impact if breached or unavailable)  
- **Critical:** 17–20 (company cannot function without them)  

> The total score is the sum of the five categories. The higher the number, the greater the inherent risk.  

---

## Tier Legend  

<img width="2970" height="720" alt="SePurity_Tier_Legend" src="https://github.com/user-attachments/assets/221a6c16-756b-4f24-9713-668efaf027be" />  

---

## Vendor Rationale  

### AWS • Total 20 • Critical Tier  
AWS is the foundation of SePurity’s platform. It stores sensitive customer information, powers the compute and database layers, and keeps the services online.  
- Handles sensitive data such as customer names, emails, scan results, and logs.  
- Manages large volumes of data across compute, storage, and databases.  
- Outage would shut down the entire SePurity platform.  
- Highly integrated into systems from IAM to S3.  
- A failure or breach could result in GDPR or CCPA consequences in addition to downtime.  

**Bottom line:** AWS is a **Critical** vendor. Without it, SePurity cannot operate.  

---

### Salesforce • Total 14 • High Tier  
Salesforce is not responsible for uptime, but it is essential to smooth business operations. It houses sales, renewals, and customer support activities. Losing it would not stop the product from functioning, but it would severely impact customer relationships.  
- Stores sensitive customer data such as contact details and deal history.  
- Holds thousands of records, though not the full product database.  
- An outage would hinder sales and support but leave the platform running.  
- Integrated through SSO and APIs, though not tied directly to infrastructure.  
- A breach could still result in GDPR or CCPA issues due to PII exposure.  

**Bottom line:** Salesforce is a **High** risk vendor. It is not Critical since the platform remains available, but its loss would harm operations and trust.  

---

### Dropbox • Total 6 • Low Tier  
Dropbox supports collaboration and internal file sharing. It is used primarily for non-sensitive content such as training documents, templates, and marketing files. Losing it would be inconvenient but not harmful to compliance or core business functions.  
- Manages internal data only, with no customer information.  
- Used company-wide, but strictly for low-sensitivity material.  
- Outage would slow collaboration, not disrupt operations.  
- Connected to SSO but not deeply integrated.  
- Carries minimal compliance concerns since it does not handle regulated data.  

**Bottom line:** Dropbox is a **Low** tier vendor. It contributes to convenience, not security or mission-critical functions.  

---

## Summary Table  

| Vendor        | Data Sensitivity | Data Volume | Criticality | System Integration | Regulatory Impact | **Total** | **Tier**   |
|---------------|------------------|-------------|-------------|--------------------|------------------|-----------|------------|
| **AWS**       | 4                | 4           | 4           | 4                  | 4                | **20**    | **Critical** |
| **Salesforce**| 3                | 3           | 3           | 2                  | 3                | **14**    | **High**     |
| **Dropbox**   | 1                | 2           | 1           | 1                  | 1                | **6**     | **Low**      |  

---

## Visual Snapshot  

```mermaid
pie showData
  title Inherent Risk Totals
  "AWS" : 20
  "Salesforce" : 14
  "Dropbox" : 6
