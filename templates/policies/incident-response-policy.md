# Incident Response Policy

**[Company Name]**
**Version:** 1.0
**Effective Date:** [Date]
**Owner:** [Name / Title, e.g. IT Security Lead]
**Approved By:** [Name / Title]

This is a template. Replace all bracketed content with your organization's actual practices before adoption. Have legal counsel and your auditor review before approval.

---

## 1. Purpose

This policy establishes the process by which [Company Name] detects, classifies, escalates, responds to, and learns from security incidents. Its purpose is to ensure a consistent, timely response that limits harm, meets applicable notification obligations, and produces evidence suitable for internal review and external audit.

## 2. Scope

This policy applies to any suspected or confirmed event that threatens the confidentiality, integrity, or availability of [Company Name]'s systems or data, including but not limited to:

- Unauthorized access to systems or data
- Malware or ransomware infection
- Data loss or exposure
- Denial of service conditions
- Loss or theft of a device containing company or customer data
- Vendor or third-party incidents affecting [Company Name] data or systems

## 3. Roles and Responsibilities

**Incident Commander.** For any incident classified as Medium severity or above, an incident commander is designated to coordinate the response, own communication, and drive the incident to resolution. This role rotates based on [on-call schedule / designated incident response team], not a single fixed individual.

**Reporting Individual.** Any employee, contractor, or system that detects a suspected incident is responsible for reporting it immediately through [reporting channel, e.g. a dedicated Slack channel, ticketing queue, or email alias] regardless of their confidence in whether it constitutes a real incident.

**IT Security / Security Team.** Responsible for triaging reported incidents, classifying severity, and leading technical investigation and remediation.

**Legal and Executive Leadership.** Engaged for any incident classified as High or Critical severity, and for any incident that may trigger a regulatory notification obligation.

**Communications Owner.** For incidents requiring external communication, whether to customers, regulators, or the public, a single individual is designated to own and approve all external messaging to ensure consistency.

## 4. Severity Classification

| Severity | Definition | Example |
|---|---|---|
| Critical | Confirmed breach of customer data, or a system outage affecting all customers with no immediate workaround | Confirmed unauthorized access to a production database containing customer data |
| High | Significant risk of data exposure or system compromise, not yet confirmed as a breach, or an outage affecting a significant subset of customers | Detected but uncontained malware on a production system |
| Medium | Contained security event with limited scope, or a service degradation affecting a subset of functionality | A single compromised employee account, contained before further access occurred |
| Low | Security-relevant event with minimal to no risk of harm, tracked for pattern awareness | A single failed phishing attempt reported by an employee before any action was taken |

Severity may be escalated as an investigation reveals additional scope. Initial classification should favor caution: it is preferable to classify conservatively high and de-escalate once facts are confirmed than the reverse.

## 5. Detection and Reporting

- Employees are trained at onboarding and at least annually thereafter on how to recognize and report a suspected incident.
- Automated detection sources, including [list relevant tools: SIEM, endpoint detection, cloud security monitoring], route alerts to [on-call rotation / security team] for triage.
- All reports, whether from automated tooling or human reporting, are logged in [incident tracking system] with a timestamp, regardless of whether they are ultimately confirmed as incidents.

## 6. Escalation and Response

- Upon report or detection, [Security Team / on-call responder] triages the event and assigns an initial severity classification within [target time, e.g. one hour for Critical/High, one business day for Medium/Low].
- For Medium severity and above, an incident commander is assigned and a dedicated incident channel or ticket is created to centralize all response activity and communication.
- The incident commander coordinates containment, investigation, and remediation, pulling in additional technical, legal, or executive resources as the situation requires.
- All response actions are logged with timestamps, creating a timeline suitable for post-incident review and audit evidence.

## 7. Internal and External Communication

- Internal status updates for Critical and High severity incidents are communicated to [leadership / relevant stakeholders] at a minimum cadence of [e.g. every 2 hours during active response].
- External communication, to customers, partners, or the public, is drafted and approved by the designated Communications Owner in coordination with Legal before release.
- No individual communicates externally about an incident on behalf of the company outside this process, regardless of role.

## 8. Regulatory and Contractual Notification

- For any incident involving actual or suspected exposure of personal data, Legal is engaged immediately to determine notification obligations under applicable law, including but not limited to HIPAA breach notification requirements where protected health information is involved, applicable state breach notification laws, and GDPR where EU personal data is in scope.
- Notification timelines and requirements vary by jurisdiction and data type. This policy does not itself define those timelines; Legal counsel determines applicable requirements for each incident based on current law and the specific data involved.
- Customer contracts may impose notification obligations independent of, and sometimes stricter than, regulatory requirements. [Note: maintain a reference to contractual notification commitments, e.g. a summary of SLA-defined notification windows, for Legal and the incident commander to consult during response.]

## 9. Post-Incident Review

- Every incident classified Medium severity or above receives a post-incident review within [e.g. 10 business days] of resolution.
- The review documents the incident timeline, root cause, what worked well in the response, what did not, and specific action items to prevent recurrence or improve future response.
- Action items are tracked to completion in [ticketing system], not just documented and left open indefinitely.
- [Life sciences note: for incidents affecting GxP-relevant systems, the post-incident review is cross-referenced with, or feeds directly into, the applicable deviation and CAPA process, rather than existing as a parallel and disconnected record.]

## 10. Tabletop Exercises

- The incident response process is tested through a tabletop exercise at least annually, simulating a realistic incident scenario relevant to [Company Name]'s environment.
- Exercise participants include, at minimum, the security team and designated incident commanders, with executive leadership participating in at least the annual exercise.
- Findings from the exercise, including any gaps identified in the response process itself, are documented and tracked to resolution, and inform updates to this policy.

## 11. Policy Review and Approval History

| Version | Date | Description of Change | Approved By |
|---|---|---|---|
| 1.0 | [Date] | Initial policy | [Name] |

This policy is reviewed at least annually, and after any Critical severity incident, to incorporate lessons learned.
