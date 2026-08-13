# Vendor Risk Management Policy

**[Company Name]**
**Version:** 1.0
**Effective Date:** [Date]
**Owner:** [Name / Title, e.g. IT Security Lead or Procurement Lead]
**Approved By:** [Name / Title]

This is a template. Replace all bracketed content with your organization's actual practices before adoption. Have legal counsel and your auditor review before approval.

---

## 1. Purpose

This policy establishes the process by which [Company Name] evaluates, monitors, and manages the security and compliance risk posed by third-party vendors and service providers. Its purpose is to ensure that vendors with access to company or customer data, or that provide services critical to company operations, are assessed proportionately to the risk they represent and are monitored on an ongoing basis rather than only at the point of initial engagement.

## 2. Scope

This policy applies to any third-party vendor, contractor organization, or service provider that:

- Has access to [Company Name] or customer data, in any form
- Provides infrastructure or services critical to the operation of in-scope systems
- Is engaged in processing, storing, or transmitting data on behalf of [Company Name]

This policy does not apply to vendors providing goods or services with no data access and no operational criticality, such as [example: office supplies, facilities maintenance], though such vendors should still be recorded in the vendor inventory for completeness.

## 3. Roles and Responsibilities

**Vendor Owner.** Each vendor relationship has a designated internal owner, typically the individual or team who initiated the engagement, responsible for completing initial due diligence, coordinating ongoing review, and serving as the primary point of contact for vendor-related risk questions.

**IT Security.** Responsible for maintaining the vendor risk tiering framework, reviewing security documentation submitted by vendors, and maintaining the central vendor inventory.

**Procurement / Legal.** Responsible for ensuring appropriate contractual protections, including data processing agreements where applicable, are in place before a vendor relationship is finalized.

## 4. Vendor Risk Tiering

Vendors are classified into risk tiers based on the sensitivity of data accessed and the criticality of the service provided:

| Tier | Definition | Example |
|---|---|---|
| Critical | Access to sensitive customer or regulated data, or the vendor's failure would materially disrupt core operations | Cloud infrastructure provider, primary database or storage vendor |
| High | Access to internal company data or limited customer data, or provides a service important but not existential to operations | Customer support platform, analytics tooling with customer data access |
| Moderate | Limited data access, primarily operational or internal-facing | HR platform, internal collaboration tools |
| Low | No meaningful data access, minimal operational dependency | Office services, non-data-processing software tools |

Tiering is assigned at onboarding by the Vendor Owner in consultation with IT Security, and reassessed if the scope of the vendor relationship changes materially.

## 5. Due Diligence Requirements by Tier

**Critical and High tier vendors:**
- Review of the vendor's most recent SOC 2 report (Type II preferred), or equivalent independent security attestation, prior to engagement
- Completion of a security questionnaire covering [key areas: data handling, encryption, access control, incident history]
- Review of the vendor's data processing agreement or equivalent contractual data protection terms
- Documented sign-off from IT Security before the engagement proceeds

**Moderate tier vendors:**
- Completion of an abbreviated security questionnaire
- Confirmation that a data processing agreement is in place if any personal data is involved

**Low tier vendors:**
- Recorded in the vendor inventory; no formal security review required unless the relationship later changes in scope

## 6. Reviewing Vendor SOC 2 Reports for Complementary Controls

When reviewing a vendor's SOC 2 report, the Vendor Owner and IT Security jointly review the "complementary user entity controls" section of the report. This section describes controls the vendor assumes their customer, meaning [Company Name], has implemented on their own side. Any complementary control identified must be evaluated for whether [Company Name] actually has it in place, and any gap is logged and remediated the same as any other control gap identified through this policy.

## 7. Ongoing Monitoring

- Critical tier vendors are reviewed [annually], with an updated SOC 2 report or equivalent attestation requested and reviewed at each cycle.
- High tier vendors are reviewed [annually], with security questionnaires refreshed as needed.
- Moderate tier vendors are reviewed [every two years, or per your actual cadence].
- Low tier vendors are not subject to a recurring review cadence but are reassessed if their scope of engagement changes.
- Review dates, findings, and any required follow-up are tracked in the central vendor inventory, not managed informally by individual owners.

## 8. Vendor Incidents

If a vendor experiences a security incident that may affect [Company Name] data or systems, the Vendor Owner is responsible for escalating to IT Security immediately upon becoming aware. The vendor incident is evaluated against [Company Name]'s own Incident Response Policy to determine whether it triggers internal incident response, customer notification, or regulatory notification obligations.

## 9. Offboarding

When a vendor relationship ends, the Vendor Owner is responsible for confirming:

- All [Company Name] and customer data held by the vendor is returned or securely destroyed, per contractual terms
- Any access the vendor had to [Company Name] systems is revoked
- The vendor inventory is updated to reflect the relationship has ended

## 10. Central Vendor Inventory

[Company Name] maintains a central inventory of all vendors in scope of this policy, including tier, due diligence status, last review date, and next review due date. The inventory is the source of truth for vendor risk status and is what will be presented to auditors as evidence of this program operating consistently.

## 11. Life Sciences Note: Coordination with GxP Vendor Qualification

Where a vendor also falls under GxP vendor qualification requirements, for example a CRO, CDMO, or clinical data platform vendor, the SOC 2 vendor risk review and the GxP qualification process should be coordinated through a single vendor record wherever possible, rather than maintained as two disconnected assessments. [Company Name]'s Quality function should be consulted before initiating SOC 2 vendor due diligence for any vendor that may already be subject to GxP qualification, so that existing qualification documentation can inform, and avoid duplicating, the SOC 2 review.

## 12. Policy Review and Approval History

| Version | Date | Description of Change | Approved By |
|---|---|---|---|
| 1.0 | [Date] | Initial policy | [Name] |

This policy is reviewed at least annually.
