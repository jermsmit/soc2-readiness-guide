# Access Control Policy

**[Company Name]**
**Version:** 1.0
**Effective Date:** [Date]
**Owner:** [Name / Title, e.g. IT Security Lead]
**Approved By:** [Name / Title]

This is a template. Replace all bracketed content with your organization's actual practices before adoption. Have legal counsel and your auditor review before approval.

---

## 1. Purpose

This policy establishes the requirements for granting, managing, reviewing, and revoking access to [Company Name]'s information systems, applications, and data. Its purpose is to ensure that access is granted only to individuals who require it to perform their job functions, at the minimum level of privilege necessary, and that access is removed promptly when it is no longer required.

## 2. Scope

This policy applies to all employees, contractors, and third parties who access [Company Name]'s systems, including but not limited to:

- Production infrastructure and cloud environments
- Source code repositories
- Business applications, including [list key systems: HR platform, CRM, ticketing system, etc.]
- Physical facilities housing company infrastructure, where applicable
- [Add or remove systems to match your actual environment]

## 3. Roles and Responsibilities

**System Owners.** Each in-scope system has a designated owner responsible for approving access requests, participating in periodic access reviews, and ensuring access aligns with this policy.

**IT Security.** Responsible for administering access provisioning and deprovisioning workflows, maintaining the access control system of record, and coordinating periodic access reviews across all in-scope systems.

**Human Resources.** Responsible for notifying IT Security of employee starts, role changes, and terminations in a timely manner, per the notification timelines in Section 6.

**People Managers.** Responsible for requesting access appropriate to a direct report's role, and for promptly notifying HR and IT Security of role changes affecting access needs.

**Employees and Contractors.** Responsible for using access solely for authorized business purposes and reporting any access they believe to be inappropriate or excessive for their role.

## 4. Access Provisioning

- Access requests must be submitted through [ticketing system / access request tool] and require approval from the relevant system owner or manager before being granted.
- Access is granted based on the principle of least privilege: individuals receive the minimum access necessary to perform their current job function, not broader access anticipated for future need.
- Role-based access control is used wherever supported by the system in question. Standard roles and their associated access levels are documented in [location, e.g. an internal access matrix].
- New hire access is provisioned as part of the onboarding process, coordinated between HR and IT Security, with access limited initially to systems required for the employee's specific role.
- Access requests and approvals are logged and retained as evidence of the provisioning decision.

## 5. Authentication Requirements

- Multi-factor authentication (MFA) is required for all access to [production systems / cloud infrastructure / any system processing customer data]. [Specify scope precisely, e.g. "all systems" or list exceptions and compensating controls.]
- Single sign-on (SSO) is used for [list applications integrated with SSO] to centralize authentication and simplify deprovisioning.
- Password requirements for any system not covered by SSO: [minimum length, complexity requirements, rotation policy if applicable].
- Shared or generic accounts are prohibited except where explicitly documented and approved, with compensating controls such as [password vaulting, session logging] in place.

## 6. Deprovisioning and Offboarding

- HR notifies IT Security of any termination, whether voluntary or involuntary, [immediately upon confirmation / within X hours, specify your actual timeline].
- For involuntary terminations, access must be revoked [at the time of termination notification / before the termination meeting occurs, specify your actual practice], given the elevated risk associated with involuntary departures.
- For voluntary terminations, access must be revoked no later than the employee's last day of employment, and sooner if the employee's role or the circumstances of departure warrant earlier revocation.
- Deprovisioning covers all systems the individual had access to, including physical access badges, VPN access, and any local accounts not managed through centralized identity management.
- Deprovisioning actions are logged and retained as evidence.
- For role changes (not departures), access is reviewed and adjusted to match the new role, with access no longer required for the prior role removed rather than accumulated.

## 7. Contractor and Temporary Access

- Contractor access follows the same provisioning and least-privilege requirements as employee access, requested and approved through the same process.
- Contractor access is granted with a defined end date wherever the system supports time-bound access, aligned to the contractor's engagement end date.
- Contractor access is reviewed at the same cadence as employee access, and is deprovisioned immediately upon engagement completion or termination.

## 8. Periodic Access Reviews

- Access to [production systems / systems in SOC 2 scope] is reviewed on a [quarterly] basis.
- Reviews are performed by the relevant system owner, who confirms that each individual with access still requires it for their current role.
- Review results, including any access removed as a result of the review, are documented and retained as evidence.
- Reviews cover both standard user access and privileged or administrative access, with privileged access reviewed with particular attention given its elevated risk.

## 9. Privileged Access

- Administrative or privileged access is granted only where required for an individual's role and is subject to additional approval from [IT Security / relevant system owner] beyond standard access requests.
- Privileged access is reviewed at least [quarterly, or more frequently than standard access if your practice differs].
- Where technically feasible, privileged actions are logged in a manner that supports audit and forensic review.

## 10. Exception Handling

Any deviation from this policy, including emergency access granted outside the standard approval process, must be documented with the business justification, the individual who approved the exception, and a plan to bring access back into compliance with standard process. Exceptions are reviewed as part of the periodic access review cycle.

## 11. Policy Review and Approval History

| Version | Date | Description of Change | Approved By |
|---|---|---|---|
| 1.0 | [Date] | Initial policy | [Name] |

This policy is reviewed at least annually, or sooner if a material change to systems, organizational structure, or regulatory requirements warrants earlier review.
