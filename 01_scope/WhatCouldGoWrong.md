# What Could Go Wrong // SePurity, Inc.

This section highlights realistic risk scenarios for each vendor in scope. The goal is to anticipate potential failures or vulnerabilities and understand how they could impact SePurity’s customers, operations, and compliance posture.  

---

## AWS (High Tier)
AWS is the foundation of the SePurity Security Suite, which means risks here are critical and have the highest impact. Some examples include but are not limited to:  

- **Misconfigured storage:** Publicly accessible S3 buckets could expose sensitive vulnerability scan results or customer data to the internet.  
- **Weak IAM controls:** Admin accounts without enforced MFA could be compromised, giving attackers full access to cloud resources.  
- **Excessive permissions:** Developers with more privileges than required could unintentionally or maliciously alter production systems.  
- **Service outages:** Downtime in EC2, RDS, or S3 would directly cause the SePurity platform to go offline.  
- **Data residency issues:** Storing customer data in regions that violate GDPR or CCPA obligations could create legal problems.  
- **Shared responsibility gaps:** Confusion about what AWS secures versus what SePurity must secure could leave monitoring and logging incomplete.  

---

## Salesforce (Medium Tier)
Salesforce supports customer relationships and revenue operations. It does not control product uptime, but a failure here would still damage trust and business continuity. These can include:  

- **Compromised user accounts:** Without strong MFA, attackers could steal customer contact information.  
- **Risky third-party integrations:** Poorly vetted Salesforce apps could misuse or expose CRM data.  
- **Misconfigured roles:** Overly broad access could give interns, contractors, or lower-level staff visibility into sensitive accounts.  
- **Export misuse:** Customer lists exported to spreadsheets could be stored on personal devices or unsecured locations.  
- **Service outage:** If Salesforce goes down, sales and support teams would be unable to manage renewals, cases, or customer communication.  

---

## Dropbox (Low Tier)
Dropbox is used for internal collaboration. While it stores only internal, low-sensitivity data, issues here can still create disruption or reputational damage. Some examples are:  

- **Accidental oversharing:** An employee might make a folder public by mistake, exposing internal training or marketing drafts.  
- **Limited log retention:** Short log history in lower-tier plans reduces the ability to investigate long-term misuse or insider threats.  
- **Insecure personal devices:** Employees accessing Dropbox from personal devices without security controls could create entry points for attackers.  
- **Unmanaged account sync:** Files synced to personal Dropbox accounts could lead to loss of company control over internal documents.  
- **Service outage:** Would cause delays in collaboration but would not affect SePurity customers or platform availability.  

---

## Cross-Cutting Risks (All Vendors)
Some risks apply across every vendor relationship:  

- **Vendor breach history:** A compromise at the vendor level could expose SePurity data, even if SePurity’s own systems remain secure.  
- **Contractual gaps:** Without strong contracts, vendors may not be required to notify SePurity quickly during incidents.  
- **Subprocessor changes:** Vendors could add new subprocessors without notice, moving data into higher-risk environments.  
- **Compliance misalignment:** Vendors may not fully meet SOC 2, ISO 27001, GDPR, or CCPA requirements, which could create compliance gaps SePurity must manage.  
