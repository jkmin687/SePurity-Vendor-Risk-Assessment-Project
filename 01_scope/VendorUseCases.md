# Vendor Use Cases — SePurity, Inc.

## AWS (High Tier)
AWS is the foundation of SePurity’s product delivery. It provides the compute, storage, and database infrastructure for the SePurity Security Suite. Engineers and administrators use AWS daily to deploy services, store customer data, and manage backups.  

**Why AWS was chosen:**  
AWS is the industry leader in cloud services, offering unmatched scalability, strong uptime commitments, and compliance with standards such as SOC 2, ISO 27001, and FedRAMP. For a security-focused company like SePurity, choosing AWS provides customer confidence because the platform is widely trusted and regularly audited.  

**Data handled:** Sensitive information, including customer names, emails, vulnerability scan results, training records, and system logs.  

**Operational impact:** A major AWS outage or breach would directly bring down the SePurity platform. Customers would lose access to the service and data confidentiality could be at risk.  

**Security considerations:**  
- IAM policies and MFA must be strictly enforced for admin accounts.  
- Customer-managed keys in KMS should be required for encryption.  
- Configurations such as S3 bucket policies must be regularly reviewed to prevent accidental public exposure.  

---

## Salesforce (Medium Tier)
Salesforce acts as SePurity’s central Customer Relationship Management (CRM) platform. It is where sales and support teams track leads, manage renewals, and respond to support cases. While Salesforce does not control the availability of SePurity’s product, it plays a critical role in business operations and customer engagement.  

**Why Salesforce was chosen:**  
It is the gold standard in CRM platforms, with powerful features, high flexibility, and global use. It also provides a wide library of integrations and comes with strong compliance certifications such as SOC 2 and ISO 27001.  

**Data handled:** Sensitive data including customer contact information, lead records, deal history, and support case details.  

**Operational impact:** A Salesforce outage would not affect customer access to the SePurity product itself but would cripple the sales and support workflow, delaying renewals and customer communications.  

**Security considerations:**  
- MFA should be enforced across all accounts through SSO.  
- Third-party app integrations should be carefully reviewed before being enabled.  
- Role-based access control (RBAC) must be applied to avoid overexposing customer data.  

---

## Dropbox (Low Tier)
Dropbox Business is used internally by SePurity staff for low-risk collaboration. Typical usage includes sharing marketing files, training materials, and internal templates. It is available to all employees through SSO integration, which keeps access centralized.  

**Why Dropbox was chosen:**  
Dropbox is lightweight, easy to use, and cost effective. It also supports secure file sharing with external partners, which is useful for occasional marketing or vendor collaboration. While it is not designed to hold highly sensitive data, it provides encryption at rest and in transit, and integrates with centralized identity providers.  

**Data handled:** Internal data only, such as training guides, marketing content, and project templates.  

**Operational impact:** A Dropbox outage would inconvenience staff but would not impact SePurity customers or the delivery of the SePurity Security Suite.  

**Security considerations:**  
- Limit sharing permissions to prevent accidental public exposure.  
- Monitor audit logs (though retention is limited in some plans).  
- Disable personal Dropbox account sync to prevent company data leakage.  
