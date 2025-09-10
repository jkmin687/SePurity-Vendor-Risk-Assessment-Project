# Scope Statement — SePurity, Inc.

## Purpose
The scope statement defines which vendors, systems, and data types are covered in this Vendor Risk Management (VRM) project. Setting a clear scope ensures that the assessment focuses on the vendors that present the highest impact to SePurity’s operations and customers, while excluding areas that are not relevant at this stage.  

---

## In Scope
The following vendors and systems are included in this assessment:  
- **AWS:** IAM (admin access), EC2/Lambda (compute), RDS (database), and S3 storage. These services are critical for hosting the SePurity platform and contain sensitive customer data.  
- **Salesforce:** Sales Cloud CRM and SSO login. This system manages customer relationships, contact details, and renewals, which are sensitive to the business but not directly tied to product uptime.  
- **Dropbox:** Business Standard plan with SSO login and admin logs. This platform is used for internal document storage and collaboration, representing lower sensitivity but still within VRM scope.  

---

## Data in Scope
The assessment includes the following data categories processed or stored by these vendors:  
- **Sensitive Data:** Customer names, emails, vulnerability scan results (AWS); customer contact information and deal history (Salesforce).  
- **Internal Data:** Training materials, templates, and marketing documents (Dropbox).  

---

## Out of Scope
The following systems and data types are excluded from this project:  
- **Payment processing systems:** SePurity uses third-party gateways that are outside the scope of this VRM project.  
- **HR and payroll systems:** These are managed by separate providers and not part of the current assessment.  
- **Highly regulated data:** PCI (credit card data) and HIPAA (health records) are not handled by SePurity at this time and are not part of the scope.  

---

## Summary
This scope ensures that SePurity’s VRM project reflects a realistic mix of **high, medium, and low-tier vendors**. It focuses on the systems that handle customer data and business-critical operations, while deliberately excluding areas that do not impact SePurity’s current service delivery.  
