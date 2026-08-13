# 5. Access Control and Identity

If there is one control domain that determines how smoothly your audit goes, it is this one. CC6, logical and physical access controls, is the most heavily tested category in almost every SOC 2 engagement, and access control is the area where the gap between what a policy says and what actually happens is most likely to surface during fieldwork. This section covers how to build a program that holds up, not just a policy that reads well.

If you have not already read the [Access Control Policy template](../templates/policies/access-control-policy.md) in Section 4, it is a useful companion to this section, since it defines the commitments this section explains how to actually keep.

## The joiner, mover, leaver process

Every access control program is really three processes wearing one name: what happens when someone joins, what happens when their role changes, and what happens when they leave. Auditors will ask about all three, and most first-time programs have only really thought through the first one.

**Joiner.** Access provisioning should be tied directly to a defined role, not assembled ad hoc by whoever is onboarding the new hire that week. The strongest version of this process starts with HR triggering a ticket or workflow the moment a start date is confirmed, IT provisions access based on a documented role-to-access mapping, and the entire sequence, request, approval, provisioning, is logged automatically rather than relying on someone remembering to screenshot an email chain later.

**Mover.** This is the process most programs forget to build at all. When someone changes roles internally, moves teams, or gets promoted into a role with different access needs, their old access needs to be removed, not just supplemented with new access. Accumulated access from every role someone has held over a multi-year tenure is a real and common audit finding, and it is also a real security risk independent of the audit. Build a trigger for role changes into the same system that handles joiners and leavers, rather than treating it as a special case that only gets handled if someone happens to notice.

**Leaver.** Timing here is the single most scrutinized element of access control in a Type II audit. Auditors will sample terminated employees from across your entire observation window and check the gap between termination date and access revocation date for every system in scope. A process that works most of the time is not good enough, because the sample will find the exception.

## Least privilege and role-based access, applied for real

Least privilege is easy to state as a principle and hard to operationalize without a clear model. The practical approach that scales is role-based access control: define a set of standard roles, map each role to the specific access it requires across your systems, and provision access according to role rather than negotiating access individually for each new hire.

This does not mean every access decision becomes rigid. It means the default is role-based, and any deviation from the standard role mapping, someone needing broader access than their role typically requires, goes through an explicit exception process with documented justification, rather than becoming the unstated norm because it was easier to grant broad access once and never revisit it.

Apply this consistently across four categories, since auditors will test all four separately:

- **Production systems and cloud infrastructure.** Access to production environments should be the most tightly scoped, given the direct risk to customer data and system integrity.
- **Source code repositories.** Write access, and especially the ability to merge to protected branches, should map to actual development responsibilities, not be granted broadly by default.
- **Cloud infrastructure and administrative consoles.** Administrative or root-level access should be rare, individually justified, and reviewed with more frequency than standard user access.
- **Business applications.** HR systems, financial systems, and customer data platforms each need their own access model, since the sensitivity and blast radius of each differs.

## Access review cadence

Most SOC 2 programs settle on a quarterly access review cycle, and this is a reasonable default for the majority of systems. What matters more than the specific cadence is that the review is real, not a rubber stamp.

A review that satisfies an auditor includes:

- A complete list of everyone with access to the system at the time of review
- Confirmation from the system owner, not just IT Security, that each person's access still matches their current role
- Documentation of any access removed as a result of the review, including who removed it and when
- A record of the review itself: who performed it, when, and what the outcome was

The most common way reviews fail to hold up under audit scrutiny is that they happen, but nobody actually looks closely. A system owner who receives a list of forty names and clicks approve without checking any of them against current org charts has technically performed a review, but has not performed one that will survive an auditor asking "how did you confirm this person still needed this access."

Privileged and administrative access should be reviewed on the same cadence at minimum, and many programs review it more frequently, given the disproportionate risk a compromised privileged account represents.

## MFA, SSO, and privileged access management

For a Type II audit, expect these to be tested directly, not just described in policy:

