# Remediation Plan — SePurity, Inc.

This step takes the risks from the register and turns them into actions.  
A risk register on its own is useful, but it is only half the story.  
The remediation plan shows how SePurity will actually close the gaps that were identified.  

---

## How the Plan Works

For each risk, I documented:  
1. Remediation ID: unique identifier for tracking  
2. Vendor: AWS, Salesforce, or Dropbox  
3. Risk Description: what could go wrong  
4. Residual Risk: the level after controls were applied  
5. Remediation Action: what steps SePurity should take to reduce the risk further  
6. Owner: which team or role is responsible for following up  
7. Target Date: when the fix should be done  
8. Status: whether it is Open, In Progress, or Closed  

This format keeps everything organized and easy to follow.  

---

## Remediation Plan Table

| Remediation ID | Vendor     | Risk Description                               | Residual Risk | Remediation Action                                   | Owner            | Target Date | Status   |
|----------------|------------|-----------------------------------------------|---------------|------------------------------------------------------|------------------|-------------|----------|
| RP-001         | AWS        | Misconfigured S3 bucket could expose vulnerability scan results | Moderate      | Enable automated S3 public access checks and run quarterly audits | Cloud Engineering | Q2 2026     | Open     |
| RP-002         | AWS        | Weak IAM controls could allow admin compromise | Moderate      | Enforce MFA on all admin accounts and run monthly IAM reviews | Security Team    | Q2 2026     | Open     |
| RP-003         | AWS        | Outage of EC2 or RDS could bring platform offline | Moderate      | Test disaster recovery annually and review SLA performance | Cloud Engineering | Q3 2026     | Open     |
| RP-004         | Salesforce | Excessive access granted to temporary staff   | Medium        | Restrict temporary staff roles and set automatic expiration | Sales Ops        | Q2 2026     | Open     |
| RP-005         | Salesforce | CRM data export could be stored insecurely    | Medium        | Limit CSV exports to admins and implement DLP alerts | Sales Ops        | Q3 2026     | Open     |
| RP-006         | Salesforce | Third-party app integration could mishandle customer data | Medium    | Approve integrations through security review process | Security Team    | Q3 2026     | Open     |
| RP-007         | Dropbox    | Staff syncing files to personal accounts      | Low           | Enforce business-only Dropbox sync through admin console | IT Admins        | Q2 2026     | Open     |
| RP-008         | Dropbox    | Limited log retention makes investigations harder | Low       | Document log retention limits and accept risk as low-impact | IT Admins        | Q2 2026     | Open     |

---

## Key Observations

AWS: The main focus is on IAM and monitoring. Even with AWS’s strong baseline, SePurity cannot assume AWS handles everything. Regular audits and recovery tests need to be built into operations.  

Salesforce: The risks are around people and integrations more than the core system. Fixing them means stronger RBAC controls, restricting exports, and tighter oversight on third-party apps.  

Dropbox: Risks are low because of the data type, but they still need to be managed. Enforcing sync restrictions and formally accepting the short log retention keeps things under control.  

---

## Next Steps

- Review remediation actions on a quarterly basis  
- Track status changes (Open → In Progress → Closed)  
- Escalate overdue items to leadership if risks remain unaddressed  
- Update the plan whenever new risks are added to the register  

---

This remediation plan shows that identifying risks is not enough.  
What matters is turning risks into tasks, assigning owners, and following through until they are closed.  
That is what creates real value in vendor risk management.  
