# Data Classification // SePurity, Inc.

## Purpose
Data classification gives SePurity a way to protect information based on its level of sensitivity. This approach ensures that information is managed properly inside the company and also helps define expectations for vendors.  

---

## 1. Public
- **Definition:** Safe for anyone to see.  
- **Examples:** Blog posts, press releases, marketing brochures.  

## 2. Internal
- **Definition:** For employees only. If shared outside, it would not cause serious harm but is not meant for the public.  
- **Examples:** Internal training content, project planning notes, draft presentations.  

## 3. Sensitive
- **Definition:** Information that could harm the company or customers if leaked. Stronger access and monitoring are imperative here.  
- **Examples:**  
  - Customer names and email addresses  
  - Vulnerability scan results from SePurity’s platform  
  - Salesforce CRM records  
  - Application logs with identifiers  

## 4. Regulated
- **Definition:** Information protected by laws, regulations, or contracts. Mishandling this type of data can lead to penalties or fines.  
- **Examples:**  
  - GDPR data for EU and UK residents  
  - CCPA data for California residents  
  - (Not currently in scope: PCI DSS card data or HIPAA health data)  

---

## Vendor Data Mapping
- **AWS:** Sensitive (customer data, scan results, log backups)  
- **Salesforce:** Sensitive (customer and lead details)  
- **Dropbox:** Internal (training files, templates, marketing content)  

Although SePurity does not process PCI or HIPAA data, it uses this model so the company can stay ready if customer requirements change in the future.  
