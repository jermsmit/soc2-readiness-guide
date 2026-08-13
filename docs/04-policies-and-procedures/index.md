# 4. Policies and Procedures

Policies are the most misunderstood artifact in a SOC 2 program. Companies often treat them as the deliverable itself, download a template, fill in the company name, get it signed, and consider the box checked. Auditors do not see it that way, and neither should you. A policy is a written commitment to a practice. The evidence that matters is whether the practice actually happens the way the policy describes, consistently, by the people who are supposed to follow it.

This section covers what a real, audit-ready policy set looks like, how to write policies that describe what you actually do rather than what a template assumes you do, and how to manage them so they hold up under scrutiny rather than becoming a stack of documents nobody has read since the day they were approved.

## The core policy set

Most SOC 2 audits, at minimum Security scope, expect to see policies covering the following areas. This is not an exhaustive list for every company, but it is the baseline auditors look for and the set most first-time programs are missing pieces of.

- **Information Security Policy.** The umbrella document establishing your overall security program, ownership, and governance structure. Often references the more specific policies below rather than duplicating their content.
- **Access Control Policy.** Covers provisioning, deprovisioning, least privilege, authentication requirements, and access review cadence. See the full template below.
- **Incident Response Policy.** Covers detection, classification, escalation, communication, and post-incident review. See the full template below.
- **Vendor Risk Management Policy.** Covers due diligence, risk tiering, and ongoing monitoring of third parties. See the full template below.
- **Change Management Policy.** Covers how changes to code, infrastructure, and configuration are reviewed, approved, and deployed.
- **Business Continuity and Disaster Recovery Policy.** Covers recovery objectives, backup requirements, and testing cadence.
- **Data Classification and Handling Policy.** Covers how data is categorized by sensitivity and what handling requirements apply to each category.
- **Acceptable Use Policy.** Covers expectations for employee use of company systems, often the first policy new hires acknowledge.
- **Risk Assessment Policy.** Covers how the organization identifies, evaluates, and tracks risk on an ongoing basis, not just during the SOC 2 gap assessment itself.
- **Human Resources Security Policy.** Covers background checks, onboarding security requirements, and security-related terms in employment agreements.

A first Type I audit can often succeed with a leaner version of this set, focused on the policies tied to the criteria you have scoped in. A Type II audit, especially a renewal, expects the fuller set, since a longer observation period gives more surface area for an auditor to ask about a practice that has no corresponding policy.

## Writing policies that describe reality

The most common and most damaging mistake in policy writing is starting from a downloaded template and editing lightly, rather than starting from what your company actually does and formalizing it. A template-first approach produces documents that describe an idealized company that does not exist, and the gap becomes visible the moment an auditor interviews someone whose actual practice does not match what the policy says.

Write policies in this order:

1. Start from the control matrix you built during the gap assessment (Section 3). You already documented current state and target state for each control area. The policy formalizes the target state, not a generic best practice pulled from elsewhere.
2. Draft in plain language. Auditors, new employees, and your own team six months from now all benefit from a policy that says what to do in direct sentences, rather than dense compliance language copied from a template that was itself copied from somewhere else.
3. Review the draft with the people who will actually execute the policy, not just leadership. If your access control policy says access reviews happen quarterly, confirm with whoever runs that review that quarterly is actually achievable given their other responsibilities, before you commit to it in writing.
4. Set a realistic cadence rather than an aspirational one. A policy that commits to monthly access reviews, but where reviews actually happen roughly every six weeks, is a policy that will generate an audit exception. A policy that commits to quarterly reviews and is followed exactly is stronger evidence than an ambitious policy followed loosely.

## Approval, version control, and proving a policy was in effect

An auditor testing a Type II report needs to confirm that a policy was actually in effect throughout the observation window, not just that a current version exists today. This means version control and approval history are not optional formatting details, they are evidence.

Every policy should carry:

- A version number and effective date
- An approval record, showing who approved it and when, ideally with a named owner rather than "leadership" as a category
- A review history, since most policies should be reviewed at least annually even if no changes are made
- A clear indication of what changed between versions, so an auditor can see whether a control's requirements shifted during the observation window

Store policies somewhere with real version history, a Git repository, a document management system with revision tracking, or a GRC platform, rather than a shared drive folder where old versions get overwritten and the history disappears. If a policy changes mid-observation-window, you need to be able to show which version applied on any given date within that window.

## Employee acknowledgement

A policy nobody has read is treated by auditors, correctly, as functionally equivalent to no policy at all. Every policy relevant to general employee conduct, particularly the Acceptable Use Policy and Information Security Policy, needs a documented acknowledgement process: employees confirm they have read and agree to follow the policy, and that confirmation is timestamped and retained.

Acknowledgement should happen at onboarding and be refreshed at least annually. Track this the same way you track any other piece of evidence, with a system that can produce a report showing who acknowledged what, and when, rather than relying on manually checking email confirmations when an auditor asks.

## Minimum set for Type I versus fuller set for Type II

If you are pursuing Type I first, as recommended in Section 2, focus initial policy-writing effort on the policies most directly tied to your in-scope criteria: Information Security, Access Control, Incident Response, and Change Management at minimum. These map most directly to the Common Criteria an auditor will test even in a Type I review.

Vendor Risk Management, Business Continuity and Disaster Recovery, and the more peripheral policies can often be developed in parallel with your Type I fieldwork, provided they are fully in place before your Type II observation window begins. Do not treat this as permission to skip them entirely for a first report, only as a sequencing decision about what needs to be airtight first.

## Life sciences note: aligning with existing SOPs

If your company already operates under a quality management system with established SOPs, the biggest risk in this section is not gaps, it is duplication and conflict. Writing a new SOC 2 Access Control Policy without cross-referencing an existing SOP that already governs access to validated systems creates two documents that can drift out of alignment with each other, and an auditor, either your SOC 2 auditor or an inspector reviewing your quality system, who finds a conflict between them will treat it as a control failure regardless of which document is more accurate.

Before drafting any policy in this section, check whether an equivalent SOP already exists. Where one does, the SOC 2 policy should reference it directly rather than restating it, and should clearly describe how the SOC 2 boundary relates to what the SOP already covers, for example noting that the SOP governs GxP-validated systems specifically while the SOC 2 policy extends the same principles to the broader system boundary. Involve Quality in the review of any policy that touches a system or process they already own. The goal is one governing document per practice wherever possible, not two documents describing the same thing to two different audiences.

## Policy templates

Full templates for the three policies most central to SOC 2 fieldwork are available below. Each is written to be adapted, not adopted verbatim. Replace bracketed placeholders with your company's actual practices, and have legal counsel and your auditor review before formal approval and rollout.

- [Access Control Policy](../../templates/policies/access-control-policy.md)
- [Incident Response Policy](../../templates/policies/incident-response-policy.md)
- [Vendor Risk Management Policy](../../templates/policies/vendor-risk-management-policy.md)

## Common mistakes this section addresses

**Adopting a template with minimal editing instead of formalizing what the company actually does.** This is the single most common root cause of policy-related audit findings. A policy that reads well but does not match reality is worse than an honest, less polished policy that does.

**No employee acknowledgement tracking, or acknowledgement tracked informally.** If you cannot produce a report showing who has acknowledged a policy and when, an auditor cannot verify the policy was communicated, regardless of how well written the policy itself is.

---

*Next: [Section 5, Access Control and Identity](../05-access-control-and-identity.md)*