- **Multi-factor authentication** should be required for any access to production systems and any system handling customer data, without exception outside a documented and time-bound compensating control.
- **Single sign-on** centralizes authentication and, critically, makes deprovisioning far more reliable, since disabling one SSO identity can cut off access to every connected application at once rather than requiring IT to remember and manually revoke access system by system.
- **Privileged access management** tooling, where in place, should log and ideally require approval for elevated access, rather than granting standing administrative privileges that sit unused most of the time but remain available as an attack surface.

If your company is not yet using SSO broadly, this is one of the higher-leverage investments to make before your Type II observation window begins, since it directly strengthens both the reliability of your deprovisioning process and the evidence you can produce to demonstrate it.

## Offboarding timing in detail

Because this is where auditors focus disproportionate attention, it is worth being explicit about what "same-day" actually means in practice, since companies interpret it differently.

For involuntary terminations, the strongest and most common practice is to revoke access at or immediately before the termination conversation itself, not afterward. This reflects the elevated risk of an employee who knows termination is imminent taking action before access is cut off.

For voluntary terminations, revocation by end of the final working day is the standard most audits expect. Some companies revoke earlier, immediately upon resignation notice for particularly sensitive roles, which is a reasonable risk-based enhancement rather than a requirement.

Whatever your actual practice is, the policy should state it precisely enough that it can be tested, and your process should be reliable enough that it survives being tested against every termination in a twelve-month sample, not just the ones that happened to go smoothly.

## Contractor and temporary access

This is a frequent gap in otherwise solid access control programs. Contractors often get provisioned quickly to unblock a project and then fall outside the normal review and offboarding cadence because they were never entered into the same HR system that triggers the standard leaver process.

Bring contractor access into the same system of record as employee access wherever possible. At minimum, contractor access should have a defined end date tied to the engagement, be included in the same periodic access review, and be explicitly assigned an owner responsible for confirming deprovisioning when the engagement ends. An auditor who asks about contractor access and receives a vague answer about "we usually remember to remove it" will treat this as a finding, and should.

## Life sciences note: reconciling with 21 CFR Part 11

If any systems in your SOC 2 boundary are also subject to 21 CFR Part 11, you have an opportunity to make one access review satisfy two regulatory expectations, but only if you design for it deliberately.

Part 11 requires that access to systems maintaining electronic records and electronic signatures be limited to authorized individuals, and that the system maintain an audit trail of access and changes. This overlaps closely with SOC 2's CC6 expectations, but Part 11 additionally expects specific attention to electronic signature integrity, meaning the system must ensure that a signature cannot be repudiated and that access controls specifically protect the signature function, not just general data access.

The practical move is to design your access review process, for any system that is both SOC 2 in-scope and Part 11 relevant, to capture both sets of evidence in a single pass: standard role-appropriateness review for SOC 2, plus specific confirmation that electronic signature privileges are held only by individuals authorized to sign for their role. Document this explicitly in the review record rather than running two separate reviews on two separate schedules for the same system, which doubles the work and creates two records that can drift out of sync with each other.

Coordinate with Quality on this before your review cadence is finalized. In many companies, Quality already has a validated access review process for GxP systems, and the right outcome is often extending that existing process to also produce SOC 2 evidence, rather than IT Security building a parallel process from scratch.

## Common mistakes this section addresses

**Access reviews that are performed but not documented, which is functionally the same as not performing them in an audit.** An auditor cannot test a process that has no evidence trail. If a review happened but nobody can produce a record of who performed it, when, and what was found, the auditor has no basis to conclude the control operated, regardless of what actually took place.

**No formal process for contractor and temporary access, which auditors specifically probe for.** Contractors are a known blind spot, and experienced auditors will ask about them directly rather than waiting to find the gap on their own. Having a clear, documented answer ready, rather than discovering the gap in the interview, is the difference between a smooth conversation and an exception.

---

*Next: [Section 6, Vendor and Third-Party Risk Management](06-vendor-and-third-party-risk.md)*
