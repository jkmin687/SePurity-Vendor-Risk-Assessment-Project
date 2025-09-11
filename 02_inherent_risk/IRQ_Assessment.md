# Inherent Risk Questionnaire (IRQ) — SePurity, Inc.

This section shows how I decided to tier SePurity’s vendors by **inherent risk**.  
Inherent risk is basically the *raw level of risk a vendor brings* if you strip away all their security controls. *i.e. How dangerous could they be to us just by the type of data they hold, how much of it, and how critical they are to the business?*  

---

## Scoring Model

When I looked at each vendor, I asked myself five key questions:  

1. **Data Sensitivity** – Do they touch customer data, internal data, or regulated data?  
2. **Data Volume** – How much data do they actually hold?  
3. **Criticality to Operations** – Would SePurity grind to a halt if this vendor failed?  
4. **System Integration** – How tightly woven is this vendor into our systems?  
5. **Regulatory Impact** – If something went wrong, would we get hit with GDPR/CCPA trouble or other compliance issues?  

### Scale I Used
- **1 = Low**  
- **2 = Medium**  
- **3 = High**  
- **4 = Critical**  

### Tier Ranges
- **Low:** 5–8 (nice to have, minimal risk if things go wrong)  
- **Medium:** 9–12 (important, but not a showstopper)  
- **High:** 13–16 (major issues if breached or down)  
- **Critical:** 17–20 (the company cannot function without them)  

> The total score is the sum of the five categories. The higher the number, the more risky the vendor is by default.

---
## Tier Legend

Here’s a simple visual for the ranges:  

<img width="2970" height="720" alt="SePurity_Tier_Legend" src="https://github.com/user-attachments/assets/221a6c16-756b-4f24-9713-668efaf027be" />

---

## Vendor Rationale

### AWS • Total 20 • Critical Tier
AWS is the engine that powers everything SePurity does. It stores customer data, runs the platform, and keeps our services online. If AWS breaks, we break.  
- Handles sensitive data (customer names, emails, scan results, logs).  
- Hosts huge amounts of information across compute, storage, and databases.  
- Outage = SePurity platform goes dark, no workarounds.  
- Deeply integrated into our systems, from IAM to S3.  
- A slip-up could mean GDPR or CCPA violations, not just downtime.  

**Bottom line:** AWS is non-negotiable. It is a **Critical** vendor because without it, SePurity doesn’t exist.  

---

### Salesforce • Total 14 • High Tier
Salesforce doesn’t keep the lights on, but it does keep the business running smoothly. It’s where sales, renewals, and support live. Losing it wouldn’t kill the product, but it would seriously hurt operations.  
- Stores sensitive customer data like contact info and deal history.  
- Holds thousands of records, but not our entire product database.  
- Outage slows sales and support teams, though the core platform stays online.  
- Connected through SSO and APIs, but not baked into the infrastructure.  
- Breach could still land us in trouble with GDPR/CCPA.  

**Bottom line:** Salesforce is a **High** risk vendor. It’s not Critical because the app itself still runs, but losing it would damage customer trust and our ability to operate.  

---

### Dropbox • Total 6 • Low Tier
Dropbox is used for low-sensitivity things such as training docs, templates, and marketing content. Losing it would be tedious, but it wouldn’t stop SePurity or put us at regulatory risk.  
- Handles internal data only, no customer info.  
- Used company-wide but for low-stakes material.  
- Outage = inconvenience, not disaster.  
- Only linked to SSO, not tightly integrated.  
- Minimal compliance concerns since it’s not storing regulated data.  

**Bottom line:** Dropbox belongs in the **Low** tier. It matters for convenience, but not for security or operations.  

---

## Summary Table

| Vendor       | Data Sensitivity | Data Volume | Criticality | System Integration | Regulatory Impact | **Total** | **Tier**   |
|--------------|------------------|-------------|-------------|--------------------|------------------|-----------|------------|
| **AWS**      | 4                | 4           | 4           | 4                  | 4                | **20**    | **Critical** |
| **Salesforce** | 3              | 3           | 3           | 2                  | 3                | **14**    | **High**     |
| **Dropbox**  | 1                | 2           | 1           | 1                  | 1                | **6**     | **Low**      |

---

## Visual Snapshot

```mermaid
pie showData
  title Inherent Risk Totals
  "AWS" : 20
  "Salesforce" : 14
  "Dropbox" : 6
