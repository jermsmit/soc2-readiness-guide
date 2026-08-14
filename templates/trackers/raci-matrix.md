# SOC 2 Program RACI Matrix

**[Company Name]**
**Version:** 1.0
**Last Updated:** [Date]

This is a template. Replace roles and names with your actual organizational structure. RACI stands for Responsible (does the work), Accountable (ultimately answerable for the outcome, typically one person per row), Consulted (provides input before a decision or action), and Informed (kept aware after the fact).

## How to use this matrix

Each row represents a control domain or recurring activity from this guide. Assign exactly one Accountable party per row, ideally a specific individual rather than a title shared by multiple people, since ambiguity in accountability is itself a common source of lapsed controls, as discussed in [Section 13](../../docs/13-continuous-compliance.md). Multiple people or roles can be Responsible, Consulted, or Informed for the same row.

Adjust the role columns to match your actual organizational structure. The columns below are a reasonable starting set for a mid-sized life sciences company, but smaller companies may combine roles, for example a single person holding both CTO/CISO and Engineering Lead responsibilities, and larger companies may need additional columns, for example a dedicated Compliance or GRC function.

## Roles referenced in this matrix

- **CTO / CISO.** Executive owner of the overall security and SOC 2 program.
- **IT Security.** Operational owner of day-to-day security controls and evidence collection.
- **Engineering Lead.** Owner of engineering practices affecting change management and access to code and infrastructure.
- **HR.** Owner of onboarding, offboarding, and personnel-related security requirements.
- **Legal.** Owner of contractual, regulatory notification, and data protection agreement matters.
- **Quality / Regulatory Affairs.** Owner of GxP validation, 21 CFR Part 11, and related regulatory compliance, relevant for life sciences specific overlap (see [Section 11](../../docs/11-life-sciences-considerations.md)).
- **Compliance Owner.** The individual with overall day-to-day responsibility for keeping the SOC 2 program operating between audits (see [Section 13](../../docs/13-continuous-compliance.md)).

## Matrix

| Activity | CTO / CISO | IT Security | Engineering Lead | HR | Legal | Quality / Reg Affairs | Compliance Owner |
|---|---|---|---|---|---|---|---|
| Overall SOC 2 program ownership | A | R | C | I | I | C | R |
| System scoping and Trust Services Criteria selection | A | R | C | I | C | C | R |
| Gap assessment | A | R | C | C | I | C | R |
| Policy drafting and approval | A | R | C | C | C | C | R |
| Access provisioning | I | A | C | R | I | I | I |
| Access deprovisioning (offboarding) | I | A | I | R | I | I | I |
| Quarterly access review | I | A | R | I | I | C | R |
| Code change review and approval | I | I | A | I | I | I | I |
| Infrastructure change review and approval | I | C | A | I | I | I | I |
| Vendor risk tiering and due diligence | I | A | C | I | C | C | R |
| Vendor SOC 2 report review | I | A | I | I | C | I | R |
| Incident detection and initial triage | I | A | R | I | I | I | I |
| Incident response coordination (Medium+ severity) | C | A | R | I | C | C | R |
| Regulatory / breach notification determination | C | C | I | I | A | C | R |
| Post-incident review | C | A | R | I | I | C | R |
| Annual incident response tabletop exercise | A | R | R | I | C | C | R |
| Backup restore testing | I | A | R | I | I | C | R |
| Annual disaster recovery test | A | R | R | I | I | C | R |
| Evidence collection and tracker maintenance | I | A | C | C | I | C | R |
| Auditor selection | A | C | I | I | C | I | R |
| Fieldwork coordination | I | A | C | I | C | C | R |
| Interview preparation and scheduling | I | A | C | I | I | C | R |
| Findings and exceptions review | A | R | C | I | C | C | R |
| Compliance calendar maintenance | I | C | I | I | I | I | A |
| Customer / prospect SOC 2 status communication | C | C | I | I | C | I | A |
| GxP / SOC 2 boundary mapping | C | C | I | I | I | A | R |
| Part 11 access and audit trail alignment | I | C | I | I | I | A | R |

## Notes on applying this matrix

Assigning "A" to more than one role in a single row is a common mistake worth avoiding deliberately. If two people are both accountable for the same activity, in practice neither reliably is, since each can reasonably assume the other is handling it. Where a decision genuinely requires shared ownership, use Consulted for the second party rather than a second Accountable designation, and make sure whoever holds the single Accountable role understands they are the one who answers for the outcome.

Revisit this matrix whenever the organizational structure changes materially, a new hire takes over a function previously covered informally, a team is restructured, or a new regulatory obligation introduces a role that did not previously need representation here. An outdated RACI matrix that no longer reflects who actually does the work is a source of confusion during an actual incident or audit, precisely when clarity matters most.
